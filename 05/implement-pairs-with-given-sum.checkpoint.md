# Implement pairs_with_given_sums

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 6273b410
* title: PSE
* points: 3
### !question

Imagine ...

### !end-question
### !placeholder

```python
def pairs_with_given_sums(numbers, target):
    pass
```
### !end-placeholder
### !tests
```python
import unittest
from main import *

class TestChallenge(unittest.TestCase):
    def test_finds_two_pairs(self):
        # Arrange
        numbers = [1, 2, 4, 5]
        target = 6

        # Act
        result = pairs_with_given_sums(numbers, target)

        # Assert
        self.assertEqual(result, 2)

    def test_finds_three_pairs(self):
        # Arrange
        numbers = [97, 51, 49, 35, 3, 65]
        target = 100

        # Act
        result = pairs_with_given_sums(numbers, target)

        # Assert
        self.assertEqual(result, 3)



```
### !end-tests
### !explanation

An example of a working implementation, with time complexity O(n^2):

```python
def pairs_with_given_sums(numbers, target):
    total = 0
    for i in range(len(numbers)-1):
        for j in range(i+1, len(numbers)):
            if numbers[i]+numbers[j] == target:
                total += 1
    return total
```

An example of a working implementation, with time complexity O(n):

```python

```


### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->



<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: code-snippet
* language: python3.6
* id: 82fb7e94-dae2-44e1-b7d2-bb2bc5d86bfd
* title: [text, a short question title]
<!-- * points: [1] (optional, the number of points for scoring as a checkpoint) -->
<!-- * topics: [python, pandas] (optional the topics for analyzing points) -->

##### !question

[markdown, your question]

##### !end-question

##### !placeholder

[the code below is the starting code in the web editor]
```py
def doSomething():
  '''
  INPUT: 2 dimensional numpy array
  OUTPUT: boolean
  Return true
  '''
#   return 1
```

##### !end-placeholder

##### !tests

[the unit tests below will run against the student submission]
```py
import unittest
import main as p
import numpy as np

class TestPython1(unittest.TestCase):
  def test_one(self):
    self.assertEqual(1,p.doSomething())
```

##### !end-tests

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, hidden, students click to view) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
<!-- !explanation - !end-explanation (markdown, students can see after answering correctly) -->

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->