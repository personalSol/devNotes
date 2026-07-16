---
created: 2026-07-09T07:16:03
status:
source:
updated: 2026-07-14T07:07
---
---


> [!NOTE] Summary
> - Arrays: fast to read, slow to change
> - Linked List: slow to read, fast to change
> - Stack: serves the newest item first, LIFO model
> - Queue: serves the oldest/earliest item first, FIFO model
> - Dequeue: serves both newest and the oldest at the same time. Both sides are accessible
> - Hashmaps: stores data in key-value format. hashes the key which makes accessing the value constant `O(1)`
> - Hashset: check if some data exists in dataset/collection or not and it's perfect at it
> - Tree: hierarchal data structure which is applied anywhere there is parent child relationship. But it has no rules for storing values, no sorting. You search entire tree to find something
> - Binary Search Tree: have a rule that `left < root < right` . A well maintained BST is very fast to lookup into. It can turn into slow linked list for sorted input. We also have self-balanced BST that looks things up faster.
> - Heap: highest priority always surfaces on top with top item being accessible instantly.


### Something totally unrelated
![[Pasted image 20260713084444.png]]


### Arrays


- fixed size, ordered collection of items
- every data/item has an index/numbered position
- computer knows exactly where something is if searched by index so reading operation becomes `O(1)`  
	- finding item no. 40000 takes the exact same time as finding item 4 and that's `O(1)`
- Constrains: fixed size at the moment of creation, and it doesnt change
- changing the array size requires allocating an entirely new block of memory and creating an entirely new array and copying all the previous data in new one
- same goes with insertion, insertion in an array requires us to shift every element to the right
- used at a lot of places like photos, videos, etc everywhere where position is fixed and known in advance


> [!NOTE] conclusion
> - arrays are blazingly fast in read operation through index
> - slow and rigid when it comes to modification of array or when data keeps changing


![[Pasted image 20260709071821.png]]


### Linked List
![[Pasted image 20260709073239.png]]
- imagine linked list like having a treasure hunt where we find the next clue is when we reach the clue before it, no jumping
- linked list is a structure where each node stores the pointer to the next node.
- they are scaterred throughout the memory
- insert/modify:
	- to insert, we just need to change pointer of the node before it and make it point towards the new node and make the new node point towards the next node
	- to delete we just remove the pointer to that node and directly point to the node afterwards and it's gone from the chain
	- to increase the size we just have the last node point to the new node
	- insertion becomes fast with `O(1)`
- read:
	- requires us to check each node for the pointer and from that pointer jump to the next node and see it's pointer.
	- to read to a 10k-th node we need to read 9.9k nodes and jump to 10k-th one
	- no index in memory to jump to, no fixed position to compute, you must find an element by following through the chain, one step at a time
	- so yeah we traverse each node before the node we want to reach to
	- reading becomes `O(n)`
![[Pasted image 20260709073459.png]]

### Stack

- being highly used everywhere around the world from how `ctrl+z` works in a document to how our browser jumps to the page just before it when we hit back button to stack calls of functions when a program runs
- works on the principle of LIFO ( last in first out ) like a stack of plates or books, etc
- can perform two operations:
	- `push`: means inserting an element to the last
	- `pop`: means deleting an element from the last
- because we know where to exactly push and pop from these actions are instant with TC of `O(1)`
- you cant touch the middle or bottom, that's a constrain
![[Pasted image 20260709075600.png]]

### Queue

- works on FIFO ( first in first out ) model. 
- literally like a queue you see anywhere, whoever comes first gets served first, no cutting in line
- has two main operations:
	- enqueue: adds to the back
	- dequeue: removes from the front
- both enqueue and dequeue are contant time operations that happens instantly
- queue is everywhere from when we write through keyboard to how server handles thousands of request to game loading, etc. 

![[Pasted image 20260709080110.png]]

### Deque

![[Pasted image 20260709080441.png]]
- you can add and remove from the front and add and remove from the back
- a specialist data structure which you need when you want to work with both ends
	- not needed most of the time but when needed to do something at both front or back, nothing else fits
- feels like a combination of stack and queue with an extra feature to add in front
	- stack: add at back, remove at back
	- queue: add at back, remove from front
	- dequeue: add/remove at back, add/remove at front
- it's everywhere in the world like:
	- browser history that allows us to move backward and forward
	- undo + redo feature

### Hashmaps

![[Pasted image 20260709082136.png]]

