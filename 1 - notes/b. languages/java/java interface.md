---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-14T07:40
updated: 2025-04-20T11:07
---
---

- very similar to abstract classes
- classes are blueprint for objects
	- means we create objects with referene to class
- interface is a blueprint for class
	- means seeing interface we make classes
- Limitations:
	- all the fields are always public static final by default
- **Why Use** Interfaces?
	- To achieve **abstraction**
	- To allow **multiple inheritance** in Java
	- To make code **flexible and loosely coupled**

| Feature             | Description                                                                           |
| ------------------- | ------------------------------------------------------------------------------------- |
| Methods             | Are **abstract** by default (no body) – unless marked `default` or `static`           |
| Fields              | Are always `public static final` (constants)                                          |
| Multiple interfaces | A class can implement **many interfaces** (this allows multiple inheritance of types) |
| Interface ≠ Class   | You can’t create objects from an interface directly                                   |


```java 
// Basic Structure

interface Animal {
    void makeSound();   // No body
}

// This says: “Any class that is an `Animal` must have a `makeSound()` method.”

// Implementing

class Dog implements Animal {
    public void makeSound() {
        System.out.println("Bark");
    }
}

// Now `Dog` is promising to follow the `Animal` rules. It **must** define `makeSound()`.
```


#### Static methods in interfaces:


- Used for utility operations that are RELATED to the interface but don't need instance state
- Cannot be overridden by implementing classes
- Called directly on the interface (not through instance)

> in simple terms, jo methods sabme classes mai sare rahenge unko define krdo. and jinko haar class ko hisab se different rakhna hai unko bas declare krdo like `validatePayment`

```java
interface PaymentValidator {
    boolean validatePayment(Payment payment);

    // Static utility method - helper functions related to validation
    static boolean isValidCreditCard(String cardNumber) {
        // Simple length check; ideally you'd implement Luhn's algorithm
        return cardNumber != null && cardNumber.length() == 16;
    }

    static boolean isValidAmount(double amount) {
        return amount > 0 && amount < 1_000_000;
    }
}

class PayPalValidator implements PaymentValidator {
    @Override
    public boolean validatePayment(Payment payment) {
        // First use static utility methods
        if (!PaymentValidator.isValidCreditCard(payment.getCardNumber()) ||
            !PaymentValidator.isValidAmount(payment.getAmount())) {
            return false;
        }

        // Then do PayPal-specific validation (placeholder)
        return true;
    }
}

// Dummy Payment class for completeness
class Payment {
    private String cardNumber;
    private double amount;

    public Payment(String cardNumber, double amount) {
        this.cardNumber = cardNumber;
        this.amount = amount;
    }

    public String getCardNumber() {
        return cardNumber;
    }

    public double getAmount() {
        return amount;
    }
}
```

#### default methods in interface

- Provide optional functionality to implementing classes
- Can be overridden if needed
- Can use other interface methods (abstract or default)
- Called through instance

```java
import java.util.List;

interface PaymentProcessor {
    void processPayment(Payment payment);

    // Default method using the abstract method
    default void processPayments(List<Payment> payments) {
        for (Payment payment : payments) {
            processPayment(payment);
        }
    }

    // Default method with common implementation
    default void validateAndProcess(Payment payment) {
        if (payment.getAmount() <= 0) {
            throw new IllegalArgumentException("Invalid amount");
        }
        processPayment(payment);
    }
}

class StripeProcessor implements PaymentProcessor {
    @Override
    public void processPayment(Payment payment) {
        // Stripe-specific implementation
        System.out.println("Processing payment with Stripe: $" + payment.getAmount());
    }

    // Optionally override validateAndProcess() if needed
    // @Override
    // public void validateAndProcess(Payment payment) {
    //     // Custom Stripe-specific validation
    //     PaymentProcessor.super.validateAndProcess(payment);
    // }
}

// Dummy Payment class for testing
class Payment {
    private String cardNumber;
    private double amount;

    public Payment(String cardNumber, double amount) {
        this.cardNumber = cardNumber;
        this.amount = amount;
    }

    public String getCardNumber() {
        return cardNumber;
    }

    public double getAmount() {
        return amount;
    }
}
```
	
# Reference
`related tags + notes + source + link(if any)`

- 