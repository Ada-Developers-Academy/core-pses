# Highest Rated

## Problem Statement

Imagine working on software that deals with restaurant reviews.

Create a function named `get_highest_rated` that is responsible for finding the highest-rated restaurant.

This function should take in a list of dictionaries named `restaurants` as a parameter. Each dictionary represents the data associated with a restaurant, including its rating. This function should have a return value of the restaurant with the highest rating.

### Example Input/Output

<!--- ***Remember to Update this in the checkpoint if it's changed here -->

|<div style="width:200px">Input (Argument of the function)</div>|<div style="width:200px">Expected Output <br> (Return value of the function)</div> |<div style="width:400px">Explanation</div> |
| -- | -- | --|
| `restaurants = [{"name": "Grillby's", "rating": 1}, {"name": "Crow's Nest", "rating": 5}]` | `{"name": "Crow's Nest", "rating": 5}`         | There are two restaurants: "Grillby's" and "Crow's Nest." The rating of "Grillby's" is `1`, and the rating of "Crow's Nest" is `5`. "Crow's Nest" has the highest rating. The return value of this function should be a dictionary, which contains the name and rating of this restaurant. |
| `restaurants = [{"name": "Crow's Nest", "rating": 1}]` | `{"name": "Crow's Nest", "rating": 1}`         | There is one restaurant in the input. Its name is "Crow's Nest," and its rating is `1`. Even though there's only one restaurant, it has the highest rating in this list! The return value of this function should be a dictionary, which contains the name and rating of "Crow's Nest." |
| `restaurants = []`                              | `None`                                         | The input is an empty list, which means that there are zero restaurants. Because there are _no_ restaurants at all, the output, or return value, of this function should be `None`. <br> *This is a common edge case to consider. In this case, it is provided. Often, behavior for this sort of edge case will need to be clarified by you!* |

## Prompts

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 00337d8b-9f33-43d8-8821-b6c0d8b3369f
* title: Gather Information
* topics: pse
##### !question

Use the box below to describe your understanding of the problem. Format the information in whatever way makes sense for you to organize your thoughts and review the contents as you continue with the upcoming prompts. Consider:
- What do we know about the problem? 
- What assumptions can we make based on the information in the problem statement? 
- What further information do the example inputs and outputs give us?

##### !end-question
##### !hint

Further questions to ask as you read through the problem statement and examples:
- What is the goal of the function?
- What are the types of the expected inputs and outputs?
- Are there any restrictions on any of the inputs?
- What do the examples show us about the values that are allowed or invalid for our inputs?
- What do the examples tell us about the return value in different scenarios?

##### !end-hint
##### !explanation 

We want to pull as much information out of the prompt and into a format that is easy for us to review and use to organize our thoughts. One of many possible examples of what this could look like:

<br>

Based on the problem statement I see that I am creating a function named `get_highest_rated`. In this function:
- There is one parameter, a list where each element is a dictionary
- Our return value is the restaurant with the highest rating

<br>

Based on the examples I see:
- Each dictionary in the input contains a `name` and `rating` key
- The function should return the whole dictionary that represents a particular restaurant, not just the name
- The input list could have a single element or no elements
- If there are no elements in the input list, I should return `None` since there is no restaurant to return.


##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: d10ece96-af0b-4f22-a55d-b630ea9b582f
* title: Ask Clarifying Questions
* topics: pse
##### !question

Before you begin solving this problem, take a moment to think like a professional software engineer. What questions would you ask a teammate, product manager, or interviewer to better understand the problem before writing any code? 

<br>

List three or more questions whose answers would clarify the problem statement. For each question:
- Include information on why we are asking the question - what are we hoping to clarify by asking this?
- Provide an answer which includes the effect your decision would have on how you would approach the problem.

<br>

As you come up with questions, assume that error handling for invalid data is managed outside the function. We want to focus on questions that affect the core behavior of the function we will write.

##### !end-question
##### !hint

- Reflect on what you stated about the problem above, what questions would give you new information?
- Assume error handling for invalid data is managed outside the function. 

<br>

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)

##### !end-hint
##### !explanation 

Example clarifying questions and reasoning:

1. What should the function return if there are multiple restaurants tied for the highest rating?
    - There could be multiple restaurants with the same rating, I want to know if it is important whether we return the first found vs. last found
    - I will return the first restaurant found with the highest rating
2. Can the `rating` value be a float, or will it only ever be an integer?
    - I want to know if we need to consider fractional numbers at all when designing our implementation
    - I will assume the rating will only be integers as in the examples
3. Can the list contain duplicate restaurant entries (same name and rating)?
    - I want to know if fully duplicate restaurants should be filtered out or considered like any other restaurant
    - I will assume that we are given a list of unique restaurants with no duplicates
4. How should the function handle non-numerical values for `rating`?
    - We cannot compare two restaurants if the rating is missing, I want to know if we should try to convert the value to a number, skip the restaurant, or raise an error
    - Since this is around error handling, I will assume error handling has been managed outside the function and that the data received by the function has a valid format
 
##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

### !challenge
* type: paragraph
* id: f9ad5047-e187-4213-9a8a-fae368cf813b
* title: Review Clarifying Questions
* topics: pse
##### !question

While we build our skills in breaking down a problem and choosing clarifying questions, let’s use an external tool like ChatGPT to review the questions we wrote above. Our goals are to: 
- ensure we are asking questions that will tell us new information about the problem space
- check our understanding of the information we expect to get from those questions
- uncover other questions that could be useful to ask
- understand why those other questions could be helpful

<br>

