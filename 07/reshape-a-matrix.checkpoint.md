# PSE 7 - Reshape the Matrix

## Given this problem prompt:

In MATLAB, there is a very useful function called 'reshape', which can reshape a matrix into a new one with different size but keep its original data.

You're given a matrix represented by a two-dimensional array, and two positive integers **r** and **c** representing the number of rows and number of columns of the wanted reshaped matrix, respectively.

The reshaped matrix need to be filled with all the elements of the original matrix in the same row-traversing order as they were.

If the 'reshape' operation with given parameters is possible and legal, output the new reshaped matrix; Otherwise, output the original matrix.

**Example 1:**
```
Input: 
nums = 
[[1,2],
 [3,4]]
r = 1, c = 4

Output: 
[[1,2,3,4]]
```

**Explanation:**

The row-traversing of nums is [1,2,3,4]. The new reshaped matrix is a 1 * 4 matrix, fill it row by row by using the previous list.


**Example 2:**

```
Input: 
nums = 
[[1,2],
 [3,4]]
r = 2, c = 4

Output: 
[[1,2],
 [3,4]]
```

**Explanation:**

There is no way to reshape a 2 * 2 matrix to a 2 * 4 matrix. So output the original matrix.

**Example 3:**

```
Input: 
nums = 
[[1,2],
 [3,4],
 [5,6],
 [7,8]]
r = 2, c = 4

Output: 
[[1,2,3,4],
 [3,4,5,6]]
```

**Explanation:**

The original matrix was 4 * 2. The new reshaped matrix is a 2 * 4 matrix, fill it row by row by using the previous list.

**Note:**

The height and width of the given matrix is in range [1, 100].
The given r and c are all positive.

Sourced from:  [Leetcode](https://leetcode.com/problems/reshape-the-matrix/)

## Answer the following prompts:

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 931b7218-6fc5-4fd5-9b6c-7945856a6041
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
* id: 34970927-cb7b-459f-b6be-673474b0b8a0
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
* id: af200ac9-1c79-4fb4-b7be-b70c7721778b
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
* id: 1ece1eb2-0d72-4068-9ca6-f77ca49d73c5
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
* id: de8a690a-da2d-46b0-821c-00ed6968d7d5
* title: Coding Solution
* points: 3
* topics: python, pse, python-lists

##### !question

Write the code to solve the problem here.  You can use the tests to guide your solution.

##### !end-question

##### !placeholder

```python
def reshape_matrix(matrix, r, c):
    '''
    INPUT: Two dimensional list, and number of rows and columns of reshaped matrix
    OUTPUT: Reshaped matrix
    '''
    pass
```

##### !end-placeholder

##### !tests

```py
import unittest
import main as p
import numpy as np
class TestPython1(unittest.TestCase):
    def test_example_one(self):
        # Arrange
        matrix = [[1,2],[3,4]]
        r = 1
        c = 4
        # Act
        answer = p.reshape_matrix(matrix, r, c)
        # Assert
        self.assertEqual([[1,2,3,4]], answer)
    def test_example_2(self):
        # Arrange
        matrix = [[1,2],[3,4]]
        r = 2
        c = 4
        # Act
        answer = p.reshape_matrix(matrix, r, c)
        # Assert
        self.assertEqual([[1,2],[3,4]], answer) 
    def test_example_3(self):
        # Arrange
        matrix = [[1,2],[3,4],[5,6],[7,8]]
        r = 2
        c = 4
        # Act
        answer = p.reshape_matrix(matrix, r, c)
        # Assert
        self.assertEqual([[1,2,3,4],[5,6,7,8]], answer) 
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
