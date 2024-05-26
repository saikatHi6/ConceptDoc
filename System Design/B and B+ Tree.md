## Important parts are 

  1. Disk Structure :
  
![image](https://github.com/saikatHi6/ConceptDoc/assets/4381376/aa708c93-1a19-488e-9eb9-e3a4dcb612d9)

**Tracks:**
Concentric circles etched on the surface of the platter represent tracks. These are like lanes on a racetrack. There are numerous tracks, typically hundreds or thousands, depending on the disk size.

**Sectors:**
Each track is further divided into wedge-shaped sections called sectors. Think of them as slices of a pie on the track. A sector is the smallest unit of data storage on a disk. In modern hard drives, sectors typically hold 512 bytes or 4 KiB of data.

**Blocks:**
Blocks are logical groups of sectors, not physical divisions on the disk. The operating system manages data storage in blocks. A block size (e.g., 4 KiB, 8 KiB) is usually a multiple of the sector size. This simplifies data management for the operating system as it deals with larger chunks of data rather than individual sectors.

Block addresses are represented by Sector & Track.

**Offset:**
<img width="593" alt="image" src="https://github.com/saikatHi6/ConceptDoc/assets/4381376/4d4c8ec7-8683-4e20-ba36-c62ba6dce762">

let's assume the block size is 512 bytes. Each byte has an address called offset.

     <img width="353" alt="image" src="https://github.com/saikatHi6/ConceptDoc/assets/4381376/a6028bc0-4b03-4783-8918-ca0584f83056">

This image shows how data is read from DBMS and stored in the RAM using Data structure for read and write.

  2. How Datastore on the disk
     This image depicts each row size as 128 Bytes. Then 4 rows can be stored in each block. This means to search a  row from the disk we have to search in 25 blocks. 
<img width="381" alt="image" src="https://github.com/saikatHi6/ConceptDoc/assets/4381376/59bce826-72e9-4347-b501-748a81e2cee0">

  3. What is indexing
Now to reduce the access of block size implement indexs.
<img width="277" alt="image" src="https://github.com/saikatHi6/ConceptDoc/assets/4381376/cf7b3ab3-639c-4a49-b26a-7c1e7f9f6bab">

Let's assume the highlighted yellow part is data and the green is an index.
Each block can store 32 rows of index. With that calculation, we can calculate the maximum 3+ blocks required to store 100 index rows. 

So to search a row in the disk we have to go through a minimum of 5 blocks(4 index blocks + 1 data block).

  5. What is multi-level indexing

<img width="302" alt="image" src="https://github.com/saikatHi6/ConceptDoc/assets/4381376/f2c5bb48-ee76-4e2c-9ce6-56806363a704">

When index size grows then we can create an index of index. It will reduce the number of block accesses to find a record.
On the upper level, we can store a collection of index addresses in an index then number of block size will be eventually reduced.


![image](https://github.com/saikatHi6/ConceptDoc/assets/4381376/5ff38fe8-199c-4d49-b18d-f820fb8a319e)




  7. M-Way search tree: Self manages multi-level indexing.


     <img width="392" alt="image" src="https://github.com/saikatHi6/ConceptDoc/assets/4381376/c361fdbb-4cde-45c1-bd68-743de65fa68c">


In the above diagram, M-way search key should have M-1 key


<img width="361" alt="image" src="https://github.com/saikatHi6/ConceptDoc/assets/4381376/d868ec60-a3b2-44e7-9e19-871c2e9518b5">


K = Key

Cp = Child Pointer

Rp = Record Pointer


The problem with creating an M-Way search tree is the number of trees will increase then searching will be time-consuming. To overcome this issue introduced B-Trees basically its M-way search tree only with some specific rules.

<img width="170" alt="image" src="https://github.com/saikatHi6/ConceptDoc/assets/4381376/0deca95c-c6a0-4548-b1cc-46dd5e29fe32">


  9. B-Trees


A B-tree is a self-balancing search tree data structure that maintains sorted data and allows searches, sequential access, insertions, and deletions in logarithmic time. It is commonly used in databases and file systems. Here are the key characteristics of a B-tree:

1. **Balanced Tree**: A B-tree is always balanced, meaning all leaf nodes are at the same depth, which ensures consistent access times.

2. **Multiple Children**: Each node can have multiple children, which makes B-trees suitable for storage systems that read and write large blocks of data.

3. **Order**: A B-tree of order \( m \) (or degree \( m \)) has the following properties:
   - Each internal node can have at most \( m \) children.
   - Each internal node (except the root) has at least \(\lceil m/2 \rceil\) children.[You will be allowed to create the next node until the current node is filled with at least half of the degree meaning m/2. m is degree]
   - The root has at least two children if it is not a leaf node.
   - Each node can contain at most \( m-1 \) keys and at least \(\lceil m/2 \rceil - 1\) keys (except for the root, which can have fewer).

4. **Node Structure**: Each node in a B-tree contains:
   - Keys: Sorted within the node.
   - Children: Pointers to child nodes.
   - Optional Data: Pointers or references to data records associated with keys (common in B+ trees).

5. **Efficient Operations**: 
   - **Search**: Starts at the root and traverses down the tree, making a decision at each node based on the keys, achieving logarithmic time complexity.
   - **Insertion**: Ensures the tree remains balanced by splitting nodes that exceed the maximum number of keys.
   - **Deletion**: Ensures balance by merging nodes or redistributing keys as necessary.

6. **Space Utilization**: B-trees are designed to optimize disk reads and writes, which is why they allow for a large number of keys per node. This minimizes the height of the tree and reduces the number of disk accesses required.

7. **Sequential Access**: In-order traversal of a B-tree yields the keys in sorted order, which is beneficial for range queries.

8. **B+ Trees**: A variant of B-trees where all data is stored in the leaf nodes, and internal nodes only store keys. This allows for efficient range queries and sequential access.

Overall, B-trees are highly efficient for storage systems, providing a good balance between read/write performance and space utilization.



