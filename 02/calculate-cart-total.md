# Calculate Cart Total

## Problem Statement

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
| `["Orange", "Apple", "Tomato", "Orange"]` | `2.9` |
| `[]` | `0.0` |

## Prompts

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 87058b56-6678-4ef9-b1e0-c3ebddeb4bf9
* title: Ask Clarifying Questions
* topics: pse
##### !question

List three or more questions whose answers would clarify the problem statement. For each question, provide an answer which includes the effect your decision would have on how you would approach the problem.

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Previous PSEs

##### !end-hint
##### !explanation 

Example clarifying questions:

1. How should the function handle special characters?
1. Should the function be case in sensitive?
1. How should the function handle invalid input like numbers?
 
##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 6aceed45-c06a-498a-9f20-2db592be3469
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `calculate_total` for the nominal and edge cases you identified in the first step.

*Note: Click the **Run Tests** button to save your tests for instructor feedback. No real tests are actually run again your unit tests.*
##### !end-question

##### !placeholder

```py
# example input 1:
# expected output 1:

# example input 2:
# expected output 2:

def test_nominal_case():
    # ^rename with meaningful test name
    # and complete test implementation below
    pass
    # arrange

    # act

    # assert

def test_edge_case():
    # ^rename with meaningful test name
    # and complete test implementation below
    pass
    
    # arrange
    
    # act
    
    # assert
```

##### !end-placeholder

##### !tests

```py
import unittest

class TestPython1(unittest.TestCase):
  def test_always_pass(self):
    self.assertEqual(1,1)
```

##### !end-tests
##### !explanation 

Example tests:

```python
# example input 1: cart = ["Cheese", "Chicken"]
# expected output 1: calculate_total(cart) = 6.5

# example input 2: cart = ["beans", "MILK"]
# expected output 2: calculate_total(cart) = 5.0

# example input 3: cart = ["Lemon", "Onion", "Onion"]
# expected output 3: calculate_total(cart) = 1.0

def test_correct_total_for_all_items():
    # nominal test case

    # Arrange
    cart = ["Cheese", "Chicken"]

    # Act
    result = calculate_total(cart)

    # Assert
    assert result == 6.5

def test_case_insensitive_gives_correct_total():
    # nominal test case

    # Arrange
    cart = ["beans", "MILK"]

    # Act
    result = calculate_total(cart)

    # Assert
    assert result == 5.0

def test_invalid_items_not_added_to_total():
    # edge test case
    
    # Arrange
    cart = ["Lemon", "Onion", "Onion"]

    # Act
    result = calculate_total(cart)

    # Assert
    assert result == 1.0

```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->


<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
### !challenge
* type: paragraph
* id: 852cbbe5-22f0-4c14-921b-a33a1e10535c
* title: Create Logical Steps
* topics: pse

##### !question

Without writing code, describe how you would implement `calculate_total` in enough detail that someone else could write the code. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps: 

1. Create a dictionary `prices` with key-value pairs for each available item and its corresponding price.
2. Initialize a variable named `total` to `0.0`
3. Loop through the items in the list `cart`
    - Check if the current item is in the `prices` dictionary using a function like `.lower` to compare case-insensitively.
    - If the current item is in `prices`, add the value of the item to the variable `total`
4. Return `total`

### !end-explanation

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->



