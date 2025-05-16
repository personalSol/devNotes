---
status: newBorn
related-links: []
created: 2025-05-12T17:27
updated: 2025-05-12T17:32
---
---

- dynamic array
- emplace vs push
	- emplace back is faster than push back
	- have to include `{}` in pair for push but in emplace we don't have to

```cpp
void explainVector() {

    vector<int> v;

    v.push_back(1);
    v.emplace_back(2);

    vector<pair<int, int>> vec;

    v.push_back({1, 2});
    v.emplace_back(1, 2);

    vector<int> v(5, 100);

    vector<int> v(5);

    vector<int> v1(5, 20);
    vector<int> v2(v1);

    vector<int>::iterator it = v.begin();

    it++;
    cout << *(it) << " ";
}

```


# Reference
`related tags + notes + source + link(if any)`
 

- 