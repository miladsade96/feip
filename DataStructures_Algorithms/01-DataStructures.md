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
