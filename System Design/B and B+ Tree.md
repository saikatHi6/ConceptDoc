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


  9. B-Trees
  10. Insertion & Deletion of B tree
  11. B+ Tree


