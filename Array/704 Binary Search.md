# 704. Binary Search

![image](https://github.com/user-attachments/assets/5fab8967-db9d-4072-be41-71bcead51574)


### ✅ Python Code ( `[left, right]`):

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left, right = 0, len(nums) - 1     # target  in a closed interval: [left, right]

        while left <= right:
            middle = left + (right - left) // 2

            if nums[middle] > target:
                right = middle - 1         # target on left
            elif nums[middle] < target:
                left = middle + 1          # target on right
            else:
                return middle              # find target
        return -1                          # if not, return -1
```

### ✅ Python Code ( `[left, right)`):
``` python 
class Solution:

    def search(self, nums: List[int], target: int) -> int:
        left, right = 0, len(nums) 

        while left < right: 
            middle = left + (right - left) //2 

            if nums[middle] > target: 
                right = middle 
            elif nums[middle] < target: 
                left = middle + 1 
            else: 
                return middle 
        return -1
```

需要特别注意的是，在处理边界的时候，left 和 right 的取值方式必须与区间定义相匹配。如果定义的是左闭右闭区间 `[left, right]`，那么 left 和 right 都是有效位置，因此在更新时必须将它们向前或向后移动一个单位（例如 `right = middle - 1`，`left = middle + 1`），以避免重复判断同一个位置导致死循环。
但如果是左闭右开区间 `[left, right)`，由于 right 本身不是有效下标，就不需要对它做 -1，直接用 `right = middle` 即可。 

It is important to handle the boundaries carefully in binary search. The values of left and right must align with the interval definition.
If you're using a left-closed, right-closed interval `[left, right]`, then both ends are inclusive. So when narrowing the search range, you must increment or decrement them by 1 (e.g.,`right = middle - 1`, `left = middle + 1`) to avoid infinite loops caused by rechecking the same element.
However, if you're using a left-closed, right-open interval `[left, right)`, since right is exclusive, there's no need to adjust it with -1; you can just use `right = middle`.
