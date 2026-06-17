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
* topics: pse
##### !question

Without writing code, describe how you would implement `merge_lists` as if you were talking through the details with another developer who will have to implement the function. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency.
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

1. Initialize a pointer for each input to 0. These will track the current index we are examining for each list.
2. Create a new empty list to gather our return value.
3. Iterate through the lists as long as both the pointers we created are less than the length of their respective lists.
    -  Inside the loop, compare the element at pointer 1 in input 1 to the element at pointer 2 in list 2
        - If the element from input 1 is smaller than the element from input 2, add the element from input 1 to our new list and increase pointer 1 by one.
        - If the element from input 1 is larger than or equal to the element from input 2, add the element from input 2 to our new list and increase pointer 2 by one.
4. At this point either: 
    - The inputs are the same length and we are done processing.
    - The inputs are different lengths and one of the input lists still has remaining values. 
        - If one of the input lists has remaining values, add them in order to the result list.
5. Return the result list

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: a6f791db-5caf-44b2-afb0-f5a1b673b450
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

As an example, let’s say we used the logical steps in the explanation for the question above in our prompt. Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat Link: `<url to your conversation>`

<br>

One strength the AI tool highlighted was the organization and clarity of my implementation roadmap. Specifically, it pointed out that the sequence of initializing pointers, creating the result list, comparing elements, handling remaining values, and returning the result would help prevent common mistakes. By outlining the major stages of the algorithm, I reduced the likelihood of forgetting an important step.

<br>

One improvement the AI recommended was strengthening my explanation of _why_ comparing the two current elements works. In my original explanation, I described the mechanics of the process by saying that I would compare the elements at each pointer and add the smaller one to the result list. However, I did not explain the reasoning behind that decision. If I were revising my explanation, I would add that because both input lists are already sorted, the smaller of the two current elements must be the next smallest value overall. Therefore, adding that element to the result preserves sorted order, and advancing only the corresponding pointer ensures that no values are skipped. Including this reasoning would demonstrate that I understand the logic behind the algorithm rather than simply recalling a sequence of steps.

<br>

One piece of feedback I _initially_ found unnecessary was the suggestion to discuss the tie-breaking rule when the two current elements are equal. The AI noted that I could mention that choosing either list first would maintain sorted order and that doing so might demonstrate thoughtfulness. Since we're working with whole numbers, it didn't seem like this really mattered for the problem at hand. However, after reflecting on this feedback, I realize, since that decision appears arbitrary, it would be worth mentioning that either choice is valid, and then think more about whether there are any implications of that choice. So the feedback seemed unnecessary at first because it didn't feel relevant to the core algorithm, but upon further reflection, I see that it could be an opportunity to demonstrate deeper understanding of the problem and the algorithm's behavior in edge cases.

<br>

One suggestion that surprised me was the recommendation to reframe my explanation of the "remaining elements" step. Initially, I described the situation in terms of whether the lists were the same length or different lengths. The AI pointed out that the important condition is actually that one of the pointers has reached the end of its list, regardless of the original lengths of the inputs. This shifted my understanding because it helped me focus on the true reason the algorithm transitions to the final step. Two lists can be the same length and still require appending remaining elements if one list's values are consistently smaller than the other's.

<br>

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->
