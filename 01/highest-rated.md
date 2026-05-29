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
* id: d10ece96-af0b-4f22-a55d-b630ea9b582f
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

##### !end-hint
##### !explanation 

One of many possible responses could look like:

1. In the problem statement I see that the goal of the function is to find the highest rated restaurant 
    - This means I will have some input that I need to compare and I will need some way to track what is the current highest rated element.

2. I also see the line "This function should take in a list of dictionaries named `restaurants` as a parameter." as well as information that the dictionaries will hold the restaurant information including a rating.
    - This means that I will likely need to iterate over the list and look inside each dictionary to make a comparison using the dictionary's `rating` value.

3. This function should have a return value of the restaurant with the highest rating.
    - Since the restaurants are represented by dictionaries, I probably need to return the whole dictionary that represents the highest rated restaurant. This theory is supported by the example inputs & outputs which show a dictionary as the expected return value.

4. The example inputs & outputs show that each dictionary in the input contains a `name` key with a string value and a `rating` key with a numerical value.
    - We can use the numerical value of the `rating` key to make our logical comparisons and find the restaurant with the highest `rating` value.

5. What should the function return if there are multiple restaurants tied for the highest rating?
    - There could be multiple restaurants with the same rating, I want to know if it is important whether we return the first found vs. last found.
    - I will return the first restaurant found with the highest rating.

6. Can the `rating` value be a float, or will it only ever be an integer?
    - This does not change the logical comparisons to check which is higher rated, but it would affect whether I write tests that also confirm everything works as expected with float inputs.
    - I will assume the rating will only be integers as in the examples.

7. Based on the second example input/output, if there is only one element in the list of restaurants, we return the one restaurant.
    - Since there are no other restaurants to compare it to, if there is only one element, it is technically the highest rated restaurant in the input so we return it.

8. Based on the last example input/output if the list is empty, we should return `None`.
    - The list is a valid list, but if there are no elements to compare, the function cannot do its work, so we return `None`. 

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
# example input 1:     
# restaurants = [
#    {"name": "Grillby's", "rating": 1},
#    {"name": "Crow's Nest", "rating": 5}
# ]
# expected output 1: {"name": "Crow's Nest", "rating": 5}

# example input 2: [{"name": "Crow's Nest", "rating": 1}]
# expected output 2: {"name": "Crow's Nest", "rating": 1}

def test_get_highest_rated_returns_highest_rated_of_two():
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

def test_get_highest_rated_one_restaurant_returns_dict():
    # edge test case

    # arrange
    restaurants = [{"name": "Crow's Nest", "rating": 1}]

    # act
    output = get_highest_rated(restaurants)
    
    # assert
    assert output == {"name": "Crow's Nest", "rating": 1}

def test_get_highest_rated_empty_list_returns_none():
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

Without writing code, describe how you would implement `get_highest_rated` as if you were talking through the details with another developer who will have to implement the function. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency. 
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

1. Check if the input `restaurants` is empty
    - If it's empty, return `None`
2. Set a variable `highest_rated` to the first element in `restaurants`
3. Loop through `restaurants` and compare the current resturant rating to the `highest_rated` rating.
    - If the current restaurant rating is higher, assign it to `highest_rated`
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

The AI pointed out that handling the edge case first was "the right instinct." I think this worked well in my explanation because addressing the empty list scenario at the very start of my steps mirrors how the code itself should behave. It acts like a guard clause that prevents any of the later logic from running on bad input. Putting it first also makes the flow easier to follow, since a reader doesn't have to keep an empty-list exception in the back of their head while reading the rest of the steps.

<br>

The AI flagged that Step 2 was missing a "why." Looking back at what I wrote, "Set a variable `highest_rated` to the first element in `restaurants`", I can see that I described the action without explaining the reasoning behind it. If I were rewriting it, I'd say something like: "Set `highest_rated` to the first element in `restaurants` so that we have a valid restaurant dictionary as our starting benchmark. This way, every comparison in the loop is between two real restaurants, and we avoid needing extra logic to handle a placeholder value like `None`."

<br>

The AI suggested that starting my loop at index 1 instead of index 0 would be "cleaner," and implied this is an inefficiency I should address. I'd push back on this for our class context. For a junior-level problem with small lists, readability and simplicity outweigh micro-optimization, and my instructors have emphasized that clear, working code comes before optimization at this stage. Calling it an "inefficiency" sets an expectation that isn't really proportionate to the problem.

<br>

I hadn't thought deeply about the difference between initializing `highest_rated` to the first element versus something like `0` or `None`. This shifted how I think about what the variable is actually supposed to hold throughout the function. The AI explained that if I initialized to `0`, my comparison in the loop would be between a number and a dictionary, which would either cause an error or require extra conditional logic. That surprised me because I probably would have instinctively used `0` as a starting value since I was thinking about ratings as numbers; I wasn't thinking about the fact that I need to return the whole dictionary, not just the rating. 

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->
