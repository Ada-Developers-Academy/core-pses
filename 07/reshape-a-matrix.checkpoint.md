# Reshape the Matrix

## Problem

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
 [5,6,7,8]]
```

**Explanation:**

The original matrix was 4 * 2. The new reshaped matrix is a 2 * 4 matrix, fill it row by row by using the previous list.

**Note:**

The height and width of the given matrix is in range [1, 100].
The given r and c are all positive.

Sourced from:  [Leetcode](https://leetcode.com/problems/reshape-the-matrix/)

## Prompts:

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 931b7218-6fc5-4fd5-9b6c-7945856a6041
* title: Ask Clarifying Questions
* points: 3
* topics: pse

##### !question

List five or more questions whose answers would clarify the problem statement

##### !end-question

##### !placeholder

Give five clarifying questions.

##### !end-placeholder

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, users can see after a failed attempt) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
##### !explanation

Here are some example clarifying questions:

1.  Is there some pattern required for the student ids?
1.  What key-value pairs should the hashes contain?
1.  What should happen if the array of names is empty?
1.  Can id numbers be negative?
1.  Should ids be Integers or can they be floats?

##### !end-explanation

##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint

##### !rubric

- The answer is wrong if there aren't at least five questions
- They should ask about what to return if the string is not a palindrome (the problem statement intentionally does not state to return `False`)
- They should ask about some set of special characters
##### !end-rubric

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 34970927-cb7b-459f-b6be-673474b0b8a0
* title: Consider Example Inputs and Outputs
* points: 3
* topics: pse

##### !question

List two or more sets of example arguments and the expected return value for these arguments

##### !end-question

##### !placeholder

Two sets of input and their expected output.

##### !end-placeholder

##### !hint

Consider unexpected test cases and edge-case situations.

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint

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
* title: Break Down the Problem into Sub-Problems
* points: 3
* topics: pse

##### !question

Divide the project prompt into two or more different sub-problems

##### !end-question

##### !placeholder

Two subproblems

##### !end-placeholder

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, users can see after a failed attempt) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
##### !hint

Consider:

- Any requirements around checking inputs
- Any requirements around calculations

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint
##### !explanation
Here are some example sub-problems:

1. How do we decide whether its possible to reshape the matrix?
1. How do we create the new lists that the values will go into?
1. How do we move the appropriate values into the new lists?

##### !end-explanation
##### !rubric

- The answer is wrong if there aren't at least two sub-problems listed
- The answer is wrong if any of the sub-problems aren't relevant to the original problem

##### !end-rubric

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 1ece1eb2-0d72-4068-9ca6-f77ca49d73c5
* title: Create Logical Steps
* points: 3
* topics: pse

##### !question

Pick one of those problems from #3 and write a numbered list explaining how to solve that problem without using full lines of code

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

Implement `reshape_matrix`.

Use these tests to guide your solution. These tests may make different assumptions about the problem than you did! Do not alter your assumptions above, and take these assumptions for this challenge.

```py
def test_convert_2_2_to_1_4():
    matrix = [[1,2],[3,4]]
    r = 1
    c = 4

    reshaped_matrix = reshape_matrix(matrix, r, c)

    assert reshaped_matrix == [[1,2,3,4]]

def test_cannot_reshape():
    matrix = [[1,2],[3,4]]
    r = 2
    c = 4

    reshaped_matrix = reshape_matrix(matrix, r, c)

    assert reshaped_matrix == [[1,2],[3,4]]

def test_convert_2_2_to_1_4():
    matrix = [[1,2],[3,4],[5,6],[7,8]]
    r = 2
    c = 4

    reshaped_matrix = reshape_matrix(matrix, r, c)

    assert reshaped_matrix == [[1,2,3,4],[5,6,7,8]]
```

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
from main import reshape_matrix
class TestPython1(unittest.TestCase):
    def test_example_one(self):
        # Arrange
        matrix = [[1,2],[3,4]]
        r = 1
        c = 4
        # Act
        answer = reshape_matrix(matrix, r, c)
        # Assert
        self.assertEqual([[1,2,3,4]], answer)
    def test_example_2(self):
        # Arrange
        matrix = [[1,2],[3,4]]
        r = 2
        c = 4
        # Act
        answer = reshape_matrix(matrix, r, c)
        # Assert
        self.assertEqual([[1,2],[3,4]], answer) 
    def test_example_3(self):
        # Arrange
        matrix = [[1,2],[3,4],[5,6],[7,8]]
        r = 2
        c = 4
        # Act
        answer = reshape_matrix(matrix, r, c)
        # Assert
        self.assertEqual([[1,2,3,4],[5,6,7,8]], answer) 
```

##### !end-tests

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, hidden, students click to view) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
<!-- !explanation - !end-explanation (markdown, students can see after answering correctly) -->

#### !explanation
An example of a working implementation:

```py
def reshape_matrix(matrix, r, c):
    '''
    INPUT: Two dimensional list, and number of rows and columns of reshaped matrix
    OUTPUT: Reshaped matrix
    '''
    rows = len(matrix)
    columns = len(matrix[0])

    if rows*columns != r*c:
        return matrix

    reshaped_matrix = []
    for i in range(r):
        new_row = []
        for j in range(i*columns, (i+1)*columns):
            new_row+=matrix[j]
        reshaped_matrix.append(new_row)
        
    return reshaped_matrix
```
#### !end-explanation

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

## Reminders

- Finish this assignment individually.
- If you'd like a full list of our tips, hints, and notes, please bring up the document "[About Problem Solving Exercises](../about-pses/about-pses.md )" in unit.
