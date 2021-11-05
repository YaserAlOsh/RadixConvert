## What is a Radix?
A radix is the base of the number. It is what we use to interpret a string of digits, or a number.\
Normally, we use base10 when we write string of digits.\
A string of digits:\
dndn-1...d2d1d0 in base10\ 
has the value:\
d0 + d1 /* 10 + d2 /* 100 + ... + dn-1 * 10^(n-1) + dn * 10^n\
For example, the string of digits 4273 represents the value:\
3 + 7 * 10 + 2 * 100 + 4 * 1000 = 4 thousands, 2 hundreds, 7 tens and 3\

It's important to distinguish between a string of digits and its value. The value or quantity can be represented in many forms, such as the form I used above in the english language. A string of digits in base10 is one way to represent that value.\
\
We can also represent it in a base other than 10, say 8.\
We will learn how to do it soon, but for now, let's try: 10261\
1 + 6 /* 8 + 2 * 8^2 + 0 /* 8^3 + 1 /* 8^4\
1 + 6 /* 8 + 2 /* 64 + 4096 = 4 thousands, 2 hundreds, 7 tens and 3\

So a base is just what we use to represent a numeric value in a string of digits.\

## How to write a numeric value in a base n?
Consider the numeric value represented above in base10 by the string of digits: 4273\
How do we represent it in a string of digits in base8? or for any base n?\

Here's a procedure, for N = string of digits in base10:\
  1. Divide the number in base10 by n
  2. The remainder part is the current digit of the new string in base n, starting from the right.
  3. Repeat the procedure for the integer part of the division
  4. Stop when the result of division is 0

An example:\
Writing it in base8: \
1. 4273 / 8 = 534 with a remainder 1\
               1 is the first digit in the result, from the right
2. 534 / 8 = 66 with a remainder 6\
               6 is the second digit in the result
3. 66 / 8 = 8 with a remainder 2\
               2 is the third digit in the result
4. 8 / 8 = 1 with a remainder 0\
               0 is the fourth digit in the result     
5. 1 / 8 = 0 with a remainder 1\
               1 is the fourth digit in the result
Done.
10261 is the result

Writing it in base2:\n
- 4273 / 2 = 2136 with a remainder 1 \
               1 is the 1st digit in the result, from the right\n
- 2136 / 2 = 1068 with a remainder 0\
               0 is the 2nd digit in the result
- 1068 / 8 = 534 with a remainder 0\
               0 is the 3rd digit in the result
- 534 / 2 = 267 with a remainder 0\
               0 is the 4th digit in the result     
- 267 / 2 = 133 with a remainder 1\
               1 is the 5th digit in the result
- 133 / 2 = 66 with a remainder 1\
               1 is the 6th digit in the result       
- 66 / 2 = 33 with a remainder 0\
               0 is the 7th digit in the result     
- 33 / 2 = 16 with a remainder 1\
               1 is the 8th digit in the result 
- 16 / 2 = 8 with a remainder 0\
               0 is the 9th digit in the result 
- 8 / 2 = 4 with a remainder 0\
               0 is the 10th digit in the result 
- 4 / 2 = 2 with a remainder 0\
               0 is the 11th digit in the result
- 2 / 2 = 1 with a remainder 0\
               0 is the 12th digit in the result
- 1 / 2 = 0 with a remainder 1\
               1 is the 12th digit in the result\
\
Done.\
1000010110001 is the result\

## What is the point in having different bases?

The last example shows just that; Remember that computers store information in bits, which can be either 0 or 1.\
To store 4273 somewhere in the computer, it has to be converted to base2 or **binary** first, then stored in disks, solid state memory, register machines etc..\

Also, in different contexts, bases other than 10 are preferred.





