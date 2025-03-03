## Find the Median of a Number Stream

### Problem Statement
Design a class to calculate the median of a number stream. The class should have the following two methods:

insertNum(int num): stores the number in the class
findMedian(): returns the median of all numbers inserted in the class
If the count of numbers inserted in the class is even, the median will be the average of the middle two numbers.

### Solution

We have to take 2 heaps, Max(the largest element will be in the top) & Min(the lowest element will be in the top) Heap. We have to follow the rules below when inserting a node in the Heap. Below rules can be followed by anyone of the heap keeping into priority. Here we are prioritizing Max heap. Here I assume that taken PriorityQueue, which will be balanced by the data structure.

maxHeap = new PriorityQueue<>((a, b) -> b - a);
minHeap = new PriorityQueue<>((a, b) -> a - b);

#### Rules of "insertNum"
    - If it is the first element of the heap, then insert into the Max heap.
    - If an inserted element is less than or equal to the Max heap's top, then insert into the Max heap, else insert into the min heap.
    - We have to balance both the heap. As we prioritized max heap, so always max heap can have one extra element. (Max Heap size+1>=Min Heap Size). We need to rebalance if this condition breaks. We have to take the top of the Max heap and push it into the min heap. If the Min Heap element is greater than the max heap, then push the top of the Min Heap into the max heap.

#### Rules of "findMedian" 
     - Return the sum/2 of the max and min heap top if the size is equal.
     - Return the top of the max heap if not equal
    
