# Various sorting method

## What is Quick sort?
a sorting method that works by selecting a "pivot" element and partitioning the other elements into two sub-arrays

## key features
- returns average time complexity as `O(n * log n)`
- returns worst time complexity as `O(n**2)`
- cache-efficient

``` python
def quick_sort(arr):
    if len(arr)<2: return arr
    
    pivot = arr[0]
    low, high=[], []
    
    for i in arr[1:]:
        if i < pivot: low.append(i)
        else: high.append(i)
    return quick_sort(low)+ [pivot] +quick_sort(high)

my_list=list(map(int, input().split()))
print("Before sorting: ", my_list)
print("After sorting: ", quick_sort(my_list))
```

## What is Merge sort?
a sorting method that works by halving an original array into two subarrays and merging them back together.


## Key features
- **always** guarantees time complexity as `O(n * log n)`
- preferred algorithm for linked lists

## When to use which 

### Use Quicksort when:
- Memory space is limited.
- Sorting a standard array where cache locality significantly boosts performance.
- Average performance is more important than the guaranteed worst-case.

### Use Mergesort when:
- Stability is required (maintaining the relative order of equal elements).
- Dealing with Linked Lists (where sequential access is faster than random access).
- You need a guaranteed $O(n \log n)$ even in the worst-case scenario (e.g., almost sorted or reverse-sorted data).






