# Knapsack

## Given this problem prompt:

Given an array of integers and a target sum, determine the sum nearest to but not exceeding the target that can be created. To create the sum, use any element of your array zero or more times.

For example, if `arr = [2, 3, 4]` and your target sum is 10, you might select `[2, 2, 2, 2, 2]`, `[2, 2, 3, 3]`, `[3, 3, 4]` or `[2, 4, 4]`. In this case, you can arrive at exactly the target.

**Sample Input**

k = 12
arr = [1, 6, 9]

**Sample Output**

12

**Sample Input**

k = 11
arr = [2, 4, 6]

**Sample Output**

10


Sourced from:  [HackerRank](https://www.hackerrank.com/challenges/unbounded-knapsack/problem)

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
* title: Knapsack Coding Challenge
* points: 1
* topics: python, loops, lists

##### !question

Write a solution to the knapsack function below.  The following tests will evaluate your solution.

<!-- prettier-ignore -->
<details>
  <summary>Tests converted to Pytest</summary>

  ```python

    def test_sum_23_arr_5_4_4_4_8(self):
        # Arrange
        sum = 23
        arr = [5, 4, 4, 4, 8]

        # Act
        answer = knapsack(sum, arr)

        # Assert
        assert answer == 23

    def test_sum_zero_arr_empty(self):
        # Arrange
        sum = 0
        arr = []

        # Act
        answer = knapsack(sum, arr)

        # Assert
        assert answer == 0

    def test_sum_zero_arr_one_two_three(self):
        # Arrange
        sum = 0
        arr = [1, 2, 3]

        # Act
        answer = knapsack(sum, arr)

        # Assert
        assert answer == 0

    def test_sum_tweleve_arr_one_six_nine(self):
        # Arrange
        sum = 12
        arr = [1, 6, 9]

        # Act
        answer = knapsack(sum, arr)

        # Assert
        assert answer == 12

    def test_sum_eleven_arr_two_four_six(self):
        # Arrange
        sum = 11
        arr = [2, 4, 6]

        # Act
        answer = knapsack(sum, arr)

        # Assert
        assert answer == 10

    def test_sum_three_arr_three_four_eight(self):
        # Arrange
        sum = 9
        arr = [3, 4, 4, 4, 8]

        # Act
        answer = knapsack(sum, arr)

        # Assert
        assert answer == 9
  ```
</details>

##### !end-question

##### !placeholder

```py
def knapsack(sum, arr):
    '''
    INPUT: Target sum and an array of numbers
    OUTPUT: Sum nearest to (or equal to) but not exceeding the target sum
    '''
    pass
    

```

##### !end-placeholder

##### !tests

```py
import unittest
from main import knapsack

class TestPython1(unittest.TestCase):
    def test_sum_23_arr_5_4_4_4_8(self):
        # Arrange
        sum = 23
        arr = [5, 4, 4, 4, 8]

        # Act
        answer = knapsack(sum, arr)

        # Assert
        self.assertEqual(answer, 23)

    def test_sum_zero_arr_empty(self):
        # Arrange
        sum = 0
        arr = []

        # Act
        answer = knapsack(sum, arr)

        # Assert
        self.assertEqual(answer, 0)

    def test_sum_zero_arr_one_two_three(self):
        # Arrange
        sum = 0
        arr = [1, 2, 3]

        # Act
        answer = knapsack(sum, arr)

        # Assert
        self.assertEqual(answer, 0)

    def test_sum_tweleve_arr_one_six_nine(self):
        # Arrange
        sum = 12
        arr = [1, 6, 9]

        # Act
        answer = knapsack(sum, arr)

        # Assert
        self.assertEqual(answer, 12)

    def test_sum_eleven_arr_two_four_six(self):
        # Arrange
        sum = 11
        arr = [2, 4, 6]

        # Act
        answer = knapsack(sum, arr)

        # Assert
        self.assertEqual(answer, 10)

    def test_sum_three_arr_three_four_eight(self):
        # Arrange
        sum = 9
        arr = [3, 4, 4, 4, 8]

        # Act
        answer = knapsack(sum, arr)

        # Assert
        self.assertEqual(answer, 9)
```

##### !end-tests

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, hidden, students click to view) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
##### !explanation

Our solution:

```python
def knapsack(sum = 0, arr = []):
    if len(arr) == 0 or sum == 0:
        return 0
    
    if sum < min(arr):
        return 0
    
    for element in arr:
        if sum % element == 0:
            return sum
        
    # A list of all booleans
    # True if the index is in arr
    # False otherwise
    sums_in_arr = [False] * (sum + 1)
    max_found_sum = 0
    
    for i in range(1, sum + 1):
        for val in arr:
            if i - val == 0 or i - val > 0 and sums_in_arr[i - val]:
                sums_in_arr[i] = True
                max_found_sum = i
                

    return max_found_sum
```

##### !end-explanation

### !end-challenge


## Reminders

- Finish this assignment individually.
- If you'd like a full list of our tips, hints, and notes, please bring up the document "[About Problem Solving Exercises](../about-pses/about-pses.md )" in unit.
