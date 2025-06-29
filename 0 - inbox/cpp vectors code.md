---
status: newBorn
related-links: 
created: 2025-06-28T10:31
updated: 2025-06-28T10:55
---
---

```cpp
void explainVector() {
    // Create
    vector<int> vec1;
    vec1.push_back(1);        // Add 1
    vec1.push_back(3);        // Add 3
    vec1.emplace_back(2);     // Add 2 (faster)
    vec1.push_back(5);        // Add 5

    vector<pair<int, int>> vec2;
    vec2.push_back({1, 2});           // Add pair using push_back
    vec2.emplace_back(1, 2);          // Add pair using emplace_back

    vector<int> vec3(5, 100);         // Create with 5 elements of 100
    vector<int> vec4(5);              // Create with 5 default-initialized (0)

    vector<int> v1(5, 20);
    vector<int> v2(v1);               // Copy v1 into v2

    vector<int> v = {10, 20, 30, 40, 50}; // Direct initialization

    // Read
    cout << "Second element: " << *(v.begin() + 1) << endl;
    cout << "Fifth element: " << *(v.begin() + 4) << endl;

    cout << "First element: " << v[0] << endl;
    cout << "First element using at(): " << v.at(0) << endl;
    cout << "The front element of the vector: " << v.front() << endl;
    cout << "Last element: " << v.back() << endl;

    cout << "All elements using iterator: ";
    for (vector<int>::iterator it = v.begin(); it != v.end(); ++it) {
        cout << *it << " ";
    }
    cout << endl;

    cout << "All elements using auto: ";
    for (auto it = v.begin(); it != v.end(); ++it) {
        cout << *it << " ";
    }
    cout << endl;

    // Update
    v[2] = 99;  // Change third element to 99
    cout << "Updated third element: " << v[2] << endl;

    // Delete
    v.pop_back();  // Removes the last element

	// erase takes address
    v.erase(v.begin()+1);  // Removes the second element
    // v.erase[start address, end address) end is exlusive
    v.erase(v.begin(), v.begin() + 3) // removes from first till 3rd index

    cout << "After deletion: ";
    for (int x : v) {
        cout << x << " ";
    }
    cout << endl;


	v.insert
}
```

