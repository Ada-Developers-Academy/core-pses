# Highest Rated

## Problem Statement

Imagine working on software that deals with restaurant reviews.

Create a function named `get_highest_rated` that is responsible for finding the highest-rated restaurant.

This function should take in a list of dictionaries named `restaurants` as a parameter. Each dictionary represents the data associated with a restaurant, including its rating. This function should have a return value of the restaurant with the highest rating.

### Example #1

| Input (Parameter of the function)                                            | Expected Output (Return value of the function) |
| ---------------------------------------------------------------------------- | ---------------------------------------------- |
| `[{"name": "Grillby's", "rating": 1}, {"name": "Crow's Nest", "rating": 5}]` | `{"name": "Crow's Nest", "rating": 5}`         |

There are two restaurants: "Grillby's" and "Crow's Nest." The rating of "Grillby's" is `1`, and the rating of "Crow's Nest" is `5`. "Crow's Nest" has the highest rating. The return value of this function should be a dictionary, which contains the name and rating of this restaurant.

### Example #2

| Input (Parameter of the function)        | Expected Output (Return value of the function) |
| ---------------------------------------- | ---------------------------------------------- |
| `[{"name": "Crow's Nest", "rating": 1}]` | `{"name": "Crow's Nest", "rating": 1}`         |

There is one restaurant in the input. Its name is "Crow's Nest," and its rating is `1`. Even though there's only one restaurant, it has the highest rating in this list! The return value of this function should be a dictionary, which contains the name and rating of "Crow's Nest."

### Example #3

| Input (Parameter of the function) | Expected Output (Return value of the function) |
| --------------------------------- | ---------------------------------------------- |
| `[]`                              | `None`                                         |

The input is an empty list, which means that there are zero restaurants. Because there are _no_ restaurants at all, the output, or return value, of this function should be `None`.

<!-- | Input (Parameters of the function)                                   | Expected Output (Return value of the function) | Explanation                                                                                                                                                                                                                                                                              |
| -------------------------------------------------------------------- | ---------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `[{"name": "Grillby's", "rating": 1}, {"name": "Crow's Nest", "rating": 5}]` | `{"name": "Crow's Nest", "rating": 5}`             | There are two restaurants: "Grillby's" and "Crow's Nest." The rating of "Grillby's" is `1`, and the rating of "Crow's Nest" is `5`. Crow's nest has the highest rating. The return value of this function should be a dictionary, which contains the name and rating of this restaurant. |
| `[{"name": "Crow's Nest", "rating": 1}]`                                 | `{"name": "Crow's Nest", "rating": 1}`             | There is one restaurant in the input. Its name is "Crow's Nest," and its rating is `1`. Even though there's only one restaurant, it has the highest rating in this list! The return value of this function should be a dictionary, which contains the name and rating of "Crow's Nest."  |
| `[]`                                                                 | `None`                                         | The input is an empty list, which means that there are zero restaurants. Because there are _no_ restaurants at all, the output, or return value, of this function should be `None`.                                                                                                      | -->

## Understanding the Problem

The first step to implementing the `get_highest_rated` function is to understand the problem. We need to read through the problem statement carefully to learn about every requirement. Take the time to do the following:

- Take notes about the original problem statement.
- Bold and highlight important pieces of the problem statement.
- Read through each example slowly. Take notes about the similarities and differences between each example.

<br/>

When you're stuck on a question, follow these steps:

1. Check your understanding on all pieces of vocabulary. Look up definitions and examples if you need to.
1. Write down your question. See if there are clues in the original problem statement that can help answer it.
1. Check the given examples. See if the given examples can answer your question.
1. Write down your question to check with someone later.

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: bb7aad77
* title: PSE
##### !question

If the input parameter, `restaurants`, is

```python
[
    {"name": "Grillby's", "rating": 1},
    {"name": "Crow's Nest", "rating": 5}
]
```

What is the return value of `get_highest_rated`?

##### !end-question
##### !options

