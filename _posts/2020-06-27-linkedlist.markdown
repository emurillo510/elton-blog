---
layout: post
title:  "Link 'em up baby!"
date:   2020-06-27 09:42:00 -0700
categories: blog
---

# What is a linkedlist?

A LinkedList is a data structure representing a dynamic list. 

In comparision to an array, a dynamic list grows without the need to reallocate space. 

In LinkedList a node contains data and are linked together by pointers to other nodes. An example Node structure would be below.

Linkedlist use the term head to represent the first element in the list and tail to represent the last element in the list.


![SingleLinkedList](/assets/singly_linkedlist.png)

``` ruby
class ListNode
    attr_accessor :val, :next_node

    def initialize(val)
      @val = val
      @next_node = nil
    end
end

class LinkedList
    attr_accessor :head, :tail

    def initialize()
        @head = nil # this is a ListNode
        @tail = @head
    end

    def add(node)
        if @head.nil?
            @head = node
        else
            @tail.next = node
            @tail = node
        end
        
    end
end
```

# How to traverse a linkedlist?

There are several ways to traverse a LinkedList. Iteratively and Recursively.

## Iteratively

``` ruby

def traverse(head)

  cur = head
  while cur
    p "process node: #{cur.val}"
    cur = cur.next
  end
end

```

## Recursively

``` ruby
def traverse(head)
  if head == nil
    return nil
  end
  p "head.val: #{head.val}"
  traverse(head.next)
end
```

# Recursive vs Iterative

In the iterative version we keep a cursor node and assign that to head.
To traverse we assign the cursor node to the next node. We terminate when cur is nil.

In the recursive version we call traverse on the next node. We terminate when the next node is nil.

# Linkedlist techniques

## Reverse LinkedList

This is a good technique to understand and get comfortable with manipulating the pointers of a LinkedList

``` ruby
def reverse(head)

  next_node = nil
  cur = head
  prev = nil

  while cur
    next_node = cur.next
    cur.next = prev
    prev = cur
    cur = next_node
  end

  head = prev

  return head
end
```

## Building list using pointers

```ruby

def append(node)

tail = head
tail.next = node
tail = node

```

# How Linkedlist relates to Tree

LinkedList are the underpinning to tree structures based on LinkedList.

It is important to know you there are techniques you can use to traverse a tree similar to linkedlist. 

For example,
Instead of a next in LinkedList. You have a left and right node in a Tree. You can traverse each direction iteratively or recursively.

By combining stacks and queues, you are table to traverse a Tree or Graph (graph is a tree), by using the stack or queue as a mechanism that lines up which node to process next.


```ruby

class ListNode
    attr_accessor :val, :next_node

    def initialize(val)
      @val = val
      @next_node = nil
    end
end

class TreeNode
    attr_accessor :val, :left, :right

    def initialize(val)
      @val = val
      @left = nil
      @right = nil
    end
end


```
