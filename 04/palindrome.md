# Palindrome

## Problem Statement

Imagine working on software that processes text. A palindrome is a word, phrase, or sequence that reads the same backward as forward.

Create a function named `check_palindrome` that determines if a string is a palindrome. This method should take in one string as a parameter. This method should return `True` if the string is a palindrome.

### Examples

| Example Input | Expected Output |
| ---------------------------- | ------------------- |
| `"Hello, world!"`            | `False`             |
| `"nascar"`                   | `False`             |
| `"racecar"`                  | `True`              |
| `"noon"`                     | `True`              |
| `"Mom"`                      | `True`              |
| `"Kayak"`                    | `True`              |

## Prompts

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: b3294ca0-b085-49e7-890f-e839e3a9efac
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

1. The problem statement says we need to determine if the input is a palindrome and that a palindrome is a word, phrase, or sequence that reads the same backward as forward.
    - This tells me that I will have an input that I need to iterate over in such a way that I can check elements at the front and back of the input at the same time.

2. Since a palindrome needs to read the same way backwards as forwards, as I'm iterating, as soon as I find letters that don't match at their corresponding positions, I know the input is not a palindrome.
    - This means that as soon as I find characters that do not match, I can exit the function; I don't need to keep iterating through the input.

3. In the problem statement, I see that I should return `True` if the string is a palindrome. The examples inputs & outputs show both `True` and `False` return values.
    - While the problem statement doesn't explicitly say we should return `False` if the input is not a Palindrome, the examples show me that we should return `False` if we determine the input is not a palindrome.

4. What should the function return if the input is an empty string, `""`?
    - The problem statement and examples don't cover this scenario. Since an empty string is the same backwards as forwards, I will assume that I should return `True`.

5. Taking a look at the examples, I see both lowercased input and input with capitalization at the front that both return `True`.
    - Since palindromes with a single capitalized letter should return `True` according to the examples, I know that whaen I compare letters, the comparison must be case-insensitive.

6. How should the function handle characters that are not letters like punctuation and white space? Is `"kayak!"` a palindrome?
    - Nothing in the problem statement or examples shows that we should ignore characters that are part of the input string. Therefore, I will assume that I should leave any non-alphabetic characters in the input and take them into account when determining if a string is a palindrome.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 3e891984-c84a-4b0c-9e2b-b652391ab7bc
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `check_palindrome` for the nominal and edge cases you identified in the first step.

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
# example input 1: to_check = "kayak"
# expected output 1: check_palindrome(to_check) = True

# example input 2: to_check = "Kayak"
# expected output 2: check_palindrome(to_check) = True

def test_check_palindrome_true_for_single_word_palindrome():
    # nominal test case

    # Arrange
    to_check = "kayak"

    # Act
    result = check_palindrome(to_check)

    # Assert
    assert result == True

def test_check_palindrome_ignores_capitalization():
    # edge test case

    # Arrange
    to_check = "Kayak"

    # Act
    result = check_palindrome(to_check)

    # Assert
    assert result == True  
```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 374a4f64-cb87-4bf5-9faf-8d3199048491
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `check_palindrome` as if you were talking through the details with another developer who will have to implement the function. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency. 
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

Example Steps: 

1. Convert input to lowercase.
2. Loop over the length of the input
3. Start by comparing the first and last element of the input. If the letters are not the same, return `False`. 
    - Each iteration of the loop we will move one character towards the middle of the string and then make the same comparison.
4.  Return `True` once the loop has finished executing. 

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 883f0fbe-2715-4c24-b949-2fdcbe8f9470
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

The AI tool stated that the strongest part of my explanation is Step 3 where I describe comparing elements in the input: "You clearly describe the two-pointer idea without relying on code syntax." I think my explanation was effective because I used clear, plain language to describe the core logic of my algorithm, which is a useful skill for me to develop for technical interviews. 

<br>

The AI tool recommended being more detailed about how I describe Step 2 because my explanation was vague. I said "Loop over the length of the input". The tool called out that an interviewer might ask "Do you actually need to check the entire length?" because my explanation is unclear about what would happen when the loop reaches the middle of the input. To revise Step 2, I would say something like this instead, "Compare characters moving inward until the pointers meet or cross". 

<br>

One piece of feedback that I believe was unnecessary was the discussion about handling punctuation and spaces in phrases such as "A man, a plan, a canal: Panama." The problem statement specifically asks for a function that determines whether a string is a palindrome and provides examples that only establish case-insensitive comparisons, such as "Mom" and "Kayak." According to the principle of deriving requirements from the prompt and examples provided, introducing additional assumptions that are not supported by the specification can unnecessarily complicate a solution. So, while the feedback itself was technically correct, I believe it was unnecessary in the context of evaluating my explanation.

<br>

One suggestion that surprised me was the recommendation to explicitly explain why reaching the middle of the string is sufficient. I had thought of the midpoint primarily as an implementation detail, but the feedback helped me recognize that articulating this reasoning can increase an interviewer's confidence in my understanding. Explaining that "each mirrored pair only needs to be checked once, so comparisons beyond the midpoint would repeat work that has already been done" demonstrates not only what the algorithm does but also why it is efficient.

<br>

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->