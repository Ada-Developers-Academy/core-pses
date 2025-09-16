# Find the Target Missing Positive Number

## Problem Description

Given an array `numbers` of positive integers sorted in a strictly increasing order and an integer `missing_target`, find the positive integer at position `missing_target` that is not present in the array.

**Example 1:**
```
Input: numbers = [2, 3, 4, 7, 11], missing_target = 5
Output: 9

Explanation: 
- The missing positive integers are [1, 5, 6, 8, 9, 10, 12, 13, ...]
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
    - This could be done several ways, some options could be creating an array of the missing elements or a counter variable.

4. The input array `numbers` is sorted in a strictly increasing order. If I know the numbers are sorted and increasing, this helps me find missing numbers in the input list. 
    - If I compare the values at positions `i` and `i + 1` in `numbers`, there should be a difference of 1 if there are no missing numbers between them. 
    - If the difference is greater than 1, I know there are missing numbers I should track.

5. Is `missing_target` guaranteed to be a missing number between two values in `numbers`?
    - Examining the second example input/output, I see that the input `numbers` is not missing any elements between the values present, and `missing_target` is 2. The expected output is "6" which is 2 larger than the last element in `numbers`. 
    - This shows me that the return value can be larger than the last value in `numbers`, it is not guaranteed to be between elements of the input list.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: bf71f5ee-d39d-4daa-bb68-6152fbd3c4ed
* title: Review Observations & Questions
* topics: pse
##### !question

While we build our skills in breaking down a problem and choosing clarifying questions, let’s use an external tool like ChatGPT to review the observations and questions we wrote while describing our understanding. 

<br>

Our goals are to: 
- confirm if our observations and assumptions make sense in the context of the code problem
- ensure we are asking questions that will tell us new information about the problem space
- check our understanding of the information we expect to get from those questions
- uncover other observations that would help shape our approach and understand how they would affect our approach
- uncover further questions that could be useful to ask and understand why those other questions could be helpful

<br>

For this question we will:
1. Build a prompt using [the template linked here](https://gist.githubusercontent.com/ada-instructors/16c97dc4b16ab2bf449d9d7a81caeb16/raw/pse_observations_questions_review_template.md)
2. Share the completed prompt with an AI tool like ChatGPT
3. After the initial review, ask the AI tool *at least one* follow up question that furthers your understanding of the problem and why certain observations or questions are useful. Some examples could be asking questions to: 
    - ensure your understanding of the analysis of the observations
    - get more details on the information we could get from asking particular questions
    - learn more about new information shared by the tool
4. Reflect on the information shared by the AI tool and summarize its findings and your learnings

<br>

In the box below, please submit:
1. A shareable link to your conversation in ChatGPT
    - [Documentation for creating a shareable link in ChatGPT](https://help.openai.com/en/articles/7925741-chatgpt-shared-links-faq)
2. Your reflections and summary of the discussion with ChatGPT

##### !end-question
##### !hint

**Troubleshooting**
- If you are having issues with the tool understanding the prompt, try formatting the problem statement or examples differently.
- If you’ve reformatted the information and are still not getting useful results, reach out in #study-hall and share what you are experiencing and the link to your chat so folks can take a look and help you troubleshoot!

<br>

**Summarizing the Review**
- Did the AI tool uncover anything about the observations you made that you hadn’t considered?
- Did the AI tool uncover anything about the questions you asked that you hadn’t considered?
- Did the AI tool suggest updates to the observations you made or questions you asked? 
    - If so, what updates and why?
- Did the AI tool suggest any new observations or questions?
    - If so, what? Why would they be useful?

##### !end-hint
##### !explanation 

For an example of what a review response might look like, let’s say that we used the example response from the "Explanation" section of the previous question to complete the review prompt. 

<br>

Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat link: `<url to your conversation>`

<br>

ChatGPT gave me feedback that the questions and observation I shared were useful and specific ones like recognizing that the target missing number might lie beyond the largest element help prevent wrong assuptions.

<br>

The feedback suggested I could add a few more clarifications:
- Some seem useful like whether the list could be empty. 
- Other suggestions leaned into validation that's outside the scope of the problem or wouldn't necessarily change the implementation, like whether the missing target always exists or how large the inputs could get. 

<br>

I asked some questions around feedback that said I could ask if duplicates were possible even though "strictly increasing" means that isn't likely, since I found it a little confusing. This gave me a better understanding that no duplicates and strict ordering is what makes the logic straightforward when checking for missing values between the elements of the input `numbers`.

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
2. Write unit tests for `find_missing_positive_number` for the nominal and edge cases you identified in the first step.

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
def test_find_missing_positive_number_missing_element_inside_list_found():
    # Arrange
    numbers = [2, 3, 4, 7, 11]
    missing_target = 5

    # Act
    result = find_missing_positive_number(numbers, missing_target)

    # Assert
    assert result == 9

# edge test case
def test_find_missing_positive_number_empty_list_returns_missing_target():
    # Arrange
    numbers = []
    missing_target = 3

    # Act
    result = find_missing_positive_number(numbers, missing_target)

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

Without writing code, describe how you would implement `find_missing_positive_number` in enough detail that another developer could reasonably implement a solution. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency. 
- The objective is to create a roadmap that we can use to keep ourselves oriented towards our goal
- It is okay to leave some of the finer details to be worked out in the implementation itself!

As you write your steps, keep the following guidelines in mind:
* We want to think about a general approach rather than what the code would look like line-by-line. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. 
    * For example: 1. Handle edge cases, 2. Perform the computation/solve the problem/etc.
* The steps should be a description as if you were talking out the problem with another person and should be agnostic of any particular language. 
    * As such, they should not include code syntax in the description.

What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question
##### !placeholder

Write the logical steps here.

##### !end-placeholder
### !explanation

Example Steps for an O(n) solution:

1. Handle edge case:
   * If `missing_target` is smaller than the first value in `numbers`, return `missing_target`
2. Create a loop over the input `numbers` that: 
   * starts at the first element of `numbers` 
   * ends one element before the last element of `numbers`
3. Inside the loop:
    1. Check if there are numbers missing between the current element and the next element in `numbers`. If there are missing numbers, store the count in a variable.
    2. If `missing_target` is less than or equal to the count variable just created, return the value of `numbers` at the current index plus `missing_target` 
    3. If we did not return, update the variable `missing_target` by subtracting the new missing count variable
4. If the loop ends, return the last element of the list plus the remaining value of `missing_target`.

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

We want to know if we are laying out an approach to the coding problem that makes sense for our context and if that approach is clearly conveying our thoughts on technical topics to others. Let’s once more use an AI tool like ChatGPT, this time to review the Logical Steps we wrote above. Our goals are to check if:
- the steps make sense for the problem being solved
- the steps are not missing important steps or scenarios
- the steps are agnostic of any particular language – steps should not include code syntax.
- the steps are written with enough detail for another developer to understand how to create a solution

<br>

For this question we will:
1. Build a prompt using [the template linked here](https://gist.githubusercontent.com/ada-instructors/670252696f1625cf0ed77c0997cd165d/raw/pse_logical_steps_review_template.md)
2. Share the completed prompt with an AI tool like ChatGPT
3. After the initial review, ask *at least one* follow up question using the AI tool. We want to ask questions that help us understand: 
    - areas where we could add clarity
    - edge cases we might have missed
    - places where our steps do not meet the expectations of the problem statement
4. Reflect on the information shared by the AI tool and summarize its findings and your learnings

<br>

In the box below, please submit:
1. A shareable link to your conversation in ChatGPT
    - [Documentation for creating a shareable link in ChatGPT](https://help.openai.com/en/articles/7925741-chatgpt-shared-links-faq)
2. Your reflections and summary of the discussion with ChatGPT

##### !end-question
##### !explanation

As an example, let’s say we used the logical steps in the explanation for the question above in our prompt. Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat Link: `<url to your conversation>`

<br>

I got feedback that my approach did a good job keeping the explanation language-agnostic and focusing on logical conditions instead of Python syntax.
While my steps can correctly solve the problem, ChatGPT suggested I make my reasoning clearer in a few spots, such as why the loop stops at the second-to-last element and how the missing count between numbers is determined. In asking ChatGPT about why I would want to include this information, it shared that this demonstrates deeper understanding, helps catch small mistakes, makes my approach easier for others to follow, and strengthens my algorithmic thinking skills. 

<br>

It was also suggested to bring up the case where the missing target is far beyond the largest element, so other developers see I’ve considered it. However, this case is already covered by my steps. If I were writing these steps again I could highlight that the last step handles when `missing_target` is beyond the end of `numbers`, but since there aren't constraints on size that we need to consider and the suggestion does not change how the implementation is handled, I don't think this suggestion from ChatGPT is especially useful in this context. 

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->