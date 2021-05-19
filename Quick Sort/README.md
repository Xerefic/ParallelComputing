# Hyper Quick Sort

## Sequential Approach

### quickSort(array, low, high)
    1. Pick Pivot as the first element of the array
    2. Partition the array in place such that:
        elements to the left of the pivot are less than the pivot and 
        element to the right of the pivot are greater than the pivot
    4. Call quickSort for the partitioned array:
          quickSort(array[:partition])
          quickSort(array[partition+1:])
          
## Parallel Approach

  1. Divide the array into n subarrays, where n = number of cpu cores
  1. Call quickSort for each of the subarrays:
        pool.map(quickSort, data)
  1. Merge the sorted subarrays (Drawback: Loses on the inplace sorting behavior)
  

