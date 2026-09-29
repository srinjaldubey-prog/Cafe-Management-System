# SANKATMOCHAN Cafe Management System. Project Statement

## 1. Problem Statement

In a cafe ordering and billing are often done by hand. This can take time. Lead to mistakes when checking if an item is in stock or calculating the total cost.

The **SANKATMOCHAN Cafe Management System** is a Python console program made to help manage cafe orders. The system shows the menu with prices lets customers pick items checks if those items are available allows for one item if needed and calculates the final amount.

This project uses Python ideas to solve a real-life problem in a small cafe setting.

---

## 2. Scope of the Project

The project focuses on a command-line process for ordering at the cafe.

It includes:

- Showing the SANKATMOCHAN Cafe menu.

- Storing food and drink names and their prices in a dictionary.

- Taking the item selected by the customer.

- Checking if that item is in the menu.

- Adding the price of an item to the order total.

- Asking if the customer wants another item.

- Accepting and checking an item only if the customer says "Yes”.

- Calculating the total for all items.

- Displaying the bill.

- Giving a thank-you message after the order is complete.

What it does not include:

- Saving data in a database.

- Login systems or user accounts.

- A interface.

- Online ordering.

- Payment methods like credit cards or digital wallets.

- Tracking inventory levels.

- Keeping orders for later reference.

- Allowing than one unit of an item.

- Applying taxes or discounts.

- Automated testing of the code.

---

## 3. Target Users

### 3.1 Cafe Customers

The main users are customers who want to see what’s on the menu choose something to eat or drink and know how they need to pay.

### 3.2 Cafe Staff

Staff members can use this system as an idea for managing orders electronically. It helps them check if an item is available and calculate the price quickly.

### 3.3 Students and Instructors

The project is also meant for teaching purposes. It shows how simple Python skills can be used to build a working solution for problems.

---

## 4. High-Level Features

### 4.1 Menu Display

The system shows the name of the cafe. Lists all the food and drinks along with their prices.

Current menu items:

- Veg Burger. Rs. 80

- Farmhouse pizza. Rs. 130

- Garlic Bread. Rs. 95

- Sandwich. Rs. 80

- Sauce pasta. Rs. 85

- White sauce pasta. Rs. 100

- Paneer butter masala. Rs. 180

- Paneer lababdar. Rs. 195

- Kadhai Paneer. Rs. 150

- Shahi Paneer. Rs. 160

- Masala tea. Rs. 25

- Filter coffee. Rs. 45

- Coffee. Rs. 60

### 4.2 First Item Selection

Customers type in the name of the item they want to buy.

The program looks up that item in the menu.

### 4.3 Item Availability Validation

If the item exists:

- Its price is added to the total.

- A confirmation message appears.

If the item is not found:

- An error message says the item is unavailable.

- That item doesn't count toward the bill.

### 4.4 Second Item Selection

After the item the system asks:

```text

Do you want to add another item? (Yes/No)

```

If the customer types `Yes` they can enter an item.

The system checks if it’s in the menu.

Two items can be ordered per session.

### 4.5 Bill Calculation

The program starts with:

```python

order_total = 0

```

Each items price is added to `order_total`.

At the end the final total is shown.

### 4.6 Final Output

Once everything is processed the system prints:

```text

The total amount of items to pay is...

Thank You

Please visit again

JAI BAJRANG BALI

```

---

## 5. Functional Modules

The app works through three parts:

### Module 1. Menu Management and Display

This part handles:

- Storing the list of menu items and their prices.

- Printing the menu clearly for customers.

### Module 2. Order Input and Validation

This module manages:

- Getting what the customer wants.

- Making sure the item exists.

- Adding the price to the total.

### Module 3. Bill Calculation and Output

This part takes care of:

- Keeping track of the running total.

- Computing the price.

- Showing the result. Ending messages.

> These are areas, not actual modules. The four files uploaded. `Main.py` `menu.py` `order.py` `bill.py`. Do not act like components yet. They contain overlapping code. Need refactoring to work better together.

---

