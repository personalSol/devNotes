---
status: newBorn
related-links: []
created: 2025-04-12T15:41
updated: 2025-04-12T16:17
---
---


better code example: [[java instance variable, this and constructor#^6uag0r]]

```java
public class classes {  
    public static void main(String[] args){  
        car car1 = new car();  
        car1.color = "yellow";  
        System.out.printf("car's color is: %s", car1.color);  
    }  
}  
  
class car{  
    String color;  
    int speed;  
  
    void color(){  
        System.out.printf("My car's color is %s", color);  
    }  
}
```


# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 