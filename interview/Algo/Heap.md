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


## Sliding Window Median


### Problem Statement
Given an array of numbers and a number ‘k’, find the median of all the ‘k’ sized sub-arrays (or windows) of the array.

#### Example 1:

Input: nums=[1, 2, -1, 3, 5], k = 2
Output: [1.5, 0.5, 1.0, 4.0]
Explanation: Lets consider all windows of size ‘2’:

[ 1, 2, -1, 3, 5] -> median is 1.5
[1, 2, -1, 3, 5] -> median is 0.5
[1, 2, -1, 3, 5] -> median is 1.0
[1, 2, -1, 3, 5] -> median is 4.0
#### Example 2:

Input: nums=[1, 2, -1, 3, 5], k = 3
Output: [1.0, 2.0, 3.0]
Explanation: Lets consider all windows of size ‘3’:

[1, 2, -1, 3, 5] -> median is 1.0
[1, 2, -1, 3, 5] -> median is 2.0
[1, 2, -1, 3, 5] -> median is 3.0

### Solution

This is similar to above, we can follow the similar approach for inserting new elements and find the median of each window. We have to maintain a window where we have to remove the old element and insert the new element. For both we have to rebalance.

  - Iterate through the given numbers of the array.
  - Add one by one element using the above insertion rule.
  - Then rebalance elements as per this condition (Max Heap size+1>=Min Heap Size).
  - Check the window is selected or not  if (i - k + 1 >= 0)
  - If satisfy the above condition
  - Find the median and update in final array
  - Fetch the element from the beginning and compare if it is <= max heap, then the element should be present in the max heap and remove it from the Max heap.
  - Else remove from Min heap
  - rebalance heaps