- stores data in key value pairs
- retrieves any value we want instantly
- what it does is it hashes a key and that gives a number and that slot is where the value gets stored
- and because it doesnt store the key directly as it is and uses hash, it works instantly
- when we search something the same function again does the hash and finds the slot number and directly goes to it. 
- going through a data of 1k or 100k, size of collection stops mattering.
- read function is `O(1)` because of it
- python dictionaries, js object, modern database indexing ways are all hashmaps
- buttt
	- uses more memory than a plain list
	- sometimes two different keys give the same slot number
	- that's called a colission

![[Pasted image 20260709084111.png]]
![[Pasted image 20260709082237.png]]

### Hashset

![[Pasted image 20260709084416.png]]

- build only to check if a value exists in a collection or not
	- a data structure build purely for checking membership
- it's a hashmap with no values, just keys
- reads in constant time `O(1)`
- no duplicates allowed
- operations: all with contant time 
	- contains: to check if something exists in collection
	- add: to insert
	- remove: to delete
- usecases:
	- tracking which users have seen notification
	- checking if the username is taken
	- filtering duplicate values in a dataset

![[Pasted image 20260709084846.png]]

### Tree

![[Pasted image 20260709085651.png]]

- not everything fits a flat datastructure point
- a tree is anywhere there is parent child relationship
- example is html dom, file explorer in windows, comment threads, ml decision tree, etc
- a hirerchal data structure with root at top, internal nodes in middle and leaf nodes at last.
- a normal/plain tree has no rules about where values go and items aren't sorted
- so to search an item in such case we will have to go through the entire tree. 

### Binary Search Tree

- a tree data structure but with a simple rule
- the node to left is small, the node to right is larger. that's it
- it just means a binary search tree with no self-balancing logic. Every node still follows the BST property (left < node < right), but there's no mechanism to keep the height small.
- for a tree with as many as a million nodes, you can find any element in 20 steps. The condition is the tree must be a well balanced BST
	- each steps cuts an entire half of the remaining tree
![[Pasted image 20260709223928.png]]
- one weakness that BST have is if we enter the numbers in an already sorted format then it will just go in a straight line and will be exactly similar to a linked list. And that will be slow
![[Pasted image 20260709224108.png]]
- we also have something called self-balancing BST. 
- In the context of BSTs (and binary search generally), "halving" refers to how each comparison eliminates about half of the remaining nodes/elements from consideration — that's _why_ operations are O(log n) in a balanced tree.
### Heap

- always keep the highest priority thing/value/item on top for easy and fast access
- we have two types of heap:
	- max heap: which reorganizes itself to keep the biggest element on top
	- min heap: reorganizes itself to keep the smallest element on top
- when something is added/removed, it reorganizes itself and the one with most priority takes the top place and it does this `efficiently`
- what happens without a heap?
	- in a data structure with values constantly coming and going we will have to do sorting with every change and doing that for millions of data is costly
	- heap avoids this because it by default keeps things sorted so we dont have to sort each time. heap does the compute at the time of insertion and removal itself I guess
- most imp task is always at top ready to be accessed instantly

![[Pasted image 20260709230458.png]]

- examples: task scheduler in cpu, map finding the shortest route with ever changing traffic data and all, and anywhere there is a live dataset where we need to find the highest priority item
![[Pasted image 20260714051713.png]]

### Graphs


- graphs are messy and chaotic but that's what makes them powerful
- in simple terms, graphs are just dots and lines.
	- ![[Pasted image 20260714052710.png]]
- ex: in fb, we all are nodes connected through edges. in maps all cities are nodes and roads are edges
![[Pasted image 20260714052458.png]]

- types of graphs:
	- undirected graphs: here connection goes both ways, like friends in facebook
	- directed graphs: here edges have direction or connection only goes one way, ex: twitter follower, you follow someone doesnt mean they follow you. 
- Adjecency: if two nodes are connected by an edge, they are adjacent ( basically live close to each other like neighbours )
- storing a graph happens in two main ways:
	- first: adjacency matrix
		- rows and columns are nodes
		- takes a lot of space
		- we basically create a matrix with each node on both side and have it 1 if both nodes are connected and 0 if they are not
	- ![[Pasted image 20260714052221.png]]
	- second: adjacency list:
		- lower in memory requirements compared to adjacency matrix
		- basically each node keeps a list of it's neighbours ( means each node keeps a list of all nodes which are connected to it )
