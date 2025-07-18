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
##### !hint

Further questions to ask as you read through the problem statement and examples:
- What is the goal of the function?
- What are the types of the expected inputs and outputs?
- Are there any restrictions on any of the inputs?
  - For example: if any of the inputs are a list, do we know anything about how the list is ordered?
- What do the examples show us about the data types and values that are allowed for our inputs?
- What do the examples tell us about the return value in different scenarios?
- Reflecting on the observations you have made so far, what questions would give you new information?

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

2. The problem statment says that we should return the total cost of all items in the list `cart`. 
    - This indicates that we are returning a numeric type. Looking at the examples below, I see prices like "0.75" and "1.25" which tells me that our return value needs to be a float.

3. The problem statement also says that `cart` is a list of strings, not prices.
    - Since `cart` is a list of strings, I will need to use a data structure to hold the prices as floats
    - I need a way to match the strings in `cart` to their price data. 

4. In the prices list, I see that the names of items are capitalized. Does this mean that the list items will always be capitalized?
    - I can assume that the input data is valid, so `cart` should only contain strings with alphabetic characters. 
    - Since I don't know for sure if `cart` could contain lowercase or mixed case names, I can write my function in a way that handles any casing of letters.

5. The problem description and examples do not show what to do if an item in `cart` does not have a price.
    - I could raise an error, but that would prevent summing the rest of the items in `cart`. 
    - Since a customer would likely still want to check out with their items even if one item is not avilable, I will ignore any items that we do not have a rpice for and return the sum for the available items.

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
* type: paragraph
* id: f9ad5047-e187-4213-9a8a-fae368cf813b
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

The feedback I received said I correctly identified key requirements like looping through the cart, handling duplicate items, and matching item names to prices. My assumption that the result should be a float was supported by the examples, and I was thinking critically about edge cases like capitalization and empty carts.

<br>

One of the suggestions was to reframe unclear parts of the prompt—like missing item prices—as questions rather than making assumptions. This will help me stay aligned with the problem’s intent and shows that I understand where decisions should come from.

<br>

Overall, I’m thinking through different scenarios, but I could use practice turning assumptions into thoughtful questions to improve how I approach ambiguous areas.

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


<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
### !challenge
* type: paragraph
* id: 852cbbe5-22f0-4c14-921b-a33a1e10535c
* title: Create Logical Steps
* topics: pse

##### !question

Without writing code, describe how you would implement `calculate_total` in enough detail that someone else could write the code. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps: 

1. Create a dictionary `prices` with key-value pairs for each available item, stored in lower case, and its corresponding price.
2. Initialize a variable named `total` to `0.0`
3. Loop through the items in the list `cart`
    - Check if the current item is in the `prices` dictionary converting each cart item to lower case to compare case-insensitively.
    - If the current item is in `prices`, add the value of the item to the variable `total`
4. Return `total`

### !end-explanation

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->



