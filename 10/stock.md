# Best time to sell Stock

## Given this problem prompt:

You are given an integer array `prices` where `prices[i]` is the price of a given stock on the ith day.

On each day, you may decide to buy and/or sell the stock. You can only hold at most one share of the stock at any time. However, you can buy it then immediately sell it on the same day.

Find and return the **maximum** profit you can achieve.

**Example 1:**

```
Input: prices = [7,1,5,3,6,4]
Output: 7
Explanation: Buy on day 2 (price = 1) and sell on day 3
   (price = 5), profit = 5-1 = 4.
Then buy on day 4 (price = 3) and sell on day 5 
   (price = 6), profit = 6-3 = 3.
Total profit is 4 + 3 = 7.
```

**Example 2:**

```
Input: prices = [1,2,3,4,5]
Output: 4
Explanation: Buy on day 1 (price = 1) and sell on 
    day 5 (price = 5), profit = 5-1 = 4.
Total profit is 4.
```

**Example 3:**

```
Input: prices = [7,6,4,3,1]
Output: 0
Explanation: There is no way to make a positive profit, so
    we never buy the stock to achieve the maximum 
    profit of 0.
```

Sourced from:  [Leetcode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)


## Prompts

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: cd479b36-b9c5-40d8-8c8c-1befa3de6174
* title: Ask Clarifying Questions
* topics: pse
##### !question

List three or more questions whose answers would clarify the problem statement. For each question, provide an answer which includes the effect your decision would have on how you would approach the problem.

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint

##### !explanation

Here are some example clarifying questions:

- How does the function handle an empty list?
- Can numbers in the input lists be negative?
- Can the list be only ascending or descending numbers?

##### !end-explanation

##### !rubric

- The answer is wrong if there aren't at least 3 questions

##### !end-rubric

### !end-challenge
<!-- prettier-ignore-end -->


<!-- Question 2 -->
<!-- prettier-ignore-start -->

### !challenge
* type: code-snippet
* language: python3.6
* id: 0f72eb75-455c-48ed-9868-337a32e2c86d
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `max_profit` for the nominal and edge cases you identified in the first step.

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
def test_two_nominal_lists():
    # nominal test case
    # Arrange
    stocks = [7,1,5,3,6,4]

    # Act
    result = max_profit(stocks)

    # Assert
    assert result == 7

def test_empty_lists():
    # edge test case
    # Arrange
    stocks = []

    # Act
    result = max_profit(stocks)

    # Assert
    assert result == 0

    # Assert
    assert result == []

def test_list_1_all_before_list_2():
    # alternative test case
    # Arrange
    stocks = [7,6,5,4,3,1]

    # Act
    result = max_profit(stocks)

    # Assert
    assert result == 0

```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 17165b99-d816-42fa-a6da-d6e25265bb92
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `max_profit` in enough detail that someone else could write the code. 

* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps for an O(n) solution:

1. Check for valid input
1. set `total` to `0`
1. set `index` to `1`
1. `while index < len(stocks)`
    *  if `stocks[index - 1] > stocks[index]`
        * `total = total + stocks[index - 1] - stocks[index]` 
    * `index = index + 1`
1. `return total`

### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->
