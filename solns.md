---
layout: page
title: "HW7 Solns: CMPT231"
subtitle: "Lectures 8-9, ch15-16"
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

### HW7 Solutions (40pts)
+ (1) *(20 pts)* (dynamic programming project, #15-1 to #15-12)
+ (2a) *(2 pts)* **Counterexample** for `c = { 1, 10, 25 }`)

  Many possibilities: 30 = 3x10 vs 25+5x1 (and similarly up to 34), <br/>
  40 = 4x10 vs 25+10+5x1 (and similarly up to 44), etc.

+ (2b) *(2 pts)* Find **all** such *n*:

  In general, \`50a + 30 + 10b + c\`, for \`a>0, b={0,1}, c={0,1,2,3,4}\`

+ (3a) *(5 pts)* Build a **Huffman** encoding tree.

  ![Huffman tree](../img/hw7-3a.svg)

+ (3b) *(2 pts)* **Encode** a text of your choosing

  | **E** | **T** | **A** | **O** | **I** | **N** | **S** | **R** | **H** | **L** | **D** | **C** |
  |-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
  |   101 |   100 |   010 |   001 |   000 |  1111 |  1101 |  1100 |  0111 |  0110 | 11101 | 11100 |

+ (3c) *(2 pts)* **Decode** using the Huffman tree: 

  `ECSTATIC`

  (To find fun words, I used the following on Linux:<br/>
  `egrep -i '^[ETAOINSRHLDC]{8,12}$' /usr/share/hunspell/en_CA.dic`<br/>
  I decided against giving you 'INTERCONTINENTAL'.)

+ (3d) *(2 pts)* Calculate the **compression ratio**

  In our Huffman code, `ETAOI` all use 3 bits, `NSRHL` use 4, and `DC` use 5.  <br/>
  Huffman coding 1000 letters with the given ratios would take
  \`3(125 + 93 + 80 + 76 + 75) + 4(72 + 65 + 63 + 51 + 41) + 5(38 + 33)\` = **2870** bits.

  Fixed encoding would require \`|~ log\_2 12 ~|\` = 4 bits per letter, for a total of **4000** bits.

  The compression ratio is 4000/2870 = **1.3937**.
  (Also accepted: file size 2870/4000 = 71.75%, or space savings 1 - 2870/4000 = 28.25%.)

+ (4) *(5 pts)* Pseudocode **0-1 knapsack**

  The recurrence for total value in the knapsack is
  \`V(i,w) = { (0, if i=0 or w=0), (V(i-1,w), if w\_i > w),
    (max( V(i-1,w), v\_i w\_i ), else ) :} \`

  In the Python solution below, the lists are indexed starting at 0
  (instead of 1), and we pad the table with a row and a col of zeroes.
  See, e.g., [GeeksForGeeks](http://www.geeksforgeeks.org/dynamic-programming-set-10-0-1-knapsack-problem/).

```
def knapsack01(weights, values, W):
  n = len(weights)
  V = [ [ 0 for x in range(W + 1) ] for x in range(n + 1) ]
 
  for i in range(1, n + 1):
    for w in range(1, W + 1):
      if weights[i-1] > w:
        V[i][w] = V[i-1][w]
      else:
        V[i][w] = max( V[i-1][w], values[i-1] + V[i-1][w - weights[i-1]] )
 
  return V[n][W]
```
