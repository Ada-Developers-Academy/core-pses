# Find the Kth Missing Positive Number

## Problem Description

Given an array `numbers` of positive integers sorted in a strictly increasing order, and an integer `kth_missing`, find the "kth" (read _kayth_) number missing from `numbers`. kth means an unknown _ordinal number_, in other words something like first, second, third, and so on. So if `kth_missing` is `5`, we're looking for the 5th number missing from the input `numbers`.

**Example 1:**
```
Input: numbers = [2, 3, 4, 7, 11], kth_missing = 5
Output: 9

Explanation: 
- The missing positive integers are [1, 5, 6, 8, 9, 10, 12, 13, ...]
- The 5th missing positive integer is 9.

Missing numbers:    [1, 5, 6, 8, 9, 10, 12, 13,...]
Count:               1  2  3  4  5
```

**Example 2:**
```
Input: numbers = [1, 2, 3, 4], kth_missing = 2
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
##### !placeholder

Add observations, assumptions, and questions here:

Eg. from the sample PSE: 
I observe that the function should return a string indicating the result of the game: "Player 1 wins!", "Player 2 wins!", or "It's a tie!"
    - Aside from checking if someone wins, I need to consider the edge case where the players could tie.

##### !end-placeholder
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

1. The problems describes numbers as containing positive integers, but sometimes people talk about positive numbers when really what they mean is not negative. Is 0 allowed in numbers?
    - The examples only show numbers starting from 1, and the counting of the missing numbers doesn't include 0 as a missing number, so I will assume the lowest number allowed in numbers is 1. This is important because this gives me a consistent starting point for counting the number of missing values.

2. Can `kth_missing` be non-positive? The prompt says that `kth_missing` is an integer, but doesn't explicitly say that it's positive as it did with the contents of `numbers`.
	- The prompt describes `kth_missing` as something like first, second, third, etc. At least in common language, we don't talk about cases like zeroth or negative first. We start from first. So I'll assume that `kth_missing` will also be a positive number, since a negative value for `kth_missing` doesn't make sense. I could raise an error for this case if needed, but since there's no clear error handling requirement, I'll assume the input value has already been constrained to positive numbers.
	
3. The input array `numbers` is sorted in a strictly increasing order. If I know the numbers are sorted and increasing, this helps me find missing numbers in the input list. 
    - If I compare the values at positions `i` and `i + 1` in `numbers`, there should be a difference of 1 if there are no missing numbers between them. If the difference is greater than 1, I know there are missing numbers I should track.

4. Also since `numbers` is sorted in a strictly increasing order, I can also assume there are no duplicates in `numbers`.
    - If there were duplicate numbers in the list, then there would be values in the array that don't increase, either because two identical values are next to one another (no increase), or because the duplicate appears after a higher number has appeared (causing a decrease).

5. Is the `kth_missing` guaranteed to be found between two values in `numbers`?
    - Examining the second example input/output, I see that the input `numbers` is not missing any elements between the values present, and `kth_missing` is 2. The expected output is "6" which is 2 larger than the last element in `numbers`. 
    - This shows me that the value of the `kth_missing` number can be larger than the last value in `numbers`, it is not guaranteed to be between elements of the input list.

6. Can the `kth_missing` value come _before_ the values in the list?
    - While there is no specific example of this, the lowest value in the first example `numbers` is `2`, and the explanation does show that the number 1 is considered to be missing from `numbers`. So if we had been asked to find the first missing number, this would be `1`, which comes before the first value in `numbers`.
    - In general, if we are asked to find a `kth_missing` value, and `kth_missing` is smaller than the first value in `numbers`, then the resulting value will be the same as `kth_missing` itself.

7. Can `numbers` be empty? Arrays in general can be empty, but how would that affect how we compute the missing numbers?
    - An empty list doesn't violate the problem statement that `numbers` is in strictly increasing order. Since there are no values, there are no _out of place_ values to violate that requirement. This would also apply to a list with a single value. There's no reason to disallow either case.
    - If we are taking the lowest allowed value in numbers to be 1, this would just result in the kth missing number being the same as `kth_missing`. This is really just a special case of the `kth_missing` number being found beyond and values in the `numbers`, so being careful to handle the first case might also handle this one. Though this could possibly be handled with an explicit case if the main implementation doesn't handle this gracefully.
    - Another perspective is that when `numbers` is empty, the `kth_missing` value comes before the first value in `numbers` (since there aren't any values). This still gives us the value of the `kth_missing` number to be the same as `kth_missing` itself, which is consistent with our earlier observation.

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
2. Write unit tests for `find_kth_missing_positive_number` for the nominal and edge cases you identified in the first step.

When naming a test, we want to ensure the name describes the scenario we are testing by including information like the function being tested, inputs, and expected outputs. 
* e.g. from the example PSE: if we wanted to test that the function winner returns a tie when `player_1` and `player_2` have the same value, then we might name the test something like `test_winner_both_inputs_paper_returns_tie`.

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
def test_find_kth_missing_positive_number_missing_element_inside_list_found():
    # Arrange
    numbers = [2, 3, 4, 7, 11]
    kth_missing = 5

    # Act
    result = find_kth_missing_positive_number(numbers, kth_missing)

    # Assert
    assert result == 9

# edge test case
def test_find_kth_missing_positive_number_empty_list_returns_kth_missing():
    # Arrange
    numbers = []
    kth_missing = 3

    # Act
    result = find_kth_missing_positive_number(numbers, kth_missing)

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

Without writing code, describe how you would implement `find_kth_missing_positive_number` as if you were talking through the details with another developer who will have to implement the function. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency.
* The objective is to practice describing algorithms and technical concepts while creating a roadmap that we can use to keep ourselves oriented towards our goal during the implementation step.
* It is okay to leave some of the finer details to be worked out in the implementation itself!

As you write your steps, keep the following guidelines in mind:
* We want to think about a general approach rather than what the code would look like line-by-line. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. 
    * For example: 1. Handle edge cases, 2. Perform the computation/solve the problem/etc.
* The steps should be a description as if you were talking out the problem with another person and should be agnostic of any particular language. 
    * As such, they should not include code syntax in the description.

What's important at this stage is to think through how you would put an approach into words, and outline the implementation before writing code.

##### !end-question
##### !placeholder

Write the logical steps here.

##### !end-placeholder
### !explanation

Example Steps for an O(n) solution:

1. Handle edge case:
    * If `numbers` is empty, then `kth_missing` is itself the missing number. Return `kth_missing`.
        * Since every number is missing, and the numbers and `kth_missing` both start from `1`, `kth_missing` is the missing number.
    * If `kth_missing` is smaller than the first value in `numbers`, then `kth_missing` is itself the missing number. Return `kth_missing`.
        * This is because it would take more numbers than `kth_missing` to even make us look at the array values. 
2. Loop over the input `numbers`: 
    * start at the first element of `numbers` 
    * end one element before the last element of `numbers`
3. Inside the loop, we will look for gaps between the values in `numbers` until we find the gap that includes the missing number. We'll do this by identifying individual gaps, and decreasing `kth_missing` by the number of missing values in the gap. As `kth_missing` gets smaller, this will mean that we're getting closer to the gap that actually contains the missing value.
    1. Check if there are numbers missing between the current element and the next element in `numbers`. If there are missing numbers, store the count in a variable representing the current gap size.
    2. If `kth_missing` is less than or equal to the gap size variable just created, the missing number is found within this gap. Return the value of `numbers` at the current index plus `kth_missing` (the remaining count of missing values).
        * `kth_missing` has been reduced with each gap we've found, so what's left is the number of values beyond the value at the current index. 
    3. If we did not return, update the variable `kth_missing` by subtracting the gap size variable. 
        * We want to keep track of how many missing values we've seen so that we know when we've found the kth missing value. Each gap we find has some number of missing values, and by reducing `kth_missing` each gap, we keep track of how many missing values we have left before we find our desired value.
4. If the loop ends, this means that even accounting for all of the gaps in the array, there are still numbers left to find. Return the last element of the list plus the remaining value of `kth_missing`.
    * `kth_missing` has been reduced by the total size of the gaps found in the array. This means the missing value we're looking for is the final value in the array plus the remaining count of missing values `kth_missing`. 

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: d424be4c-55d2-4c7f-be56-e14240f51c01
* title: Review Logical Steps
* topics: pse
##### !question

We want to know if we are laying out an approach to the coding problem that makes sense for our context and if that approach is clearly conveying our thoughts on technical topics to others. While we build our skills in breaking down and describing algorithms, let’s use an AI tool like ChatGPT to review the Logical Steps we wrote above. Our goals are to check if the steps:
- convey the technical concepts and requirements of the problem in a way that another person can understand
- make sense for the problem being solved
- are not missing important steps or scenarios
- are agnostic of any particular language – the steps should not include code syntax.

<br>

For this question we will:
1. Build a prompt using [the template linked here](https://gist.githubusercontent.com/ada-instructors/670252696f1625cf0ed77c0997cd165d/raw/pse_logical_steps_review_template.md)
2. Share the completed prompt with an AI tool like ChatGPT
3. Reflect on the information shared by the AI tool, then use the prompts below to summarize its findings and your learnings.

<br>

Reflection Prompts

1. Identify one specific strength the AI highlighted in your explanation. 
    * Quote or paraphrase the part of the feedback that mentions this strength, and explain why you think that aspect of your explanation was effective.
2. Point out at least one specific improvement the AI recommended.
    * Describe exactly which part of your explanation would benefit from strengthening then outline how you would revise that part if you were rewriting it now.
3. Identify one piece of AI feedback you believe was inaccurate, irrelevant, or unnecessary. 
    * Explain why it doesn’t apply to this problem, and cite a source (docs, class notes, instructor explanation, or trusted online reference) that supports your reasoning.
4. Describe one change the AI suggested that was new or surprised you. 
    * Share how this suggestion shifted your understanding of the problem or your explanation.

<br>

In the box below, please submit:
1. A shareable link to your conversation in ChatGPT
    - [Documentation for creating a shareable link in ChatGPT](https://help.openai.com/en/articles/7925741-chatgpt-shared-links-faq)
2. Your reflections and summary of the discussion with ChatGPT

##### !end-question
##### !explanation

As an example, let’s say we used logical steps similar to the explanation for the question above in our prompt. Depending on how the supplied steps differ and exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat Link: `<url to your conversation>`

<br>

One strength the AI tool highlighted was that my overall "consume the gaps" strategy was correct and led to the standard linear solution. The AI noted that subtracting missing counts from kth_missing until finding the gap containing the answer was a solid core approach.

<br>

One improvement the AI recommended was explicitly accounting for missing numbers before the first element in the array. While I handled the case where `kth_missing` was less than the first value, I did not clearly explain or process situations where there were missing values before the array begins, but the kth missing number isn't in that pre-array gap. My current steps only start processing the first gap within the array. Either I need to account for this in the main loop or I need to handle it as a separate case before the loop.

<br>

One piece of feedback I found unnecessary was a suggestion to include the explicit formula for calculating the next gap size in my logical steps. The explicit formula requires accessing adjacent array indices, which ends up being noisy in the context of the logical steps. While I would remain open to including the formula if the interviewer asked, I'll eventually show the formula in my implementation, where I'll also have a chance to work out any discrepancies with test scenarios rather than spending time working out a solution by hand in the logical steps, which might end up being slightly incorrect anyway.

<br>

One suggestion that surprised me was the suggestion to reframe `kth_missing` as "how many missing values are still left to skip" instead of "how many missing values we've seen." In retrospect, this is a more accurate description of the variable, since we are decrementing it as we find missing values. I had been thinking of it as a count of how many missing values we've seen, but that doesn't make sense because we don't know how many missing values there are until we find them. It was a small change in perspective, but it helped me clarify my understanding of the variable and how it is used in the algorithm.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->