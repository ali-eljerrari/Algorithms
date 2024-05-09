Here's a simple implementation of the heap sort algorithm in Python:

```python
def heapify(arr, n, i):
    largest = i
    left = 2 * i + 1
    right = 2 * i + 2

    if left < n and arr[left] > arr[largest]:
        largest = left

    if right < n and arr[right] > arr[largest]:
        largest = right

    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)

def heap_sort(arr):
    n = len(arr)

    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]
        heapify(arr, i, 0)

    return arr

# Example usage:
arr = [64, 25, 12, 22, 11]
sorted_arr = heap_sort(arr)
print("Sorted array is:", sorted_arr)
```

This code sorts an array in ascending order using the heap sort algorithm. It first builds a max heap from the input array, then repeatedly extracts the maximum element from the heap and reconstructs the heap until the array is sorted.