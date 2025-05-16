---
status: newBorn
related-links:
  - "[[Core-Concepts-MOC]]"
  - "[[time complexity]]"
created: 2025-05-09T19:52
updated: 2025-05-16T00:18
---
---

### questions

```cpp
// 1: tell the exact time complexity of this code

#include<iostream>
using namespace std;

int main(){
    int n;
    cin>> n;
    for(int i = 0; i<n; i++){
        for(int j = 0; j<i; j++){
            cout<<"Hello"<<endl;
        }
    }
    return 0;
}


```


### answers

```markdown
// 1: it's : (n^2/2) + n/2
- with sum to n formula

and normally it will be n^2
```


# Reference
`related tags + notes + source + link(if any)`
 

- 