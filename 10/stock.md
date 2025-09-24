# Best time to sell Stock

You are given an integer array `prices` that represents the cost of a stock across a sequence of days. `prices[day]` is the price of a given stock on that day.
- On each day, you may decide to buy and/or sell the stock. 
- You can only hold one share of the stock at any time. 
- You can buy the stock and then immediately sell it on the same day.

Find and return the maximum cumulative profit you can achieve.

**Example 1:**

```
Input: prices = [7, 1, 5, 3, 6, 4]
Output: 7

Explanation: 
- Buy on day 2 (price = 1) and sell on day 3 (price = 5) 
    • profit = 5 - 1 = 4.
- Buy on day 4 (price = 3) and sell on day 5 (price = 6)
    • profit = 6 - 3 = 3.

Total profit is 4 + 3 = 7.
```

**Example 2:**

```
Input: prices = [1, 2, 3, 4, 5]
Output: 4

Explanation: 
- Buy on day 1 (price = 1) and sell on day 5 (price = 5)
    • profit = 5 - 1 = 4.

Total profit is 4.
```

**Example 3:**

```
Input: prices = [7, 6, 4, 3, 1]
Output: 0

Explanation: 
- There is no way to make a positive profit, so
  we never buy the stock to achieve the maximum 
  profit of 0.
```

Sourced from: [Leetcode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)

## Prompts

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: cd479b36-b9c5-40d8-8c8c-1befa3de6174
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

1. Our input is a list of the prices of a stock over a certain number of days, and we need to find where we can make a profit. 
    - To find where we can profit, I will need to iterate over the input and compare the value for a day against the value for the next day to see if a profit can be made. 

2. I need to return the maximum cumulative profit across the days of data provided. 
    - Since it is a cumulative profit, I will need a variable to collect the total profit in as I iterate through the input list. 

3. There are no examples or mention in the problem description for how to handle a valid but empty list. How should the function handle an empty list?
    - Since there are no prices for the stock to compare, I will assume that I should return 0 since there is no way to generate a profit.

4. The problem statement only mentions integers, can numbers in the input list be negative?
    - In general things for sale do not have a negative cost, so I will assume that the input will only contain positive integers.

5. Is there any limit to how many times I can buy or sell the stock?
    - This would impact whether I need to find the best out of a certain number of possible transactions. In a real world scenario there might be restrictions, but the problem statement says we can buy and/or sell the stock each day. This means I can focus on tracking the total for all profitable transactions, I don't need to keep data about which transaction is the best. 

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: a3bd7eff-6c26-4e8b-b3db-210e433ebfd2
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

ChatGPT shared that asking about empty lists was called a smart edge-case question, and my assumption that the result should be `0` matched common practice. My point about negative prices was valid, since clarifying input constraints avoids misinterpretation. The reviewer suggested extra questions I could add, like what happens if there’s only one day of prices, whether days are guaranteed to be consecutive, or if transaction history matters.

<br>

The first couple suggestions for ChatGPT seem useful, but since the retun value is pretty explicit for this problem, clarifying the transaction history doesn't feel very applicable or helpful for this problem. I asked about why it's useful to clarify between the empty list and one element list cases and was told that simple cases like a one-day input can be worth clarifying, since it exposes implicit assumptions and distinguishes between the cases where there is no data and when there is not enough data. 

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 0f72eb75-455c-48ed-9868-337a32e2c86d
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `max_profit` for the nominal and edge cases you identified in the first step.

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
def test_max_profit_nominal_input_can_profit_twice_returns_7():
    # nominal test case
    # Arrange
    stocks = [7, 1, 5, 3, 6, 4]

    # Act
    result = max_profit(stocks)

    # Assert
    assert result == 7

def test_max_profit_empty_input_returns_0():
    # edge test case
    # Arrange
    stocks = []

    # Act
    result = max_profit(stocks)

    # Assert
    assert result == 0

    # Assert
    assert result == []

def test_max_profit_only_decreasing_prices_returns_0():
    # alternative test case
    # Arrange
    stocks = [7, 6, 5, 4, 3, 1]

    # Act
    result = max_profit(stocks)

    # Assert
    assert result == 0

```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 17165b99-d816-42fa-a6da-d6e25265bb92
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `max_profit` in enough detail that someone else could write the code. 

* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps for an O(n) solution:

1. Check for valid input
1. set `total` to `0`
1. set `index` to `1`
1. `while index < len(stocks)`
    *  if `stocks[index - 1] > stocks[index]`
        * `total = total + stocks[index - 1] - stocks[index]` 
    * `index = index + 1`
1. `return total`

### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->
