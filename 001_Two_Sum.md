# 001 Two Sum

**Problem:** 
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

## Logic:


## Pseudocode:


---
## Answer:

1. First submission:
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> hashmap = new HashMap<>();
        int n = nums.length;

        for(int i=0; i<n; i++){
            hashmap.put(nums[i], i);
        }
        for(int i = 0; i < n; i++){
            int diff = target - nums[i];
            if(hashmap.containsKey(diff) && hashmap.get(diff)!= i){
                return new int[]{i, hashmap.get(diff)};
            }
        }
        return new int[]{}; //no solution
    }
}
```
