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
