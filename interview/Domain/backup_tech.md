## What is the difference between Block Storage, File Storage, and Object Storage?

### **Block Storage:**  
Block storage chops data into blocks and stores them as separate pieces. Each block of data is given a unique identifier, which allows a storage system to place the smaller pieces of data wherever is most convenient. That means that some data can be stored in a Linux® environment and some can be stored in a Windows unit.

It is usually deployed in storage-area network (SAN) environments and must be tied to a functioning server.Block storage divides files and data into equally sized blocks. Each block has a unique identifier, stored in a data lookup table. When data needs to be retrieved, the data lookup table is used to find the required blocks, which are then reassembled into their original form.

### **File Storage:**
File storage, also called file-level or file-based storage, is exactly what you think it might be: Data is stored as a single piece of information inside a folder, just like you’d organize pieces of paper inside a manila folder. When you need to access that piece of data, your computer needs to know the path to find it.

It’s the type most often used to store information on a computer hard drive or on a device for network-attached storage (NAS) and is best used for quick in-and-out data storage and access.

- Shared files – centralized storage on a local area network (LAN) makes it easy for anyone to access the stored data
- Familiar protocols – file storage relies on common protocols used throughout computing, such as Network File System (NFS), Common Internet File System (CIFS), and Server Message Block (SMB)
- Cost-efficient (to a point) – using a NAS device, you can remove data from expensive servers and store it on less costly LAN-connected devices
- Backup/recovery – storing backup data on LAN devices allows you to recover quickly if your network goes down

### **Object Storage:**
Object storage, also known as object-based storage, is a flat structure in which files are broken into pieces and spread out among hardware. In object storage, the data is broken into discrete units called objects and is kept in a single repository, instead of being kept as files in folders or as blocks on servers.

Object storage volumes work as modular units: each is a self-contained repository that owns the data, a unique identifier that allows the object to be found over a distributed system, and the metadata that describes the data. That metadata is important and includes details like age, privacies/securities, and access contingencies.

![image](https://github.com/user-attachments/assets/a76c51c1-ffd2-428d-9726-938ff742351b)

### Which One to Use?
- Choose Block Storage if you need low latency and high performance (e.g., databases, VMs).
- Choose File Storage if you need a shared file system for multiple users (e.g., team collaboration, file servers).
- Choose Object Storage if you need scalable, cost-effective storage for large unstructured data (e.g., backups, logs, media files

Ref : 
- Example described very well for Block & Object store : https://www.cloudflare.com/learning/cloud/object-storage-vs-block-storage/
- Definitions: https://www.redhat.com/en/topics/data-storage/file-block-object-storage
- Advantages/Disadvantages: https://www.nutanix.com/blog/block-storage-vs-object-storage-vs-file-storage
- https://www.oracle.com/in/cloud/storage/block-volumes/what-is-block-storage/vs-object-storage/


## How does RAID work? Explain different RAID levels (RAID 0, 1, 5, 6, 10, 50, 60).

RAID is a data storage virtualization technology that combines multiple hard drive components into a single logical unit for the purposes of data redundancy, performance improvement, or both.

Data is distributed across the drives in one of several ways, seen as RAID levels, depending on the required level of redundancy and performance. The different schemas, or data distribution layouts, are named as RAID followed by a number, for example RAID 0 or RAID 1. Each schema, or RAID level, provides a different balance among the key goals: Reliability, availability, performance, and capacity.

- RAID 0: It's built with 2 drives. Each drive stores different blocks. Data spread across the drives used stripes. It is very fast. It doesn't provide reliability but high performance.
  ![image](https://github.com/user-attachments/assets/57dbf4c4-dfae-4621-a871-c6a59aca96d4)

- RAID 1: This provides data mirroring facilities. Data written simultaneously in 2 different disks. The primary advantage of RAID 1 is that it provides 100 percent data redundancy. Because the contents of the disk are written to a second disk, the system can sustain the failure of one disk. Both disks contain the same data always.
  ![image](https://github.com/user-attachments/assets/e5ff8531-bb97-4722-931e-55f28374d57b)

- RAID 5 & 6: Parity Data is redundant data that is generated to provide fault tolerance within certain RAID levels. When a drive failure occurs, the controller uses the parity data to regenerate user data. Parity data is present for RAID 5, 6, 50, and 60. The parity data is distributed across all the hard drives in the system. If a single hard drive fails, it can be rebuilt from the parity and the data on the remaining hard drives.
  ![image](https://github.com/user-attachments/assets/909f4c7e-8ec0-4bab-8331-5feedcb4774d)

  ![image](https://github.com/user-attachments/assets/3459a675-de75-4e2c-847a-90c045f65746)

Need to read : https://www.arcserve.com/blog/understanding-raid-performance-various-levels
Ref : https://www.dell.com/support/kbdoc/en-in/000128635/dell-servers-what-are-the-raid-levels-and-their-specifications

https://www.techtarget.com/searchstorage/answer/RAID-types-and-benefits-explained







RAID Level Discussion : https://www.dell.com/support/kbdoc/en-in/000128635/dell-servers-what-are-the-raid-levels-and-their-specifications
