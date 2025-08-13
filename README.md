# Leetcode-13.-Roman-to-Integer
# Description
Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

Symbol       Value

I             1

V             5

X             10

L             50

C             100

D             500

M             1000

For example, 2 is written as II in Roman numeral, just two ones added together. 12 is written as XII, which is simply X + II. The number 27 is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

I can be placed before V (5) and X (10) to make 4 and 9.

X can be placed before L (50) and C (100) to make 40 and 90. 

C can be placed before D (500) and M (1000) to make 400 and 900.

Given a roman numeral, convert it to an integer.

 # Solution
 Given a Roman numeral string, convert it to its integer value following Roman numeral rules — including subtractive cases like IV (4) and IX (9).

Map each Roman symbol to its value. Loop through the string comparing each symbol with the next:

If the current value is smaller than the next, subtract it.

Otherwise, add it. Finally, add the value of the last symbol and return the total.

Example 1:

Input: s = "III"

Output: 3

Explanation: I+I+I= 3.

Example 2:

Input: s = "LVIII"

Output: 58

Explanation: L = 50, V= 5, I+I+I = 3 . 50+5+3 = 58

Example 3:

Input: s = "MCMXCIV"

Output: 1994

Explanation: M = 1000, C-M = 900, X-C = 90 and I-V = 4. 1000+900+90+4 = 1994
# Algorithm
1. Create a variable named total which stores the final and total integer value , initilised as 0.
2. Create a dictionary which stores the key-value pairs of the roman symbol and its corresponding value.
3. Loop through each character in s string , and check if the ith and i+1 th character (d[s[i]]<d[s[i+1]]) , subtract d[s[i]] from the total value.
4. Else addd d[s[i]] in the d[s[i+1]].
5. If the loop ends we have to add the last value of the string since the loop processes  characters from index 0 to len(s)-2.
6. Return the total.
# Code
class Solution:

    def romanToInt(self, s: str) -> int:
        total=0
        d={'I':1,'V':5,'X':10,'L':50,'C':100,'D':500,'M':1000}
        for i in range(len(s)-1):
            if d[s[i]]<d[s[i+1]]:
                total-=d[s[i]]

            else:
                total += d[s[i]]
        total += d[s[-1]]
        return total
# Complexity
Time Complexity: O(n) — one pass through the string.

Space Complexity: O(1) — fixed-size dictionary.





Ask ChatGPT
