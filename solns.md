---
layout: page
title: "HW5 Solns: CMPT231"
subtitle: "Lecture 5, ch10,12"
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

### HW5 Solutions (20pts)

+ 1a *(1pt)* Pseudocode, linked list class definition:

```
class DblNode:
  def __init__( self, key, prev, next ):
    (self.key, self.prev, self.next) = (key, prev, next)

class LinkedList:
  def __init__( self ):
    self.head = None
```

+ 1b *(4pts)* Pseudocode, delete duplicates:

  If we were not able to assume keys are in range 0..99, then we could
  use a hashtable to store the keys we've already seen.

```
class LinkedList:
  def delete( self, node ):
    if ( node != None ):
      if ( node.prev != None ):
        node.prev.next = node.next
      if ( node.next != None ):
        node.next.prev = node.prev
      if ( node == self.head ):
        self.head = node.next
      del node

  def delete_duplicates( self ):
    seen = [ False for i in range(100) ]	# array of booleans
    cur = self.head
    while ( cur != None ):
      if ( seen[ cur.key ] ):			# duplicate: delete
        self.delete( cur )
      else:					# first time: set flag
        seen[ cur.key ] = True
      cur = cur.next
```

+ 1c *(1pt)* Running time:

  &Theta;(n) (and uses extra storage, an array of 100 booleans).

+ 2 *(4pts)* Augment `Stack` to track length:

```
class Node:
  def __init__( self, key, next ):
    (self.key, self.next) = (key, next)

class Stack:
  def __init__( self ):
    (self.head, self.len) = (None, 0)

  def length( self ):
    return self.len

  def isEmpty( self ):
    return self.len< 1

  def push( self, key ):
    self.head = Node( key, self.head )
    self.len += 1

  def pop( self ):
    if (self.isEmpty()):			# underflow
      return None
    item = self.head
    key = item.key
    self.head = item.next
    del item
    self.len -= 1
    return key
```

+ 3 *(3pts)* Illustrate operations on BST:

  Your solution should show the BST after each step, but the final BST is

  ![hw5-3 BST insert/del](../img/hw5-3.svg)

  The above assumes the convention of delete using the **successor**.
  If using the predecessor, then:

  ![hw5-3 BST ops with pred](../img/hw5-3-succ.png)

+ 4a *(2pts)* Binary tree from preorder:

  Note that sequentially inserting nodes from a preorder traversal
  exactly reproduces the original tree:

  ![hw5-4a BST from preorder](../img/hw5-4a.svg)

+ 4b *(2pts)* Postorder traversal:

  `D G K L H F N Q T S P V M`

+ 5 *(3pts)* Create balanced BST from sorted input:

  We know the length of the array and can directly address it,
  so pick the median as the root, and recursively fill in the
  left and right subtrees.

  To handle recursion in the constructor, I define a 
  helper function `buildtree` within the lexical scope
  of the constructor, inheriting the parameter `keys`.

```
class BSTNode:
  def __init__( self, key=None, parent=None, left=None, right=None ):
    (self.key, self.parent, self.left, self.right) = (key, parent, left, right)

class BST:
  def __init__( self, keys=[] ):
    def buildtree(parent, start, end):
      if start > end:
        return None
      mid = int( (start+end)/2 )
      node = BSTNode( keys[mid], parent )
      node.left  = buildtree( node, start, mid-1 )
      node.right = buildtree( node, mid+1, end   )
      return node
    self.root = buildtree( None, 0, len(keys)-1 )
```
