# Kth Missing Positive Number

## Problem Description

Given an array `numbers` of positive integers sorted in a strictly increasing order and an integer `missing_target`, find the positive integer at position `missing_target` that is not present in the array.

**Example 1:**
```
Input: numbers = [2, 3, 4, 7, 11], missing_target = 5
Output: 9

Explanation: 
- The missing positive integers are [1, 5, 6, 8, 9, 10, 12, 13, ...]. 
- The 5th missing positive integer is 9.

Missing numbers:    [1, 5, 6, 8, 9, 10, 12, 13,...]
Count:               1  2  3  4  5
```

**Example 2:**
```
Input: numbers = [1, 2, 3, 4], missing_target = 2
Output: 6

Explanation: 
- The missing positive integers are [5, 6, 7, ...]. 
- The 2nd missing positive integer is 6.

Missing numbers:    [5, 6, 7, ...]
Count:               1  2
``` 

Sourced from:  [Leetcode](https://leetcode.com/problems/kth-missing-positive-number/)

## Prompts

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: d0bbf25f-3aa8-4849-9d6e-fa5112ebe2cc
* title: Describe Your Understanding
* topics: pse
##### !question

Before you begin solving this problem, take a moment to think like a professional software engineer. 
- What do we know about the problem? 
- What assumptions can we make based on the information in the problem statement? 
- What further information do the example inputs and outputs give us?
- What questions would you ask a teammate, product manager, or interviewer to better understand the problem before writing any code?

<br>

In the box below, list 5 or more observations about the problem or questions whose answers would clarify the problem statement. For each observation or question, include information on why that observation is important or why you are asking the question.
- For each observation, answer how that observation will affect your approach to the problem.
- For each question, describe what you are hoping to clarify about the problem and provide an answer which includes the effect your decision would have on how you might approach the problem.

<br>

As you come up with observations and questions, assume that error handling for invalid data is managed outside the function. We want to focus on the core behavior of the function we will write. 

##### !end-question
##### !hint

Further questions to ask as you read through the problem statement and examples:
- What is the goal of the function?
- What are the types of the expected inputs and outputs?
- Are there any restrictions on any of the inputs?
  - For example: if any of the inputs are a list, do we know anything about how the list is ordered?
- What do the examples show us about the data types and values that are allowed for our inputs?
- What do the examples tell us about the return value in different scenarios?
- Reflecting on the observations you have made so far, what questions would give you new information?

<br>

Consider the following for inspiration:
- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Previous PSEs

##### !end-hint
##### !explanation

One of many possible responses could look like:

1. The problem statement says the input `numbers` is positive integers, does this include 0?
    - I want to be sure if the count for missing numbers should start at 0 or 1 to prevent off-by-one counting errors.
    - The two examples given do not count 0 as a missing number, so my implementation will assume that we start at 1.

2. The problem statement mentions that the input `numbers` will be positive integers and we need to "find the positive integer at position `missing_target` that is not present in the array".
    - This means that I do not need to consider any negative numbers for the return value. Any looping I may need to do will only need to consider positive numbers.

3. Thinking more about the sentence "find the positive integer at position `missing_target` that is not present in the array", I will need some way to track how many missing numbers I've seen.
    - This could be done with an array of the missing elements, or a counter variable

4. The input array `numbers` is sorted in a strictly increasing order. If I know the numbers are sorted and increasing, this helps me find missing numbers in the input list. 
    - If I compare the values at positions `i` and `i + 1` in `numbers`, there should be a difference of 1 if there are no missing numbers between them. 
    - If the difference is greater than 1, I know there are missing numbers I should track.

5. Is `missing_target` guaranteed to be a missing number between two values in `numbers?
    - Examining the second example input/output, I see that the input `numbers` is not missing any elements between the values present, and `missing_target` is 2. The expected output is "6" which is 2 larger than the last element in `numbers`. 
    - This shows me that the return value can be larger than the last value in `numbers`, it is not guaranteed to be between elements of the input list.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 1c95204d-d1c0-4e9a-b16a-5fdb3d91ba34
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `kth_missing_positive_number` for the nominal and edge cases you identified in the first step.

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
# nominal test case
def test_nominal_list():
    # Arrange
    arr = [2,3,4,7,11]
    k = 5

    # Act
    result = kth_missing_positive_number(arr, k)

    # Assert
    assert result == 9

# edge test case
def test_empty_lists():
    # Arrange
    arr = []
    k = 3

    # Act
    result = kth_missing_positive_number(arr, k)

    # Assert
    assert result == 3

```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 9deb4772-73ad-4f8f-ba65-ae645ed33a65
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `kth_missing_positive_number` in enough detail that someone else could write the code. 

* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps for an O(n) solution:

1. Check for valid input
2. If `k` is smaller than the first value in the input list `arr`, return `k`
3. Create a loop over the input `arr` that: 
   * starts at the first element of `arr` 
   * ends one element before the last element of `arr`
4. Inside the loop:
    1. Check if there are numbers missing between the current element and the next element in `arr`. Store the difference between the next element and the current element of `arr` in a new variable `missing_count`.
    2. if `k` is less than or equal to `missing_count`, return the value of `arr` at `index` plus `k` 
    3. Update the variable `k` by subtracting `missing_count`
5. If the loop ends, return the last element of the list plus the remaining value of `k`.

### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->
