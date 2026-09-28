# SANKATMOCHAN Cafe Management System

## 1. Project Overview

**SANKATMOCHAN Cafe Management System** is a simple Python-based, console-oriented cafe ordering application.

The program displays a predefined cafe menu with item prices, accepts the customer's first order, checks whether the selected item is available, optionally accepts a second item, calculates the total amount, and displays the final payable amount.

The current version is intentionally simple and uses basic Python programming concepts such as dictionaries, variables, user input, conditional statements, membership checking, arithmetic operations, and formatted strings.

> **Important:** This README describes the code exactly as it is currently provided. It does not claim database storage, GUI functionality, payment processing, quantity management, automated testing, or unlimited item selection because those features are not present in the uploaded implementation.

---

## 2. Problem Statement

In a small cafe, taking customer orders and calculating the total price manually can require repeated effort and may lead to calculation mistakes.

The purpose of this project is to create a basic computerized cafe ordering system that displays the available menu, accepts customer choices, checks item availability, and automatically calculates the amount payable for the selected items.

---

## 3. Objectives

The objectives of this project are:

- To create a simple digital cafe ordering system.
- To display available food and beverage items with their prices.
- To accept customer input through the console.
- To check whether an entered item is available in the menu.
- To add the price of valid items to the order total.
- To allow the customer to add one additional item.
- To calculate the final order amount automatically.
- To display clear confirmation and unavailable-item messages.
- To apply basic Python concepts to a practical real-world problem.

---

## 4. Functional Requirements

The current system provides the following major functional areas.

### 4.1 Menu Display

The application displays the cafe name and the available menu before taking the order.

The current menu is:

| Menu Item | Price (Rs.) |
|---|---:|
| Veg Burger | 80 |
| Farmhouse pizza | 130 |
| Garlic Bread | 95 |
| Sandwich | 80 |
| Red sauce pasta | 85 |
| White sauce pasta | 100 |
| Paneer buteer masala | 180 |
| Paneer lababdar | 195 |
| Kadhai Paneer | 150 |
| Shahi Paneer | 160 |
| Masala tea | 25 |
| Filter coffee | 45 |
| Cold coffee | 60 |

The menu is stored in a Python dictionary in the current implementation.

### 4.2 Order Input and Item Validation

The program asks the customer:

```text
Enter the name of item you want to order =
```

The entered item is checked against the menu.

If the item is available:

- Its price is added to `order_total`.
- A confirmation message is displayed.

If the item is not available:

- The program displays an unavailable-item message.
- The item's price is not added to the total.

### 4.3 Second Item Selection

After processing the first item, the program asks:

```text
Do you want to add another item? (Yes/No)
```

If the customer enters `Yes`, the program accepts a second item and performs the same availability check.

The current version supports **a maximum of two item selections in one run**.

### 4.4 Bill Calculation and Final Output

The program starts with:

```python
order_total = 0
```

The prices of valid selected items are added to this value.

At the end, the program displays:

```text
The total amount of items to pay is ...
```

It then displays:

```text
Thank You
Please visit again
JAI BAJRANG BALI
```

---

## 5. Input and Output Structure

### Inputs

The program accepts:

1. The name of the first menu item.
2. A `Yes`/`No` response asking whether another item should be added.
3. The name of the second menu item if `Yes` is selected.

### Outputs

The program produces:

1. Cafe welcome message.
2. Menu and prices.
3. Item-added confirmation for valid items.
4. Unavailable-item message for invalid items.
5. Final order total.
6. Thank-you and closing messages.

---

## 6. System Workflow

```text
                    START
                      |
                      v
          Display Welcome Message
                      |
                      v
                Display Menu
                      |
                      v
          Initialize order_total = 0
                      |
                      v
             Enter First Item
                      |
                      v
            Is item in the menu?
                 /                         Yes           No
                |             |
                v             v
       Add price to total   Display item
                |            unavailable
                |             |
                +------->-----+
                      |
                      v
          Ask: Add another item?
                 /                      Yes        No
                |          |
                v          |
         Enter Second Item |
                |          |
                v          |
        Is second item     |
          in the menu?     |
          /        \       |
        Yes         No     |
         |           |     |
         v           v     |
    Add price      Display |
    to total       error    |
         |           |      |
         +-----+-----+------+
               |
               v
       Display Final Total
               |
               v
       Display Thank You
               |
               v
              END
```

