In this, we have solved mainly array and Linkedlist-related problems. Most of the problems need the steps below. Use 2 pointers one will move faster than the other.

1. Find the circle in the list. Using 2 pointers we can find whether a loop exists or not in the linked list.
2. To find the head of the circle we need to find the length of the circle. Then, the fast pointer will be moving with that particular length. Suppose I have a list where the cycle size is 5. Then the fast pointer should be moving 5 times more than the slower one. Fast = slow + 5.
3. To find the happy number or not : we need to use 2 pointers. We can find the circle if the same number is found by both slow and fast. We can break the loop if we find 1.
4. To find the middle of the linked list also we can use 2 pointers. This is required for some cases like finding a palindrome linked list. Also, need to reverse the list from the second half of the linked list.
5. Rearrange a LinkedList is also required to find the middle node and reverse a linked list from the second half.