* `{"name": "Crow's Nest", "rating": 1}`
* `{"name": "Grillby's", "rating": 5}`
* `None`
* `{"name": "Crow's Nest", "rating": 5}`

##### !end-options
##### !answer

* `{"name": "Crow's Nest", "rating": 5}`

##### !end-answer
##### !explanation

The problem states that `restaurants` is `[{"name": "Grillby's", "rating": 1}, {"name": "Crow's Nest", "rating": 5}]`. In this list of dictionaries, the dictionary `{"name": "Crow's Nest", "rating": 5}` represents a restaurant named "Crow's Nest," and has a rating of `5`. This restaurant has a higher rating than the other restaurant in the list, "Grillby's," which has a rating of `1`.

<br/>

The function `get_highest_rated` should return the highest-rated restaurants. We can see in the examples that the return value is usually a dictionary with the key-value pairs `name` and `rating`.

<br/>

The option that is a dictionary with the key-value pairs `name` and `rating` and accurately describe "Crow's Nest" with a rating of `5` is `{"name": "Crow's Nest", "rating": 5}`.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: 0892f8e8
* title: PSE
##### !question

Read the following code.

```python
restaurants = [{"name": "Crow's Nest", "rating": 1}]

output = get_highest_rated(restaurants)
```

What is the value of `output`?

##### !end-question
##### !options

* `{"name": "Crow's Nest", "rating": 1}`
* `{"name": "Grillby's", "rating": 5}`
* `None`
* `{"name": "Crow's Nest", "rating": 5}`

##### !end-options
##### !answer

* `{"name": "Crow's Nest", "rating": 1}`

##### !end-answer
##### !explanation

In this code, `restaurants` is a variable that is assigned to a list of dictionaries. There is only one dictionary in the list.

<br/>

We call the function `get_highest_rated`, passing in `restaurants`.

<br/>

The function `get_highest_rated` returns a value. The variable `output` is assigned to this value.

<br/>

The value of `output` is the return value of `get_highest_rated` when `restaurants` is `[{"name": "Crow's Nest", "rating": 1}]`.

<br/>

The highest-rated restaurant in this list is `{"name": "Crow's Nest", "rating": 1}`. Therefore, the value of `output` is `{"name": "Crow's Nest", "rating": 1}`.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: c6f2e17e
* title: PSE
##### !question

Read the following code.

```python
restaurants = []

output = get_highest_rated(restaurants)
```

What is the value of `output`?

##### !end-question
##### !options

* `{"name": "Crow's Nest", "rating": 1}`
* `{"name": "Grillby's", "rating": 5}`
* `None`
* `{"name": "Crow's Nest", "rating": 5}`

##### !end-options
##### !answer

* `None`

##### !end-answer
##### !explanation

The value of the variable `restaurants` is an empty list, `[]`.

<br/>

This value gets passed in to the function `get_highest_rated` as the input parameter.

<br/>

The original problem statement lists three examples. The third example states that when `restaurants` is `[]`, the expected return value is `None`.

<br/>

We can apply that rule to this question. The variable `output` is assigned to the return value of `get_highest_rated([])`, which is `None`.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 4 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: 92b85cbd
* title: PSE
##### !question

If `restaurants` is

```python
[
    {"name": "North Star", "rating": 3},
    {"name": "South Pole", "rating": 2.5},
    {"name": "East Side", "rating": 2.5},
    {"name": "West Egg", "rating": 3.5}
]
```

What is the return value of `get_highest_rated`?

##### !end-question
##### !options

* `{"name": "North Star", "rating": 3}`
* `{"name": "South Pole", "rating": 2.5}`
* `{"name": "East Side", "rating": 2.5}`
* `{"name": "West Egg", "rating": 3.5}`
* We need to ask for more information in order to answer this question.

##### !end-options
##### !answer

* `{"name": "West Egg", "rating": 3.5}`

##### !end-answer
##### !explanation

When looking through these four dictionaries, the dictionary with the highest value of `"rating"` is `{"name": "West Egg", "rating": 3.5}`.

