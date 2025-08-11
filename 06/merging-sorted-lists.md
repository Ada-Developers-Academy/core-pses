# Merging Sorted Lists

## Problem

Imagine working on software that processes lists of numbers. Create a function named `merge_lists` that takes two sorted lists and merges them into a single sorted list. This function should take in two lists of whole numbers. The function should return a new sorted list which consists of the elements of the two arguments.

| List 1                | List 2       | Output                            |
| --------------------- | ------------ | --------------------------------- |
| [1, 2, 4, 5]          | [6]          | [1, 2, 4, 5, 6]                   |
| [-30, -10, 0, 15, 16] | [-20, -5, 5] | [-30, -20, -10, -5, 0, 5, 15, 16] |

Sourced from: [Leetcode](https://leetcode.com/problems/merge-sorted-array/)

## Prompts

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: ce61e622-d172-495c-a6b2-653f0c3c6624
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

1. In the problem statement I see that the function should take in 2 lists and return a new sorted list with the elements of both inputs.
    - This tells me that, however I choose to do it, the implementation will have to iterate over all elements of both input lists to create the return value.

2. Both of the input lists are sorted, and the return value should be in sorted order as well.
    - If I know the inputs are sorted, I can look at the values from the front to back and know they are increasing. If I iterate in the same direction, I can build my return value in sorted order by comparing the elements of the inputs and choosing the smaller value.

3. Are duplicate numbers allowed, and should duplicates be preserved?
    - The examples shown do not have any duplicated numbers between the two input lists but nothing in the problem statement says that the numbers will be unique between the inputs, or that we should filter anything out for the return value. I will assume that all duplicate values should be kept in the output.

4. How should the function handle the scenario where one or both of the input lists is empty?
    - An empty list would have no elements to add to the output. 
    - If one list is empty, I will assume that the function should return a copy of the other list. 
    - If both inputs are empty, I will assume we should return a new empty list, which technically contains all of the elements of the inputs. 

5. Does time complexity matter?
    - There are several ways this could be implemented, some of which require a sorting step. 
    - Since nothing in the problem statement that says we must reach a linear time complexity, I will assume that it's okay to take an approach that requires resorting the input, which would be a minimum time complexity of O(n log n).

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 28fc6fd5-c6c0-476f-a15b-2e7dc743b26f
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

ChatGPT noted that I did a good job focusing on details that influence understanding. My point about both inputs being sorted was accurate, and in the future I should confirm if “sorted” means non-decreasing. Also, when asking about duplicates I want to remember that they might exist within a single list as well as between lists. 

<br>

The review suggested an extra clarification around whether stability matters. It explained that “stable merge” would mean keeping a consistent order for duplicates and that clarifying if a merge should be stable can help avoid misunderstandings. Overall, my analysis was solid, but adding these kinds of clarifications in the future would make my explanations more complete!

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 29e0e4f8-78bd-4519-b832-2a090f3bf724
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `merge_lists` for the nominal and edge cases you identified in the first step.

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
def test_merge_lists_second_input_one_element():
    # nominal test case
    # Arrange
    list1 = [1, 2, 4, 6]
    list2 = [5]

    # Act
    result = merge_lists(list1, list2)

    # Assert
    assert result == [1, 2, 3, 4, 5, 6]

def test_merge_lists_empty_inputs_returns_empty_list():
    # edge test case
    # Arrange
    list1 = []
    list2 = []

    # Act
    result = merge_lists(list1, list2)

    # Assert
    assert result == []

def test_merge_lists_list_1_all_before_list_2():
    # alternative test case
    # Arrange
    list1 = [-50, -25, 0]
    list2 = [10, 20, 30]

    # Act
    result = merge_lists(list1, list2)

    # Assert
    assert result == [-50, -25, 0, 10, 20, 30]

```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 1f6d0c1e-df66-454b-a6e8-61ce8726b859
* title: Create Logical Steps
* points: 3
* topics: pse
##### !question

Without writing code, describe how you would implement `merge_lists` in enough detail that someone else could write the code. 

* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps for an O(n) solution:

1. Check for valid input
1. set `i` to 0 and `j` to 0
1. initialize `result` as an empty list
1. while `i` < length of `list1` and `j` < length of `list2`
    - if `list1[i]` < `list2[j]`
        - append `list1[i]` to `result`
        - increment `i`
    - else
        - append `list2[j]` to `result`
        - increment `j`
1. while `i` < length of `list1`
    - append `list1[i]` to `result`
    - increment `i`
1. while `j `< length of `list2`
    - append `list2[j]` to `result`
    - increment `j`
1. return `result`

### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->