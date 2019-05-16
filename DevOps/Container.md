Namespaces: Features of linux kernal. Isolate and virtulization system resources for a process. System resources that can be virtulaized an
  Mount(mnt)
  Process ID(pid)
  Network(net)
  Interprocess communication (ipc)
  UTS (host name)
  * Using the namespace features of kernal, we isolate one process to another. As container is nothing but a process. We isolate each container using different namespace. 

CGroups: Features of linux kernal which limits, accounts and isolate resource usage of following resource to group of process.
  CPU
  Memory
  Disk I/O
  Network
  Devices

UnionFS: Transparently overlays file and directories of separate file system to create coharent file system. Each participent directory is referred as a branch. UnionFS is used for implimenting a layered image. 
