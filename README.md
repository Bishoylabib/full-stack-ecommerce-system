# Full Stack E-Commerce System

A robust and extensible e-commerce system implemented in Java, designed to manage diverse product types, handle cart and checkout operations, integrate shipping logic, and demonstrate clean OOP design, maintainability, and testability.

---

## 🚀 Project Overview

This system supports:

- Expirable products (e.g., Cheese, Biscuits) and non-expirable products (e.g., TV, Mobile).  
- Shippable products (with weight) and non-shippable products (e.g., mobile scratch cards).  
- Customer cart operations with quantity validation.  
- Checkout process that includes:
  - Calculating subtotal, shipping fees, paid amount, and remaining customer balance.  
  - Handling errors such as empty carts, insufficient balance, out-of-stock, or expired products.  
  - Integrating a shipping service for shippable items via an interface-based contract.

The system emphasizes structured Java development, strong OOP principles, and a modular, maintainable architecture.

---

## 🏗️ Technical Approach

- **Language:** Java  
- **OOP Design:** Interfaces and class inheritance implement different product behaviors (`Expirable`, `Shippable`).  
- **Validation Layer:** Centralized input validation for stock, expiration, and customer balance.  
- **Extensibility:** Supports addition of new product types and business rules without modifying existing code.  
- **Console Output:** Provides formatted checkout receipts and shipment notices for clarity.

---

## 📦 Features

- Add products to cart with validation against stock and quantity.  
- Track product expiration and shippable items.  
- Graceful error handling with descriptive messages.  
- Shipping service processes shippable items through an interface-driven design.  
- Example usage scenarios included in code for testing and demonstration.

---

## 🧑‍💻 Example Usage

```java
Cheese cheese = new Cheese("Cheddar", 100, 200, LocalDate.of(2026, 1, 1), 400);
TV tv = new TV("Samsung TV", 5000, 1000, 1500);
ScratchCard scratchCard = new ScratchCard("Scratch Card", 50, 20);

Customer customer = new Customer("Bishoy", 10000);
Cart cart = new Cart();

cart.add(cheese, 2);
cart.add(tv, 1);
cart.add(scratchCard, 2);

CheckoutService.checkout(customer, cart);
```

---

## 🧑‍💻 Sample Console Output

```text
** Shipment notice **
2x Cheddar 400g
1x Samsung TV 1.5kg
Total package weight 2.3kg

** Checkout receipt **
2x Cheddar 200
1x Samsung TV 5000
2x Scratch Card 100
----------------------
Subtotal    5300
Shipping    30
Amount      5330
----------------------
Balance     4670
```

---

## 📝 Code Structure

- `models/` – Product classes (`Product`, `Cheese`, `TV`, `ScratchCard`)  
- `interfaces/` – Interfaces for `Shippable` and `Expirable` behaviors  
- `utils/` – `InputValidator` for centralized validation logic  
- `services/` – `ShippingService` and `CheckoutService`  
- `Cart.java` – Manages shopping cart operations  
- `Customer.java` – Represents customer accounts and balances  
- `Main.java` – Entry point with usage example

---

## 🧠 Design Decisions

- **Interface-driven product behavior**  
  Using `Shippable` and `Expirable` interfaces allows new product types to be added easily without modifying existing logic.

- **Centralized validation layer**  
  `InputValidator` ensures consistent checks for stock, quantity, expiration, and balance, reducing duplication and errors.

- **Extensible checkout process**  
  Checkout service is decoupled from product and shipping implementations, making it maintainable and testable.

- **Clear output and messaging**  
  Formatted console receipts and shipment notices improve transparency and usability.

---

## 🚀 Future Improvements

- Integrate a GUI or web frontend instead of console output  
- Persist products, carts, and customer data in a database  
- Add multi-currency support and discount handling  
- Implement automated unit and integration tests for all modules  
- Expand shipping logic to support multiple carriers and dynamic rates  
- Add scheduled expiration checks and notifications for expirable products

