# Parallel Merge Sort

## Sequential Approach

### mergeSort(array)
    If right>left:
        1. Find the middle point to divide the array into two halves:
            middle = left + (right-l)/2
        2. Call mergeSort for first half:
            Call mergeSort(array[left:middle])
        3. Call mergeSort for second half:
            Call mergeSort(array[middle+1:right])
        4. Merge the two halves sorted in step 2 and 3:
            Call merge(array[left:middle], array[middle+1:right])

## Parallel Approach

  1. Divide the array into n subarrays, where n = number of cpu cores
  1. Call mergeSort for each of the subarrays:
        pool.map(mergeSort, data)
  1. Merge the sorted subarrays