- to traverse in graph we have either DFS ( deapth first search ) or BFS ( breath first search )
- other operations:
	- finding path between two nodes
		- like finding if there is then what's the shortest path between two nodes
	- checking if a cycle exists
	- ![[Pasted image 20260714054153.png]]
	- detecting connected components
- real world usecases of graphs:
	- recommendation systems
	- maps
	- social networks
	- webpage links
	- network routing
- BASICALLY: if things are connected in any way, you are dealing with a graph. 

### Trie

![[Pasted image 20260714055005.png]]
- pronounciation: "try"
- it's a variation of tree data strucuture where each level represents one character in a word
- whenever we type a few words we are already narrowed down at a level where only words that start with those letter remain
- ![[Pasted image 20260714055153.png]]
- for prefix search it's better than hashmap:
	- hashmap is good for exact keys to find value
	- but if we give prefix it will have to hash every key in list to find the one that starts with "app"
	- but trie does the same prefix search for us in the same exact steps as the number of letters we have typed
	- ![[Pasted image 20260714055452.png]]
- used in:
	- autocomplete
	- dictionary lookups
	- spell checkers
	- phone number lookups: we type start of a name and it gives us all those who match and those with the same prefix


### Disjoint set

- also known as Union-find
- ![[Pasted image 20260714055948.png]]
- without a smart structure if we try to check connection in a network that means checking every connection in a chain step by step
	- for millions of users in a social network, that's not fast enough
- disjoint set tracks group membership effectively even when the groups keep evolving/growing and merging
	- basically in start every node is a separete group. But as we connect them they become part of same one group.
	- each group has a representative we call leader
	- ![[Pasted image 20260714063927.png]]
	- to check if two elements are in same group. You check if they have the same leader
	- this check of seeing the leader is almost instant even after million of merges
- path compression
	- ![[Pasted image 20260714064155.png]]
	- once they know the path now it makes the path simpler so next time it's easier to search them
	- ![[Pasted image 20260714064237.png]]
	- literally gets more efficient as it's used
- examples from real world:
	- is computer A connected to same network as Computer B
	- in image processing if we try to find out two pixels in two images form the same object
	- game world design: to find if these two areas are rechable from each other
- it's a special data structure which works best for the problem of tracking connected groups that keep evolving

### Bloom Filter

![[Pasted image 20260714064640.png]]

- it literally lies
- in this data strucutre, lookup is very very fast
- when you search something it givies yes or no
	- when it says no - it's 100% accurate and that thing doesnt exist in data structure
	- when it says yes - there is a small possibility that it's not accurate
![[Pasted image 20260714064836.png]]
- that's the same false positive: it's giving a positive but that's incorrect
- but again it will never say no to something that's actually there
- why use bloom filter?
	- it's for speed and space
	- it's trades a little certainity for massive gain in speed and space
- real world examples:
	- assume we are building a password checker: we have 10s of thousands of password which are there in password breaches - file is 10gb
		- we can use that same file in bloom filter data structure in a few mbs
	- chrome safe browsing: checks the website we visit is not a fake/harmful website frm a big list of websites without storing a massive list of urls
	- etherium nodes: use it to check data without loading the entire blockchain
	- username availability: fast lookup and give yes you can take if not available in database 
	- spell checker


### LRU Cache

- smart about what to store and what to throw away
- LRU stands for Least Recently Used
	- helps basically decide what to forget
- used in cache
	- when we store data in browser cache for fast retrieval then one problem occur
	- space is limited, we cant store just everything
	- when some new data comes, some data needs to go to make space for it
	- that's where LRU cache comes, it knows which one is the least recently used item and assumes that it's not needed anytime soon so it throws that away and give space to new data
- so the data which hasnt been used in the longest time gets removed first
- ![[Pasted image 20260714070037.png]]
- ![[Pasted image 20260714070101.png]]
- ![[Pasted image 20260714070142.png]]
- it's a combination of hashmap and doubly linked list
	- hashmap gives instant access to lookups and doubly linked list tracks MRU and LRU
	- most recently used stays at front of list, least recently used stays at back
	- when you use something or new data comes move it to the front
	- when out of space, chop of the back 
- has two operations: both have time complexity of `O(1)`
	- get: retrieves a values
	- put: enters new value I think
- real world examples:
	- browsers
	- databases
	- operating systems
- every system that needs to remember something but cant afford to remember everything almost always relies on LRU cache
	- because memory is limited so your computer constantly make decisions