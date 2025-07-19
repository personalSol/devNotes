---
status: newBorn
related-links: 
created: 2025-07-15T10:32
updated: 2025-07-19T11:00
---
---

![[cpp stl brief#Algorithms]]


- `_buildin_popcount()`: returns number of set bits like 7 in binary is 111 so it will give 3, 6 is 2, etc.
	- for long there is `_buildin_popcountll()`
- `next_permutation()`: 
	- gives all possibilites
	- must be sorted in ascending to get all results
	- not sure why it follows a pattern to give permutations
- `max_element()`: give address of max element
- `min_element()`: '' of min element
```cpp
#include<bits/stdc++.h>
using namespace std;

bool comp (pair<int, int> p1, pair<int, int> p2){
    if(p1.second < p2.second) return true;
    if(p1.second > p2.second) return false;

    // if both second term are equal
    if(p1.first > p2.first) return true;
    return false;
}

int main (){

    // creating variables
    array<pair<int, int>, 3> a1 = {{{1,2}, {2,1}, {5,2}}};
    pair<int, int> a2[] = {{1,2}, {2,1}, {5,2}};
    int a[] = {1,5,4};
    int n = 3;

    // ascending
    sort(a, a+n);

    // for any other way we can write comparators 
    // comparators are nothing but condition which sort checks the object it's about to sort with. if the comparator gives true for condition then it sorts otherwise not
    sort(a1.begin(), a1.end(), comp);
    sort(a2, a2+n, comp);

    // for ascending from index x to y only
    int x = 2;
    int y = 4; 
    sort(a+x, a+y); // to sort only a particular part of array

    sort(a, a+n, greater<int>()); // for descending

    for (auto it: a1){
        cout<<"First: "<<(it).first <<" Second: "<<(it).second<<endl;
    }
    // for (auto it: a2){
    //     cout<<"First: "<<(it).first <<" Second: "<<(it).second<<endl;
    // }


	// permutation
	do{
        cout<<s<<endl;
    } while(next_permutation(s.begin(), s.end()));

	int max = *max_element(a, a+n);
    int min = *min_element(a, a+n);

    cout<<"max: "<<max<<endl;
    cout<<"min: "<<min<<endl;

}
```

