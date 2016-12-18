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

TODO

#### 2.1-4
Consider the problem of adding two _n_-bit binary integers, stored in two _n_-element arrays `A` and `B`. 
The sum of the two integers should be stored in binary form in an _`(n+1)-element`_ array `C` . 
State the problem formally and write pseudocode for adding the two integers.

TODO