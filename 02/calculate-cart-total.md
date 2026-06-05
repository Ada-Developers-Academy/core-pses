# Calculate Cart Total

## Problem Statement

Imagine programming the logic for a grocery store's online shopping system. In our scenario, a user has a cart of items, and each item has a cost. 

Create a function named `calculate_total` that is responsible for summing the cost of the items in a user's cart.
* This function should take in a list of strings named `cart` as a parameter. 
* This function should return the total cost of all items in the list `cart`.

Refer to this table for the price of each item carried by the store.

| Item | Price |
| ---- | ----- |
| Apple | $0.75 |
| Beans | $2.00 |
| Cheese | $2.50 |
| Chicken | $4.00 |
| Flour | $1.75 |
| Onion | $0.50 |
| Orange | $0.85 |
| Lettuce | $1.25 |
| Milk | $3.00 |
| Tomato | $0.45 |

### Examples

| Input | Expected Output |
| ----- | --------------- |
| `["Cheese"]` | `2.5` |
| `["Chicken", "Flour", "Milk"]` | `8.75` |
| `["Tomato", "Orange", "Beans", "Apple"]` | `4.05` |
| `[]` | `0.0` |

## Prompts

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 87058b56-6678-4ef9-b1e0-c3ebddeb4bf9
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

<br>

Consider the following for inspiration:
- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Previous PSEs

##### !end-hint
##### !explanation 

One of many possible responses could look like:

1. In the problem statement, I see that the function will take in a list, `cart`, and that the function should sum up the prices of the items in `cart`.
    - This means that I will need to loop over the input `cart` and access each element.
    - I will need to maintain a variable to hold the running total as I loop through `cart`

2. The problem statement says that we should return the total cost of all items in the list `cart`. 
    - This indicates that we are returning a numeric type. Looking at the examples below, I see prices like "0.75" and "1.25" which tells me that our return value needs to be a float.

3. The problem statement also says that `cart` is a list of strings, not prices.
    - Since `cart` is a list of strings, I will need to use a data structure to hold the prices as floats
    - I need a way to match the strings in `cart` to their price data. 

4. In the prices list, I see that the names of items are capitalized. Does this mean that the list items will always be capitalized?
    - I can assume that the input data is valid, so `cart` should only contain strings with alphabetic characters. 
    - Since I don't know for sure if `cart` could contain lowercase or mixed case names, I can write my function in a way that handles any casing of letters.

5. The problem description and examples do not show what to do if an item in `cart` does not have a price.
    - I could raise an error, but that would prevent summing the rest of the items in `cart`. 
    - Since a customer would likely still want to check out with their items even if one item is not available, I will ignore any items that we do not have a price for and return the sum for the available items.

6. Can an item appear in `cart` more than once?
    - The examples don't show duplicate items in the input `cart`, but there is nothing in the description that says folks cannot buy multiples of an item. 
    - I will assume that the input `cart` could contain duplicate items, such as "Apple" three times.

7. Based on the last example input/output if the list is empty, we should return `0.0`.
    - The list is a valid list, but if there are no items in the cart to sum prices, the function cannot do its work, so we return `0.0`.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 6aceed45-c06a-498a-9f20-2db592be3469
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `calculate_total` for the nominal and edge cases you identified in the first step.

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
# example input 1: cart = ["Cheese", "Chicken"]
# expected output 1: calculate_total(cart) = 6.5

# example input 2: cart = ["beans", "MILK"]
# expected output 2: calculate_total(cart) = 5.0

# example input 3: cart = ["Lemon", "Onion", "Onion"]
# expected output 3: calculate_total(cart) = 1.0

def test_correct_total_for_all_items():
    # nominal test case

    # Arrange
    cart = ["Cheese", "Chicken"]

    # Act
    result = calculate_total(cart)

    # Assert
    assert result == 6.5

def test_case_insensitive_gives_correct_total():
    # nominal test case

    # Arrange
    cart = ["beans", "MILK"]

    # Act
    result = calculate_total(cart)

    # Assert
    assert result == 5.0

def test_invalid_items_not_added_to_total():
    # edge test case
    
    # Arrange
    cart = ["Lemon", "Onion", "Onion"]

    # Act
    result = calculate_total(cart)

    # Assert
    assert result == 1.0

```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 852cbbe5-22f0-4c14-921b-a33a1e10535c
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `calculate_total` as if you were talking through the details with another developer who will have to implement the function. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency. 
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

1. Create a dictionary to hold the price data. 
    - The keys are the available item names as strings and the values are the prices of those items.
2. Initialize a variable to `0.0` to accumulate our prices sum.
3. Loop through the items in the input list `cart`
    - case-insensitively, check if the current item is in our prices data
    - If the current item is in the price data, add the value of the item to our running total variable. Otherwise ignore the current item and move on.
4. Once the loop ends, return the variable holding the total price

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 3237e637-3679-4302-bac2-3ac3f11da0f3
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

The AI pointed out that my explanation had a clear sequence: define the prices data first, then iterate through the cart, then return the accumulated total. I think this worked well because it reflects the natural flow of the problem, and another developer can quickly understand what needs to happen and in what order.

<br>

The AI recommended I be more explicit about assumptions, especially how unknown item names should be handled. Looking back, my steps implied this but did not clearly state it. If I rewrote the steps, I would add a line that says "Unknown items will be silently ignored so the function still returns a valid total for recognized items".

<br>

The AI suggested that I could sort the cart before processing items to make the logic more consistent. I would treat that feedback as unnecessary for this problem. The total cost is independent of item order, and sorting adds extra work without changing correctness. This aligns with the problem statement, which asks only for the sum of item costs and does not require any ordering behavior.

<br>

One suggestion that I hadn't thought about was to explain why a data structure that maps item names to price is useful, not just that it should be used. That shifted my understanding because I can see that explaining the reasoning behind a step, like fast lookups from item name to price, helps communicate both the approach and the design decision.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->
