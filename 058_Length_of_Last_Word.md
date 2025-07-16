# 058_Length_of_Last_Word

**Problem:** 
Given a string `s` consisting of words and spaces, return the length of the last word in the string.

## Logic:
### First Approach:

- Used `stripTrailing()` to remove trailing whitespaces.
- Used a counter to count the number of whitespaces
- Assigned `index` to accept value of string `charAt` when character is an empty space.
- Generated substring from new index value and obtained it's length

## Pseudocode:

if(s.length==1)
return s.length 
for(i; i<s.length;i++)
if(charAt(i) = ' ')
    index = i 
    count++
Then,
if(count = 0)
    substring = count, s.length()
else
    substring = index, s.length()
return s.length()

---
## Submission 1 :
Runtime: 2ms, can be slower

- Tried with `s.trim()` first, something did not work out
- Chose this despite knowing it would be slower 
- Submission 2 will include something faster. 

```java
class Solution {
    public int lengthOfLastWord(String s) {
        int count = 0;
        int index = 0;
        s = s.stripTrailing();

        if(s.length()==1){
            return s.length();
        }

        for(int i = 0; i < s.length(); i++){
            if(s.charAt(i) == ' '){
                index = i;
                count++;
            }
        }
        if(count==0){
            String sub = s.substring(count, s.length());
            return sub.length();
        }else{
            String sub = s.substring(index + 1, s.length());
            return sub.length();
        }
    }
}
```
