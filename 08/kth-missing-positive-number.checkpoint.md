# PSE 8 - Kth Missing Positive Number

## Given this problem prompt:

Given an array arr of positive integers sorted in a strictly increasing order, and an integer k.

Find the kth positive integer that is missing from this array.

**Example 1:**

```
Input: arr = [2,3,4,7,11], k = 5
Output: 9
Explanation: The missing positive integers are [1,5,6,8,9,10,12,13,...]. The 5th missing positive integer is 9.
```

**Example 2:**

```
Input: arr = [1,2,3,4], k = 2
Output: 6
Explanation: The missing positive integers are [5,6,7,...]. The 2nd missing positive integer is 6.
``` 

**Constraints:**

```
1 <= arr.length <= 1000
1 <= arr[i] <= 1000
1 <= k <= 1000
arr[i] < arr[j] for 1 <= i < j <= arr.length
```

Sourced from:  [Leetcode](https://leetcode.com/problems/kth-missing-positive-number/)

## Answer the following prompts:

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 97a009d4-4793-4492-a769-12b320514995
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
* id: 9f29742f-ed9b-4060-b766-c41976bebc51
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
* id: c09628e3-f62f-43a0-8341-cf56f4eda378
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
* id: 32396452-4c2f-4b4b-9ec1-9137729b1526
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

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: code-snippet
* language: python3.6
* id: 5a380194-96e2-4b87-9aa7-2fe407448e1f
* title: Coding Solution
* points: 3
* topics: python, pse, python-lists

##### !question

Implement `kth_missing_positive_number`.  Use these tests to guide your solution.

<details>
  <summary>Tests converted to Pytest</summary>

  ```python
    def test_kth_missing_positive_number_finds_num_before_entire_given_list(self):
        # Arrange
        list = [2,3,4,7,11]
        k = 1

        # Act
        answer = kth_missing_positive_number(list, k)

        # Assert
        assert 1 == answer

    def test_kth_missing_number_finds_num_near_end_of_list(self):
        # Arrange
        list = [2,3,4,7,11]
        k = 5

        # Act
        answer = kth_missing_positive_number(list, k)
        
        # Assert
        assert 9 == answer

    def test_kth_missing_positive_number_finds_num_after_entire_given_list(self):
        # Arrange
        list = [1,2,3,4]
        k = 2

        # Act
        answer = kth_missing_positive_number(list, k)
        
        # Assert
        assert 6 == answer

    def test_kth_missing_positive_number_2nd_number_before_list_starts(self):
        # Arrange
        list = [3,4,5,7,11]
        k = 2

        # Act
        answer = kth_missing_positive_number(list, k)
        
        assert 2 == answer
  ```

</details>

##### !end-question

##### !placeholder

```python
def kth_missing_positive_number(numbers, k):
    '''
    INPUT: List of numbers in increating order & a positive integer k
    OUTPUT: The kth missing number
    '''

    pass
```

##### !end-placeholder

##### !tests

```py
import unittest
from main import kth_missing_positive_number

class TestPython1(unittest.TestCase):

  def test_kth_missing_positive_number_finds_num_after_entire_given_list(self):

    # Arrange
    list = [1,2,3,4]
    k = 2

    # Act
    answer = kth_missing_positive_number(list, k)

    # Assert
    self.assertEqual(6, answer)

  def test_kth_missing_number_finds_num_near_end_of_list(self):

    # Arrange
    list = [2,3,4,7,11]
    k = 5

    # Act
    answer = kth_missing_positive_number(list, k)

    # Assert
    self.assertEqual(9, answer)

  def test_kth_missing_positive_number_finds_num_before_entire_given_list(self):

    # Arrange
    list = [2,3,4,7,11]
    k = 1

    # Act
    answer = kth_missing_positive_number(list, k)

    # Assert
    self.assertEqual(1, answer)
    
```

##### !end-tests

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, hidden, students click to view) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
<!-- !explanation - !end-explanation (markdown, students can see after answering correctly) -->

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

## Reminders

- Finish this assignment individually.
- If you'd like a full list of our tips, hints, and notes, please bring up the document "[About Problem Solving Exercises](../about-pses/about-pses.md )" in unit.
