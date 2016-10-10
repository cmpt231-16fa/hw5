---
layout: page
title: "HW5: CMPT231"
subtitle: "Lecture 5, ch10,12"
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

{% include policies.md %}

### HW5 (20pts)
1. (a) *(1pt)* Write (pseudocode) a class definition for a node of a doubly-linked list and a class definition for the list as a whole.
  + (b) *(4pts)* Write (pseudocode) a function that deletes **duplicate** items from such a list. <br/>
    E.g., input `[ 7, 1, 4, 7, 3, 4, 7 ]` &rarr; output `[ 7, 1, 4, 3 ]` <br/>
    You may assume the items are integers between 0 and 99.
  + (c) *(1pt)* What is the **running time** of your algorithm, in terms of the length *n* of the list?

2. *(3 pts)* Illustrate the following sequence of operations on a **binary search tree** (starting from an empty tree):
  + `insert( 'D' )`
  + `insert( 'M' )`
  + `insert( 'B' )`
  + `insert( 'G' )`
  + `insert( 'K' )`
  + `insert( 'H' )`
  + `delete( 'D' )`
  + `insert( 'L' )`
  + `delete( 'G' )`
