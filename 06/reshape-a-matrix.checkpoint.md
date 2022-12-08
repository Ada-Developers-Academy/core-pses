# Implement Reshape the Matrix

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

### !challenge

* type: paragraph
* id: 976fd220-e3f3-41f4-adb2-908e30d1e363
* title: What is the time complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices

##### !question

What is the time complexity of your solution? Explain. Define your variable(s).

##### !end-question

##### !placeholder

Time Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge

### !challenge

* type: paragraph
* id: 7bb7f05e-257c-43ba-a811-8900cfd622e9
* title: What is the space complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices

##### !question

What is the space complexity of your solution? Explain. Define your variable(s).

##### !end-question

##### !placeholder

Space Complexity?

##### !end-placeholder

### !end-challenge
