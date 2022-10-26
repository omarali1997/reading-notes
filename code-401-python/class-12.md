# Read 12 - Stack and Queue

># Stack and Queue
### Data structure organizes the storage in computers so that we can easily access and change data. Stacks and Queues are the earliest data structure defined in computer science. A simple Python list can act as a queue and stack as well. A queue follows FIFO rule (First In First Out) and used in programming for sorting. It is common for stacks and queues to be implemented with an array or linked list.

# Stack :

### A Stack is a data structure that follows the LIFO(Last In First Out) principle. To implement a stack, we need two simple operations:

1. push - It adds an element to the top of the stack.

<img src = 'https://static.javatpoint.com/python/images/python-stack-and-queue.png'>

2. pop - It removes an element from the top of the stack.

<img src = 'https://static.javatpoint.com/python/images/python-stack-and-queue-1.png'>

## Operations:

* ## Adding :
### It adds the items in the stack and increases the stack size. The addition takes place at the top of the stack.

* ## Deletion :
### It consists of two conditions, first, if no element is present in the stack, then underflow occurs in the stack, and second, if a stack contains some elements, then the topmost element gets removed. It reduces the stack size.

* ## Traversing :
### It involves visiting each element of the stack.

## Characteristics:

* ## Insertion order of the stack is preserved.
* ## Useful for parsing the operations.
* ## Duplicacy is allowed.

# Code : 

```python
# Code to demonstrate Implementation of   
# stack using list   
x = ["Python", "C", "Android"]   
x.push("Java")   
x.push("C++")   
print(x)   
print(x.pop())   
print(x)   
print(x.pop())   
print(x)   
```
# Output :

```python
['Python', 'C', 'Android', 'Java', 'C++']
C++
['Python', 'C', 'Android', 'Java']
Java
['Python', 'C', 'Android']
```

># Queue :


### A Queue follows the First-in-First-Out (FIFO) principle. It is opened from both the ends hence we can easily add elements to the back and can remove elements from the front.

## To implement a queue, we need two simple operations:

* ## enqueue : It adds an element to the end of the queue.

<img src = 'https://static.javatpoint.com/python/images/python-stack-and-queue-2.png'>

* ## dequeue : It removes the element from the beginning of the queue



<img src = 'https://static.javatpoint.com/python/images/python-stack-and-queue-3.png'>


## Operations on Queue :

* ## Addition :
### It adds the element in a queue and takes place at the rear end, i.e., at the back of the queue.
* ## Deletion :
### It consists of two conditions - If no element is present in the queue, Underflow occurs in the queue, or if a stack contains some elements then element present at the front gets deleted.
* ## Traversing :
### It involves to visit each element of the queue.


## Characteristics :

* ## Insertion order of the queue is preserved.
* ## Duplicacy is allowed.
* ## Useful for parsing CPU task operations.


# Code :

```python
import queue   
# Queue is created as an object 'L'  
L = queue.Queue(maxsize=10)   
  
# Data is inserted in 'L' at the end using put()   
L.put(9)   
L.put(6)   
L.put(7)   
L.put(4)   
# get() takes data from   
# from the head    
# of the Queue   
print(L.get())   
print(L.get())   
print(L.get())   
print(L.get())   
```

# Output:

```python
9
6
7
4
```








