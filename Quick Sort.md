Here's a basic implementation of the quick sort algorithm in Python:

```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quick_sort(left) + middle + quick_sort(right)

# Example usage:
arr = [64, 25, 12, 22, 11]
sorted_arr = quick_sort(arr)
print("Sorted array is:", sorted_arr)
```

This code sorts an array in ascending order using the quick sort algorithm. It selects a pivot element from the array, partitions the array into elements less than the pivot, equal to the pivot, and greater than the pivot, and recursively sorts the subarrays. Finally, it concatenates the sorted subarrays together.