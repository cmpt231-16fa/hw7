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

2. The task is to **make change** for *n* (>0) cents using the fewest number of coins of given denominations \`c\_1=1 < c\_2 < ... < c\_k\`. Consider the following **greedy** strategy: use a coin of largest denomination smaller than the remaining amount, and iterate on the rest.
  + (a) *(2 pts)* Demonstrate via **counterexample** that this greedy strategy is **not** optimal if we can only use pennies, dimes, and quarters (i.e., `c = { 1, 10, 25 }`).
    (A coin set is called *canonical* if greedy is optimal for all *n*.)
  + (b) *(2 pts)* Find **all** *n* for which the greedy strategy is not optimal, on the above coin set.

3. Below are 12 most-frequently used letters in the English language, and their relative frequencies,
  *(Source: [Norvig + Mayzner, 2012](http://norvig.com/mayzner.html))*
  + | **E** | **T** | **A** | **O** | **I** | **N** | **S** | **R** | **H** | **L** | **D** | **C** |
    |-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
    | 12.5% |  9.3% |  8.0% |  7.6% |  7.5% |  7.2% |  6.5% |  6.3% |  5.1% |  4.1% |  3.8% |  3.3% |
  + (a) *(5 pts)* Build a **Huffman** encoding tree for these 12 letters, following the pseudocode
    in lecture.  (The sequence of *left* vs *right* child is important.)
  + (b) *(2 pts)* **Encode** a text of your choosing (at least 8 letters long) using the above Huffman tree.
    Show your chosen text and split it up by letter, to make it easier for the TA to read.
  + (c) *(2 pts)* **Decode** using the Huffman tree: `10111100110110001010000011100` <br/>
    (If it looks like gibberish or doesn't end properly, just do as much as you can.)
  + (d) *(2 pts)* Calculate the **compression ratio** of this Huffman code, versus a fixed-length encoding.
    (Assume the text to be compressed uses only these 12 letters.)

4. *(5 pts)* Design (i.e., pseudocode) a **dynamic programming** solution
  for the **0-1 knapsack** problem. <br/>
  *Hint:* For *n* items and a knapsack capacity of *W*,
  the subproblem graph is a 2D *n* x *W* table,
  where each subproblem *(i, w)* solves 
  for the first *i* items and a capacity of *w*.
