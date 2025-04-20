---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-12T08:47
updated: 2025-04-20T11:07
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


### formated string:

syntax `System.out.printf()`

format flags list:

- `%d`: Integer type
- `%f`: float or double type
- `c`: character type
- `%s`: for string type without changes
- `%S`: for string type with upper case converted
- `%n` or `\n`: to bring cursor to new line


> we can also say how much `white spaces` we want by writing number in front of % before flag type. It starts filling from that position and go from right to left. for left to right we ue negative number


```java
class formatString{
	public static void main(String[] args){
		int x = 345;
		System.out.printf("%8d %n", x);
		
		int y = 3929
		System.out.printf("%-8d\n", x);
		
		int z = 2891;
		System.out.printf("%0.8d\t", z); //this one will do the same but instead of whitespace it will give us 0
		
		double p = 82793.38742899;
		System.out.printf("%.3f", p) // will only print till given value after roundoff
		//output: 82793.388 

		double p = 82793.38742899;
		System.out.printf("%8.3f", p) // before decimal for spaces, decimal is also included
		// here 8 is total space and .3 is wherr it round off from
		
		String str = "Sanskar";
		System.out.printf("%10s", str);
	}
}
```


### methods

- note method just returns a new string and doesn't modify the older one so we have to store it in new variable. 




# Reference
`related tags + notes + source + link(if any)`
 
- 