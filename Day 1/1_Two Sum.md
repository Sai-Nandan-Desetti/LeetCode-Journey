**Approach: Hashmap**
* As you scan through `nums`, since it's given that a solution exists, you're guaranteed to find a `nums[i]` such that you would've already `seen` `target - nums[i]`.
	* `seen`: `{nums[i]: i}`
	* It's a dictionary that records the positions of the elements of `nums` scanned.
* Once you come across such an element, immediately
	* return the index of `diff = target - nums[i]`
		* which you would've recorded in `seen` since you would've already seen it;
	* and the index of the current element.
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        seen = {}
        for i, n in enumerate(nums):
            diff = target - n
            if diff in seen:
                return [seen[diff], i]
            seen[n] = i
```
