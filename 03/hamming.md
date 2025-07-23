# Hamming

## Problem Statment

Imagine working on software that analyzes mutations in DNA.

Create a function named `hamming_distance` that calculates the number of differences between two DNA strands (aka two strings). This method should take in two different DNA strands as inputs and the return value should be the number of differences between each string. 
- Input strings are guaranteed to be non-empty and only contain the characters “G”, “A”, “T”, & “C”. 
- A hamming distance can only be calculated if the inputs are the same length. 

For example, given these two DNA strands (strings), `hamming_distance` should return `7` because there are 7 differences:

|Example Input | Expected Ouput |
|--|--|
|`strand1 = "GAGCCTACTAACGGGAT"` <br> `strand2 = "CATCGTAATGACGGCCT"` | `7`|

Explanation:
```
Strand #1:   GAGCCTACTAACGGGAT
Strand #2:   CATCGTAATGACGGCCT
Differences: ^ ^ ^  ^ ^    ^^
             7 in total
```

(This problem is sourced from [http://rosalind.info/problems/hamm/](http://rosalind.info/problems/hamm/))

## Prompts

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 733d51d0-bad2-4a5c-8475-68dc11e91618
* title: Describe Your Understanding
* topics: pse
##### !question

Before you begin solving this problem, take a moment to think like a professional software engineer. 
- What do we know about the problem? 
- What assumptions can we make based on the information in the problem statement? 
- What further information do the example inputs and outputs give us?
- What questions would you ask a teammate, product manager, or interviewer to better understand the problem before writing any code?

<br>

In the box below, list 5 or more observations about the problem or questions whose answers would clarify the problem statement. For each observation or question, include information on why that observation is important or why you are asking the question
- For each observation, answer how that observation will affect your approach to the problem
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

1. In the problem statement is says "...two DNA strands (aka two strings)" and "This method should take in two different DNA strands as inputs..."
    - This tells me that the function `hamming_distance` should have two inputs that are both strings.

2. The problem statement says that we are calculating the number of differences between two DNA strands and that the return value should be the number of differences between each string.
    - This tells me that we need to compare two string inputs and the function will return a numeric type. 
    - Since we are counting differences which are typically whole numbers, and the example shows a return value of "7", I'm inferring that we should return an integer.

3. The problem statement guarantees that the two inputs will be non-empty and only contain the characters “G”, “A”, “T”, & “C”.
    - This means I can trust that the inputs will always contain one or more character that we can compare
    - The strings should should contain only uppercased letters.

4. What should we do if the inputs are not the same length? There is a note in the problem statement that a hamming distance can only be calculated if the inputs are the same length. 
    - Nothing in the problem statement says that the inputs are guaranteed to be the same length. This means that we might need to check if they are the same length before trying to compare the strings. For this problem, if the input strings are not the same length, I will raise an error.

5. Looking at the example and explanation, the return value should be the number of characters that are different between the two strings. The explanation of the example points out the indices where each charater is different. 
    - We need to compare the inputs character-by-character at the same position in each string, to find the differences. This means we need to choose a loop that will allow us to iterate over both strings at the same time. 

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: dc680be5-2c7f-4d23-8540-c506b2da7cf1
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

I got feedback that my observations show I’m thinking critically about what’s guaranteed (like valid DNA characters) and what’s left open (like string length). I was also commended for using the example to reason about how character-by-character comparisons might work. 

<br>

One suggestion was to be more precise with language, like clarifying that “different” strands just means “two inputs,” not that they must differ in content. Another improvement I could make is explaining why I’d raise an error for unequal string lengths. The feedback also gave me ideas for new questions to ask, like clarifying whether inputs are guaranteed to be uppercased. I was encouraged to continue considering edge cases as I move forward.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: cbb95ff3-17ef-438b-9f84-755a3d184ab8
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `hamming_distance` for the nominal and edge cases you identified in the first step.

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
# example input 1: strand1 = "GAGCCTACTAACGGGAT", strand2 = "CATCGTAATGACGGCCT"
# expected output 1: hamming_distance(strand1, strand2) = 7

# example input 2: strand1 = "GAG", strand2 = "G"
# expected output 2: ValueError: Strands must be the same length

def test_hamming_distance_counts_correct_number_diffs():
    # nominal test case

    # Arrange
    strand1 = "GAGCCTACTAACGGGAT"
    strand2 = "CATCGTAATGACGGCCT"

    # Act
    result = hamming_distance(strand1, strand2)

    # Assert
    assert result == 7

def test_hamming_distance_raises_error_for_unequal_lengths():
    # edge test case

    # Arrange
    strand1 = "GAG"
    strand2 = "G"

    # Act/Assert
    with pytest.raises(ValueError):
        hamming_distance(strand1, strand2)   
```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 4d19dc79-3595-4e24-a88a-78b007805cfb
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `hamming_distance` in enough detail that another developer could reasonably implement a solution. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency. 
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

1. Check if the input strings are the same length.
    - If they're different lengths, raise an exception
2. Initialize a counter variable to keep track of the number of differences between the inputs
3. Loop over both strings at the same time comparing the characters at each index
    - At each index, check if the characters in each string are the same
       - If they are different, increment the counter variable by 1
4. When the loop finishes, return the counter variable

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 90d0876e-eb2e-4dac-80d2-4e0717db3a8f
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

The AI tool gave positive feedback that I included a length check before doing any comparison. One suggestion was to clarify how the loop compares the two strings, specifically that Hamming distance relies on comparing characters at the same index. Making that change could better show I understand both the logic and the reasoning behind the algorithm. 

<br>

Other suggestions were to expand the initialization step to explain what the counter is tracking and soften how I phrased the error condition (to leave room for interpretation depending on the context or language). Overall, they said my steps were strong and that another developer could follow them, but that small clarifications would make my explanation more precise and reliable. 

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->
