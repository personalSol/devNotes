---
status: newBorn
related-links: 
created: 2025-07-14T18:49
updated: 2025-07-14T19:24
---
---

#### code for binary search, upper_bound, lower_bound

```cpp
#include<bits/stdc++.h>
using namespace std;


int main(){
    
    // array<int, 6> a = {10,11,12,13,14,15};
    // int n = a.size();

    int a[] = {10,15,20,25,30,35,40};
    int b[] = {40,35,30,25,20,15,10};
    int n = 7;
    int c[n];
    copy(b, b+n, c);
    sort(c, c+n);

    bool ind3 = binary_search(a, a+n, 40);
    int ind2 = upper_bound(a, a+n, 15) - a;
    int ind1 = lower_bound(a, a+n, 15) - a;
    bool ind4 = binary_search(c, c+n, 40);
    int ind5 = upper_bound(c, c+n, 15) - c; // will give 2
    int ind5_2 = upper_bound(c, c+n, 16) - c; // will give 2
    int ind6 = lower_bound(c, c+n, 15) - c;

    cout<<ind1<<endl;
    cout<<ind2<<endl;
    cout<<ind3<<endl;
    cout<<ind4<<endl;
    cout<<ind5<<endl;
    cout<<ind6<<endl;

}
```



