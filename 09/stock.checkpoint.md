# PSE 9 - Best time to sell Stock

## Given this problem prompt:

You are given an integer array `prices` where `prices[i]` is the price of a given stock on the ith day.

On each day, you may decide to buy and/or sell the stock. You can only hold at most one share of the stock at any time. However, you can buy it then immediately sell it on the same day.

Find and return the **maximum** profit you can achieve.

**Example 1:**

```
Input: prices = [7,1,5,3,6,4]
Output: 7
Explanation: Buy on day 2 (price = 1) and sell on day 3 (price = 5), profit = 5-1 = 4.
Then buy on day 4 (price = 3) and sell on day 5 (price = 6), profit = 6-3 = 3.
Total profit is 4 + 3 = 7.
```

**Example 2:**

```
Input: prices = [1,2,3,4,5]
Output: 4
Explanation: Buy on day 1 (price = 1) and sell on day 5 (price = 5), profit = 5-1 = 4.
Total profit is 4.
```

**Example 3:**

```
Input: prices = [7,6,4,3,1]
Output: 0
Explanation: There is no way to make a positive profit, so we never buy the stock to achieve the maximum profit of 0.
```

Sourced from:  [Leetcode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)

## Answer the following prompts:

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: c0163bb9-06be-4e25-bd6f-0a6dddf9232e
* title: List at least 5 questions whose answers would clarify the problem statement
* points: 1
* topics: pse

##### !question

List at least 5 questions whose answers would clarify the problem statement.

##### !end-question

##### !placeholder

Give five clarifying questions.

##### !end-placeholder

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, users can see after a failed attempt) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
##### !explanation

Some sample clarifying questions could be:

1.  Is there some pattern required for the student ids?
1.  What key-value pairs should the hashes contain?
1.  What should happen if the array of names is empty?
1.  Can id numbers be negative?
1.  Should ids be Integers or can they be floats?

##### !end-explanation

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 05075142-9e7e-43af-abd3-54333976d6db
* title: List 2 sets of example inputs and their expected output
* points: 1
* topics: pse

##### !question

List 2 sets of example inputs and their expected output.

##### !end-question

##### !placeholder

Two sets of input and their expected output.

##### !end-placeholder

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, users can see after a failed attempt) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 259281a9-fe53-477a-8c07-1291d103440f
* title: Two subproblems
* points: 1
* topics: pse

##### !question

Divide the project prompt into at least 2 different sub-problems.

##### !end-question

##### !placeholder

Two subproblems

##### !end-placeholder

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, users can see after a failed attempt) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
##### !explanation



##### !end-explanation

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: d4e1ccc6-1676-4413-b277-915de1d39012
* title: How to solve a subproblem
* points: 1
* topics: pse

##### !question

Pick one of those problems from #3 and write a numbered list explaining how to solve that problem without using full lines of code.

##### !end-question

##### !placeholder

Steps to solve a subproblem

##### !end-placeholder

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, users can see after a failed attempt) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
<!-- !explanation - !end-explanation (markdown, students can see after answering correctly) -->

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->


### !challenge

* type: code-snippet
* language: python3.6
* id: 7176204d-f1da-463c-8d46-af9229de96b2
* title: Buying Stock Coding Challenge
* points: 1
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
<<<<<<< HEAD:09/stock.checkpoint.md
def max_profit(arr):
=======
def knapsack(sum, arr):
    '''
    INPUT: Target sum and an array of numbers
    OUTPUT: Sum nearest to (or equal to) but not exceeding the target sum
    '''
>>>>>>> 234b9a62d5e42980f68001d098f39679fdf2345e:09/knapsack.checkpoint.md
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
    profit = 0
    for i in range(1, len(prices)):
        profit += max(prices[i]-prices[i-1], 0)
    return profit
```

##### !end-explanation

### !end-challenge


## Reminders

- Finish this assignment individually.
- If you'd like a full list of our tips, hints, and notes, please bring up the document "[About Problem Solving Exercises](../about-pses/about-pses.md )" in unit.