For this question we will:
1. Build a prompt using [the template linked here](../shared-resources/questions-review-prompt-template.md)
2. Share the prompt with an AI tool like ChatGPT
3. Hold a discussion with the tool to ensure our understanding of what new information we would get from the initial questions submitted, and what other questions we might want to ask.
4. Reflect on the information shared by the AI tool and summarize its findings

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
- Did ChatGPT uncover anything about the questions you asked that you hadn’t considered?
- Did ChatGPT suggest updates to the questions you asked? 
    - If so, what updates and why?
- Did ChatGPT suggest any new questions?
    - If so, what questions and why would they be useful?

##### !end-hint
##### !explanation 

Everyone’s questions and conversation with ChatGPT will be a little different, and thus the summaries will look a little different. 

<br>

As an example, let’s say we used the questions and explanations from the “Explanation” section of the previous question to create our prompt. Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat link: https://chatgpt.com/share/682fa7c7-6de0-8005-9377-11396b70c984 

<br>

In the chat above, ChatGPT helped me confirm that I am asking about edge cases that are missing in the description, and that the questions I’m asking are relevant to the problem I am trying to solve.

<br>

I discovered that there are follow up questions or tweaks to my initial questions that could give even more clarity than I was thinking about, like asking if returning one restaurant is sufficient, or if returning all tied restaurants is acceptable when there is a tied highest rating. 

<br>

They are mostly related to data validation rather than the core problem, but ChatGPT did also uncover questions I had not thought of, such as asking if ratings can be floats or if they will always be integers like in the examples since that could affect if there is precision or rounding we need to manage.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 890d7045-28cb-4832-812b-d65803ce2618
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `get_highest_rated` for the nominal and edge cases you identified in the first step.

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
# example input 1:     
# restaurants = [
#    {"name": "Grillby's", "rating": 1},
#    {"name": "Crow's Nest", "rating": 5}
# ]
# expected output 1: {"name": "Crow's Nest", "rating": 5}

# example input 2: [{"name": "Crow's Nest", "rating": 1}]
# expected output 2: {"name": "Crow's Nest", "rating": 1}

def test_picks_highest_rated_from_list():
    # nominal test case

    # arrange
    restaurants = [
            {"name": "Grillby's", "rating": 1},
            {"name": "Crow's Nest", "rating": 5}
        ]

    # act
    output = get_highest_rated(restaurants)
    
    # assert
    assert output == {"name": "Crow's Nest", "rating": 5}

def test_picks_from_list_of_one():
    # edge test case

    # arrange
    restaurants = [{"name": "Crow's Nest", "rating": 1}]

    # act
    output = get_highest_rated(restaurants)
    
    # assert
    assert output == {"name": "Crow's Nest", "rating": 1}

def test_returns_none_with_zero_restaurants(self):
    # edge test case

    # arrange
    restaurants = []

    # act
    output = get_highest_rated(restaurants)
    
    # assert
    assert output is None
```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 085ad8a1-7dbd-49ad-aa7a-2213dd0d3c76
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `get_highest_rated` in enough detail that someone else could write the code. 

As you write your steps, keep the following guidelines in mind:
* We want to think about a general approach rather than what the code would look like line-by-line. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. 
    * For example: 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* The steps should be a description as if you were talking out the problem with another person and should be agnostic of any particular language. 
    * As such, they should not include code syntax in the description.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question
##### !placeholder

Write the logical steps here.

##### !end-placeholder
### !explanation

Example Steps:

1. Check if restaurants is empty
    - if it's empty, return `None`
2. Set `highest_rated` to the first element in `restaurants`
3. Loop through restaurants and compare the current resturant rating to the `highest_restaurant` rating.
    - If the current restaurant rating is higher, assign it to `highest_restaurant`
4. Return `highest_rated`

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 3237e637-3679-4302-bac2-3ac3f11da0d1
* title: Review Logical Steps
* topics: pse
##### !question

We want to know if we are laying out an approach to the coding problem that makes sense for our context and if that approach is clearly conveying our thoughts on technical topics to others. Let’s once more use ChatGPT, this time to review the Logical Steps we wrote above. Our goals are to check if:
- the steps make sense for the problem being solved
- the steps are not missing important steps or scenarios
- the steps are agnostic of any particular language – steps should not include code syntax.
- the steps are written with enough detail for another person to understand how to create a solution to the problem description

<br>

For this question we will:
1. Build a prompt using [the template linked here](../shared-resources/steps-review-prompt-template.md)
2. Share the prompt with an AI tool like ChatGPT
3. Hold a discussion with the tool to ensure our Logical Steps meet the goals listed above and understand areas where we could add clarity or better meet our goals
4. Reflect on the information shared by the AI tool and summarize its findings

<br>

In the box below, please submit:
1. A shareable link to your conversation in ChatGPT
   - [Documentation for creating a shareable link in ChatGPT](https://help.openai.com/en/articles/7925741-chatgpt-shared-links-faq)
2. Your reflections and summary of the discussion with ChatGPT

##### !end-question
##### !explanation

As an example, let’s say we used the logical steps in the explanation for the question above in our prompt. Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat Link: https://chatgpt.com/share/682fa890-6278-8005-8e17-085ebb1fea57 

<br>

ChatGPT said the approach was clear, logically structured, and aligned with the problem requirements. It highlighted strengths like language-agnostic phrasing, thoughtful handling of edge cases, and simple, easy-to-follow steps. 

<br>

Suggestions for improvements were things like refining explanations for clarity, especially why certain steps are done, and improving the iteration logic by starting from the second item in the list. Overall, ChatGPT suggested minor tweaks to improve clarity and communication, but affirmed that the core approach was solid.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->
