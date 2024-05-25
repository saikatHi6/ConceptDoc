## Ways to find similar text
  1. shingling : similar documents can be turned into such a set problem
  2. minhashing : which compresses large sets in such a way that we can still deduce the similarity of the underlying sets from their compressed versions.
  3. locality-sensitive hashing : Another important problem that arises when we search for similar items of any kind is that there may be far too many pairs of items to test each pair for their degree of similarity, even if computing the similarity of any one pair can be made very easy. That concern motivates a technique called “locality-sensitive hashing,” for focusing our search on pairs that are most likely to be similar.
