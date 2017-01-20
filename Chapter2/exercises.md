#### 2.1-1
Using Figure 2.2 as a model, illustrate the operation of INSERTION-SORT on the array `[31, 41, 59, 26, 41, 58]`.

|    step    | state |
|--------|-----------|
| 1 | [**31**, 41 , 59, 26, 41, 58] |
| 2 | [**31**, **41**, 59, 26, 41, 58] |
| 3 | [**31**, **41**, **59**, 26, 41, 58] |
| 4 | [**26**, **31**, **41**, **59**, 41, 58] |
| 5 | [**26**, **31**, **41**, **41**, **59**, 58] |
| 6 | [**26**, **31**, **41**, **41**, **58**, **59**] |


#### 2.1-2
Rewrite the INSERTION-SORT procedure to sort into non-increasing instead of non-decreasing order.

```scala
for j = 2 to A.length
  key = A[j]
  i = j - 1
  while i > 0 and A[i] < key
    A[i + 1] = A[i]
    i = i - 1
  A[i + 1] = key
```

#### 2.1-3
Consider the searching problem:
Input: A sequence of `n` numbers `A = [a1, a2, ..., an]` and a value `v`.

Output: An index i such that `v = A[i]` or the special value `NIL` if `v` does not appear in `A`.

Write pseudocode for _**linear search**_, which scans through the sequence, looking for `v`. 
Using a loop invariant, prove that your algorithm is correct. Make sure that your loop invariant fulfills the three necessary properties.

![alt text](./2.1-3.png "Pseudocode")

Let us see how three properties of loop invariant hold for linear search algorithm.

**Initialization**: we start by showing that the loop invariant holds before the first loop iteration, when there is no found index of 
given value `v` from given array `A`. 

**Maintenance**: Next, we tackle the second property: showing that each iteration maintains the loop invariant. Informally, the body of 
the **for** loop works by checking each element in sequence of given array `A` until it finds the value by index `i`, such that `v = 
A[i]`. Incrementing `i` by 1 for the next iteration of the **for** loop then preserves the loop invariant with not found index.

**Termination**: Finally, we examine what happens when the loop terminates. There are two conditions causing the **for** loop to terminate:
1. when the value `v` is found by the index `i` in the array `A`. We must have `1 <= i <= A.length` at that time.
2. when the value `v` is not found by the index `i` in the array `A`. We must have `i = A.length + 1` at that time.

Observing that the output of the linear search algorithm is an index `i` such that `v = A[i]` or the special value `NIL` if `v` does not
 appear in `A`, we conclude that the algorithm is correct.


#### 2.1-4
Consider the problem of adding two _n_-bit binary integers, stored in two _n_-element arrays `A` and `B`. 
The sum of the two integers should be stored in binary form in an _`(n+1)-element`_ array `C` . 
State the problem formally and write pseudocode for adding the two integers.

**Input**: Two _n_-bit binary integers, stored in two _n_-element arrays `A` and `B`

**Output**: The sum of the two integers stored in binary form in an _`(n+1)-element`_ array `C`

Given below pseudocode for binary addition called **ADD**, which is responsible for adding two binary digits represented in
 array data structure. The algorithm creates new array C of n+1 size for holding the result of addition, iterates through A and B from 
 least significant bit to the most significant one, adds bits using XOR binary operator and keeps the carry for the next iteration using 
 AND binary operator. After adding A and B, the resulting carry bit is stored at C[1].

```scala
function add(A, B)
  C = [A.length+1]
  carry = 0
  for i = A.length to 1 by -1
    C[i] = (A[i] XOR B[i]) XOR carry
    carry = ((A[i] XOR B[i]) AND carry) OR (A[i] AND B[i])
  C[1] = carry
  return C
```
