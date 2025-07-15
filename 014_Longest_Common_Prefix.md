# 014 - Longest Common Prefix

**Problem:** 

Write a function to find the longest common prefix string amongst an array of strings.
If there is no common prefix, return an empty string `""`.

## Logic:
- First string in the array is assigned to the variable `result`.
- Then, a for loop checks if index of `result` is 0.
    - If not, `result` is truncated by 1.


## Pseudocode:

for(i = 0; i < arraylength; i++)
while(array[i].indexOf(result != 0)) 
    result = result.substring(0, result.length() - 1)

---
## Submission 1:

Runtime: 0ms
Memory: 41.34 Mb

```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        String result = strs[0];
        if(strs.length==1){
            return result;
        }
        for(int i=1; i < strs.length; i++){
            while(strs[i].indexOf(result) != 0){
                result = result.substring(0, result.length() - 1);
            }
        }
        return result;
    }
}
```