<br/>

Because this function returns the highest-rated restaurant as a dictionary with `"name"` and `"rating"` keys, this function should return `{"name": "West Egg", "rating": 3.5}`.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 5 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: 8b541695
* title: PSE
##### !question

If `restaurants` is

```python
[
    {"name": "North Star", "rating": 1},
    {"name": "South Pole", "rating": 1},
    {"name": "East Side", "rating": 5},
    {"name": "West Egg", "rating": 5}
]
```

What is the return value of `get_highest_rated`?

##### !end-question
##### !options

* `{"name": "North Star", "rating": 1}`
* `{"name": "South Pole", "rating": 1}`
* `{"name": "East Side", "rating": 5}`
* `{"name": "West Egg", "rating": 5}`
* We need to ask for more information in order to answer this question.

##### !end-options
##### !answer

* We need to ask for more information in order to answer this question.

##### !end-answer
##### !explanation

The restaurants "East Side" and "West Egg" both have a rating of `5`, which is the highest rating in this list.

<br/>

There are two highest-rated restaurants in `restaurants`.

<br/>

The original problem does **not** specify what to return when there are two highest-rated restaurants.

<br/>

We could try to learn from previous examples. However, there are no previous examples that have two highest-rated restaurants.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

### !callout-info

## Word Problems Will Not Tell You Everything You Need to Know

Problems will **not** contain all the information you need to know to solve the problem.

<br/>

It is **our responsibility** to ask questions to clarify the problem. We **must** discover what is known and unknown about the problem space.

<br/>

To discover details, we **must** ask detailed questions. As a tip, write down every question that comes into your mind as you work through a problem!

### !end-callout

## Understanding Requirements

Sometimes requirements are extremely vague and open-ended. On the other hand, sometimes they're extremely specific!

Let's check our understanding of the requirements.

When you're stuck on a question, follow these steps:

- Re-read through the options slowly and check _each word_!
- Reword any confusing sentences in your own words.
- Rubber-duck with someone and talk through the question with a peer. Sometimes, repeating the words out loud will help you see something new.
- Double-check to see if you're making any assumptions that you don't need to make right now.
- Guess and find the right answer, and then read the explanation. Then, redo the question to see if you understand it more.

<!-- Question 6 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: 9965e76a
* title: PSE
##### !question

Read through the original problem statement again:

> Imagine working on software that deals with restaurant reviews.
>
> Create a function named `get_highest_rated` that is responsible for finding the highest-rated restaurant.
>
> This function should take in a list of dictionaries named `restaurants` as a parameter. Each dictionary represents the data associated with a restaurant, including its rating. This function should have a return value of the restaurant with the highest rating.

| Input (Parameters of the function)                                           | Expected Output (Return value of the function) |
| ---------------------------------------------------------------------------- | ---------------------------------------------- |
| `[{"name": "Grillby's", "rating": 1}, {"name": "Crow's Nest", "rating": 5}]` | `{"name": "Crow's Nest", "rating": 5}`         |
| `[{"name": "Crow's Nest", "rating": 1}]`                                     | `{"name": "Crow's Nest", "rating": 1}`         |
| `[]`                                                                         | `None`                                         |

Select every statement that is true.

##### !end-question
##### !options

* The function's name is `get_highest_rated`
* Restaurant data is passed in to the function through parameters
* Restaurant data is passed in to the function through the return value
* The function returns a list of all restaurant data
* The function returns the data of the highest-rated restaurant
* The highest-rated restaurant is the dictionary with the biggest value of `name`
* The highest-rated restaurant is the dictionary with the biggest value of `rating`
* The highest-rated restaurant is the dictionary with the biggest value of `ratings`
* If there are no restaurants, then the function returns `None`
* If there are two or more highest-rated restaurants, then the function returns a list containing both restaurants
* If there are two or more highest-rated restaurants, then the function returns `None`
* If there are two or more highest-rated restaurants, the original problem statement doesn't mention what to return

