---
status: newBorn
related-links:
  - "[[Core-Concepts-MOC]]"
created: 2025-02-25T18:52
updated: 2025-05-25T10:40
---
---


**Algorithm**: Algorithm is step by step process of solving a problem
**Program**: Program is step by step process of solving a problem but using programming.

| points           | **Algorithm**                                                | **Program**                                        |
| ---------------- | ------------------------------------------------------------ | -------------------------------------------------- |
| Part of SDLC     | at design level                                              | implementation process                             |
| Knowledge        | domain knowledge is required                                 | programming knowledge is required                  |
| Language         | any lang ( can use pseudo code or english )                  | programming language                               |
| Hardware and OS  | not required                                                 | require                                            |
| After completion | called priori analysis. done using time and space complexity | posteriori testing is done in watch time and bytes |

##### Characteristics of algorithm
- input: it can have 0 or more input
- output: atleast 1 output
- definiteness: problem must be clear and solvable and solving algorithm must also have a clear meaning
	- you are only doing possible operations and not something magical like finding root of negative numbers
- finiteness: it should terminate at some point
- effectiveness: there mustn't be any unnecessary things in algorithm 

##### to analyze an algorithm
- time
- space
- Network: How much data is getting transfered over the network
- power
- cpu registers
main are top 2


this is just my speculation but the way we check O(`<anything>`) is that we check if there is any variable in the last in f(n) or S(n) and if there is then we take that variable and it's exponent. If there is no variable then we consider variable with power 0 and it will be 1. We ignore constants


### example of algorithm

- a task is given, add 0 to 1 lakh numbers
- there can be two ways/algorithms
	- adding each number from 0 to 1 lakh one by one
	- using n(n+1)/2 formula to get sum
- first will take a lot of time while second will not
- this is the difference in algorithms, we need to try to write an optimized algorithm with any way possible.



