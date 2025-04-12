---
status: newBorn
related-links: []
created: 2025-04-12T08:47
updated: 2025-04-12T09:13
---
---


- strings are stored inside a separate specially area called string pool which is inside heap.
- whenever we create a new string, it first checks if that same value exists in string pooll already, if yes then it simply points towards that if not then it stores the new value there and store it's address in stack.
- to create a new object even with the same string value, we use new keyword.

```java
String a = new String("hello");
String b = new String("hello");

System.out.println(a == b);       // false – different objects
System.out.println(a.equals(b));  // true – same content
```

^8kflsq

- strings are immutable
	- so even if two objects are pointing at the same value
	- if one changes it's value then it doesn't effect the other
	- because of immutability, it will just create a new object and assign the value to it instead of changing the older one
```java
public static void main(String[] args) {  
    String str1 = "HELLO";  
    String str2 = "HELLO";  
  
    System.out.println(str1);  
    System.out.println(str2);  
  
    str1 = "HELLO WORLD";  
    System.out.println(str1);  
    System.out.println(str2);  
}
```


### methods

- note method just returns a new string and doesn't modify the older one so we have to store it in new variable. 




# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 