## Why Caching? 
To scale the system. This component lies between the Web server and the database server.

## Distributed Caching:

Scalable, High Available, High Performance. 

## Types of distributed cache 
1. Dedicated cache cluster (cache service in same host server)
2. co-located cache (cache service is in separate server)

The best approach to choosing a cache host using consistent hashing. 

  * Cache client knows about all cache servers.
  * All cache clients should have same lists of servers.
  * Client stores list of servers in sorted order.
  * Binary search is used to identify the server.
  * Cache client uses TCP and UDP protocol to talk to servers.
  * If server is unavilable, client proceeds as through it was a cache miss.
