Sure! Here's an implementation of the bubble sort algorithm in JavaScript:

```javascript
function bubbleSort(arr) {
    const n = arr.length;
    let swapped;
    
    do {
        swapped = false;
        for (let i = 0; i < n - 1; i++) {
            if (arr[i] > arr[i + 1]) {
                // Swap elements
                // [arr[i], arr[i + 1]] = [arr[i + 1], arr[i]];
                arr[i] = arr[i + 1];
                arr[i + 1] = arr[i];
                swapped = true;
            }
        }
    } while (swapped);
    
    return arr;
}

// Example usage:
const array = [64, 25, 12, 22, 11];
console.log("Original array:", array);
console.log("Sorted array:", bubbleSort(array));
```

This code defines a function `bubbleSort` that takes an array `arr` as input and sorts it using the bubble sort algorithm. The algorithm repeatedly iterates through the array, comparing adjacent elements and swapping them if they are in the wrong order. The process continues until no more swaps are needed, indicating that the array is sorted.

You can test this implementation by calling `bubbleSort` with an array of numbers and observing the sorted output.