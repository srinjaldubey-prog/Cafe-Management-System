# SANKATMOCHAN Cafe Management System — Project Statement

## 1. Problem Statement

In a small cafe, customer orders and bill calculations may be handled manually. This can require repeated effort when checking menu availability and calculating the total price of selected items.

The **SANKATMOCHAN Cafe Management System** is a basic Python console application designed to provide a simple computerized cafe ordering process. The system displays the available menu and prices, accepts a customer's selected item, checks whether the item is available, optionally accepts one additional item, and calculates the total amount payable.

The project applies basic Python programming concepts to a practical cafe-ordering problem.

---

## 2. Scope of the Project

The scope of the current project is a basic command-line cafe ordering workflow.

The system currently covers:

- Displaying the SANKATMOCHAN Cafe menu.
- Storing menu items and prices in a Python dictionary.
- Accepting the first item selected by the customer.
- Checking whether the selected item is available.
- Adding the price of a valid item to the order total.
- Asking whether the customer wants another item.
- Accepting and validating a second item when the customer enters `Yes`.
- Calculating the total price of valid selected items.
- Displaying the final amount.
- Displaying a thank-you message after the order.

The current version does not include:

- Database storage.
- Customer login or accounts.
- Graphical user interface.
- Online ordering.
- Payment processing.
- Inventory management.
- Persistent order history.
- Item quantities.
- Tax or discount calculation.
- Automated unit testing.

---

## 3. Target Users

### 3.1 Cafe Customers

The primary users are customers who need to view the available menu, select food or beverage items, and see the amount payable.

### 3.2 Cafe Staff

Cafe staff can use the concept of the system as a basic computerized approach for checking item availability and calculating the price of a small order.

### 3.3 Students and Instructors

The project is also intended to demonstrate how basic Python programming concepts can be applied to a real-world problem.

---

## 4. High-Level Features

### 4.1 Menu Display

The system displays the cafe name and the available food and beverage items with their prices.

The current menu contains:

- Veg Burger — Rs. 80
- Farmhouse pizza — Rs. 130
- Garlic Bread — Rs. 95
- Sandwich — Rs. 80
- Red sauce pasta — Rs. 85
- White sauce pasta — Rs. 100
- Paneer buteer masala — Rs. 180
- Paneer lababdar — Rs. 195
- Kadhai Paneer — Rs. 150
- Shahi Paneer — Rs. 160
- Masala tea — Rs. 25
- Filter coffee — Rs. 45
- Cold coffee — Rs. 60

### 4.2 First Item Selection

The customer enters the name of the item they want to order.

The program checks whether the entered item exists in the menu.

### 4.3 Item Availability Validation

If the item is present in the menu:

- The item's price is added to the order total.
- The system displays a confirmation message.

If the item is not present:

- The system displays an unavailable-item message.
- The invalid item is not added to the total.

### 4.4 Second Item Selection

The system asks:

```text
Do you want to add another item? (Yes/No)
```

If the customer enters `Yes`, a second item is requested and checked against the menu.

The current implementation supports a maximum of two selected items in one program run.

### 4.5 Bill Calculation

The program uses:

```python
order_total = 0
```

Valid item prices are added to `order_total`.

The final amount is then displayed to the customer.

### 4.6 Final Output

After processing the order, the system displays:

```text
The total amount of items to pay is ...
Thank You
Please visit again
JAI BAJRANG BALI
```

---

## 5. Functional Modules

The current functionality can be described through three major functional areas:

### Module 1 — Menu Management and Display

Responsible for:

- Storing menu items and prices.
- Displaying the menu to the customer.

### Module 2 — Order Input and Validation

Responsible for:

- Taking customer input.
- Checking whether an item exists in the menu.
- Adding valid item prices to the order.

### Module 3 — Bill Calculation and Output

Responsible for:

- Maintaining the order total.
- Calculating the amount payable.
- Displaying the final result and closing message.

> These are **functional areas of the current application**, not claims that the four uploaded Python files are already four independent software modules. The current files contain substantial duplicated code and should be refactored for stronger modularity.

---

## 6. Non-Functional Requirements

### 6.1 Usability

The application should provide simple prompts and readable messages so that users can understand the ordering process without needing technical knowledge.

### 6.2 Performance

The system should respond quickly during normal operation because it performs only simple dictionary lookups, conditional checks, and arithmetic operations.

### 6.3 Reliability

Only menu items that pass the availability check should contribute their prices to the order total.

### 6.4 Maintainability

Menu information is stored in a dictionary, making it relatively easy to modify menu entries and prices.

The current implementation can be made more maintainable by separating menu, order, bill, and validation logic into genuinely independent modules.

### 6.5 Error Handling

The system handles the basic case where a customer enters an item that is not present in the menu by displaying an unavailable-item message.

---

## 7. Inputs

The system accepts the following inputs:

1. Name of the first item.
2. `Yes` or `No` response for adding another item.
3. Name of the second item when `Yes` is entered.

---

## 8. Outputs

The system produces:

1. Welcome message for SANKATMOCHAN Cafe.
2. Menu with prices.
3. Confirmation message for a valid selected item.
4. Unavailable-item message for an invalid item.
5. Total amount to be paid.
6. Thank-you and closing messages.

---

## 9. Basic Workflow

```text
START
  |
  v
Display Cafe Welcome Message
  |
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
             |
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
- Python dictionary
- Variables
- `input()` and `print()`
- Conditional statements
- Membership checking using `in`
- Arithmetic addition
- f-strings
- Command-line interface

No external Python libraries or database are used by the current implementation.

---

## 11. Current Project Files

The submitted project contains four Python files:

```text
main.py
menu.py
order.py
bill.py
```

The current uploaded versions contain substantial duplicated code.

For example, `main.py` contains the complete menu, order input, validation, total calculation, and final output. The other uploaded files also repeat significant portions of this same logic.

Therefore, the current project should be treated as a **basic working implementation**, while the file structure can be improved in the next development stage.

---

## 12. Current Limitations

The current implementation has several limitations:

- A maximum of two items can be selected in one run.
- Quantity selection is not available.
- There is no persistent order storage.
- There is no database.
- There is no GUI.
- There is no payment system.
- Taxes and discounts are not calculated.
- Inventory is not managed.
- There is no customer account system.
- Menu-item input is case-sensitive.
- Automated unit tests are not included.
- The source files contain duplicated code.

These limitations are consistent with the current beginner-level implementation.

---

## 13. Future Enhancements

Possible future improvements include:

1. Allowing customers to select more than two items.
2. Adding item quantities.
3. Creating a cart or order list.
4. Adding subtotal, tax, discount, and final amount calculations.
5. Generating a detailed receipt.
6. Adding a database for storing orders.
7. Adding order history.
8. Adding inventory management.
9. Adding stronger input validation.
10. Supporting case-insensitive menu searches.
11. Adding automated unit tests.
12. Refactoring the code into meaningful independent modules.
13. Creating a graphical user interface.
14. Adding customer/staff functionality.
15. Adding payment functionality if required in a future version.

---

## 14. Project Goal

The goal of the project is to demonstrate how a simple real-world cafe ordering problem can be converted into a Python-based software solution.

The project focuses on:

- Problem identification.
- Menu representation.
- User input.
- Validation.
- Conditional logic.
- Price calculation.
- User-friendly console output.

The project can serve as a foundation for developing a more complete cafe management system in future iterations.