##### !end-options
##### !answer

* The function's name is `get_highest_rated`
* Restaurant data is passed in to the function through parameters
* The function returns the data of the highest-rated restaurant
* The highest-rated restaurant is the dictionary with the biggest value of `rating`
* If there are no restaurants, then the function returns `None`
* If there are two or more highest-rated restaurants, the original problem statement doesn't mention what to return

##### !end-answer
##### !hint

The correct answer has six options selected.

##### !end-hint
##### !explanation

According to the original problem statement and given examples:

* The function `get_highest_rated` has one parameter, `restaurants`, which is a list of restaurants.
* The highest-rated restaurant is the restaurant with the largest value of **rating** specifically. This problem statement does _not_ need to compare restaurant names, or restaurants themselves!
* One of the examples says that if `restaurants` is an empty list, then the function should return `None`.
* The original problem statement doesn't mention what to return if there are two or more highest-rated restaurants. We would need to make assumptions or ask questions to know what behavior is required here.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 7 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: d7586297
* title: PSE
##### !question

Select all statements that are true about the input parameter, `restaurants`.

##### !end-question
##### !options

* `restaurants` is a list of restaurants.
* `restaurants` is a dictionary of restaurants.
* Each restaurant is a list.
* Each restaurant is a dictionary.
* Each dictionary contains two key-value pairs: `name` and `rating`.
* Each restaurant has a `name` field and a `rating` field.

##### !end-options
##### !answer

* `restaurants` is a list of restaurants.
* Each restaurant is a dictionary.
* Each dictionary contains two key-value pairs: `name` and `rating`.
* Each restaurant has a `name` field and a `rating` field.

##### !end-answer
##### !hint

The correct answer has four options selected.

##### !end-hint
##### !explanation

We can find our answer in the problem statement and the examples.

> This function should take in a list of dictionaries named `restaurants` as a parameter. Each dictionary represents the data associated with a restaurant ...

```python
[
    {"name": "Grillby's", "rating": 1},
    {"name": "Crow's Nest", "rating": 5}
]
```

`restaurants` is a list, not a dictionary. If `restaurants` were a dictionary, its outermost braces would be curly braces `{}`, not square brackets `[]`.

<br/>

Each restaurant is a dictionary, not a list. If each restaurant were a list, it would have square brackets `[]`, not curly braces `{}`.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 8 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: 795d2fa8
* title: PSE
##### !question

Why is the answer to #7 an effective data structure for the parameter, `restaurants`?

Select all statements that are true.

##### !end-question
##### !options

* We know that there will be zero or more restaurants. Lists are good data structures to contain zero or more objects.
* We know that there will be zero or more restaurants. Dictionaries are good data structures to contain zero or more objects.
* We know that each restaurant contains data, such as name data and ratings data. Lists are good data structures to represent each restaurant.
* We know that each restaurant contains pairs of data, such as name data and ratings data. Dictionaries are good data structures to represent each restaurant.

##### !end-options
##### !answer

* We know that there will be zero or more restaurants. Lists are good data structures to contain zero or more objects.
* We know that each restaurant contains pairs of data, such as name data and ratings data. Dictionaries are good data structures to represent each restaurant.

##### !end-answer
##### !hint

The correct answer has two options selected.

##### !end-hint
##### !explanation

We determined that `restaurants` is a list of dictionaries that represents a list of restaurants.

<br/>

Whenever we need to contain more than one object, we can use a list.

<br/>

One example restaurant is named "Grillby's" and has a rating of `1`. We can take the attributes "name" and "rating" as inspiration to create a dictionary. `name` and `rating` can be keys in this dictionary!

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 9 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: 7caf7230
* title: PSE
##### !question

Select all statements that describe the data structure of what the function returns.

##### !end-question
##### !options

* The return value can be a list.
* The return value can be a dictionary.
* The return value represents a restaurant.
* The return value represents a list of restaurants.
* The return value can contain two key-value pairs: `name` and `rating`.
* If there are zero restaurants, the return value is `None`.

