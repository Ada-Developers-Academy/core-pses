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

| Input (Parameters of the function)                                           | Expected Output (Return value of the function) |
| ---------------------------------------------------------------------------- | ---------------------------------------------- |
| `[{"name": "Grillby's", "rating": 1}, {"name": "Crow's Nest", "rating": 5}]` | `{"name": "Crow's Nest", "rating": 5}`         |
| `[{"name": "Crow's Nest", "rating": 1}]`                                     | `{"name": "Crow's Nest", "rating": 1}`         |
| `[]`                                                                         | `None`                                         |

### !end-question
### !placeholder

```python
def get_highest_rated():
    pass
```
### !end-placeholder
### !tests
```python
import unittest
from main import *

class TestChallenge(unittest.TestCase):
    def test_picks_highest_rated_from_list(self):
        restaurants = [{"name": "Grillby's", "rating": 1},
                       {"name": "Crow's Nest", "rating": 5}]

        output = get_highest_rated(restaurants)
        self.assertEqual(output["name"], "Crow's Nest")
        self.assertEqual(output["rating"], 5)
        self.assertEqual(len(output.keys()), 2)

    def test_picks_from_list_of_one(self):
        restaurants = [{"name": "Crow's Nest", "rating": 1}]

        output = get_highest_rated(restaurants)
        self.assertEqual(output["name"], "Crow's Nest")
        self.assertEqual(output["rating"], 1)
        self.assertEqual(len(output.keys()), 2)

    def test_returns_none_with_zero_restaurants(self):
        restaurants = []

        output = get_highest_rated(restaurants)
        self.assertIsNone(output)
```
### !end-tests
### !rubric

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

### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->
