---
layout: post
title: "Data Structure #2: Stacks"
author: "Dedi Prakasa"
categories: cs
tags: [data structure,algortihm]
image: stak.jpg
---

Stacks is another type of data structure that is commonly used in computer programming. The idea of a stack is that we can only access element at the end of the sequence. A fancy way to call this kind of rule is **L.I.F.O**, which stands for **last in, first out**.

Formally, stack is an abstract data type (ADT) since it only gives us the the rule to store data without explicitly telling us how it is implemented. Here, we will use linked lists to implement a stack class.


```python
class Node():
    def __init__(self, value):
        self.value = value
        self.next = None
        
class LinkedList():
    def __init__(self, head=None):
        self.head = head
        
    def append(self, new_node):
        current = self.head
        if self.head != None:
            while current.next != None:
                current = current.next
            current.next = new_node
    
    def insert_head(self, new_node):
        new_node.next = self.head
        self.head = new_node
        
    def delete_head(self):
        if self.head != None:
            deleted_node = self.head
            self.head = self.head.next
            deleted_node.next = None
            return deleted_node
        else:
            return None
        
class Stack():
    def __init__(self, top=None):
        self.ll = LinkedList(top)
        
    def push(self, new_node):
        self.ll.insert_head(new_node)
    
    def pop(self):
        return self.ll.delete_head()
```


```python
#Set up nodes
e1 = Node(1)
e2 = Node(2)
e3 = Node(3)
e4 = Node(4)

# Build stack
stack = Stack(e1)
# Put other element on top of previous element
stack.push(e2)
stack.push(e3)
stack.push(e4)
# Test
print('After pushing 2, 3, 4, the head is now ', stack.ll.head.value)
```

    After pushing 2, 3, 4, the head is now  4



```python
# Delete top element
stack.pop()
print('First pop, the head is now ', stack.ll.head.value)
stack.pop()
print('Second pop, the head is now ', stack.ll.head.value)
stack.pop()
print('Third pop, the head is now ', stack.ll.head.value)
```

    First pop, the head is now  3
    Second pop, the head is now  2
    Third pop, the head is now  1


