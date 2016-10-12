---
layout: page
title: "HW5: CMPT231"
subtitle: "Lecture 5, ch10,12"
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

{% include policies.md %}

### HW5 (20pts)
1. Consider a **doubly-linked** list.
  + (a) *(1pt)* Write (pseudocode) **class definitions** for a single node in the list and for the list as a whole.
  + (b) *(4pts)* Write (pseudocode) a function that deletes **duplicate** items from such a list. <br/>
    E.g., input `[ 7, 1, 4, 7, 3, 4, 7 ]` &rarr; output `[ 7, 1, 4, 3 ]` <br/>
    You may assume the items are integers between 0 and 99.
  + (c) *(1pt)* What is the **running time** of your algorithm, in terms of the length *n* of the list?

2. *(4pts)* **Augment** the `Stack` pseudocode in the lecture slides
  to track the size of the stack and implement `length()` and `isempty()`.
  Handle stack **underflow** properly.

3. *(3pts)* Illustrate the **binary search tree** after each operation in the following sequence (starting from an empty tree):
  + `insert( 'D' )`
  + `insert( 'M' )`
  + `insert( 'B' )`
  + `insert( 'G' )`
  + `insert( 'K' )`
  + `insert( 'H' )`
  + `delete( 'D' )`
  + `insert( 'L' )`
  + `delete( 'G' )`

4. **Preorder** traversal of a binary search tree of characters yields the following sequence: `M F D H G L K V P N S Q T`
  + (a) *(2pts)* **Draw** the tree.
  + (b) *(2pts)* Print a **postorder** traversal.

5. *(3pts)*
