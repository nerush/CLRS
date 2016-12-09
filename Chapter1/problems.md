### 1-1 Comparison of running times

For each function f(n) and time t in the following table, determine the largest size n of a problem that can be solved in time t, assuming that the algorithm to solve the problem takes f(n) microseconds.

Answers are given for a CPU of 1 MHz (10^6).

|        | 1 second     | 1 minute     | 1 hour | 1 day | 1 month | 1 year | 1 century |
|--------|--------------|--------------|--------|-------|---------|--------|-----------|
| lgn    | 2^(10^6) | 2^(6 * 10^7) | 2^(3.6 * 10^9) | 2^(8.64 * 10^10) | 2^(2.59 * 10^12) | 2^(3.15 * 10^13) | 2^(3.15 * 10^15) |
|  √n    | 10^12 | 36*10^14 | 1.3 * 10^19 | 7.46 * 10^21 | 6.7 * 10^24 | 9.9 * 10^26 | 9.9 * 10^20 |
|   n    | 10^6 | 6 * 10^7 | 3.6 * 10^9 | 8.64 * 10^10 | 2.59 * 10^12 | 3.15 * 10^13 | 3.15 * 10^15 |
| nlgn   | 62746 | 2801417 | 133378058 | 2755147513 | 71817532807 | 796755391090 | 68535016035843 |
|  n^2   |         |              |        |       |         |        |           |
|  n^3   |           |              |        |       |         |        |           |
|  2^n   |            |              |        |       |         |        |           |
|  n!    | 9 |              |        |       |         |        | 17 |