### Question
Given two sorted arrays ```nums1``` and ```nums2``` of size m and n respectively, return the median of the two sorted arrays. The overall run time complexity should be O(log (m+n))

### Brute Force
An obvious approach would be to
- Combine both arrays to a single array, say, ```arr```.
- Sort it.
- Then return the median of arr.

### Algorithm
The problem states that the overall complexity should be O(log (m+n)). Sorting would take an O(AlogA) where A=m+n. However, we can reduce the run time complexity to O(log (m+n)) by using merge sort.  
The [merge sort](https://en.wikipedia.org/wiki/Merge_sort)  algorithm combines two sorted list to a single list while keeping the order of list. 

Code 
``` Python
def checker(nums1, nums2):
    sorted_list = []
    i, j = 0, 0
    while i < len(nums1) and j < len(nums2):
        if nums1[i] <= nums2 [j]:
            sorted_list.append(nums1[i])
            i += 1
        else:
            sorted_list.append(nums2[j])
            j += 1

    left_remain = nums1[i:]
    right_remain = nums2[j:]

    x = sorted_list + left_remain + right_remain
    lo = 0
    hi = len(x)-1
    mid = (lo + hi) // 2
    if len(x) % 2 != 0:
        return x[mid]
    else:
        return (x[mid] + x[mid+1])/2
    


class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        return checker(nums1, nums2)
        
```
