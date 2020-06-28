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

# Reversing Linkedlist

# Linkedlist techniques

- Building list using pointers

# How Linkedlist relates to Tree
