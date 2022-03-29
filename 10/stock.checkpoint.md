# PSE 10 - Best time to sell Stock

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
Explanation: There is no way to make a positive profit, 
    so we never buy the stock to achieve the maximum
    profit of 0.
```

Sourced from:  [Leetcode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)

### !challenge

* type: code-snippet
* language: python3.6
* id: 7176204d-f1da-463c-8d46-af9229de96b2
* title: Buying Stock Coding Challenge
* points: 3
* topics: python, loops, lists

##### !question

Write a solution to the Buying Stock function below.  The following tests will evaluate your solution.

<!-- prettier-ignore -->
<details>
  <summary>Tests converted to Pytest</summary>

  ```python

    def test_profit_7_1_5_3_6_4(self):
        # Arrange
        arr = [7, 1, 5, 3, 6, 4]

        # Act
        answer = max_profit(arr)

        # Assert
        assert answer == 7

    def test_profit_1_2_3_4_5(self):
        # Arrange
        arr = [1, 2, 3, 4, 5]

        # Act
        answer = max_profit(arr)

        # Assert
        assert answer == 4

    def test_profit_7_6_4_3_1(self):
        # Arrange
        arr = [7, 6, 4, 3, 1]

        # Act
        answer = max_profit(arr)

        # Assert
        assert answer == 0
  ```
</details>

##### !end-question

##### !placeholder

```py
def max_profit(arr):
    pass
    

```

##### !end-placeholder

##### !tests

```py
import unittest
from main import max_profit

class TestPython1(unittest.TestCase):
    def test_profit_7_1_5_3_6_4(self):
        # Arrange
        arr = [7, 1, 5, 3, 6, 4]

        # Act
        answer = max_profit(arr)

        # Assert
        self.assertEqual(answer, 7)

    def test_profit_1_2_3_4_5(self):
        # Arrange
        arr = [1, 2, 3, 4, 5]

        # Act
        answer = max_profit(arr)

        # Assert
        self.assertEqual(answer, 4)

    def test_profit_7_6_4_3_1(self):
        # Arrange
        arr = [7, 6, 4, 3, 1]

        # Act
        answer = max_profit(arr)

        # Assert
        self.assertEqual(answer, 0)
```

##### !end-tests

##### !explanation

Our solution:

```python
def max_profit(prices):
    total_profit = 0
    for i in range(1, len(prices)):
        # if prices[i] - prices[i-1] is > 0, then we have a profit
        total_profit += max(prices[i]-prices[i-1], 0)
    return total_profit
```

##### !end-explanation

### !end-challenge

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->

### !challenge

* type: short-answer
* id: 9707003f-e842-446b-9c39-e90e62a9da85
* title: What is the time complexity of your solution?
* points: 0
* topics: Big-O, python, lists

##### !question

What is the time complexity of your answer?

##### !end-question

##### !placeholder

Time Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->

### !challenge

* type: short-answer
* id: db5f2381-7288-442c-835e-0972ae72973a
* title: What is the space complexity of your solution?
* points: 0
* topics: Big-O, python, lists

##### !question

What is the space complexity of your answer?

##### !end-question

##### !placeholder

Space Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

## Reminders

- Finish this assignment individually.
- If you'd like a full list of our tips, hints, and notes, please bring up the document "[About Problem Solving Exercises](../about-pses/about-pses.md )" in unit.
