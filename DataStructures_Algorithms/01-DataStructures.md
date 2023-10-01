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
- **Space complexity - O(n)**

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
- **Space complexity - O(n)**

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
  - **Space complexity - O(n)**

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
- **Space complexity - O(n)**

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
