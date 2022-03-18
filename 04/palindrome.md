# Palindrome

## Problem Statment

Imagine working on software that processes text. A palindrome is a word, phrase, or sequence that reads the same backward as forward.

Create a function named `is_palindrome` that determines if a string is a palindrome. This method should take in one string as a parameter. This method should return `True` if the string is a palindrome.

### Examples

| Original string as parameter | Is it a palindrome? |
| ---------------------------- | ------------------- |
| `"Hello, world!"`            | No                  |
| `"racecar"`                  | Yes                 |
| `"noon"`                     | Yes                 |
| `"mom"`                      | Yes                 |
| `"kayak"`                    | Yes                 |

## Prompts

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 733d51d0-bad2-4a5c-8475-68dc11e91618
* title: Ask Clarifying Questions
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
##### !explanation

Here are some example clarifying questions:

1. What should the function return if the string is not a palindrome?
1. What should the function return if the string is an empty string, `""`?
1. Does capitalization matter? Is this case-sensitive? Is `"Kayak"` a palindrome?
1. What do we do with punctuation? Is `"kayak!"` a palindrome?
1. What do we do with white space? Is `"k ayak"` a palindrome?
1. Do we accept input other than strings such as lists or integers?

##### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->

### !challenge
* type: code-snippet
* language: python3.6
* id: cbb95ff3-17ef-438b-9f84-755a3d184ab8
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
* id: 4d19dc79-3595-4e24-a88a-78b007805cfb
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
