# Palindrome

## Problem

Imagine working on software that processes text. A palindrome is a word, phrase, or sequence that reads the same backward as forward.

Create a function named `is_palindrome` that determines if a string is a palindrome. This method should take in one string as a parameter. This method should return `True` if the string is a palindrome.

This is one example input/output for this method:

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
* id: 20067602-05d7-4cea-94c1-1cadfc8e787e
* title: Ask Clarifying Questions
* points: 3
* topics: pse
##### !question

List five or more questions whose answers would clarify the problem statement

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

##### !end-explanation
##### !rubric

- The answer is wrong if there aren't at least five questions
- They should ask about what to return if the string is not a palindrome (the problem statement intentionally does not state to return `False`)
- They should ask about some set of special characters

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 56e15301-9e21-4963-b3cb-a1c5e9c89f07
* title: Consider Example Inputs and Outputs
* points: 3
* topics: pse
##### !question

List two sets of example arguments and the expected return value for these arguments

##### !end-question
##### !hint

Consider unexpected test cases and edge-case situations.

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint
##### !explanation

Here are some example sets of inputs and outputs:

1. Input: `ada`, Output: `True`
1. Input: `Ada`, Output: `False`

##### !end-explanation
##### !rubric

- The answer is wrong if there aren't 2 examples
- The answer is wrong if either of them aren't valid/consistent with each other
- The answer is wrong if the example inputs were not what the problem stated for valid input
- The answer is wrong if the example outputs were not what the problem stated or raised errors/exceptions

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: c5c250c9-8f71-4a72-b42b-60cbee93e02b
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

1. How do we look at the first character of the string and the last character of the string at the same time?
1. What do we do when we compare the two characters?
1. How do we repeat this process, looking at the second character and the second-to-last character, until we've checked every character?

##### !end-explanation
##### !rubric

- The answer is wrong if there aren't at least two sub-problems listed
- The answer is wrong if any of the sub-problems aren't relevant to the original problem

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 4 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 52c7bf67-d5e6-4655-8c1e-7d4c10184152
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
* id: Cf1pAM
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
