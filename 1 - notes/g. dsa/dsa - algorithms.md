---
status: newBorn
related-links: 
created: 2025-07-19T11:00
updated: 2025-07-21T06:47
---
---

- to find length of a number
- to find divisors of a number
- [[Euclidean Algorithm]]

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
// ---------- to find divisors of a number -----------
	// method 1 - same but brute force and we can run the loop till n
	// method 2 - we only went till square root of number as after that the divisors start to repeat -- best explained by striver in his maths video
	// this is code to find if a number is prime
	bool state = true;
    for(int i = 2; i * i <= n; i++){
        if(n%i == 0){
            state = false;
            break;
        }
    }
    return state;
```

