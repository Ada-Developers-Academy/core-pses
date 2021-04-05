# Hamming

## Problem

Imagine working on software that analyzes mutations in DNA.

Create a function named `hamming_distance` that calculates the number of differences between two DNA strands (aka two strings). This method should take in two different DNA strands as parameters. This method should have a return value of the number of differences between each string.

For example, given these two DNA strands (strings), `hamming_distance` should return `7` because there are 7 differences:

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
* id: 50c3b4fb-5706-482f-8300-a2e4a1c2c8ed
* title: Ask Clarifying Questions
* points: 1
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

1. What happens if the strings are two different lengths?
1. How small can the DNA strands be? What happens if the strings are empty?
1. Can we assume that DNA strands be made up of only "A", "C", "G", and "T"? Will there ever be any exceptions?
1. How large can the DNA strands be?
1. Are there ever any patterns in DNA strands?

##### !end-explanation
##### !rubric

- The answer is wrong if there aren't at least five questions
- The answer is wrong if there were no questions clarifying what you should do if the two strings are different lengths

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 14f28838-7d15-413e-97ed-3dd3511949e8
* title: Consider Example Inputs and Outputs
* points: 1
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

Input:
    - `"GAGCC"`
    - `"CATCG"`
Output: 3

Input:
    - `"G"`
    - `"C"`
Output: 1

##### !end-explanation
##### !rubric

- The answer is wrong if there aren't 2 examples
- The answer is wrong if either of them aren't valid/consistent with each other
- The answer is wrong if the example inputs were not two strings for valid input
- The answer is wrong if the example outputs were not integers or exceptions raised

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: ec0bd5c8-b262-4eba-b15a-0b6139cb479c
* title: Break Down the Problem into Sub-Problems
* points: 1
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
* id: 8bb89173-1352-4bd0-8fc3-b9d5e0f8e588
* title: Create Logical Steps
* points: 1
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
* id: 84c9d1b5-ba85-417c-b04d-10ff0024f169
* title: Solve a Sub-Problem
* points: 1
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
