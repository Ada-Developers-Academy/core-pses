# Palindrome

## Problem Statment

Imagine working on software that processes text. A palindrome is a word, phrase, or sequence that reads the same backward as forward.

Create a function named `check_palindrome` that determines if a string is a palindrome. This method should take in one string as a parameter. This method should return `True` if the string is a palindrome.

### Examples

| Example Input | Expected Output |
| ---------------------------- | ------------------- |
| `"Hello, world!"`            | `False`                  |
| `"nascar"`                   | `False`                  |
| `"racecar"`                  | `True`                 |
| `"noon"`                     | `True`                 |
| `"mom"`                      | `True`                 |
| `"kayak"`                    | `True`                 |

## Prompts

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: b3294ca0-b085-49e7-890f-e839e3a9efac
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

1. The problem statement says we need to determine if the input is a palindrome and that a palindrome is a word, phrase, or sequence that reads the same backward as forward.
    - This tells me that I will have an input that I need to iterate over in such a way that I can check elements at the front and back of the input at the same time.

2. In the problem statement, I see that I should return `True` if the string is a palindrome. The examples inputs & outputs show both `True` and `False` return values.
    - While the problem statement doesn't explicitly say we should return `False` if the input is not a Palindrome, the examples show me that we should return `False` if we determine the input is not a palindrome.

3. What should the function return if the string is not a palindrome?
4. What should the function return if the string is an empty string, `""`?
5. Does capitalization matter? Is this case-sensitive? Is `"Kayak"` a palindrome?
6. What do we do with punctuation? Is `"kayak!"` a palindrome?
7. What do we do with white space? Is `"k ayak"` a palindrome?
8. Do we accept input other than strings such as lists or integers?

##### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->

### !challenge
* type: code-snippet
* language: python3.6
* id: 3e891984-c84a-4b0c-9e2b-b652391ab7bc
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `palindrome` for the nominal and edge cases you identified in the first step.

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
# example input 1: s = "kayak"
# expected output 1: palindrome(s) = True

# example input 2: s = "Kayak"
# expected output 2: palindrome(s) = True

def test_true_for_single_word_palindrome():
    # nominal test case

    # Arrange
    s = "kayak"

    # Act
    result = palindrome(s)

    # Assert
    assert result == True

def test_ignores_capitalization():
    # edge test case

    # Arrange
    s = "Kayak"

    # Act
    result = palindrome(s)

    # Assert
    assert result == True  
```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 374a4f64-cb87-4bf5-9faf-8d3199048491
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `palindrome` in enough detail that someone else could write the code. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps: 

1. Check that the input is a string.
    - If it is not, raise an exception
2. Convert input to lowercase.
3. Initialize one pointer to move forward through the string, and one pointer to move backwards through the string.
4. Create a while loop that keeps looping until the pointers have passed each other.
5. Check if the character at index of the forward pointer is alphanumeric
    - If not, increment the pointer
6. Check if the character at index of the backwards pointer is alphanumeric
    - If not, decrement the pointer
7. Check if the characters at the forward/backward pointers match
    - If not, return `False`
8. Increment/decrement the forward and backward pointers respectively.
9. Return `True` once the loop has finished executing. 

##### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->