##### !end-options
##### !answer

* The return value can be a dictionary.
* The return value represents a restaurant.
* The return value can contain two key-value pairs: `name` and `rating`.
* If there are zero restaurants, the return value is `None`.

##### !end-answer
##### !hint

The correct answer has four options selected.

##### !end-hint
##### !explanation

Consider this statement from the original problem, and this given example:

> This function should have a return value of the restaurant with the highest rating.

<br/>

| Input (Parameters of the function)                                           | Expected Output (Return value of the function) |
| ---------------------------------------------------------------------------- | ---------------------------------------------- |
| `[]`                                                                         | `None`                                         |

From these pieces of information, we can deduce that this function returns a dictionary that represents a restaurant or `None`.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 10 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: 5a510f81
* title: PSE
##### !question

This function returns the highest-rated restaurant.

Select all statements that are true about the return value.

##### !end-question
##### !options

* In this problem, each restaurant is represented by a list of restaurants.
* In this problem, each restaurant is represented by a dictionary with a name and rating.
* We can represent the idea of no restaurant with an empty list.
* We can represent the idea of no restaurant with `None`.

##### !end-options
##### !answer

* In this problem, each restaurant is represented by a dictionary with a name and rating.
* We can represent the idea of no restaurant with `None`.

##### !end-answer
##### !hint

The correct answer has two options selected.

##### !end-hint
##### !explanation

The problem statement says to return the highest-rated restaurant.

In this problem, restaurants are represented by dictionaries. Also, in every example, the return value was always a dictionary or `None`.

In this problem, there is _no_ highest-rated restaurant when the list of restaurants is empty! `None` is great at representing "no answer."

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

## Implementing `get_highest_rated`

In order to implement the function `get_highest_rated`, we can break down the problem into smaller problems.

Once we have a list of smaller problems, we can collect our ideas for how to solve the problems in code.

<!-- Question 11 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: 1dbf466d
* title: PSE
##### !question

Every big problem is made up of smaller sub-problems.

Which of these smaller questions must be answered in order to implement `get_highest_rated`?

Select all relevant questions.

##### !end-question
##### !options

* How do we compare every restaurant's name?
* How do we compare every restaurant's rating?
* How do we compare every restaurant?
* How do we check if a restaurant has the highest rating?

##### !end-options
##### !answer

* How do we compare every restaurant's rating?
* How do we check if a restaurant has the highest rating?

##### !end-answer
##### !hint

The correct answer has two options selected.

##### !end-hint
##### !explanation

This problem asks for the "highest-rated" restaurant. That means that we only need to compare one thing: the restaurant's rating!

<br/>

The problem statement does not ask us to compare restaurant names or the entire restaurant itself!

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 12 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: 7ecaf9b7
* title: PSE
##### !question

Based on the answer to the previous question, select the statements that will help us solve this problem.

##### !end-question
##### !options

* When we need to compare one value to another, we can use the comparison operators, `<`, `>`, `<=`, `>=`, `==`, `is`, or `not`.
* When we need to look at every item in a list, we can use loops and iteration.
* When we need to add, subtract, multiply, divide, find the remainder, or exponentiate, we can use the arithmetic operators `+`, `-`, `*`, `/`, `%`, or `**`.
* When we need to store more than one item, we can create a variable that references a list.

##### !end-options
##### !answer

* When we need to compare one value to another, we can use the comparison operators, `<`, `>`, `<=`, `>=`, `==`, `is`, or `not`.
* When we need to look at every item in a list, we can use loops and iteration.

##### !end-answer
##### !hint

The correct answer has two options selected.

##### !end-hint
##### !explanation

This problem asks for the "highest-rated" restaurant.

Being the _most_ of something (such as having the "highest rating," having the "largest family," or traveling the "slowest speed") usually means:

* We need to compare that quality, and therefore use comparison operators
* We need to check _each and every possible item_ just in case. Loops and iteration are great for checking every item in a collection.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->
