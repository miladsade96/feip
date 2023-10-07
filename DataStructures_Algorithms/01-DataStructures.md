# Data Structures in Javascript


## Array:

**Short introduction:**  
JavaScript's arrays are zero-indexed, meaning the first element is at index 0, not 1. Arrays can hold elements of
any data type - numbers, strings, booleans, objects, even other arrays. Arrays have dynamic size in JS. You don't
need to pre-define a fixed size like other languages.  

**Big O:**  
- **Access - O(1):** Get an element by index using bracket notation like arr[0]. Accessing by index is very fast.
- **Search - O(n):** Search for an element using indexOf() or includes(). This is linear search so grows slower as the array size increases.
- **Insert:**
  - **O(n):** Add to end of array with push(). Add to beginning with unshift(). This is slow since it requires shifting subsequent elements over.
  - **O(1):** Insert into middle of array using splice(). This is faster than push/unshift.
- **Delete:**
  - **O(n):** Remove from end with pop(). Remove from beginning with shift(). This is slow like insert since it requires shifting elements.
  - **O(1):** Delete from middle using splice(). Faster than pop/shift.
- **Space complexity - O(n):**  because arrays are typically implemented using a contiguous block of memory. In order to access or modify an element in the array, the array needs to keep track of the address of the first element in the array and the size of each element in the array.

**Tips and tricks:**
- Use hash maps/objects for fast lookup of values. Store array values as keys for O(1) access.
- Use two pointer technique for efficient traversal and comparison. Example: detecting duplicates, merging sorted arrays etc.
- Binary search to efficiently find index of a specific value in a sorted array. Time complexity is O(log n).
- Modify array in-place instead of creating new arrays to avoid costly memory overhead.
- Slice array into chunks when dealing with large arrays. Divide and conquer.
- Sort the array first if the problem relies on element order. Use built-in .sort()

---

## Hash table:

**Short introduction:**  
A hash table is a data structure that maps keys to values using a hash function. JavaScript objects
implement a basic hash table where properties act as keys. They provide fast lookup time and flexible
storage at the cost of order being arbitrary.

**Big O:**  
- **Access - O(1):** Get a value by its key using square bracket notation like hash[key]. Access by key is very fast with hash tables.
- **Search - O(1):** Check if a key exists in the hash table using hasOwnProperty() or key in hash. This is a fast lookup.
- **Insert - O(1):** Insert a new key-value pair using square bracket notation. Takes constant time.
- **Delete - O(1):** Delete a key-value pair using delete hash[key]. Very fast removal.
- **Space complexity - O(n):** because the hash table needs to store all of the key-value pairs in the table. This is because hash tables are typically implemented using an array of buckets. Each bucket in the array can store one or more key-value pairs.

**Note:** Many collisions - A poor hash function can result in lots of keys mapping to the same hash code. This leads to the same array bucket containing many entries, slowing down lookup speed.

**Tips and tricks:**
- Use hashing to quickly check if an element exists in an array or string.
- Store values as object keys and counters/frequencies as values. Helps with problems involving counting, frequencies, duplicates etc.
- Use two hash tables to check if two arrays or strings have the same elements and counts. Compare the tables.
- For problems involving intersections, unions etc. use a hash table to quickly check containment.
- Hash tables are great for caching/memoization to store calculated results to avoid recalculation.
- Use hash tables as adjacency lists for graph problems to represent edges between nodes.
- In problems involving finding substrings, hashing substrings can give fast lookup time complexity.
- Be careful of collisions degrading worst case time complexity - understand your language's hash table implementation.
- If order of insertion matters (FIFO, LIFO), hash tables alone aren't enough. Maintain separate list.
- Estimate hash table capacity needed to figure out if a hash table implementation would fit memory constraints.
- Drawing out a few example key-value pairs in a hash table can help visualize lookup process and collisions.
- Practice questions involving maximum occurring frequency, anagrams, palindromes to get familiar with hashing strings/arrays.

