---
layout: post
title: "Data Structure #1: Linked List"
author: "Dedi Prakasa"
categories: computer science
tags: [data structure,algortihm]
image: chain.jpg
---

In this writing I will explain about a data structure known as linked list. But before that, let's first see a brief overview about arrays.

Arrays is a collection of items of a single type. For example, an array may consist of either integers, strings, boolean, or other object. 

```python
# arrays of integers
[23, 5, 6, 43, 36]

# arrays of strings
['coffee', 'tea', 'cake', 'orange']

# arrays of booleans
[True, False, False, False, True]
```
Arrays have index associated with the location of the element of the array.

![alt text](https://i.imgur.com/eT6Mf5V.jpg "Array index")

A problem appears when one wants to insert or delete elements. Let's say that we want to insert new element at index 3. We need to move every element after the inserted element to different box.

![alt text](https://i.imgur.com/NeVq6pO.png "Inserting element")

This operation is inefficient and the time complexity of the worst case of this process is O(n). Deleting element also takes the same time as insertion because we also need to move every element to different location or index.

To avoid that kind of complexity, we might want to consider using linked list. While each element in arrays store the value and its index, element in linked list store its value and the value of next element. Here, we used to name this pair of 'value-next value' as a node.

![alt text](https://i.imgur.com/BnEsDGV.jpg "Information stored")
![alt text](https://i.imgur.com/mQRrlN0.jpg "Linked list")

With this scheme, inserting new value will be faster because we only need to change reference of the next value of one node. The time complexity of this operation will be O(1).

![alt text](https://i.imgur.com/ASK4v7d.jpg "Insertion in linked list")

Now, let's see how we implement it in python

``` python
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
        else:
            self.head = new_node
            
    def get_position(self, position):
        counter = 0
        current = self.head
        if position < 0:
            return None 
        while current != None and counter <= position:
            if counter == position:
                return current
            counter = counter+1
            current = current.next
        return None

e1 = Node(1)
e2 = Node(2)
e3 = Node(3)
e4 = Node(4)

ll = LinkedList(e1)
ll.append(e2)
ll.append(e3)
ll.append(e4)

print(ll.get_position(0).value)
print(ll.get_position(1).value)
print(ll.get_position(2).value)
print(ll.get_position(3).value)
```
    1
    2
    3
    4

Thank you!