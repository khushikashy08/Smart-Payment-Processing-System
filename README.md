# Smart Payment Processing System (OOP in Python)

## 📌 Problem Statement

Design and implement a Smart Payment Processing System using Object-Oriented Programming concepts in Python. The system should support multiple payment methods such as Credit Card, UPI, PayPal, and Digital Wallet. Each method must follow a common interface but apply different business rules to compute the final payable amount.

---

## 💡 Approach

The system is designed using core OOP principles:

### 1. Abstraction

* An abstract base class `Payment` is created using the `abc` module.
* It defines a common method `pay()` (abstract) and `generate_receipt()` (concrete).

### 2. Inheritance

* All payment types (`CreditCardPayment`, `UPIPayment`, `PayPalPayment`, `WalletPayment`) inherit from the `Payment` class.

### 3. Polymorphism

* A function `process_payment(payment, amount)` is used to process payments.
* It works differently depending on the object passed (runtime polymorphism).

### 4. Business Logic Implementation

* **Credit Card**: 2% gateway fee + 18% GST on fee.
* **UPI**: ₹50 cashback if amount > ₹1000.
* **PayPal**: 3% international fee + ₹20 conversion fee.
* **Wallet**: Deducts from balance, fails if insufficient funds.

---

## 🧪 Sample Output

Processing Credit Card Payment...
Gateway Fee (2%) : ₹40.00
GST on Fee (18%) : ₹7.20

----- PAYMENT RECEIPT -----
User Name       : Khushi
Original Amount : ₹2000.00
Final Amount    : ₹2047.20
--------------------------

Processing UPI Payment...
Cashback Applied : ₹50.00

----- PAYMENT RECEIPT -----
User Name       : Khushi
Original Amount : ₹1200.00
Final Amount    : ₹1150.00
--------------------------

Processing PayPal Payment...
International Fee (3%) : ₹15.00
Conversion Fee         : ₹20.00

----- PAYMENT RECEIPT -----
User Name       : Khushi
Original Amount : ₹500.00
Final Amount    : ₹535.00
-------------------------

Processing Wallet Payment...
Available Balance : ₹1500.00
Transaction Successful ✅
Remaining Balance : ₹500.00

----- PAYMENT RECEIPT -----
User Name       : Khushi
Original Amount : ₹1000.00
Final Amount    : ₹1000.00
--------------------------

Processing Wallet Payment...
Available Balance : ₹500.00
Transaction Failed: Insufficient Balance ❌

----- PAYMENT RECEIPT -----
User Name       : Khushi
Original Amount : ₹600.00
Final Amount    : ₹0.00
-----------------------

---

## ✅ Conclusion

This project demonstrates how OOP concepts like abstraction, inheritance, and polymorphism can be used to build a real-world payment processing system in Python. The design is modular and easily extendable for adding new payment methods in the future.

---