---

## 7. Technologies and Tools Used

- **Programming Language:** Python
- **Interface:** Command-line / console
- **Data structure:** Python dictionary
- **Programming concepts:** Variables, dictionaries, `input()`, `print()`, `if-else`, membership checking using `in`, arithmetic addition, f-strings
- **External libraries:** None
- **Database:** None

---

## 8. Requirements

To run the current project, you need:

- Python 3.x
- A terminal or command prompt
- Any Python-compatible editor/IDE, such as VS Code, PyCharm, or IDLE

No external Python packages are required.

---

## 9. Installation and Setup

### Step 1: Install Python

Install Python 3.x on your computer.

Check that Python is installed:

```bash
python --version
```

If your system uses `python3`, use:

```bash
python3 --version
```

### Step 2: Get the Project

Download the project files or clone the GitHub repository:

```bash
git clone <YOUR-GITHUB-REPOSITORY-URL>
```

Then enter the project folder:

```bash
cd <PROJECT-FOLDER>
```

### Step 3: Run the Main Program

The recommended entry point for the current project is:

```bash
python main.py
```

or:

```bash
python3 main.py
```

---

## 10. Example Run

A valid example using two menu items is:

```text
Welcome to SANKATMOCHAN Cafe
Here is the menu for the day
Veg Burger: Rs80
Farmhouse pizza: Rs130
Garlic Bread: Rs95
Sandwich: Rs80
Red sauce pasta: Rs85
White sauce pasta: Rs100
Paneer buteer masala: Rs180
Paneer lababdar: Rs195
Kadhai Paneer: Rs150
Shahi Paneer: Rs160
Masala tea: Rs25
Filter coffee: Rs45
Cold coffee: Rs60

Enter the name of item you want to order =Veg Burger
Your item Veg Burger has been added to your order

Do you want to add another item? (Yes/No) Yes

Enter the name of second item =Farmhouse pizza
Item Farmhouse pizza is has been added to order

The total amount of items to pay is 210
Thank You
Please visit again
JAI BAJRANG BALI
```

The calculation in this example is:

```text
Veg Burger       = Rs. 80
Farmhouse pizza  = Rs. 130
----------------------------
Total            = Rs. 210
```

---

## 11. Testing Instructions

The current program can be tested manually from the terminal.

### Test Case 1 — One valid item

**Input:**

```text
Veg Burger
No
```

**Expected total:**

```text
80
```

### Test Case 2 — Two valid items

**Input:**

```text
Veg Burger
Yes
Farmhouse pizza
```

**Expected total:**

```text
210
```

### Test Case 3 — Invalid first item

**Input:**

```text
French Fries
No
```

**Expected behavior:**

The program should display:

```text
Ordered item French Fries is not available yet!
```

and the total should remain:

```text
0
```

### Test Case 4 — Valid first item and invalid second item

**Input:**

```text
Sandwich
Yes
French Fries
```

**Expected total:**

```text
80
```

The second item should not be added because it is not present in the menu.

### Test Case 5 — Valid first item and no second item

**Input:**

```text
Masala tea
No
```

**Expected total:**

```text
25
```

---

## 12. Error Handling

The current implementation performs basic item validation.

The important check is:

```python
if item_1 in menu:
```

and similarly for the second item.

This means an item is added to the total only when its name exists in the menu dictionary.

If an item is not found, the program displays an error/unavailable message.

### Current validation limitation

The comparison is case-sensitive.

For example:

```text
Veg Burger
```

matches the menu entry, while:

```text
veg burger
```

does not match the current dictionary key.

The current program also expects the response to the second-item question to be exactly:

```text
Yes
```

for the second item to be processed.

---

## 13. Non-Functional Requirements

The following non-functional requirements are relevant to the current project.

### 13.1 Usability

The system should provide simple prompts and readable output so that a user can understand the menu, enter an order, and view the final amount.

### 13.2 Performance

The application performs only a small number of dictionary lookups and arithmetic operations, so normal execution should complete immediately for the current menu size.