---

## Linked list:

**Short introduction:**  
A linked list is a linear data structure that stores elements in nodes. Each node contains the data and a pointer to
the next node. The elements are not stored contiguously in memory like arrays, instead each node points to the next 
one in the chain. Common types of linked lists include singly linked (one pointer), doubly linked (forward and backward
pointers), and circular linked list.

**Big O:**
- **Singly and doubly linked list:**
  - **Access - O(n):** To access a node in a linked list, you have to start from the head and traverse sequentially until you reach the index you want; This is linear time.
  - **Search - O(n):** Search involves traversal to find a specific value. Also, linear time since in the worst case, you may have to visit each node once.
  - **Insert - O(1):** To insert a new node, you can rewire the pointers to insert a node after a given node in constant time O(1).
  - **Delete - O(1):** Deleting a node just requires rewiring the previous node's next pointer to skip over the node to delete. So it's constant time to delete.
  - **Space complexity - O(n):** Because each node in the linked list needs to store a pointer to the next node in the list. This means that the amount of space required by the linked list will increase linearly as more nodes are added to the list.

**Tips and tricks:**
- Draw out example linked lists visually and walk through the state changes step-by-step. Visualization helps greatly.
- Be very comfortable with traversal using while loops, updating node pointers, etc. These are very common.
- For problems involving a sublist or traversal ending condition, maintain pointers to both the head and tail nodes of sublists.
- To reverse a linked list, keep track of the previous node and swap next pointers accordingly.
- To detect cycles, use two pointers moving at different speeds - fast and slow. If they meet, there's a loop.
- For deleting nodes without head reference, copy next node's data over and delete next node instead.
- For merging two sorted lists, create a dummy head and traverse both lists picking smaller node each time.
- To find the middle node, use fast/slow pointers again where fast moves 2x speed. When fast hits end, slow is at middle.
- Recursion works well for operations like linked list reversal.

---

## Stack:

**Short introduction:**  
A stack is a linear data structure that follows the LIFO (Last In First Out) principle. The last element added to the stack is the first one removed.

**Big O:**
- **Access - O(n):** To access an element on the stack you have to pop all the elements on top of it first to reach it.
- **Search - O(n):** To search for an element, you have to linearly iterate through the stack to find it.
- **Insert - O(1):** Pushing an element onto the stack just puts it at the top, so it takes constant time.
- **Delete - O(1):** Popping an element removes the top element, which is done in constant time.
- **Space complexity - O(n):** Because the stack needs to store all the items in the stack. This is because stacks are typically implemented using a last-in-first-out (LIFO) data structure, such as an array or linked list.

**Tips and tricks:**
- Use stacks to help reverse elements - pop everything and push onto a new stack.
- Track opening/closing brackets or tags with a stack and pop/push for each one. Check empty at end.
- Use two stacks to implement a queue when needed.
- Recursion and recursive backtracking lend themselves well to stacks. Visualize call stack.
- Check for palindromic strings or substrings using a stack.
- Use stacks to do DFS (depth first search) on graphs and trees. Recursion works well here.
- Draw out stack contents step-by-step during operations on paper. Visualize pushes and pops.
- Remember to consider edge cases like empty or full stacks.
- Consider amortized costs for resize operations as stack grows.
- Compare tradeoffs to other structures like queues or heaps for the problem.
- Practice questions like decimal to binary conversion, histogram maximum rectangle area etc.

---

## Queue:

**Short introduction:**  

A queue is a linear data structure that follows the First In First Out (FIFO) principle. Items are added to the queue
at the back (tail) and removed from the queue at the front (head). This is similar to a line of people waiting to
purchase tickets, where the first person in line is the first person served. Queues are implemented using a variety
of methods, including arrays, linked lists, and circular buffers. The most common implementation is a linked list,
where each item in the queue contains a pointer to the next item in the queue.

