# Read 15 - Tree
># Tree

## What is a Tree data structure ?


### A tree is non-linear and a hierarchical data structure consisting of a collection of nodes such that each node of the tree stores a value and a list of references to other nodes (the “children”).

### This data structure is a specialized method to organize and store data in the computer to be used more effectively. It consists of a central node, structural nodes, and sub-nodes, which are connected via edges. We can also say that tree data structure has roots, branches, and leaves connected with one another. 


<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201129105858/Tree-Basic-Terminology.png">

## Recursive Definition: 

### A tree consists of a root, and zero or more subtrees T1, T2, … , Tk such that there is an edge from the root of the tree to the root of each subtree.

<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201129092959/Recursive-Tree1.png">

## Why Tree is considered a non-linear data structure?

### The data in a tree are not stored in a sequential manner i.e, they are not stored linearly. Instead, they are arranged on multiple levels or we can say it is a hierarchical structure. For this reason, the tree is considered to be a non-linear data structure.

## Basic Terminologies In Tree Data Structure:

* ##  Parent Node: 
###  The node which is a predecessor of a node is called the parent node of that node. `{2}` is the parent node of `{6, 7}`.

* ## Child Node: 
###  The node which is the immediate successor of a node is called the child node of that node. Examples: `{6, 7}` are the child nodes of `{2}`.

* ## Root Node: 
###  The topmost node of a tree or the node which does not have any parent node is called the root node. `{1}` is the root node of the tree. A non-empty tree must contain exactly one root node and exactly one path from the root to all other nodes of the tree.

* ## Leaf Node or External Node: 
###  The nodes which do not have any child nodes are called leaf nodes. `{6, 14, 8, 9, 15, 16, 4, 11, 12, 17, 18, 19}` are the leaf nodes of the tree.

* ## Ancestor of a Node: 
###  Any predecessor nodes on the path of the root to that node are called Ancestors of that node. `{1, 2}` are the ancestor nodes of the node `{7}`.

* ## Descendant: 
###  Any successor node on the path from the leaf node to that node. `{7, 14}` are the descendants of the node.`{2}`.

* ## Sibling: 
###  Children of the same parent node are called siblings. `{8, 9, 10}` are called siblings.

* ## Level of a node: 
###  The count of edges on the path from the root node to that node. The root node has level 0.

* ## Internal node: 
###  A node with at least one child is called Internal Node.

* ## Neighbour of a Node: 
###  Parent or child nodes of that node are called neighbors of that node.

* ## Subtree: 
###  Any node of the tree along with its descendant.


## Properties of a Tree:

* ## Number of edges: 
###  An edge can be defined as the connection between two nodes. If a tree has N nodes then it will have (N-1) edges. There is only one path from each node to any other node of the tree.

* ## Depth of a node: 
###  The depth of a node is defined as the length of the path from the root to that node. Each edge adds 1 unit of length to the path. So, it can also be defined as the number of edges in the path from the root of the tree to the node.

* ## Height of a node: 
###  The height of a node can be defined as the length of the longest path from the node to a leaf node of the tree.

* ## Height of the Tree: 
###  The height of a tree is the length of the longest path from the root of the tree to a leaf node of the tree.

* ## Degree of a Node: 
###  The total count of subtrees attached to that node is called the degree of the node. The degree of a leaf node must be 0. The degree of a tree is the maximum degree of a node among all the nodes in the tree.


# Example of Tree data structure

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20211127152300/imi-300x258.png">

* Node A is the root node
* B is the parent of D and E
* D and E are the siblings
* D, E, F and G are the leaf nodes
* A and B are the ancestors of E

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20210620211627/Graph2.png">

# Code

