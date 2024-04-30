Bloom Filter(Probablistic datastructure) - https://www.youtube.com/watch?v=V3pzxngeLqw&list=PLCRMIe5FDPseVvwzRiCQBmNOVUIZSSkP8&index=3 

![image](https://github.com/saikatHi6/ConceptDoc/assets/4381376/310b0a03-624a-407c-b0aa-26f923130aaf)


1. It helps to reduce time & space complexity to find a key that exists in the system.
2. Its probabilistic data structure. A bloom filter would answer with either "firm no" or "probably yes"
3. In the bloom filter "False Positive" can be possible but not "False Negative"
4. We can not remove an item from the bloom filter.

Real Worl Example : 
     Many No SQL databases are used to reduce the disk reads for keys that don't exist. LSM tree takes more time to find the key in it
     Content delivery network Akamai uses bloom filters to prevent caching "one-hit-wonders".
     Web browsers like Chrome use it to identify malicious URL
     Some password validators use a bloom filter to prevent users from using weak passwords.

Properties Of Hash Functions :
     fast
     evenly & randomly distributed
     collisions are ok
     collisions should be rare

https://www.youtube.com/watch?v=bgzUdBVr5tE&t=430s - Here explain the mathematical calculation for error result.

Further study material - https://www.youtube.com/watch?v=hFMuWNscjyI

Deletable Bloom Filter Explanation and other types of bloom filter - https://www.youtube.com/watch?v=mItewjU-YG8
