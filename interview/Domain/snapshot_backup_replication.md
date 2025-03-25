## What is a storage snapshot?
A storage snapshot is a set of reference markers for data at a particular point in time (PIT).
    
    - It's a collection of saved application data.
    - Comprehensive log that details how the saved data has changed over time.
When these two elements are taken together, the storage snapshot lets an enterprise protect an application's data in real-time. It minimizes the recovery point objective while allowing workload managers to restore, or roll back, the application's data state to any previous PIT where a storage snapshot is available.
    

### What is a virtual hard disk (VHD)?
A virtual hard disk (VHD) is a disk image file format for storing the entire contents of a computer's hard drive. The disk image, sometimes called a virtual machine (VM), replicates an existing hard drive, including all data and structural elements. It can be stored in any location accessible to the physical host, and it is also transportable, meaning it can be stored and moved with a USB flash memory device.

## Benifits of Virtualization 

1. Easier Management : Virtualization abstruct the actual complexity of a storage system to help admin perform backup, recovery and archiving more easily and quickly. 
2. Better Storage Utilization : Pooling storage capacity across multiple systems make it easier to efficiently allocate and use the total storage.
3. Extending Life for Older Storage Systems: Including older storage gear in the virtualized storage pool extends its usefullness by handaling archival or less critical data.
4. Universal Additional Features: Tiering, Caching and replication can be implemeted at the virtualization level, helping to standarized these practices across all storage system.

Ref VHD : https://www.techtarget.com/searchvirtualdesktop/definition/virtual-hard-disk-VHD 

### How storage snapshots work

Storage snapshots are often based around the idea of change, which is also referred to as delta or differencing. Snapshots often use a differencing disk, which is a special type of virtual hard disk that's linked to a parent virtual hard disk.

1. Any storage snapshot starts with a complete backup of the workload's current data state.
2. Once an initial backup is created, the storage snapshot system captures and records the changes that take place to the application's data, that is, the differences or deltas in the data. Only those changes are recorded and logged at that PIT.
3. When an administrator creates a storage snapshot, the underlying system creates a differencing disk that's bound to the original virtual hard disk. All future write operations are directed to the differencing disk, leaving the original virtual hard disk in an unaltered state.

![image](https://github.com/user-attachments/assets/0a726208-22b2-4d8d-921b-28f574536dad)


Snapshot Ref : https://www.techtarget.com/searchdatabackup/definition/storage-snapshot

![image](https://github.com/user-attachments/assets/8ffff1a9-1f3b-45db-ba86-509a68b23ee8)

![image](https://github.com/user-attachments/assets/94d21ad2-1341-4430-a398-814f2daabb00)


Backup Type Ref : https://www.techtarget.com/searchdatabackup/tip/Data-backup-types-explained-Full-incremental-differential-and-incremental-forever-backup

### Synchronous vs. asynchronous replication

Synchronous replication is typically used to provide high availability of critical applications. In these scenarios, failover from the primary to secondary array is nearly instantaneous, which ensures little to no application downtime and minimal negative impact to users.

Asynchronous replication mainly differs from synchronous replication in the data writing method to the storage replica site. In synchronous replication, data is written to the primary storage and the replica simultaneously -- hence the term synchronous. Since the primary -- the source -- and replica copies are always synchronized, the possibility of data loss is zero.

![image](https://github.com/user-attachments/assets/c59e6221-29a4-414a-8f93-3a85f49db4f4)



### How Snapshot works?

#### Copy-on-write: 

A storage snapshot is created by the use of the pre-designated space allocated to it. When the snapshot is created at first, the meta-data related to the original data is stored and is backed up as a copy. There is no physical copy of the snapshot which is created. When the writes to the original volume are being lodged, the snapshot carefully tracks down the changing blocks taking place due to writes, on the original volume. The original data is then overwritten and will fetch the name of “copy-on-write” technique.

![image](https://github.com/user-attachments/assets/99bf87b5-4767-4052-a0ed-18f44494e249)


#### Redirect-on-Write:

It is a clone to the Copy-on-write technique related to storage snapshot. Redirect-on-write doesn’t deal in double writing and offers storage space and performance with efficient snapshots. In this technique, new writes are reflected to another location which is separately allocated for snapshots. The main advantage in redirecting the write is that one write takes place at a time, which is different to copy-on-write; where two writes can occur at a time, where one is for writing data on original copy onto the storage and the other one is for the changed data copy.

With the technique of redirect-on-write, the original copy will have point in time data, which will be the snapshot and the changed data will be diverted to the snapshot storage. If a snapshot gets deleted, then the snapshot storage will be re-diverted back into the original volume. If multiple snapshots are created, then complexity factor will rise as access to original data, tracking of the data in snapshots and original volume and reconciliation upon snapshot deletion becomes complex. As the snapshot relies on the original copy of the data, the original set can get quickly fragmented.

![image](https://github.com/user-attachments/assets/52963d19-7b2d-4c56-82b6-2ddba019108a)
