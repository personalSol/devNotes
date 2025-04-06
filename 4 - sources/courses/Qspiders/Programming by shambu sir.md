---
created: 2025-03-20T12:37:57
status: 
source: 
updated: 2025-03-21T12:55
---
---

## recurssion


Recurssion: it's a programming technique where a method or function calls itself to solve a complex progam.

Recurssion is widely used to solve complex programs because with the help of recussion, program is solved in very simple manner. 


> every recurssion statement have two main things:
> - recurssion function caller
> - recurssion terminator ( mostly an if condition)


there are 3 ways to achieve recurssion:
1. when we call that function from inside function body ( aka by calling function from inside function body )
2. when we call the function in parameter of that function itself ( by calling function from method call as an argument )
3. by calling that function from it's return statement

##### a. by calling function from body

when a method is called from it's block then it starts it execution repeatedly. to control this execution, we have to provide base condition and terminating condition by using flow control statement to control the execution flow


each stack runs which have it's own value for variables. 

backtracking is when stack creation finally stops and then it starts running from the top/last block all the ramaining code of that function.

```java
public class recurssion{
    public static void main(String[] args) {
        test1(1);
        System.out.println("main finished");
    }
public static void test1(int n) {
        if (n<=3) {
            System.out.println(n);
            test1(n+1);
        } else{
            System.out.println("else block n is: " + n);
        }
        System.out.println("value of n is: " + n);
    }
}
```


recurssion by calling method/function as an argument
- we can call a function from function call which will repeatedly execute same function to achieve the recurssion. 

find the biggest number from given 5 numbers



---

Recurssion by calling method from return statement

- we can call a method from return statement which will call recurssion. we have to privide appropriate condition which should terminate the execution of recurssion once the result is found. 
# Reference
`related link(if any)`

