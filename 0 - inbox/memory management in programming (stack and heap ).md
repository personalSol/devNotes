---
status: newBorn
related-links: []
created: 2025-04-12T08:38
updated: 2025-04-12T08:46
---
---
> Most programming languages have two types of memory.

- Stack
    - Stack is a part of main memory
    - There is a separate stack for each method
    - Used to store local variables and their values or address.
    - It follows LIFO [Last In First Out] method
        - Means if we store 5, 4, 6, 7 and try to retrieve values. We will first get 7 then 6 then 4 and then 5.
    - number of columns and rows depend on the data we will store
    - Stack will have a key and value pair.
        - Key is the variable and value is the thing stored inside it
    - **Note:** Most programming languages like java, js, c, c++, rust, etc store their primitive type variables with values in a key pair system in stack
- Heap
    - Those same languages stores the non primitive data types values in heap
    - Note that only values get stores inside heap and their variable name still resides inside stack.
	- in simple terms, variables which are stored inside stack in key value pair have heap address of those variables pointed in heap.  
    ![[image 1.png]]

I think the reason is because stack are made to store and allot a limited data such as primitive datatypes but because non primitive datatypes are a combination of primitive and they don't have a definitive size. this makes it difficult to store them in stack. so a simple way to get out of this is store the variable name with their address in stack and the address will be pointing towards heap which is a much larger storage area to store data such as non primitive data types. 

the reason we get a jargon string when we try to directly print a non primitive like array is that it actually prints the address of values for that array in heap. And by particular methods we can use that address to retrieve values. By particular method i mean accessing singular values of array using square brackets and such other methods. 

( i think ): that stack are faster to access while getting data from heap takes a little more time. 



# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 