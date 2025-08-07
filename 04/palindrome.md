# Palindrome

## Problem Statment

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
* type: paragraph
* id: 06aaf99b-ff22-47dd-b3b7-4ea930a796f6
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

My feedback said my notes about how input should behave, such as edge cases like empty strings or punctuation, were clear and relevant. 

<br>

Some suggestions for improvement included refining how I describe missing behavior in the examples and calling out inconsistencies between the problem description and the actual examples. I was encouraged to look for mismatches like these and use them to guide clarifying questions. Practicing this can help uncover hidden rules or edge cases early. 

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
# example input 1: s = "kayak"
# expected output 1: check_palindrome(s) = True

# example input 2: s = "Kayak"
# expected output 2: check_palindrome(s) = True

def test_check_palindrome_true_for_single_word_palindrome():
    # nominal test case

    # Arrange
    s = "kayak"

    # Act
    result = check_palindrome(s)

    # Assert
    assert result == True

def test_check_palindrome_ignores_capitalization():
    # edge test case

    # Arrange
    s = "Kayak"

    # Act
    result = check_palindrome(s)

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

Without writing code, describe how you would implement `check_palindrome` in enough detail that another developer could reasonably implement a solution. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency. 
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

The review shared that I’m avoiding code syntax and focusing on behavior, and that my steps all support the overall goal. A few suggestions were around being more specific, such as how I describe the loop. I could clarify that the loop stops as soon as a mismatch is found, and that if the loop finishes without issues, we return `True`.

<br>

I also learned why going only halfway through the string is more efficient. Comparisons only need to go halfway since we check mirrored characters from both ends, which avoids repeat comparisons. Overall, my structure was strong, but adding precision and a few clarifying details would make my explanation easier for others to follow.


##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->