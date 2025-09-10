# Implement Reshape the Matrix

## Problem

In MATLAB, a programming platform for numeric computing, there is a very useful function called 'reshape', which can reshape a matrix into a new one with different size while keeping its original data.

You're given a matrix represented by a two-dimensional array, and two positive integers **rows** and **columns** representing the number of rows and number of columns of the intended reshaped matrix, respectively.

The reshaped matrix needs to be filled with all the elements of the original matrix in the same row-traversing order as they were.
- If the 'reshape' operation with given parameters is possible, output the new reshaped matrix.
- Otherwise, raise a `ValueError` (You may choose the specific error message)

**Example 1:**

```
Input: 
nums = 
[[1,2],
 [3,4]]
rows = 1, columns = 4

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
rows = 2, columns = 4

Output: 
ValueError
```

**Explanation:**

There is no way to reshape a 2 * 2 matrix to a 2 * 4 matrix, so we raise a ValueError.

**Example 3:**

```
Input: 
nums = 
[[1,2],
 [3,4],
 [5,6],
 [7,8]]
rows = 2, columns = 4

Output: 
[[1,2,3,4],
 [5,6,7,8]]
```

**Explanation:**

The original matrix was 4 * 2. The new reshaped matrix is a 2 * 4 matrix, fill it row by row by using the previous list.

**Note:**

It can be assumed that all given `rows` and `columns` are positive numbers.

Sourced from:  [Leetcode](https://leetcode.com/problems/reshape-the-matrix/)

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: de8a690a-da2d-46b0-821c-00ed6968d7d5
* title: Coding Solution
* points: 3
* topics: python, pse, python-lists
##### !question

Implement `reshape_matrix`.

Use these tests to guide your solution. These tests may make different assumptions about the problem than you did! Do not alter your previous submission, and use these assumptions for this challenge.

```py
def test_1_by_4_can_reshape_into_4_by_1():
    # Arrange
    matrix = [[1], [2], [3], [4]]
    rows = 1
    columns = 4

    # Act
    result = reshape_matrix(matrix, rows, columns)

    # Assert
    assert result == [[1, 2, 3, 4]]

def test_2_by_2_can_reshape_into_1_by_4():
    # Arrange
    matrix = [[1,2],[3,4]]
    rows = 1
    columns = 4

    # Act
    result = reshape_matrix(matrix, rows, columns)

    # Assert
    assert result == [[1,2,3,4]]

def test_4_by_2_can_reshape_into_2_by_4():
    # Arrange
    matrix = [[1,2],[3,4],[5,6],[7,8]]
    rows = 2
    columns = 4

    # Act
    result = reshape_matrix(matrix, rows, columns)

    # Assert
    assert result == [[1,2,3,4],[5,6,7,8]]

def test_3_by_3_can_reshape_into_9_by_1():
    # Arrange
    matrix = [[7, 2, 1], [4,3,5], [6,9,8]]
    rows = 9
    columns = 1 

    # Act
    result = reshape_matrix(matrix, rows, columns)

    # Assert
    self.assertEqual([[7],[2],[1],[4],[3],[5],[6],[9],[8]], result)

def test_2_by_2_raises_error_reshaping_to_4_by_2():
    # Arrange
    matrix = [[1,2], [3,4]]
    rows = 4
    columns = 2

    # Act & Assert
    with pytest.raises(ValueError)
        result = reshape_matrix(matrix, rows, columns)
```

##### !end-question
##### !placeholder

```python
def reshape_matrix(matrix, rows, columns):
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
    def test_1_by_4_can_reshape_into_4_by_1(self):
        # Arrange
        matrix = [[1], [2], [3], [4]]
        rows = 1
        columns = 4

        # Act
        result = reshape_matrix(matrix, rows, columns)

        # Assert
        assert result == [[1, 2, 3, 4]]

    def test_2_by_2_can_reshape_into_1_by_4(self):
        # Arrange
        matrix = [[1,2],[3,4]]
        rows = 1
        columns = 4

        # Act
        result = reshape_matrix(matrix, rows, columns)

        # Assert
        assert result == [[1,2,3,4]]

    def test_4_by_2_can_reshape_into_2_by_4(self):
        # Arrange
        matrix = [[1,2],[3,4],[5,6],[7,8]]
        rows = 2
        columns = 4

        # Act
        result = reshape_matrix(matrix, rows, columns)

        # Assert
        assert result == [[1,2,3,4],[5,6,7,8]]

    def test_3_by_3_can_reshape_into_9_by_1(self):
        # Arrange
        matrix = [[7, 2, 1], [4,3,5], [6,9,8]]
        rows = 9
        columns = 1 

        # Act
        result = reshape_matrix(matrix, rows, columns)

        # Assert
        self.assertEqual([[7],[2],[1],[4],[3],[5],[6],[9],[8]], result)

    def test_2_by_2_raises_error_reshaping_to_4_by_2(self):
        # Arrange
        matrix = [[1,2], [3,4]]
        rows = 4
        columns = 2

        # Act & Assert
        with pytest.raises(ValueError)
            result = reshape_matrix(matrix, rows, columns)

```

##### !end-tests
#### !explanation

An example of a working implementation:

```py
def reshape_matrix(matrix, rows, columns):
    '''
    INPUT: Two dimensional list, and number of rows and columns of reshaped matrix
    OUTPUT: Reshaped matrix
    '''
    originalRows = len(matrix)
    originalColumns = len(matrix[0])
    
    # if rows * cols of original matrix is not 
    # equal to given r * c
    # not possible to transform matrix into desired shape 
    if originalRows * originalColumns != rows * columns:
        raise ValueError("Matrix cannot be reshaped to desired size")

    # flatten the original matrix
    flattened = []
    for row in matrix:
        for element in row:
            flattened.append(element)
    
    # create result matrix
    new_matrix = []
    for index in range(rows):
        row_start = columns * index
        row_end = columns *(index + 1)
        new_row = flattend[row_start : row_end]
        new_matrix.append(new_row)
    return new_matrix
```

#### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
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
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
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
<!-- prettier-ignore-end -->

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, hidden, students click to view) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
<!-- !explanation - !end-explanation (markdown, students can see after answering correctly) -->