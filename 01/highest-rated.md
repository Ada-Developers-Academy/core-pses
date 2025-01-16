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

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: d10ece96-af0b-4f22-a55d-b630ea9b582f
* title: Ask Clarifying Questions
* topics: pse
##### !question

List three or more questions whose answers would clarify the problem statement. For each question, provide an answer which includes the effect your decision would have on how you would approach the problem.

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)

##### !end-hint
##### !explanation 

Example clarifying questions:

1. What should the function return if there are multiple restaurants tied for the highest rating?
1. How should the function handle restaurant dictionaries with missing data (name or rating)?
1. How should the function handle restaurant dictionaries with keys in addition to `"name"` and `"rating"`?
1. How should the function handle non-numerical values for `"rating"`?
1. How should the function handle input that is a single dictionary (not a list)?
 
##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
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

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 085ad8a1-7dbd-49ad-aa7a-2213dd0d3c76
* title: Create Logical Steps
* topics: pse

##### !question

Without writing code, describe how you would implement `get_highest_rated` in enough detail that someone else could write the code. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere inbetween. What's important at this stage is to think through and outline the implementation before writing code.

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

<!-- ======================= END CHALLENGE ======================= -->

