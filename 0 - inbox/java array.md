---
status: newBorn
related-links: []
created: 2025-04-12T10:05
updated: 2025-04-12T10:22
---
---

define: An array in Java is a data structure that stores a fixed-size sequential collection of elements of the same type.

- Why do we need arrays
	- We need arrays to store more than one value of same type of data in a single place. This will save us from the work of creating multiple variables and it will be easy to locate them as well.
- How we create arrays
    - Declaration
        - We can declare a array by:
        ```java
        int variableToMakeArray[] = new int[4];
        dataType arr[]; OR dataType[] arr; OR dataType []arr; // are are equivalent
        ```
        - While creating int variable, we added [] at the end to make compiler understand it’s a variable. And then we used new and tell that it will have a size of that dataytype(which is int here) 4.
        ```kotlin
        public class array {
            public static void main(String[] args){
                int[] arru = {4,5,9};
        
                System.out.println(arru[1]);
            }
        }
        ```
        
        - NOTE: in the main method, we are creating a string array with variable name args. We can also change the variable name there to a or anything.
        
    - Initialization or alter values
        - We can initialize values of an array only by mentioning one value of a index at a time if we didn’t initialize during declaration.
        
        ```java
        public class array {
            public static void main(String[] args){
                int arru[] = new int[4];
                // arru[] = {4,6,4,5} we can't initialize the values of array like this if we have declared it earlier.
                arru[0] = 4;
                arru[1] = 5;
        
                System.out.println(arru[1] + " " + arru[2] + "" + arru[4]);
            }
        }
        
        ```
        
    - Default values if value not given
        
        - If we declare a string to let’s say 4 and only give value of 0 and 1 index then the value of other 2 for that time will depend on the type of array. For:
	        - int - it’s 0.
	        - String - it’s null



# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 