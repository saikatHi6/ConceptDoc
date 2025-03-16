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