**Big O:**
- **Access - O(n):** Because the queue is a linear data structure, accessing an item at the front of the queue requires iterating over all the items in the queue until the desired item is found.
- **Search - O(n):** For the same reason as access, searching for an item in a queue requires iterating over all the items in the queue until the desired item is found.
- **Insert - O(1):** Inserting an item into a queue is a constant time operation because it only requires adding the item to the back of the queue.
- **Delete - O(1):** Deleting an item from a queue is also a constant time operation because it only requires removing the item from the front of the queue.
- **Space complexity - O(n):** Because the queue needs to store all the items in the queue. The amount of space required by the queue will increase as more items are added to the queue

**Tips and tricks:**
- Use queues for breadth-first search (BFS) on trees and graphs instead of recursion or stacks.
- Implement other queues like priority queue, circular queue, deque to fit problem constraints.
- Use queues to model real-world queueing behavior like job scheduling, server requests, etc.
- Reverse a queue by enqueueing all items into a new queue. The order will be reversed.
- Use queues to cache or rate limit actions, only allowing one action per timestep like keypresses.
- Model a queue abstractly using two stacks when a full queue implementation is not available.
- Pay attention to empty/full queue conditions and how the implementation handles resizing.

---

## Binary Search tree:

**Short introduction:**  

A binary search tree is a hierarchical binary tree data structure that stores values in a way that allows for efficient
search, insertion and deletion. BSTs provide efficient sorting and access for dynamic datasets while being relatively
simple to implement compared to more complex tree structures.

**Big O:**
- **Access - O(n):** Because the worst-case scenario is that the BST is a linked list, in which case we need to traverse the entire tree to find the desired node.
- **Search - O(n):** Because the worst-case scenario is that the BST is a linked list, in which case we need to traverse the entire tree to find the desired node.
- **Insert - O(n):** Because the worst-case scenario is that the BST is a linked list, in which case we need to traverse the entire tree to find the correct location for the new node.
- **Delete - O(n):** Because the worst-case scenario is that the BST is a linked list, in which case we need to traverse the entire tree to find the node to be deleted.
- **Space complexity - O(n):** Because it can degenerate into a linked list. In this case, we would need to store a pointer to every node in the tree in order to traverse it.

**NOTE:** O(h) or O(n)?  
Whether a binary search tree (BST) operation is O(h) or O(n) depends on the height of the tree. The height of
a BST is the length of the longest path from the root node to a leaf node. In a well-balanced BST, the height of the
tree is logarithmic in the number of nodes in the tree. This means that the time complexity of BST operations on a
well-balanced BST is logarithmic in the number of nodes in the tree, or O(h). However, if a BST is not well-balanced,
the height of the tree can be equal to the number of nodes in the tree. In this case, the time complexity of BST
operations on the BST would be O(n).

**Tips and tricks:**
- Be familiar with the properties of a BST - left child < parent < right child and no duplicates.
- To check if a tree is BST, keep track of min/max range while traversing and compare node values against range.
- Know common BST operations - search, insert, delete, find min/max, successor, predecessor, traversal.
- Deleting a node can be tricky. Common ways are copying successor, promoting child node, reducing to two child case.
- BST problems often involve constructing a valid BST from a sorted array. Pick middle as root and recur on subarrays.
- For balanced BSTs like AVL and Red-Black, understand rotation operations and color flips needed on insert/delete.
- BST inversion counts can be found by traversing tree and counting inversions of each node versus subtrees. Merge sort approach also works.
- BST iterator problems require tracking stack of nodes or parent pointers during traversal.
- BST problems often have followup of optimizing for minimal height, improving insert/search costs etc. which leads to balanced BSTs.
- Compare runtime complexity vs other trees, understand impact of balance and height.
- Draw out examples of insert, delete, search on sample BSTs. Walk through operations visually.
- Practice coding BST construction, traversal, insert, delete, successor, predecessor type problems.

---