### 13.3 Reliability

The system should not add the price of an unavailable item to the order total. The current implementation performs a menu-membership check before adding an item's price.

### 13.4 Maintainability

The menu is stored in a dictionary, making it relatively straightforward to change item names or prices.

However, the current uploaded files contain substantially duplicated code. For a stronger final submission, the code should be refactored so that each file has a meaningful and separate responsibility.

### 13.5 Error Handling

The program handles the basic error case of an item not being present in the menu by displaying an unavailable-item message.

---

## 14. Current Project Files

The uploaded project contains:

```text
SANKATMOCHAN-Cafe/
│
├── main.py
├── menu.py
├── order.py
└── bill.py
```

### Current role of the files

Although the filenames suggest separate responsibilities, the uploaded versions currently contain substantial duplication.

- `main.py` contains the complete ordering flow.
- `menu.py` contains the menu data and menu display.
- `order.py` contains the menu plus the ordering flow.
- `bill.py` contains the menu, ordering flow, total calculation, and final output.

Therefore, these files should **not** currently be described as four independent software modules. Refactoring them into genuinely separate modules would improve the project's modularity and maintainability.

---

## 15. Suggested Modular Structure for Final Submission

The VITyarthi guidelines expect modular implementation and, for coding projects, a minimum of 5–10 meaningful modules/classes/files.

A possible improved structure is:

```text
SANKATMOCHAN-Cafe/
│
├── main.py
├── menu.py
├── order.py
├── bill.py
├── validation.py
├── test_menu.py
├── test_order.py
├── README.md
└── statement.md
```

These additional files should only be added when they contain actual functionality or tests. Creating empty files merely to increase the file count would not make the project genuinely modular.

---

## 16. System Architecture

The current logical architecture can be represented as:

```text
+------------------+
|     Customer     |
+--------+---------+
         |
         v
+------------------+
|   Menu Display   |
+--------+---------+
         |
         v
+------------------+
|  Order Input &   |
| Item Validation  |
+--------+---------+
         |
         v
+------------------+
|  Bill / Total    |
|    Calculation   |
+--------+---------+
         |
         v
+------------------+
| Final Output /   |
|   Thank You      |
+------------------+
```

---

## 17. Limitations

The current version has the following limitations:

- Only one first item and one optional second item can be selected.
- Item quantities are not supported.
- There is no persistent order history.
- There is no database.
- There is no graphical user interface.
- There is no online ordering.
- There is no payment processing.
- Taxes and discounts are not calculated.
- Inventory is not tracked.
- Customer accounts are not supported.
- Input matching is case-sensitive.
- The current uploaded files contain duplicated code.
- Automated unit tests are not included in the uploaded implementation.

---

## 18. Future Enhancements

The following features can be added in future versions:

1. Allow unlimited menu-item selections.
2. Add quantity selection for each item.
3. Create a proper cart/order list.
4. Add subtotal, tax, discount, and final bill calculations.
5. Generate a detailed receipt.
6. Add database storage.
7. Store and retrieve order history.
8. Add inventory management.
9. Improve input validation and case handling.
10. Add a graphical user interface.
11. Add automated unit tests.
12. Refactor the existing files into genuinely separate modules.
13. Add customer and staff functionality.
14. Add payment-related functionality in a later version if required.

---

## 19. VITyarthi Requirement Alignment

The VITyarthi project guidelines require:

- A meaningful problem and technical solution.
- At least three major functional modules.
- Clear input/output structure.
- A logical user workflow.
- At least four non-functional requirements.
- Appropriate technical implementation.
- Modular and clean implementation.
- Validation and error handling.
- Testing where applicable.
- Git/version control.
- `README.md` and `statement.md`.
- Design artefacts such as architecture and workflow diagrams.

The current project already demonstrates a basic menu, order-validation, and bill-calculation workflow.

However, the **current code should be improved before final submission** to fully satisfy the broader technical expectations, particularly meaningful modular separation, testing, and the required design artefacts.

---

## 20. References

- VITyarthi — Build Your Own Project: General Project Instructions & Submission Guidelines.
- Python 3 language concepts used in the project.

