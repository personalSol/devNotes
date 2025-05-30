---
status: newBorn
related-links: 
created: 2025-05-22T14:55
updated: 2025-05-22T14:55
---
---

```cpp
#include <iostream>
using namespace std;

// Engine class
class Engine {
public:
    void start() {
        cout << "Engine started." << endl;
    }

    void stop() {
        cout << "Engine stopped." << endl;
    }
};

// Car class HAS-A Engine
class Car {
private:
    Engine engine; // Composition: Engine is part of Car

public:
    void startCar() {
        engine.start();
        cout << "Car is moving." << endl;
    }

    void stopCar() {
        engine.stop();
        cout << "Car has stopped." << endl;
    }
};

int main() {
    Car myCar;
    myCar.startCar();
    myCar.stopCar();

    return 0;
}
```

- here Car owns the engine object and it will be destroyed as soon as object of car gets destroyed
- 
