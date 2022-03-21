# Pairs With a Given Sum

## Problem

Imagine working on software that processes lists of numbers. Create a function named `pairs_with_given_sum` It finds the number of pairs of `numbers` in a list which add up to a given `target`. This function should take in a list of whole `numbers` and a `target` as parameters. This function should have a return value of the integer of number of pairs.

| numbers                 | target | Number of pairs (return value)|
| ----------------------- | --- | --------------- |
| [1, 2, 4, 5]            | 6   | 2               |
| [97, 51, 49, 35, 3, 65] | 100 | 3               |

Sourced from: [Geeks for Geeks](https://www.geeksforgeeks.org/count-pairs-with-given-sum/)

## Prompts

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 43ea9dc8-d8bf-4210-bffa-313201683be5
* title: Ask Clarifying Questions
* points: 3
* topics: pse
##### !question

List three or more questions whose answers would clarify the problem statement

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint
### !explanation

Here are some example clarifying questions:

1. How does the function handle non-numeric elements in the list of `numbers`?
1. What is the behavior for a non-numeric `target`?
1. Can each of the numbers be used more than once in a pair that sums to the target?
1. What is the behavior for an empty list?

##### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->

### !challenge
* type: code-snippet
* language: python3.6
* id: 068f00d6-4519-454f-a913-80216d9e26c8
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `pairs_with_a_given_sum` for the nominal and edge cases you identified in the first step.

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
# example input 1: numbers = [1, 2, 4, 5], target = 6            
# expected output 1: hamming_distance(numbers, target) = 2

# example input 2: numbers = [1, 2, 4, 5, 1], target = 6  
# expected output 2: hamming_distance(numbers, target) = 2 (assumption: the number 5 can only be used in one pair)

def test_finds_two_pairs():
    # nominal test case

    # Arrange
    numbers = [1, 2, 4, 5]
    target = 6

    # Act
    result = pairs_with_given_sum(numbers, target)

    # Assert
    assert result == 2

def test_finds_two_pairs_with_duplicate_number():
    # edge test case
    
    # Arrange
    numbers = [1, 2, 4, 5, 1]
    target = 6

    # Act
    result = pairs_with_given_sum(numbers, target)

    # Assert
    assert result == 2 
```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 03d126b0-86dc-49db-9647-563c37c3711b
* title: Create Logical Steps
* points: 3
* topics: pse
##### !question

Without writing code, describe how you would implement `pairs_with_given_sum` in enough detail that someone else could write the code. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps for an O(n^2) solution: 

1. Check for valid input
2. Loop through the `numbers` from the first number to the second last number using a `for i in range...` loop.
3. Loop through the `numbers` from `i+1` to the last number using a `for j in range...` loop.
4. If `numbers[i] + numbers[j]` is equal to the target, incremement a counter by 1.
5. return the value of the counter

### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->