```python
# python program to demonstrate some of the above
# terminologies
  
# Function to add an edge between vertices x and y
  
# Function to print the parent of each node
  
  
def printParents(node, adj, parent):
  
    # current node is Root, thus, has no parent
    if (parent == 0):
        print(node, "->Root")
    else:
        print(node, "->", parent)
  
    # Using DFS
    for cur in adj[node]:
        if (cur != parent):
            printParents(cur, adj, node)
  
# Function to print the children of each node
  
  
def printChildren(Root, adj):
  
    # Queue for the BFS
    q = []
  
    # pushing the root
    q.append(Root)
  
    # visit array to keep track of nodes that have been
    # visited
    vis = [0]*len(adj)
  
    # BFS
    while (len(q) > 0):
        node = q[0]
        q.pop(0)
        vis[node] = 1
        print(node, "-> ", end=" ")
  
        for cur in adj[node]:
            if (vis[cur] == 0):
                print(cur, " ", end=" ")
                q.append(cur)
        print("\n")
  
# Function to print the leaf nodes
  
  
def printLeafNodes(Root, adj):
  
    # Leaf nodes have only one edge and are not the root
    for i in range(0, len(adj)):
        if (len(adj[i]) == 1 and i != Root):
            print(i, end=" ")
    print("\n")
  
# Function to print the degrees of each node
  
  
def printDegrees(Root, adj):
  
    for i in range(1, len(adj)):
        print(i, ": ", end=" ")
  
        # Root has no parent, thus, its degree is equal to
        # the edges it is connected to
        if (i == Root):
            print(len(adj[i]))
        else:
            print(len(adj[i])-1)
  
# Driver code
  
  
# Number of nodes
N = 7
Root = 1
  
# Adjacency list to store the tree
adj = []
for i in range(0, N+1):
    adj.append([])
  
# Creating the tree
adj[1].append(2)
adj[2].append(1)
  
adj[1].append(3)
adj[3].append(1)
  
adj[1].append(4)
adj[4].append(1)
  
adj[2].append(5)
adj[5].append(2)
  
adj[2].append(6)
adj[6].append(2)
  
adj[4].append(7)
adj[7].append(4)
  
# Printing the parents of each node
print("The parents of each node are:")
printParents(Root, adj, 0)
  
# Printing the children of each node
print("The children of each node are:")
printChildren(Root, adj)
  
# Printing the leaf nodes in the tree
print("The leaf nodes of the tree are:")
printLeafNodes(Root, adj)
  
# Printing the degrees of each node
print("The degrees of each node are:")
printDegrees(Root, adj)
  
# This code is contributed by rj13to.
```

# Output

```python
The parents of each node are:
1->Root
2->1
5->2
6->2
3->1
4->1
7->4
The children of each node are:
1-> 2 3 4 
2-> 5 6 
3-> 
4-> 7 
5-> 
6-> 
7-> 
The leaf nodes of the tree are:
3 5 6 7 
The degrees of each node are:
1: 3
2: 2
3: 0
4: 1
5: 0
6: 0
7: 0
```

># Types of Tree data structures : 

## 1. General tree

### A general tree data structure has no restriction on the number of nodes. It means that a parent node can have any number of child nodes.  

## 2. Binary tree  

### A node of a binary tree can have a maximum of two child nodes. In the given tree diagram, node B, D, and F are left children, while E, C, and G are the right children.  

## 3. Balanced tree

### If the height of the left sub-tree and the right sub-tree is equal or differs at most by 1, the tree is known as a balanced tree.  

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20220614001043/upload.png">

## 4. Binary search tree

### As the name implies, binary search trees are used for various searching and sorting algorithms. The examples include AVL tree and red-black tree. It is a non-linear data structure. It shows that the value of the left node is less than its parent, while the value of the right node is greater than its parent.


># Applications of Tree data structure:

## 1. Spanning trees: It is the shortest path tree used in the routers to direct the packets to the destination.  

## 2. Binary Search Tree: It is a type of tree data structure that helps in maintaining a sorted stream of data.  

## 3. Storing hierarchical data: Tree data structures are used to store the hierarchical data, which means data is arranged in the form of order.  

## 4. Syntax tree: The syntax tree represents the structure of the program’s source code, which is used in compilers.  

## 5. Trie: It is a fast and efficient way for dynamic spell checking. It is also used for locating specific keys from within a set.  

## 6. Heap: It is also a tree data structure that can be represented in a form of an array. It is used to implement priority queues.  