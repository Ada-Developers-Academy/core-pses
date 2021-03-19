# Example PSE

Here is an example PSE prompt, an example of answers, and the rubric.

## Example Problem-Solving Exercise: Ratings

Imagine working on software that deals with restaurant reviews. Create a function named `get_highest_rated` that is responsible for finding the highest-rated restaurant. This function should take in a list of dictionaries called `restaurants` as a parameter. Each dictionary represents the data associated with a restaurant, including its rating. This function should have a return value of the restaurant with the highest rating.

Answer the following prompts:

1. List five or more questions whose answers would clarify the problem statement
2. List two sets of example arguments and the expected return value for these arguments
3. Divide the project prompt into at least two different sub-problems
4. Pick one of those problems from #3 and write a numbered list explaining how to solve that problem without using full lines of code
5. Write the pseudocode or code solution for your answer for #4

## Example Answers

### #1 Five or More Clarifying Questions

1.  Should I return the restaurant's name, or the dictionary that represents the restaurant data, or the rating?
1.  What is the name of the key in each dictionary whose value is the rating?
1.  What kind of data-type is rating stored in?
1.  What should happen if there's more than one highest-rated restaurant?
1.  Is the restaurant's name included in this dictionary?
1.  What else is included in each dictionary?
1.  Will there ever be zero restaurants? What should happen?
1.  What should I do if there is no rating?

### #2 Two Example Inputs/Outputs

1.  Example one
    - Input: `[{name: "Grillby's", rating: 1}, {name: "Crow's Nest", rating: 5}]`
    - Output: `{name: "Crow's Nest", rating: 5}`
1.  Example two
    - Input: `[{name: "Crow's Nest", rating: 1}]`
    - Output: `{name: "Crow's Nest", rating: 1}`

### #3 Two Sub-Problems

1.  How do you check/iterate over all of the restaurants?
1.  How do you compare the ratings between restaurants?

### #4 Steps to Solve a Sub-Problem

How to solve "How do you compare the ratings between restaurants":

1.  Have a variable that stores the highest rating named `highest_rating`
1.  Have a variable that stores the rating of a specific restaurant named `rating`
1.  Use the comparison operators to find out if the new restaurant is more highly rated `rating > highest_rating`
1.  If `rating > highest_rating` is `true`, then the rating of this restaurant is rated more highly

### #5 Pseudocode/Code Solution to a Sub-Problem

```python
if rating > highest_rating:
    highest_rating = rating
```

## Rubric

#### Reviewing #1 (list at least 5 questions):

No. 1 is used to stretch minds. It should feel like a lot of questions, and it should be really hard! Most questions are still valid even if these questions challenge very basic assumptions, like "is this a running Python script?" or "is this on a computer?"

- The answer is wrong if there aren't at least 5 questions
- The answer is wrong if there were no questions clarifying the structure of the restaurant dictionary (what are the keys in each dictionary, etc.)

#### Reviewing #2 (2 example input/output):

- The answer is wrong if there aren't 2 examples
- The answer is wrong if either of them aren't valid/consistent with each other
- The answer is wrong if the inputs were not lists, (correct even the lists had one or zero restaurants)

#### Reviewing #3 (2 sub-problems):

- The answer is wrong if there aren't at least 2 sub-problems listed
- The answer is wrong if any of the sub-problems aren't relevant to the original problem

#### Reviewing #4 (List of steps to solve one sub-problem):

- The answer is wrong if it doesn't have at least two steps
- The answer is wrong if it doesn't make sense

#### Reviewing #5 (Code for solving one sub-problem):

The point of this exercise is not fully check if the code is correct at the moment, but to let them practice writing code with their hands.

- The answer is wrong if it is blank
- The answer is wrong if it is obviously incorrect code (ie you wrote `puts "Oops!"` for your entire response)
