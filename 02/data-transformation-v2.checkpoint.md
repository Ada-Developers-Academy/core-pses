# Data Transformation

## Problem

Imagine working on software that tracks students. Create a function named `get_student_data` that is responsible for giving back student data. This function should take in a list of student name strings. This function should have a return value of a list of dictionaries. Each dictionary should have the name of the student and a student id. The ids should **not** be consecutive numbers.

## Prompts

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 59886932-f38e-4a16-8bc9-2f3c2c9e76bb
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

1.  Is there some pattern required for the student IDs?
1.  What key-value pairs should the student dictionaries contain?
1.  What should happen if the list of names is empty?
1.  Can ID numbers be negative?
1.  Should IDs be integers? Can they be floats?

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: a9e5d06a-3e7e-44a7-9584-07890255069b
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

1.  Input:  `["Zahra", "Sally", "Ada"]`  Output:  `[{ id: 1, name: "Zahra"}, { id: 3, name: "Sally"}, {id: 5, name: "Ada" }]`
1.  Input: `[]`  Output: `[]`

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 4fab32fb-cf8f-40be-b6cf-eb6b949bb06c
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

1.  Calculating id numbers
1.  Converting an array of names into an array of hashes
1.  Ensuring id numbers are not consecutive

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 4 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 5dfd3ed2-c609-4881-9415-4f819cb41bfa
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
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 5 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: dbad7079-f9d2-4131-8883-0b4fbde7e6bd
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
### !end-challenge
<!-- prettier-ignore-end -->
