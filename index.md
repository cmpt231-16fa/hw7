---
layout: page
title: "HW7: CMPT231"
subtitle: "Lectures 8-9, ch15-16"
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

{% include policies.md %}
{% include programming.md %}

### HW7 (40pts)
1. *(20pts)* Choose one of the **textbook** problems #15-1 to #15-12 (p.406-412). <br/>
  Some of them, e.g., 15-2 and 15-5, may benefit from reading section 15.4.
  Others, e.g., 15-1 and 15-7, may benefit from ch22. <br/>
  Code your own implementation to solve the problem
  using **dynamic programming** (bottom-up). <br/>
  All **policies** for programming projects apply.
  **User interface** is your choice and can be rudimentary.
  Be sure to answer any **questions** given in the problem statement.

2. The task is to **make change** for *n* cents using the fewest number of coins of given denominations. Consider the following **greedy** strategy: use the coin of largest denomination smaller than the remaining amount, and iterate on the rest. For each of the following sets of coin denominations, **prove** the greedy strategy is optimal, or disprove via counterexample.
  + (a) *(4 pts)* `{ 1, 10, 25 }` (i.e., pennies, dimes, and quarters)
  + (b) *(4 pts)* `{ 1, 5, 10, 25 }` (i.e., add nickels)

3. *(6pts)* (Huffman)
