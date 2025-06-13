# Implement Highest Rated

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 95b91049
* title: PSE
* points: 3
### !question

Imagine working on software that deals with restaurant reviews.

Create a function named `get_highest_rated` that is responsible for finding the highest-rated restaurant.

This function should take in a list of dictionaries named `restaurants` as a parameter. Each dictionary represents the data associated with a restaurant, including its rating. This function should have a return value of the restaurant with the highest rating.

<!--- ***Remember to Update this in highest-rated.md if it's changed here -->

| Input (Parameters of the function)                                           | Expected Output (Return value of the function) |
| ---------------------------------------------------------------------------- | ---------------------------------------------- |
| `restaurants = [{"name": "Grillby's", "rating": 1}, {"name": "Crow's Nest", "rating": 5}]` | `{"name": "Crow's Nest", "rating": 5}`         |
| `restaurants = [{"name": "Crow's Nest", "rating": 1}]`                                     | `{"name": "Crow's Nest", "rating": 1}`         |
| `restaurants = []`                                                                         | `None`                                         |

### !end-question
### !placeholder

```python
def get_highest_rated(restaurants):
    pass
```
### !end-placeholder
### !tests
```python
import unittest
from main import *

class TestChallenge(unittest.TestCase):
    def test_get_highest_rated_returns_highest_rated_when_last(self):
        restaurants = [{"name": "Grillby's", "rating": 1},
                       {"name": "Crow's Nest", "rating": 5}]

        output = get_highest_rated(restaurants)
         
        self.assertEqual(output["name"], "Crow's Nest")
        self.assertEqual(output["rating"], 5)
        self.assertEqual(len(output.keys()), 2)


    def test_get_highest_rated_returns_highest_rated_when_first(self):
        restaurants = [{"name": "Communion", "rating": 5},
                       {"name": "Fat's Chicken", "rating": 4}]

        output = get_highest_rated(restaurants)

        self.assertEqual(output["name"], "Communion")
        self.assertEqual(output["rating"], 5)
        self.assertEqual(len(output.keys()), 2)

    def test_get_highest_rated_returns_highest_in_middle_of_list(self):
        restaurants = [{"name": "A guy on the street giving away granola bars", "rating": 1},
                       {"name": "Soul", "rating": 4},
                       {"name": "Dick's", "rating": 2}]

        output = get_highest_rated(restaurants)

        self.assertEqual(output["name"], "Soul")
        self.assertEqual(output["rating"], 4)
        self.assertEqual(len(output.keys()), 2)

    def test_get_highest_rated_one_restaurant_returns_dict(self):
        restaurants = [{"name": "Crow's Nest", "rating": 1}]

        output = get_highest_rated(restaurants)
        self.assertEqual(output["name"], "Crow's Nest")
        self.assertEqual(output["rating"], 1)
        self.assertEqual(len(output.keys()), 2)

    def test_get_highest_rated_empty_list_returns_none(self):
        restaurants = []

        output = get_highest_rated(restaurants)
        self.assertIsNone(output)
```
### !end-tests
### !explanation

An example of a working implementation:

```python
def get_highest_rated(restaurants):
    if not restaurants:
        return None

    highest_rated = restaurants[0]
    for restaurant in restaurants:
        if restaurant["rating"] > highest_rated["rating"]:
            highest_rated = restaurant

    return highest_rated
```

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->
