Code
```Python
def checker (nums, target):
    nums.sort()
    constraint = 1001

    for i in range(0, len(nums)-2):
        if nums[i] == nums[i-1] and i > 0:
            continue

        left_pointer = i + 1
        right_pointer = len(nums) - 1

        while left_pointer < right_pointer: 
            sum1 = nums[i] + nums[right_pointer] + nums[left_pointer]
            if sum1 == target:
                return sum1
            if abs(target - sum1) < abs (target - constraint):
                constraint = sum1
            if sum1 <= target:
                left_pointer += 1
                while nums[left_pointer] == nums[left_pointer-1] and left_pointer < right_pointer:
                    left_pointer += 1
            else:
                right_pointer -= 1
                
    return constraint


class Solution:
    def threeSumClosest(self, nums: List[int], target: int) -> int:
        return checker(nums, target)
```
