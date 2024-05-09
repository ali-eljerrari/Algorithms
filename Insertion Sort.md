Here's a basic implementation of the insertion sort algorithm in Python:

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr

# Example usage:
arr = [64, 25, 12, 22, 11]
sorted_arr = insertion_sort(arr)
print("Sorted array is:", sorted_arr)
```

This code sorts an array in ascending order using the insertion sort algorithm. It iterates through the array, moving each element into its correct position within the sorted portion of the array.