# Hamming

## Problem Statment

Imagine working on software that analyzes mutations in DNA.

Create a function named `hamming_distance` that calculates the number of differences between two DNA strands (aka two strings). This method should take in two different DNA strands of the same length as parameters. This method should have a return value of the number of differences between each string.

For example, given these two DNA strands (strings), `hamming_distance` should return `7` because there are 7 differences:

|Example Input | Expected Ouput |
|--|--|
|`strand1 = "GAGCCTACTAACGGGAT"` <br> `strand2 = "CATCGTAATGACGGCCT"` | `7`|
Explanation:

```
Strand #1:   GAGCCTACTAACGGGAT
Strand #2:   CATCGTAATGACGGCCT
Differences: ^ ^ ^  ^ ^    ^^
             7 in total
```

(This problem is sourced from http://rosalind.info/problems/hamm/)

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

1. What happens if the strings are two different lengths?
1. How small can the DNA strands be? What happens if the strings are empty?
1. Can we assume that DNA strands be made up of only "A", "C", "G", and "T"? Will there ever be any exceptions?
1. How large can the DNA strands be?
1. Are there ever any patterns in DNA strands?

##### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: cbb95ff3-17ef-438b-9f84-755a3d184ab8
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `score` for the nominal and edge cases you identified in the first step.

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
# example input 1: strand1 = "GAGCCTACTAACGGGAT", strand2 = "CATCGTAATGACGGCCT"
# expected output 1: hamming_distance(strand1, strand2) = 7

# example input 2: strand1 = "GAG", strand2 = ""
# expected output 2: ValueError: Strands must be the same length

def test_correct_score_for_all_letters():
    # nominal test case

    # Arrange
    strand1 = "GAGCCTACTAACGGGAT"
    strand2 = "CATCGTAATGACGGCCT"

    # Act
    result = hamming_distance(strand1, strand2)

    # Assert
    assert result == 7

def test_ignores_special_characters():
    # edge test case

    # Arrange
    strand1 = "GAG"
    strand2 = ""

    # Act/Assert
    with pytest.raises(ValueError):
        hamming_distance(strand1, strand2)
    
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

Without writing code, describe how you would implement `get_highest_rating` in enough detail that someone else could write the code. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps: 

1. Check if the strands are the same length
    - If they're different lengths, raise an exception
2. Initialize a variable `distance` to 0
3. Iterate through the characters in the strings using a for in range loop
4. Check if the characters at corresponding indices are the same
    - If they're different, incremenet `distance`
5. Return `distance`

##### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->
