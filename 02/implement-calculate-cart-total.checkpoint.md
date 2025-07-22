# Implement Calculate Cart Total

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: f998bb4d
* title: PSE
* points: 3
### !question

Imagine programming the logic for a grocery store's online shopping system. In our scenario, a user has a cart of items, and each item has a cost. 

Create a function named `calculate_total` that is responsible for summing the cost of the items in a user's cart.
* This function should take in a list of strings named `cart` as a parameter. 
* This function should return the total cost of all items in the list `cart`.

Refer to this table for the price of each item carried by the store.

| Item | Price |
| ---- | ----- |
| Apple | $0.75 |
| Beans | $2.00 |
| Cheese | $2.50 |
| Chicken | $4.00 |
| Flour | $1.75 |
| Onion | $0.50 |
| Orange | $0.85 |
| Lettuce | $1.25 |
| Milk | $3.00 |
| Tomato | $0.45 |

### Examples

| Input | Expected Output |
| ----- | --------------- |
| `["Cheese"]` | `2.5` |
| `["Chicken", "Flour", "Milk"]` | `8.75` |
| `["Tomato", "Orange", "Beans", "Apple"]` | `4.05` |```
| `[]` | `0.0` |

### !end-question
### !placeholder

```python
def calculate_total(cart):
    pass
```
### !end-placeholder
### !tests
```python
import unittest
from main import *

class TestChallenge(unittest.TestCase):
    def test_calculate_total_capitalized_items(self):
        items = ["Cheese", "Chicken"]
        expected = 6.5
        result = calculate_total(items)
        self.assertEqual(result, expected)

    def test_calculate_total_lowercase_item(self):
        items = ["apple"]
        expected = 0.75
        result = calculate_total(items)
        self.assertEqual(result, expected)

    def test_calculate_total_uppercased_item(self):
        items = ["LETTUCE"]
        expected = 1.25
        result = calculate_total(items)
        self.assertEqual(result, expected)

    def test_calculate_total_mixed_case_item(self):
        items = ["BeAnS"]
        expected = 2.0
        result = calculate_total(items)
        self.assertEqual(result, expected)

    def test_calculate_total_no_items(self):
        items = []
        expected = 0.0
        result = calculate_total(items)
        self.assertEqual(result, expected)

        self.assertEqual(calculate_total(["Lemon", "Onion"]), 0.5)
        self.assertEqual(calculate_total(["Orange", "Orange", "Orange"]), 2.55)
        all_items = ["Apple", "Beans", "Cheese", "Chicken", "Flour", 
                    "Onion", "Orange", "Lettuce", "Milk", "Tomato"]
        self.assertEqual(calculate_total(all_items), 17.05)

    def test_calculate_total_one_item_no_price(self):
        items = ["Lemon", "Onion"]
        expected = 0.5
        result = calculate_total(items)
        self.assertEqual(result, expected)

        self.assertEqual(calculate_total(["Orange", "Orange", "Orange"]), 2.55)
        all_items = ["Apple", "Beans", "Cheese", "Chicken", "Flour", 
                    "Onion", "Orange", "Lettuce", "Milk", "Tomato"]
        self.assertEqual(calculate_total(all_items), 17.05)

    def test_calculate_total_duplicate_items(self):
        items = ["Orange", "Orange", "Orange"]
        expected = 2.55
        result = calculate_total(items)
        self.assertEqual(result, expected)

        all_items = ["Apple", "Beans", "Cheese", "Chicken", "Flour", 
                    "Onion", "Orange", "Lettuce", "Milk", "Tomato"]
        self.assertEqual(calculate_total(all_items), 17.05)

    def test_calculate_total_one_of_each_item(self):
        items = ["Apple", "Beans", "Cheese", "Chicken", "Flour", 
                    "Onion", "Orange", "Lettuce", "Milk", "Tomato"]
        expected = 17.05
        result = calculate_total(items)
        self.assertEqual(result, expected)
```
### !end-tests
### !explanation

An example of a working implementation:

```python
def calculate_total(cart):
    total = 0.0

    for item in cart:
        item_lowercase = item.lower()
        if item_lowercase == "apple":
            total += 0.75
        elif item_lowercase == "beans":
            total += 2.0
        elif item_lowercase == "cheese":
            total += 2.5
        elif item_lowercase == "chicken":
            total += 4
        elif item_lowercase == "flour":
            total += 1.75
        elif item_lowercase == "onion":
            total += 0.5
        elif item_lowercase == "orange":
            total += 0.85
        elif item_lowercase == "lettuce":
            total += 1.25
        elif item_lowercase == "milk":
            total += 3.0
        elif item_lowercase == "tomato":
            total += 0.45

    return total
```

Another example of a working implementation:

```python
def calculate_total(cart):
    prices = {
        "apple": 0.75,  "beans": 2.0, "cheese": 2.5, "chicken": 4.0, 
        "flour": 1.75, "onion": 0.5, "orange": 0.85, "lettuce": 1.25, 
        "milk": 3.0, "tomato": 0.45
    }
    total = 0
    
    for item in cart:
        item_lowercase = item.lower()
        if item_lowercase in prices:
            total += prices[item_lowercase]

    return total
```

### !end-explanation
### !end-challenge