## 6. Non-Functional Requirements

### 6.1 Usability

The app should have instructions and easy-to-read messages so anyone, even without tech experience can follow the steps.

### 6.2 Performance

The system responds fast because it only runs checks: looking up values comparing strings and adding numbers.

### 6.3 Reliability

Only items that are actually in the menu should affect the total.

Invalid entries are. Won’t cause errors.

### 6.4 Maintainability

The menu is stored as a dictionary changing prices or adding new items is straightforward.

However the current setup mixes functions across files. Better structure would make future updates easier.

### 6.5 Error Handling

The app deals with missing items by showing a message like "Item not available." That’s the kind of error handling included right now.

---

## 7. Inputs

The system receives these inputs from the user:

1. Name of the item.

2. Response to whether to add another item (`Yes` or `No`).

3. Name of the item if the answer to the previous question was `Yes`.

---

## 8. Outputs

The system gives the following outputs:

1. A welcome message for the SANKATMOCHAN Cafe.

2. The full menu with prices.

3. A confirmation when an item is successfully added.

4. An error message for items.

5. The total amount to pay.

6. A thank-you message and closing lines.

---

## 9. Basic Workflow

```text

START

|

v

Display Cafe Welcome Message

v

Display Menu

|

v

Initialize order_total

|

v

Enter First Item

|

v

Check Item Availability

|

+------ Available ------> Add Price

|

+------ Not Available --> Display Error

|

v

Ask Whether Another Item Is Required

|

+------ No -------------> Display Total

|

+------ Yes

v

Enter Second Item

|

v

Check Availability

/                Valid       Invalid

|            |

v            v

Add Price     Display Error

|            |

+-----+------+

|

v

Display Total

|

v

Display Thank You

|

v

END

```

---

## 10. Technology Used

- Python 3

- Dictionary to store menu items and prices

- Variables for storing data

- `input()` to get user text

- `print()` to show results

- statements like `if`

- Using `in` to check if an item exists

- Simple math for addition

- f-strings for formatting output

- Command-line interface only

No external libraries or databases are used.

---

## 11. Current Project Files

There are four Python files in the project:

```text

main.py

menu.py

order.py

bill.py

```

But the current versions repeat the logic in each file. For example `main.py` has all the code for menus, input, validation and billing. The other files also include parts of that same code.

So the project is currently a **working prototype**, not a well-structured application. Future development should split responsibilities properly into independent modules.

---

## 12. Current Limitations

The implementation has some limits:

- up to two items can be chosen in one session.

- Users cannot select multiple units of the same item.

- Orders are not saved anywhere.

- There is no database.

- No interface.

- No way to process payments.

- Taxes and discounts are not applied.

- Inventory tracking is missing.

- No user accounts.

- Menu input must match case-sensitive.

- No automated tests.

- Code duplication across files.

These limitations match the level of a beginner learning Python.

---

## 13. Future Enhancements

Possible improvements include:

1. Allow customers to pick than two items.

2. Let users choose quantities for each item.

3. Create a shopping cart feature.

4. Add subtotal, tax, discount and final amounts.

5. Print a receipt.

6. Store orders in a database.

7. Keep a history of orders.

8. Track. Update inventory.

9. Improve input validation.

10. Make search, for menu items ignore case.

11. Adding automated unit tests to make sure the code works correctly and stays reliable.

12. Refactoring the code into independent modules so it’s easier to read maintain and extend.

13. Creating a graphical user interface to improve user interaction and make the system more accessible.

14. Adding customer and staff functionality to support user roles and their needs.

15. Adding payment functionality if needed in a version to complete the ordering process.

---

## 14. Project Goal

The goal of the project is to show how a simple real-world cafe ordering problem can be turned into a working software solution using Python.

The project focuses on:

- Identifying the problem clearly.

- Representing the menu in a way.

- Getting input from the user.

- Validating the input to avoid errors.

- Using logic to make decisions.

- Calculating prices accurately.

- Providing user-friendly output in the console.

This project can act as a starting point, for building a complete cafe management system in the future.

