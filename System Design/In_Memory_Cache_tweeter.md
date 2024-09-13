
## Twitter deploys the cache environment as a single tenant & single layer cache.[https://www.usenix.org/conference/osdi20/presentation/yang]

## Findings from the research of 153 Twemcache clusters on Twitter

  1. In-memory caching does not always serve read-heavy workloads, write-heavy (defined as write ratio > 30%) workloads are very common, occurring in more than 35% of the 153 cache clusters we studied.
  2. TTL must be considered in in-memory caching because it limits the effective (unexpired) working set size. Efficiently removing expired objects from the cache needs to be prioritized over cache eviction.
  3. In-memory caching workloads follow approximate Zipfian popularity distribution, sometimes with very high skew. The workloads that show the most deviations tend to be write-heavy workloads.
  4. The object size distribution is not static over time. Some workloads show both diurnal patterns and experience sudden, short-lived changes, which pose challenges for slab-based caching systems such as Memcached.
  5. Under reasonable cache sizes, FIFO often shows similar performance as LRU, and LRU often exhibits advantages only when the cache size is severely limited.








![image](https://github.com/user-attachments/assets/0b054b39-4afa-483b-93f2-42a8555eefb8)


![image](https://github.com/user-attachments/assets/aefa95be-95ba-4d75-8513-d86c2d965164)


![image](https://github.com/user-attachments/assets/517cd30f-07c8-44a4-9675-d799c2a7e397)


## There are three approaches to choosing the slab to evict: 
    - choosing a slab randomly (random slab), 
    - choosing the least recently used slab (slabLRU)
    - choosing the least recently created slab (slabLRC). 

### Cache UseCases
    - caching for storage: Backend storage such as databases usually has a longer latency and a lower bandwidth than in-memory cache. Therefore, caching these objects reduces access latency, increases throughput, and shelters the backend from excessive read traffic. This use case has received the most attention in research
    - caching for computation: 
    - caching for transient data:  In-memory caching is often the only production solution that meets both the performance and scalability requirements of such use cases. Some notable examples are rate limiters, deduplication caches, and negative result caches. Rate limiters are counters associated with user activities. They track and cap user requests in a given time window and prevent denial-of-service attacks. Deduplication caches are a special case of rate limiters[**How in-memory cache used in rate limiter and deduplication cache**], where the cap is 1. Negative result caches store keys from a larger database that are known to be misses against a smaller, sparsely populated database. These caches shortcircuit most queries with negative results, and drastically reduce the traffic targeting the smaller database.



### Compared to CDN caching in-memory caching usually has a lower miss ratio.

### Measuring all Twemcache workloads, we observe that the majority of the cache workloads still follow Zipfian distribution.

## Findings
  - write-heavy workloads usually use short TTLs


## Eviction algorithm candidates

    - Object LRU and object FIFO LRU and FIFO are the most common algorithms used in production caching systems
    - slabLRU and slabLRC These two algorithms are part of eviction algorithms offered in Twemcache. slabLRU and slabLRC are equivalent to LRU and FIFO but executed at a level much coarser granularity of slabs rather than a single object
    - Random slab eviction Besides slabLRU and slabLRC, Twemcache also offers Random slab eviction, which globally picks a random slab to evict
    - Memcached-LRU Memcached adapted LRU by creating one LRU queue per slab class. We call the resulted eviction algorithm Memcached-LRU, which does not enable Memcached’s slab auto-move functionality. 


### open-source simulator called libCacheSim to study the steady-state miss ratio of the different eviction algorithms. 
    
  ![image](https://github.com/user-attachments/assets/7cbdb26f-2d5e-4346-8749-afa88e75c981)



1. The second type of result shows that for some workloads LRU works better than others. Such a result is often expected because LRU protects recently accessed objects and is well known for its miss ratio performance in workloads with strong temporal locality.

### Miss Ratio comparison 
1. Twemcache uses random slab eviction by default because random eviction is simple and requires less metadata.
2. The second type of result shows that for some workloads LRU works better than others. Such a result is often expected because LRU protects recently accessed objects and is well known for its miss ratio performance in workloads with strong temporal locality. For workloads with inter-arrival time like Figure 14a, LRU can work better than FIFO because it promotes recently accessed objects, which have a higher chance of being reused soon. 
3. The third type of result shows that FIFO is the best eviction algorithm, such as CDN caching. FIFO can perform better than LRU. Such workloads may include scan type of requests such as a service that periodically sends emails.
4. The last type of result show that in some workloads, slabLRU performs much better than any other algorithms.

- We see that at the large cache size slabLRU is the best for around 10% of workloads, and this fraction gradually increases as we reduce cache size. 
- only at very small cache sizes, LRU becomes significantly better than FIFO.

** Write-heavy workloads in caching systems usually have lower throughput and higher latency, because the write path usually involves more work and can trigger more expensive events such as eviction.
write-heavy workloads have shorter TTLs with less skewed popularity, which are in sharp contrast to read-heavy workloads.


### Short TTLs

1. Transient object cache:  An approach employed for proactive expiration (especially for handling short TTLs), proposed in the context of in-memory caches at Facebook [59], is to use a separate memory pool (called transient object pool) to store short-lived objects. The transient object cache consists of a circular buffer of size t with the element at index i being a linked list storing objects expiring after i seconds. Every second, all objects in the first linked list expire and are removed from the cache, then all other linked lists advance by one.
2. Background crawler: Another approach for proactive expiration, which is employed in Memcached, is to use a background crawler that proactively removes expired objects by scanning all stored objects.


**File system caching is different from distributed in-memory caches due to a variety of reasons. , file system caches usually stores objects of fixed-sized chunks (512 bytes, 4 KB or larger), while in-memory caches store objects of a much wider range (Section 4.6), and scan is common in file systems, while rare in in-memory caches.**
