## Why Caching? 
To scale the system. This component lies between the Web server and the database server.
  1. To Avoid network call
  2. To Avoid computation
  3. Reduced DB load

## Cache Policy
   The main idea is data loading into the cache and evicted from the cache.
Type of caches:
   1. LRU
   2. LFU
   3. Sliding Window base cache
   

## Distributed Caching:

Scalable, High Available, High Performance. 

## Types of distributed cache 
1. Dedicated cache cluster (cache service in same host server)
2. co-located cache (cache service is in separate server)

   ![image](https://github.com/saikatHi6/ConceptDoc/assets/4381376/7541be30-c972-4de2-8118-7f89c8cf0ddc)

## Cache Write policies
   1. Write Through
   2. Write Back
   


## The best approach to choosing a cache host using consistent hashing. 

  * Cache client knows about all cache servers.
  * All cache clients should have same lists of servers.
  * Client stores list of servers in sorted order.
  * Binary search is used to identify the server.
  * Cache client uses TCP and UDP protocol to talk to servers.
  * If server is unavilable, client proceeds as through it was a cache miss.
  
  
 ## Maintaining List of Cache server
 
  * Everything keep in a singel host and use configaration management tools to deploy modified fiel to every service host.
  * Use shared storage service.
  * Use configaration service e.g. zookeper
  
  
  ### Concept refarences
  
  [Redis system design | Distributed cache System design](https://www.youtube.com/watch?v=DUbEgNw-F9c)
  
  [System Design Interview - Distributed Cache](https://www.youtube.com/watch?v=iuqZvajTOyA&feature=youtu.be)
  
  [Cache algoritham way of implimentation](http://highscalability.com/blog/2016/1/25/design-of-a-modern-cache.html)
  
  [Strategy of design cache](http://blog.gainlo.co/index.php/2016/05/17/design-a-cache-system/)
  
  [Interview Quistions](https://www.interviewbit.com/problems/design-cache/)
  
  
  ## Usecases of memcache parformance improvement in FB.
  
  1) Basic Problem : Crashing
     a) Create wrapper script to restart memcached.
     b) Fix overflow in memory counters and statistics.
     c) Outgrowing 4 GB memory. Major change moving to 64
     
  Attach to the folder   
  

  

  
  
  
  
  
  [Use case of Facebook ](https://www.youtube.com/watch?time_continue=813&v=UH7wkvcf0ys&feature=emb_logo)
