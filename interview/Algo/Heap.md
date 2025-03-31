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

### Maximize Capital

## Problem Statement
Given a set of investment projects with their respective profits, we need to find the most profitable projects. We are given an initial capital and are allowed to invest only in a fixed number of projects. Our goal is to choose projects that give us the maximum profit. Write a function that returns the maximum total capital after selecting the most profitable projects.

We can start an investment project only when we have the required capital. Once a project is selected, we can assume that its profit has become our capital.

### Example 1:

Input: Project Capitals=[0,1,2,3], Project Profits=[1,2,3,5], Initial Capital=0, Number of Projects=3
Output: 8
Explanation:

With ‘0’ capital, we can only select the first project, bringing out capital to 1.
Next, we will select the second project, which will bring our capital to 3.
Next, we will select the fourth project, giving us a profit of 5.
After selecting the three projects, our total capital will be 8 (1+2+5).

### Solution

Find all the projects that we can choose with the available capital.
From the list of projects in the 1st step, choose the project that gives us a maximum profit.

We can take Min heap for capitals and max heap for project profit
    PriorityQueue<Integer> minCapitalHeap = new PriorityQueue<>(n, (i1, i2) -> capital[i1] - capital[i2]);
    PriorityQueue<Integer> maxProfitHeap = new PriorityQueue<>(n, (i1, i2) -> profits[i2] - profits[i1]);

  - Insert indexes of all capital into min heap.
  - Iterate till provided number of projects
  - find all projects that can be selected within the available capital and insert them in a max-heap  while (!minCapitalHeap.isEmpty() && capital[minCapitalHeap.peek()] <= availableCapital). Add to max profit heap from min heap capital. 
  - terminate if we are not able to find any project that can be completed within the available capital. if (maxProfitHeap.isEmpty())
  - select the project with the maximum profit

## Next Interval

Given an array of intervals, find the next interval of each interval. In a list of intervals, for an interval i its next interval j will have the smallest ‘start’ greater than or equal to the ‘end’ of i.

Write a function to return an array containing indices of the next interval of each input interval. If there is no next interval of a given interval, return -1. It is given that none of the intervals have the same start point.

### Example 1:

Input: Intervals [[2,3], [3,4], [5,6]]
Output: [1, 2, -1]
Explanation: The next interval of [2,3] is [3,4] having index ‘1’. Similarly, the next interval of [3,4] is [5,6] having index ‘2’. There is no next interval for [5,6] hence we have ‘-1’.

### Example 2:

Input: Intervals [[3,4], [1,5], [4,6]]
Output: [2, -1, -1]
Explanation: The next interval of [3,4] is [4,6] which has index ‘2’. There is no next interval for [1,5] and [4,6].


- Create 2 max heaps one for start intervals and another for end intervals.
      PriorityQueue<Integer> maxStartHeap = new PriorityQueue<>(n, (i1, i2) -> intervals[i2].start - intervals[i1].start);
      PriorityQueue<Integer> maxEndHeap = new PriorityQueue<>(n, (i1, i2) -> intervals[i2].end - intervals[i1].end);
- Update heaps with the indexes and create an array to store the final results.
- iterate through all elements of the intervals
- Poll indexes from maxEndHeap
- Store -1 for the top index fetch from maxEndHeap
- Compare the top of maxStartHeap and the top of maxEndHeap. Will update the result If the top of the maxStartHeap index is greater or equal to the top of maxEndHeap   if (intervals[maxStartHeap.peek()].start >= intervals[topEnd].end)
- find the interval that has the closest 'start' until maxStartHeap gets empty and maxStartHeap index is greater or equal to the top of maxEndHeap.while (!maxStartHeap.isEmpty() && intervals[maxStartHeap.peek()].start >= intervals[topEnd].end) {topStart = maxStartHeap.poll();}
- update the final array with the latest top start
- add back the topStart in the maxStartHeap heap for the  next comparison.
