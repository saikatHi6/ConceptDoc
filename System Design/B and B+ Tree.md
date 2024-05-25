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



  2. How Datastore on the disk

     <img width="353" alt="image" src="https://github.com/saikatHi6/ConceptDoc/assets/4381376/a6028bc0-4b03-4783-8918-ca0584f83056">

In this image shown how data is read from DBMS and stored in the RAM using Data structure for read and write.

  4. What is indexing
  5. What is multi level indexing
  6. M-Way search tree
  7. B-Trees
  8. Insertion & Deletion of B tree
  9. B+ Tree


