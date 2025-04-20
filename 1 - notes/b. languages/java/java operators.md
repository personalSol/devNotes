---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-12T09:39
updated: 2025-04-12T15:38
---
---

### ARITHMETIC OPERATORS
- +, - , / , 
- *For both the operants to give answer in higher data type like float, etc. One of them must be of higher datatype. If not then we can covert it into a higher one using .tofloat() function.
- Modulus Operator (%) — Remainder operator • Example - 13 % 2 = 1


### RELATIONAL/COMPARISON OPERATORS

- Greater Than ( > )
- Less Than ( < )
- Greater Than Equal To ( ≥ )
- Less Than Equal To ( ≤ )
- Double Equal( == ) used to check if LHS is equal to RHS, checks if both reference variables are poinitng at the same object or not.
- Not Equal ( ! = ) gives true if LHS isn’t equal to RHS


### INCREMENT & DECREMENT OPERATORS

- Pre increment: ++i & - - i ( first increases the value then use it )
- Post increment: i++ & i - - ( first use the value the increase it )


    ```kotlin
    fun main() {
    var i = 10
    println( i++ + ++i) 
    ```


### LOGICAL OPERATORS


##### && (AND)

- AND returns True only if both conditions are True.
- Doesn’t execute code after it get’s false resulting in short circuiting.

##### || (OR)

- OR returns True if at least one condition is True.
- Doesn’t execute code after it gets one true and returns true sometimes causing 
- short circuiting. Example below

##### ! (NOT)

- Give the opposite of what is entered


### ASSIGNMENT OPERATOR

- Use the assignment operator (`"="`) to assign a value to a variable either during declaration of the variable or updating the variable.
- `+=`
- `-+`


### BITWISE OPERATOR ( we can skip )

- &
	- - It works on binary numbers so when we compare 2&3. It sees it like 2 (10 in binary ) & 3 (11 in binary ) and compare them on bit level. It’s same as and and will return 1 only if all the cases are 1. so it will compare 0 ( first digit of 2 ) and 1 ( first digit of 3 ) and will return 0 because all were not 1. Then it will compare 1 and 1 and return 1.
	- Note: after doing the work in bitwise and getting result, it returns the result in normal decimal form.

- !
	- It’s also exactly same as OR operator and work on operants binary form in bit levels. Like comparing ones digit of one operand with ones digit of another operand.



# Reference
`related tags + notes + source + link(if any)`
 

- 