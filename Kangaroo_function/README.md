You are choreographing a circus show with various animals. For one act, you are given two kangaroos on a number line ready to jump in the positive direction (i.e. toward positive infinity).
The first kangaroo starts at location 21 and moves at a rate of v1 meters per jump.
The second kangaroo starts at location 22 and moves at a rate of v2 meters per jump.
You have to figure out a way to get both kangaroos at the same location at the same time as part of the show. If it is possible, return YES, otherwise return NO.
Example
x * 1 = 2
v * 1 = 1
x * 2 = 1
v * 2 = 2
After one jump, they are both at x = 3 (x1 + v1 = 2 + 1. x2 + 2 = 1 + 2), so the answer is YES.
Function Description
Complete the function kangaroo in the editor below.
kangaroo has the following parameter(s):
int xl, int vl: starting position and jump distance for kangaroo 1
int x2, int v2: starting position and jump distance for kangaroo 2

Returns
string: either YES or NO
Input Format
A single line of four space-separated integers denoting the respective values of 21. v1, x2. and v2.
Constraints
0 <= x * 1 < x * 2 <= 10000
1 <= v * 1 <= 10000
1 <= v * 2 <= 10000
Sample Input O
0342
Sample Output O
YES

### Kangaroo Problem Explanation

Two kangaroos start at different positions on a number line and jump forward at fixed distances.

Parameters:
- `x1` → starting position of kangaroo 1  
- `v1` → jump distance of kangaroo 1  
- `x2` → starting position of kangaroo 2  
- `v2` → jump distance of kangaroo 2  

After `n` jumps their positions will be:

kangaroo1 = x1 + n * v1  
kangaroo2 = x2 + n * v2  

For both kangaroos to land on the same location:

x1 + n * v1 = x2 + n * v2

Rearranging the equation:

n = (x2 - x1) / (v1 - v2)

To meet, two conditions must be satisfied:

1. **The first kangaroo must jump faster than the second one.**

<!-- js -->
if (v1 <= v2) return "NO";

2. **The number of jumps (n) must be a whole number.**

if ((x2 - x1) % (v1 - v2) === 0)

The modulo operator % checks if the division has no remainder.
If the remainder is 0, it means the kangaroos land at the same position after an integer number of jumps.