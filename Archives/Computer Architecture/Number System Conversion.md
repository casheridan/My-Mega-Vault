# Converting Number Systems
1. Divide the decimal number by the value of the new base
2. Get the remainder of Step 1.
3. Divide the quotient of the previous divide by the new base.
4. Record the remainder from step 3 as the next digit of the new base number.
5. Repeat steps 3 and 4 until the quotient becomes zero

(29)10 --> (...)2

Operation Results Remainder
	29/2          14              1
	14/2            7              0
	7/2              3              1
	3/2              1              1
	1/2              0              1
	Answer: 11101

(25)8 --> (...)2

Convert to decimal

25)8 = 2\*8^1 + 5\*8^0 = 16+5=21)10
21/2 10 1
10/2 5 0

Convert each digit to 3 bits and that will get the conversion from octal to binary
this also works in reverse as well, remember if there is only 5 digits add a 0 to the front of the byte.

Short cut for binary to hex: do previous conversion process but instead of 3 use 4 bits

35)10 -> (?)2
35/2 17 1
17/2 8 1
8/2 4 0
4/2 2 0
2/2 1 0
1/2 0 1

100011
1 x 0 + 0 + 0 + (1 x 2^1) + (1 x 2^0) = 

(010)(101)(010) = 252


2^-2 = 0.25

2^-2 = 1/2^2 = 1/4 = 0.25

101.101 = 5.0 + (0.500 + 0.125)= 5.625)10

.25)10 = (0.01)2

13 = D

32.45)10

32/2 16 0
16/2 8 0
8/2 4 0
4/2 2 0
2/2 1 0
1/2 0 1
100000

0.45x2 0.9 0
