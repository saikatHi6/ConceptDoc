
## Twitter deploys the cache environment as a single tenant & single layer cache.

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
    
