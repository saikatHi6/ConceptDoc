- Reverse a LinkedList
   - Take 3 Nodes. cur will initialized with head. prev & next will initialized with null
   - Iterate loop until cur does not equal null. while(cur!=null)
   - put cur.next into next. next=cur.next
   - put prev into cur.next. prev=cur.next.
   - cur put into the prev. prev = cur
   - next put into cur. cur = next 
- Reverse a Sub-list
   ![image](https://github.com/user-attachments/assets/6aacfa41-1cba-4045-a072-4148c505d686)

      Here will have 3 inputs. head node, starting and ending of sub list. So we need to reverse the sub list.
   - skip nodes until the start index.  Iterate over the list and change prev=cur and cur =cur.next
   - Will another 2 nodes. last node of the first part and another last node of the sublist. So that the last node can hold the  head of the reverse list and put the head of the last part in the reversed list. so initialized lastNodeOfFastPart = prev and lastNodeOfSublist=cur.
   - reverse the list using the above logic. from cur we have to change the sub list.
   - Post iterate sub list will be rotated and cur will be very next to the sub list and prev in the last node of the sub list
   - if lastNodeOfFastPart.next!=null then lastNodeOfFastPart.next = prev
   - else head = prev
   - lastNodeOfSublist.next = cur
   - return head

- Reverse the first ‘k’ elements of a given LinkedList.
   - It is similar to the above. Write a function that can be passed starting, ending index and head.
   - Then pass 0 and k as an index.
- Given a LinkedList with ‘n’ nodes, reverse it based on its size in the following way:
   - If ‘n’ is even, reverse the list in a group of n/2 nodes.
   - If n is odd, keep the middle node as it is, reverse the first ‘n/2’ nodes, and reverse the last ‘n/2’ nodes.

     - This is also similar to the above. Write a function that can pass the start and end index and the head.
     - if n is even then reverse(1,n/2,head) and reverse(n/2+1,n,head)
     - if n is odd then reverse(1,n/2,head) and reverse(n/2+2,n,head)
    
       
- Given the head of a LinkedList and a number ‘k’, reverse every ‘k’ sized sub-list starting from the head. If, in the end, you are left with a sub-list with less than ‘k’ elements, reverse it too.
   We have to follow the same as above only thing is we have to reverse k elements until current is null.
    - Assign cur is head and prev is null. cur = head and prev = null.
    - Start with an infinity loop. while(true)
    - lastNodeOfFirstPart will assign with prev and lastNodeOfSubstring equal to cur. lastNodeOfFirstPart=prev & lastNodeOfSubstring=cur
    - reverse the till k elements. Using for loop will reverse it till k.
    - If lastNodeOfSubstring.next is not null then lastNodeOfSubstring.next = prev. To connect with the previous part
    - Else head = prev. Means it's the last node.
    - lastNodeOfSubstring.next = cur. To connect with the next part
    - Break if cur = null
- Given the head of a LinkedList and a number ‘k’, reverse every alternating ‘k’ sized sub-list starting from the head. If, in the end, you are left with a sub-list with less than ‘k’ elements, reverse it too.
    - This problem is similar to the above. Only we have to skip the list for the next k elements.
- Rotate a LinkedList. Given the head of a Singly LinkedList and a number ‘k’, rotate the LinkedList to the right by ‘k’ nodes.
   ![image](https://github.com/user-attachments/assets/dff27d2a-1ab8-451d-9303-40504cb6fa75)

   - Find the length of the linked list.
   - Then in the last insert the head of the list.
   - Do a mod length with k. means k = len%k
   - Skip K elements and put the head on the K+1
   - Now prev will point to the kth element. So prev.next update with null

