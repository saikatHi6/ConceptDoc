## What is SAN?

SAN stands for Storage Area Network, a dedicated network of servers, Storage Arrays, and switches that provide high-speed data transfer and access. SAN enable multiple hosts to share storage resources, such as disk,tape, and arrays without interfering with each other. SAN also offers such as scalability, redundancy, reliability, and manageability. 

## What is FC?

FC protocol uses optical or copper cables to connect SAN devices. FC operates at the physical and data link layers of the OSI model, and supports various upper layers of protocols such as SCSI, IP, and NVMe. FC is known for its low latency, high bandwidth, and long-distance reach. FC can deliver up to 128 Gbps of throughput per port, and up to 10 km of distance with single-mode fiber.

## What is NVMe-oF?

NVMe-oF is a protocol that extends the NVMe interface to remote storage devices over a fabric. NVMe is a standard that defines communication with SSD using a PCI Express bus. NVMe-of enables hosts to access SSDs over FC, Ethernet or InfiniBand. It aims to reduce latency, increase parallelism, and improve efficiency for flash-based storage.

## How do FC and NVMe-oF differ?

FC & NVMe-oF differ in various aspects, such as Architecture, Performance, compatibility, and cost. 

| NVMe-oF                                                                                                            | FC                                                                                                                |
|--------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| NVMe-oF uses a host-to-target model, where each host has a queue pair (QP) that connects to a target's controller. | FC uses a switched fabric topology, where each device has a unique address and a direct path to any other device. |
| NVMe-oF has higher throughput and IOPS than FC.                                                                    | FC has lower latency than NVMe-oF                                                                                 |
| NVMe-oF can leverage existing Ethernet or InfiniBand infrastructure.                                               | FC requires FC-specific hardware and software                                                                     |
|                                                                                                                    | FC is more expensive and complex to deploy and maintain than NVMe-oF, but also more mature and stable.            |
