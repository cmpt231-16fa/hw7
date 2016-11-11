---
layout: page
title: "HW7: CMPT231"
subtitle: "Lectures 8-9, ch15-16"
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

{% include policies.md %}
{% include programming.md %}

### HW7 (40pts)
1. *(20 pts)* Choose one of the **textbook** problems #15-1 to #15-12 (p.406-412). <br/>
  Some of them, e.g., 15-2 and 15-5, may benefit from reading section 15.4.
  Others, e.g., 15-1 and 15-7, may benefit from ch22. <br/>
  Code your own implementation to solve the problem
  using **dynamic programming** (bottom-up). <br/>
  All **policies** for programming projects apply.
  **User interface** is your choice and can be rudimentary.
  Be sure to answer any **questions** given in the problem statement.

2. The task is to **make change** for *n* cents using the fewest number of coins of given denominations \`c\_1=1 < c\_2 < ... < c\_k\`. Consider the following **greedy** strategy: use a coin of largest denomination smaller than the remaining amount, and iterate on the rest.
  + (a) *(2 pts)* Demonstrate via **counterexample** that this greedy strategy is **not** optimal if we can only use pennies, dimes, and quarters (i.e., `c = { 1, 10, 25 }`).
  + (b) *(8 pts)* **Prove** that greedy **is** optimal for all *n* if we can also use nickels (i.e., `c = { 1, 5, 10, 25 }`). A coin set is called *canonical* if greedy is optimal for all *n*.

3. *(5 pts)* (Huffman hand-sim)

<!-- given freqs, build Huffman, calc compression ratio -->

4. *(5 pts)* Design (i.e., pseudocode) a **dynamic programming** solution for the 0-1 knapsack problem. *Hint:* For *n* items and a knapsack capacity of *W*, the subproblem graph is a 2D *n* x *W* table, where each subproblem *(i, w)* solves for the first *i* items and a capacity of *w*.

