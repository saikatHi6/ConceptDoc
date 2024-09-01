
## Twitter deploys the cache environment as a single tenant & single layer cache.

## Findings from the research of 153 Twemcache clusters on Twitter

  1. In-memory caching does not always serve read-heavy workloads, write-heavy (defined as write ratio > 30%) workloads are very common, occurring in more than 35% of the 153 cache clusters we studied.
  2. TTL must be considered in in-memory caching because it limits the effective (unexpired) working set size. Efficiently removing expired objects from the cache needs to be prioritized over cache eviction.
  3. In-memory caching workloads follow approximate Zipfian popularity distribution, sometimes with very high skew. The workloads that show the most deviations tend to be write-heavy workloads.
  4. The object size distribution is not static over time. Some workloads show both diurnal patterns and experience sudden, short-lived changes, which pose challenges for slab-based caching systems such as Memcached.
  5. Under reasonable cache sizes, FIFO often shows similar performance as LRU, and LRU often exhibits advantages only when the cache size is severely limited.








![image](https://github.com/user-attachments/assets/0b054b39-4afa-483b-93f2-42a8555eefb8)


![image](https://github.com/user-attachments/assets/aefa95be-95ba-4d75-8513-d86c2d965164)


