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
