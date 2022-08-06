# Reverse Bits
--- 
- ## Question:
> Reverse bits of a given 32 bits unsigned integer.
---
- ## Example:
> Input: n = 00000010100101000001111010011100
> 
> Output:    964176192 (00111001011110000010100101000000)
---
- ## Solution:
**Code :**
```java
public class Solution {
    // you need treat n as an unsigned value
    public int reverseBits(int n) {
        int res=0;
    for(int i=0;i<32;i++){
    	res= ( res << 1 ) | ( n & 1 );         
    	n = n >> 1;                  
    }
    return res;
    } }
