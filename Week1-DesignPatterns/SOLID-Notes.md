# SOLID Principles

## S - Single Responsibility Principle
A class should have only one reason to change.

Bad:
Employee class manages employee data and generates reports.

Good:
Employee class stores employee data.
ReportGenerator class generates reports.

## O - Open Closed Principle
Software should be open for extension but closed for modification.

Example:
Add new payment methods without changing existing code.

## L - Liskov Substitution Principle
Child classes should be replaceable for parent classes.

Example:
A Bike and Car should both work correctly if they extend Vehicle.

## I - Interface Segregation Principle
Clients should not depend on methods they don't use.

Bad:
Worker interface with work() and eat()

Robot implements eat() unnecessarily.

## D - Dependency Inversion Principle
Depend on abstractions, not concrete classes.

Example:
PaymentService depends on Payment interface, not UpiPayment directly.