---
status: newBorn
related-links: []
created: 2025-05-09T11:27
updated: 2025-05-19T09:56
---
---

### call by value

- a copy of the original gets passed
- basically the value gets passed and not the variable itself

```cpp
#include<iostream>
using namespace std;
  
int doSomething(string s1){
    s1[0] = 'W';
    cout<<s1<<endl;
}

int main(){
    string str = "HELLO WORLD!";
    doSomething(str);
    cout<<str;

    return 0;
}
```


### call by reference

- we pass the reference of the original variable
- changes in the reference effects the real variable
- the only difference is we used `&` which allows `s1` to store reference instead of value
- unlike primitive datatypes, non primitive datatypes like arrays always pass by reference ^fqmpwk

```cpp
#include<iostream>
using namespace std;
  
int doSomething(string &s1){
    s1[0] = 'W';
    cout<<s1<<endl;
}

int main(){
    string str = "HELLO WORLD!";
    doSomething(str);
    cout<<str;

    return 0;
}
```


### in detail

here we can see
- s1 and str have same address

```cpp
#include<iostream>
using namespace std;

int doSomething(string &s1){
    s1[0] = 'W';
    cout<<&s1<<endl;
    cout<<s1<<endl;
}

int main(){
    string str = "HELLO WORLD!";
    doSomething(str);
    cout<<&str<<endl;
    cout<<str;
    return 0;
}
```


# Reference
`related tags + notes + source + link(if any)`
 

- 