
### Garbage Collection:
Garbage collection is very impotant to achieve high performance and latency. The Java Virtual Machine (JVM) automatically allocates memory when objects are created and reclaims it when they are no longer needed. This automatic process is both a blessing and a challenge for developers, especially in low-latency environments.

### Garbage collection in Java works in phases:

 - Object Creation & Heap Allocation: Objects are allocated memory in the heap.
 - Object Reachability Analysis: The GC identifies unreachable objects using algorithms like GC Roots Tracing.
 - Garbage Collection Process: The GC frees memory occupied by unreachable objects and compacts memory (in some strategies).
 - Memory Reclamation: The freed memory is returned to the heap for future allocations.

### Choosing the Right Garbage Collector

- Serial GC: Ideal for small applications with low memory footprint. Not suitable for low-latency applications due to longer GC pauses. Algorithm: Uses a single thread to perform GC.
- Parallel GC (Throughput Collector): Focuses on maximizing application throughput by utilizing multiple threads for garbage collection. However, it still suffers from significant pause times, making it less ideal for low-latency applications.Algorithm: Uses multiple threads for GC, improving efficiency in multi-core systems.
- CMS (Concurrent Mark Sweep): Designed to minimize pause times by performing most of its work concurrently with application threads. While it offers lower pause times, CMS can suffer from fragmentation and longer overall GC times.Algorithm: Runs concurrently with the application to reduce pause times.
- G1 (Garbage-First Collector): Aims to provide a good balance between throughput and pause times. It works by dividing the heap into regions and prioritizing the collection of regions with the most garbage, hence the name ‘Garbage-First’.Algorithm: Divides the heap into regions and prioritizes GC in regions with the most garbage.
- ZGC (Z Garbage Collector) : The newest collectors designed for low-latency applications. They aim to achieve pause times of less than 10ms, even on large heaps, by performing most tasks concurrently with the application threads.Algorithm: Uses colored pointers to perform low-latency GC with minimal stop-the-world pauses.
- Shenandoah Garbage Collector : Algorithm: Uses concurrent garbage collection with region-based memory management.

