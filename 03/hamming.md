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
* title: Break Down the Problem into Sub-Problems
* points: 3
* topics: pse
##### !question

Divide the project prompt into at least two different sub-problems

##### !end-question
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

1. How can I iterate over every element in both DNA strands at the same time?
1. What's the best way for me to compare the difference between two letters in a string?

##### !end-explanation
##### !rubric

- The answer is wrong if there aren't at least 2 sub-problems listed
- The answer is wrong if any of the sub-problems aren't relevant to the original problem

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 4 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: c7469bd0-4ff8-4d72-8dd0-5fedad6afa87
* title: Create Logical Steps
* points: 3
* topics: pse
##### !question

Pick one of those problems from #3 and write a numbered list explaining how to solve that problem without using full lines of code

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint
##### !rubric

- The answer is wrong if it doesn't have at least two steps
- The answer is wrong if it isn't logical to another reader

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 5 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: db9dfcdb-0176-48e7-8329-ecfd7f076b2c
* title: Solve a Sub-Problem
* points: 3
* topics: pse
##### !question

Write the pseudocode or code solution for your answer for #4

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint
##### !rubric

The point of this exercise is not fully check if the code is correct at the moment, but to practice writing code outside of a text editor.

- The answer is wrong if it is blank
- The answer is wrong if it is obviously incorrect code (ie writing `print("Oops!")` for the entire response)

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->
