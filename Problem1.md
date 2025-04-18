
# Leetcode 8: String to Integer (atoi)


[Problem Link:](https://leetcode.com/problems/string-to-integer-atoi/description/)

<img width="347" alt="Screenshot 2025-04-18 at 11 29 41 PM" src="https://github.com/user-attachments/assets/61954628-8e25-4c93-81cd-465146b74a56" />


### 🔸 **1\. Trim the String**

*   **Why?** To remove any **leading or trailing whitespaces** which are irrelevant to the number.

  
```
s = s.trim();
```


*   If the trimmed string is **empty**, return 0.
    

### 🔸 **2\. Initialize Variables**

*   num = 0: to build the final number.
    
*   sign = 1: to store whether the number is positive or negative.
    
*   i = 0: pointer to iterate over the string.
    
*   n = s.length(): store string length to avoid repeated calls.
    

### 🔸 **3\. Handle Sign**

*   Check if the first non-space character is '+' or '-'.
    
*   If '-', set sign = -1; otherwise, leave it as 1.
    
*   Move pointer i to the next character.
    

### 🔸 **4\. Process Digits**

*   While i < n and s.charAt(i) is a digit:
    
    *   Convert the char to a digit using s.charAt(i) - '0'.
        
    *   Update num = num \* 10 + digit.
        

### 🔸 **5\. Overflow / Underflow Handling**

*   After adding each digit, check:

  
 ```
if (num * sign > Integer.MAX_VALUE) return Integer.MAX_VALUE;
if (num * sign < Integer.MIN_VALUE) return Integer.MIN_VALUE;

```


This ensures you never cross the 32-bit integer range.

### 🔸 **6\. Return Result**

*   Multiply num with sign to return the final result.
    

### 📦 **Time and Space Complexity**

*   **Time Complexity:** O(n) — we traverse the string once.
    
*   **Space Complexity:** O(1) — no extra space used except a few variables.
