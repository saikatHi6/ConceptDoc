### Namespaces

Features of linux kernal. Isolate and virtulization system resources for a process. System resources that can be virtulaized an
  - Mount(mnt)
  - Process ID(pid)
  - Network(net)
  - Interprocess communication (ipc)
  - UTS (host name)
  
**Using the namespace features of kernal, we isolate one process to another. As container is nothing but a process. We isolate each container using different namespace.** 

### CGroups

Features of linux kernal which limits, accounts and isolate resource usage of following resource to group of process.
  - CPU
  - Memory
  - Disk I/O
  - Network
  - Devices

### UnionFS

Transparently overlays file and directories of separate file system to create coharent file system. Each participent directory is referred as a branch. UnionFS is used for implimenting a layered image. 


## Container Runtimes
    - runC
    - Docker
    - Rocket(rkt)
 
### runC

It's not use demon process.

### Docker 

Client communication with the Docker demon running on the Docker host with REST API. Docker introduced "containerd". Docker demon manage docker runtime

### Rocket(rkt)

rkt has no demon process. It's works well with "systemd". Rkt currently using ACI. ACI has two component. rocket has a modular architecture for execution invoking process.  

  - rootfs : A tar file which contains all files to execute the application.
  - Image Manifest : A file which define execution paramete and resource constraints.

### Docker Enviornment 

Docker toolbox is use to run docker on windows and mac platform. It's comes with
    - full vertualization environment
    - boot2Docker virtualization
    - Docker compose
    - Docker Engine

### Unikernal

With unikernal we can build a OS Construct with minimum set of libaries to run just given application. The applcation and libery comile together to build a machine image. Which can run directly on hypervisor or baermetal. 

## Containers in windows
    - Windows server container
          
          Container done through namespace, cgroup like funtionality of linux kernal. Container share the kernal with host machine 
    - Hyper-v containers
        
          run Wendows server containar inside the highly optimised virtual machine. do not share kernal with host machine.


