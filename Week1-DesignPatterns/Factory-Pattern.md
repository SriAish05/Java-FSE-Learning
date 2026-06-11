# Factory Design Pattern

## What is Factory Pattern?

Factory Pattern is a Creational Design Pattern.

It creates objects without exposing object creation logic to the user.

Instead of:

```java
new UpiPayment();
```

We ask the Factory:

```java
PaymentFactory.createPayment("UPI");
```

The Factory decides which object to create.

---

## Real Life Example

Imagine ordering coffee.

You tell the cashier:

"I want a Cappuccino."

You do NOT:

- Roast beans
- Grind coffee
- Steam milk

The coffee machine creates the coffee.

The coffee machine acts like a Factory.

---

## Problem Without Factory

```java
if(type.equals("UPI"))
{
    payment = new UpiPayment();
}
else if(type.equals("CARD"))
{
    payment = new CardPayment();
}
else if(type.equals("NETBANKING"))
{
    payment = new NetBankingPayment();
}
```

Every time a new payment method is added,
you modify existing code.

Bad design.

---

## Solution Using Factory

Step 1

Create Interface

```java
interface Payment {
    void pay();
}
```

---

Step 2

Implement Classes

```java
class UpiPayment implements Payment {

    public void pay() {
        System.out.println("UPI Payment");
    }
}
```

```java
class CardPayment implements Payment {

    public void pay() {
        System.out.println("Card Payment");
    }
}
```

---

Step 3

Create Factory

```java
class PaymentFactory {

    public static Payment createPayment(String type) {

        if(type.equals("UPI")) {
            return new UpiPayment();
        }

        if(type.equals("CARD")) {
            return new CardPayment();
        }

        return null;
    }
}
```

---

Step 4

Use Factory

```java
Payment payment =
    PaymentFactory.createPayment("UPI");

payment.pay();
```

Output:

UPI Payment

---

## Advantages

- Loose coupling
- Cleaner code
- Easier maintenance
- Easier extension

---

## Disadvantages

- Extra classes
- Slightly more complex

---

## Interview Question

Q: Factory vs Singleton?

Singleton:
Only ONE object exists.

Factory:
Creates objects.

Singleton controls NUMBER of objects.

Factory controls CREATION of objects.

---

## Real World Usage

- Spring Framework
- JDBC Drivers
- Notification Systems
- Payment Gateways

---

## Key Takeaway

User asks for object.

Factory creates object.

User does NOT know how object is created.
