---
status: newBorn
related-links: 
created: 2025-07-19T11:00
updated: 2025-07-19T11:00
---
---

- to find length of a number




```cpp
// ----------- length of numbers --------------
	// method 1
    int a;
    cout<<"enter the number: ";
    cin>>a;

    int digits = (int)(log10(a) + 1);

    cout<<"The number of digits in "<<a<<" is: "<<digits<<endl;

    // method 2
    int count = 0;

    while (a>0){
        count++;    
        a = a/10;
    }
    cout<<"number of digits will be: "<< count<<endl;

```

