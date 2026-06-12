# Pairs With a Given Sum

## Problem

Imagine working on software that processes lists of numbers. Create a function named `pairs_with_given_sum`. It finds the total pairs of numbers in a list which add up to a given target value. This function should take in a list, `numbers`, of whole numbers and a `target` as parameters. This function should return an integer representing the number of pairs.

| numbers                 | target | Number of pairs (return value)|
| ----------------------- | ------ | --------------- |
| [1, 2, 4, 5]            | 6      | 2               |
| [97, 51, 49, 35, 3, 65] | 100    | 3               |

Sourced from: [Geeks for Geeks](https://www.geeksforgeeks.org/count-pairs-with-given-sum/)

## Prompts

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 43ea9dc8-d8bf-4210-bffa-313201683be5
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
### !explanation

One of many possible responses could look like:

1. The problem statement and examples show that we should return the total number of pairs that create the "target", not the actual pairs themselves.
    - This means that we only need to count matching pairs, we do not need to store or return them.

2. Looking at the first example, given the inputs numbers = [1, 2, 4, 5] with target = 6, there are two unique pairs: [1, 5] and [2, 4] and the expected output is "2". 
    - This means that however we iterate through the input "numbers" we should not double count pairs. I will need some way to keep track of the numbers that have been used in pairs as I go.

3. Can a number can be reused in more than one pair?
    - It isn't mentioned in the problem statement and the examples do not include repeated numbers or duplicate pairs. Since nothing says that numbers should be used more than once, I will assume a number can only be used in a single pair.
    - If I am assuming a number can only be used in a single pair, as with the previous observation, I will need to keep track of the used numbers.

4. The problem uses the phrase “list of whole numbers,” which usually means non-negative integers.
    - If numbers are non-negative, I don’t need to worry about negative values in calculations or checking for negative complements

5. Can the same number be used in a pair with itself? For example if "numbers" = [5, 5] and "target" = 10, would that be 1 pair?
    - The examples don’t show duplicate entries in the inputs, but as long as the number appears in the list twice nothing shows that it would be invalid. I will assume that a number can be paired with itself if it appears in "numbers" at least twice and the sum equals "target".

6. How should the function handle an empty list?
    - There are no values to try to sum, so I will assume that we will return 0 since no pairs can be summed to reach the target.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 068f00d6-4519-454f-a913-80216d9e26c8
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `pairs_with_a_given_sum` for the nominal and edge cases you identified in the first step.

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
# example input 1: numbers = [1, 2, 4, 5], target = 6            
# expected output 1: pairs_with_a_given_sum(numbers, target) = 2

# example input 2: numbers = [1, 2, 4, 5, 1], target = 6  
# expected output 2: pairs_with_a_given_sum(numbers, target) = 2 (assumption: the number 5 can only be used in one pair)

def test_pairs_with_a_given_sum_finds_two_pairs():
    # nominal test case

    # Arrange
    numbers = [1, 2, 4, 5]
    target = 6

    # Act
    result = pairs_with_given_sum(numbers, target)

    # Assert
    assert result == 2

def test_pairs_with_a_given_sum_finds_two_pairs_with_duplicate_number():
    # edge test case
    
    # Arrange
    numbers = [1, 2, 4, 5, 1]
    target = 6

    # Act
    result = pairs_with_given_sum(numbers, target)

    # Assert
    assert result == 2 
```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 03d126b0-86dc-49db-9647-563c37c3711b
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `pairs_with_given_sum` as if you were talking through the details with another developer who will have to implement the function. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency.
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

Example Steps for an O(n<sup>2</sup>) approach: 

1. Create an empty set to store the indices of numbers we use to make pairs and initialize a counter at zero.
2. Loop through the input `numbers` from the first number to the second last number
3. Create a nested loop that starts one index past the current index of the outer loop. It should iterate until the last number in the input `numbers`. Each iteration:
    - Check if the current indices of the outer and inner loops are already in the set of used indices. 
        - If either index has been used, continue.
    - If both indices have not been used, check if the current value of the outer loop summed with the current value of the inner loop is equal to the `target`. 
        - If so, increment a counter by 1 and add the current indices of the outer and inner loop to the set of used indices.
4. Return the value of the counter

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 772ff0fe-4cf0-47be-a386-fbb427f5d9a0
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

One strength the AI tool identified was that my explanation provided a clear implementation roadmap. Specifically, it stated that my "steps are detailed enough to code from". I think this aspect of my explanation was effective because one of my goals was to develop an approach that I could reliably follow while coding. By breaking the solution into sequential steps, I reduced the chances of getting lost during implementation. 

<br>

One improvement recommended was that I should be more careful about assumptions that are not explicitly stated in the prompt. In particular, it questioned my decision to use a set to store used indices to prevent numbers from being included in more than one pair. Looking back, the part of my explanation that would benefit most from strengthening is the justification for introducing that constraint. If I were rewriting my explanation, I would explicitly acknowledge that the problem statement does not clarify whether numbers can be reused across multiple valid pairs. I would then either state my assumption clearly or choose an approach that aligns more closely with the wording of the prompt. Making my reasoning explicit would help the interviewer understand that I am intentionally interpreting the requirements rather than accidentally overlooking alternative interpretations. Instead of "I use a set of used indices", I could say "I'm using this set because I'm assuming indices shouldn't be reused across pairs"

<br>

I believe the suggestion that I should proactively mention more efficient solutions is unnecessary for this problem. The prompt did not ask for an optimized solution, and the interview context was described as entry-level and focused on the details present in the prompt. In introductory algorithm discussions, it is generally acceptable to present a correct brute-force approach first, especially when explaining one's thought process. According to class guidance, correctness and clear reasoning should take priority before discussing optimizations. Therefore, while being aware of more efficient approaches can be beneficial, I do not think failing to mention them should be viewed as a weakness in this particular context.

<br>

The feedback that surprised me most was the distinction between describing what my algorithm does and explaining why I made certain design choices. For example, the AI suggested that instead of simply stating that the inner loop starts one position ahead of the outer loop, I should explain that this ensures each unique pair is evaluated exactly once. This shifted my understanding of interview explanations because I realized that interviewers are not only evaluating whether I can produce an algorithm, but they are also assessing whether I understand the reasoning behind each step. In future explanations, I want to focus more on connecting my decisions to the problem requirements so that my understanding is more visible to the interviewer.

<br>

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->
