 - Given a binary tree, populate an array to represent its level-by-level traversal. You should populate the values of all nodes of each level from left to right in separate sub-arrays.
    - Take a List of List to store the final node values from left to right
    - Take another Queue to store and traverse each level
    - Add root node to the queue
    - iterate a while loop until q is empty
    - initialize the level as q size
    - inside the while loop, create another list where we will add all nodes in that level
    - iterate from 0 to level using for loop
    - Pull the current node from q using the poll method and add to the list
    - check if there any left node if yes add to the q
    - check if there any right node if yes add to the q
    - after the for loop add the list to the final list
    - return the list of list
    
 - Given a binary tree, populate an array to represent its level-by-level traversal in reverse order, i.e., the lowest level comes first. You should populate the values of all nodes in each level from left to right in separate sub-arrays.
 - Given a binary tree, populate an array to represent its zigzag level order traversal. You should populate the values of all nodes of the first level from left to right, then right to left for the next level and keep alternating in the same manner for the following levels.
 - Given a binary tree, populate an array to represent the averages of all of its levels.
 - Find the minimum depth of a binary tree. The minimum depth is the number of nodes along the shortest path from the root node to the nearest leaf node.
 - Given a binary tree and a node, find the level order successor of the given node in the tree. The level order successor is the node that appears right after the given node in the level order traversal.
 - Given a binary tree, connect each node with its level order successor. The last node of each level should point to a null node.
 - Given a binary tree, connect each node with its level order successor. The last node of each level should point to the first node of the next level.
 - Given a binary tree, return an array containing nodes in its right view. The right view of a binary tree is the set of nodes visible when the tree is seen from the right side.


