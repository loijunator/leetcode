# 020_Valid_Parantheses

**Problem:** 
Given a string s containing just the characters `(, ), {, }, [ and ]`, determine if the input string is valid.

An input string is valid if:
    1. Open brackets must be closed by the same type of brackets.
    2. Open brackets must be closed in the correct order.
    3. Every close bracket has a corresponding open bracket of the same type.

## Logic:
if s.length % 2 != 0, return false
- The string length **must** be even because each bracket has a corresponding closing bracket,implying there are pairs

- Using stack for storing the brackets:
    - store each opening bracket in the stack.
    - then using if-else-if, pop the stack when corresponding closing bracket is received.
- return isStringEmpty().

## Pseudocode:

foreach(char c in string)
if(c = ( || { || `[` )
stack.push(c)
elseif(c=)) || elseif(c=}) || elseif(c= ])
stack.pop()
else false;
return isStringEmpty()

---
## Submission 1:
- Same as below code but used for-loop, and was 1 ms slower

## Submission 2 uses foreach, which resulted in:
Runtime: 2ms Memory: 41.82 MB

```java
class Solution {
    public boolean isValid(String s) {
        Stack<Character> str = new Stack<>();
        if(s.length() % 2 !=0) return false;

        for(char c : s.toCharArray()){
            if(c=='(' || c=='{' || c=='['){
                str.push(c);
            }else if(c==')' && !str.isEmpty() && str.peek()=='('){
                str.pop();
            }else if(c=='}' && !str.isEmpty() && str.peek()=='{'){
                str.pop();
            }else if(c==']' && !str.isEmpty() && str.peek()=='['){
                str.pop();
            }else{
                return false;
            }
        }
        return str.isEmpty();
    }
}
```
