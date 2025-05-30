---
status: newBorn
related-links: 
created: 2025-05-22T14:56
updated: 2025-05-22T15:29
---
---
method 1:
```cpp
#include <iostream>

#include <vector>

#include <algorithm>

using namespace std;

class Engine {
    public:
        void startEngine(){
            cout<<"Engine started"<<endl;
        }
        void stopEngine(){
            cout<<"Engine stopped"<<endl;
        }
};
  

class Car {
    public:
        Engine* engine;
    Car(){
        engine = new Engine();
    }
        void startCar(){
            engine->startEngine();
            cout<<"Car started"<<endl;
        }
};
  

int main() {

    Car myCar;
    myCar.startCar();
    myCar.engine->stopEngine();

    return 0;  // Clean exit

}
```

method 2:
```cpp
#include <iostream>
using namespace std;

class Engine {
public:
    Engine() {
        cout << "Engine: Constructor called." << endl;
    }

    void start() {
        cout << "Engine: Starting..." << endl;
    }

    void stop() {
        cout << "Engine: Stopping..." << endl;
    }

    ~Engine() {
        cout << "Engine: Destructor called." << endl;
    }
};

class Car {
private:
    Engine* engine;  // Aggregation: Car does not own the engine
    // here we have created a pointer named engine of Engine class that doesn't store anything

public:
    // Car takes an existing Engine object
    Car(Engine* eng) : engine(eng) {
        cout << "Car: Constructor called." << endl;
    }

    void drive() {
        engine->start();
        cout << "Car: Driving..." << endl;
    }

    void park() {
        engine->stop();
        cout << "Car: Parked." << endl;
    }

    ~Car() {
        cout << "Car: Destructor called." << endl;
    }
};

int main() {
    cout << "--- Program Start ---" << endl;

    Engine* myEngine = new Engine(); // Engine created outside of Car

    {
        Car myCar(myEngine);  // Aggregation: Car uses existing Engine
        myCar.drive();
        myCar.park();
    } // Car object destroyed here

    delete myEngine;  // Manually delete the engine (not owned by Car)

    cout << "--- Program End ---" << endl;
    return 0;
}
```

- here car class doesn't own engine object
- it's only storing a reference object of object pointer with `Engine* engine`
	- in this we are creating a pointer for `Engine` class with name engine using `*`
	- if we normally write `Engine engine` then it will create a new object
	- but in `Engine* engine` a new object gets created with new keyword ( `new Engine()`) which we are not giving
	- then we are using constructor to pass the object that we created in main to engine
- so this way car class doesn't own the engine object and engine object can exist without class too