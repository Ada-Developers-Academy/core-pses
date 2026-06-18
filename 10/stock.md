# Best Time to Sell Stock

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

Without writing code, describe how you would implement `max_profit` as if you were talking through the details with another developer who will have to implement the function. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency. 
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

1. Create a variable to accumulate the total profit initialized to 0.
2. Loop over the input prices:
   1. For each index of prices, check if the value at the next index is greater than the value at the current index. If the value at the next index is greater, that means a profit can be made. 
   2. If a profit can be made, add the difference between the next value and the current value to the variable that's accumulating our total.
3. When the loop over the input prices is complete, return the accumulator variable

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: a2827252-eb6f-4dd8-b826-d0452ecd8f37
* title: Review Logical Steps
* topics: pse
##### !question

We want to know if we are laying out an approach to the coding problem that makes sense for our context and if that approach is clearly conveying our thoughts on technical topics to others. While we build our skills in breaking down and describing algorithms, let’s an AI tool like ChatGPT to review the Logical Steps we wrote above. Our goals are to check if the steps:
- convey the technical concepts and requirements of the problem in a way that another person can understand
- make sense of the problem being solved
- are not missing important steps or scenarios
- are agnostic of any particular language - the steps should not include code syntax 

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

One strength the AI tool pointed out was that I clearly established an accumulator variable initialized to zero before beginning the loop. The feedback noted that starting with a defined baseline makes it easy for another developer to understand where the running total lives and ensures the function handles the case where no profitable trades are possible. I think this was effective because it shows that I was thinking about the initial state of the algorithm before describing the loop logic, which helps prevent confusion about where the profit value comes from.

<br>

One improvement the AI recommended was being more explicit about the loop boundary. In my steps, I said to "loop over the input prices" and check if the value at the next index is greater than the current index, but I did not specify that the loop should stop before the last element. Because the comparison always looks one position ahead, iterating all the way to the last index would attempt to access a position that does not exist. If I were rewriting my steps, I would specify that the loop runs from the first index up to but not including the last index, so the next-day comparison is always valid.

<br>

One piece of feedback I believe was inaccurate was the suggestion that my steps did not address the edge case of a non-increasing price list. The feedback implied I needed an explicit step for this scenario. However, my steps already handle it implicitly: if the next value is never greater than the current value, the condition in step 2 is never true, the accumulator remains at zero, and zero is returned. Since the behavior is a natural consequence of the described logic rather than a gap, I think the AI was flagging something that does not require a separate step.

<br>

One suggestion that stood out to me was the recommendation to explain *why* capturing every individual upward move across consecutive days produces the maximum total profit, not just *that* we should do it. The AI noted that stating the comparison and profit-adding steps without the reasoning behind them could leave an interviewer uncertain whether I understood the strategy or was just pattern-matching. This shifted my thinking about interview communication because I realized that a roadmap step can be technically correct but still miss an opportunity to demonstrate understanding. If I were revising my explanation, I would add a note that summing every positive day-over-day difference is equivalent to finding the best overall buy-and-sell sequence, because holding through a rise and selling immediately then rebuying yields the same result as a single longer hold.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->