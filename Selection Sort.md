Sure, here's a simple implementation of the selection sort algorithm in Python:

```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_index = i
        for j in range(i+1, n):
            if arr[j] < arr[min_index]:
                min_index = j
        arr[i], arr[min_index] = arr[min_index], arr[i]
    return arr

# Example usage:
arr = [64, 25, 12, 22, 11]
sorted_arr = selection_sort(arr)
print("Sorted array is:", sorted_arr)
```

This code sorts an array in ascending order using the selection sort algorithm. It iterates through the array, finds the minimum element in the unsorted portion, and swaps it with the first unsorted element.