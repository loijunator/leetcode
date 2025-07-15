# 013_Roman_to_Integer

**Problem:** Given a Roman number, convert it into an integer.

## Logic:

- Roman numbers are written from largest value to smallest, *from left to right*.
- **But**, there are a few exceptions:
    - 4 is written as IV and not IIII
    - 9 is written as IX and not VIIII
- It is observed that the *only time* a smaller value appears before a larger value is in cases of 4, 9, 99, etc.
- Hence the Roman number is to be traversed from right to left.

- We will use a hashmap for storing Roman numbers and their respective values.

## Pseudocode:
```java
int result = Hashmap.get(last character)
for(i = RomanNumberlength - 2; i >= 0; i--){
    if(Hashmap.get(charAt(i)) > Hashmap.get(charAt(i + 1))){
        result -= Hashmap.get(charAt(i));
    }else{
        result += Hashmap.get(charAt(i));
    }
return result;
```

---
Submission 1:

Runtime : 7ms :(

```java
class Solution {
    public int romanToInt(String s) {
        Map<Character, Integer> map = new HashMap<>();
        map.put('I', 1);
        map.put('V', 5);
        map.put('X', 10);
        map.put('L', 50);
        map.put('C', 100);
        map.put('D', 500);
        map.put('M', 1000);

        s = s.toUpperCase();
        int result = map.get(s.charAt(s.length() - 1));
        
        for(int i = s.length() - 2; i>=0; i--){
            if(map.get(s.charAt(i))<map.get(s.charAt(i+1))){
                result = result - map.get(s.charAt(i));
            }else{
                result = result + map.get(s.charAt(i));
            }
        }
        return result;
    }
}
```




