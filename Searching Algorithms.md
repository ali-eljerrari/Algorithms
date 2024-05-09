Let's define the binary search algorithm first:

**Binary Search Algorithm**:

Binary search is an efficient searching algorithm used to find the position of a target value within a sorted array. It works by repeatedly dividing the search interval in half until the target value is found or the interval is empty.

1. **Objective**: The primary goal of binary search is to locate a target value within a sorted array by repeatedly dividing the search interval in half.

2. **Input**: Binary search requires a sorted array as input and a target value that needs to be found within the array.

3. **Procedure**:
   - Begin with defining two pointers, `left` and `right`, which represent the leftmost and rightmost indices of the search interval, respectively.
   - Compute the middle index `mid` of the search interval using the formula `mid = Math.floor((left + right) / 2)`.
   - Compare the target value with the element at the middle index:
     - If the target value matches the middle element, return the index of the middle element.
     - If the target value is greater than the middle element, the search continues on the right half of the array.
     - If the target value is smaller than the middle element, the search continues on the left half of the array.
   - Repeat the process until the target value is found or the search interval becomes empty (`left` exceeds `right`).

4. **Time Complexity**: Binary search has a time complexity of O(log n), where n is the number of elements in the array. This makes it significantly faster than linear search for large arrays.

5. **Space Complexity**: Binary search has a space complexity of O(1), as it only requires a few variables to store indices and temporary values.

Binary search is a fundamental algorithm used in various applications, including searching in databases, finding elements in sorted arrays, and implementing data structures like binary search trees.

---

Certainly! Here's an example of binary search in JavaScript:

```javascript
function binarySearch(arr, target) {
    let left = 0;
    let right = arr.length - 1;
    
    while (left <= right) {
        const mid = Math.floor((left + right) / 2);
        
        // If the target is found at the middle
        if (arr[mid] === target) {
            return mid;
        }
        
        // If the target is greater, ignore the left half
        if (arr[mid] < target) {
            left = mid + 1;
        } else {
            // If the target is smaller, ignore the right half
            right = mid - 1;
        }
    }
    
    // If the target is not found
    return -1;
}

// Example usage:
const array = [1, 3, 5, 7, 9, 11, 13, 15];
const target = 7;
const index = binarySearch(array, target);
if (index !== -1) {
    console.log(`Target ${target} found at index ${index}`);
} else {
    console.log(`Target ${target} not found in the array`);
}
```

In this example, the `binarySearch` function takes a sorted array `arr` and a target value `target` as input. It then performs the binary search algorithm to find the index of the target value within the array. If the target value is found, the function returns the index; otherwise, it returns -1 to indicate that the target value is not present in the array.

You can test this example by providing a sorted array and a target value, and observing whether the function correctly identifies the presence and index of the target value in the array.