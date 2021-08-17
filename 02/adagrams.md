# Adagrams

## Problem Statement

Imagine programming the logic for a word game.

In this game, every player submits one word. Each word gets a score based on the letters in the word and its point value.

Create a function named `score` that is responsible for scoring a given word.

This function should take in a string named `word` as a parameter. This function should return the word's total number of points.

Refer to this table for the point values of each letter.

| Letter                       | Value |
| ---------------------------- | ----- |
| A, E, I, O, U, L, N, R, S, T | 1     |
| D, G                         | 2     |
| B, C, M, P                   | 3     |
| F, H, V, W, Y                | 4     |
| K                            | 5     |
| J, X                         | 8     |
| Q, Z                         | 10    |

### Examples

| Input                                              | Expected Output |
| -------------------------------------------------- | --------------- |
| `"dog"`                                            | `5`             |
| `"cat"`                                            | `5`             |
| `"cabbage"`                                        | `14`            |
| [`"quartz"`](https://en.wikipedia.org/wiki/Quartz) | `24`            |
| `""`                                               | `0`             |
| `"Dog"`                                            | `5`             |
| `"DOG"`                                            | `5`             |
| `"dOG"`                                            | `5`             |

## Understanding the Problem

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: b0923fc3
* title: PSE
##### !question

Which of the following statements best explains why the score of `"dog"` is `5`?

##### !end-question
##### !options

* The word "dog" has the letter "G," which is worth 5 points. The word's total score is the score of the letter with the highest amount of points.
* The word "dog" has three letters, "D," "O," and "G." This means that "dog" is `2 + 1 + 2` points, or `5`.
* The word "dog" has the five most frequently used letters in the English alphabet

##### !end-options
##### !answer

* The word "dog" has three letters, "D," "O," and "G." This means that "dog" is `2 + 1 + 2` points, or `5`.

##### !end-answer
##### !explanation

In this problem, we calculate the total word score by adding the point values of each letter in the word.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: f9b6df98
* title: PSE
##### !question

Which of the following statements best explains why the score of `"quartz"` is `24`?

##### !end-question
##### !options

* The word "quartz" is made up of the letters, "Q," "U," "A," "R," "T," and "Z," which means `10 + 1 + 1 + 1 + 1 + 10`, which is `24`.
* The word "quartz" is made up of the letters, "Q," "U," "A," "R," "T," and "Z." In this problem, the average number of points per letter is `4`. There are six letters in "quartz," so the total score is `4 * 6`, which is `24`.

##### !end-options
##### !answer

* The word "quartz" is made up of the letters, "Q," "U," "A," "R," "T," and "Z," which means `10 + 1 + 1 + 1 + 1 + 10`, which is `24`.

##### !end-answer
##### !explanation

In this problem, scores are calculated by adding the point value of each letter in the word.

<br/>

It's true that "quartz" has six letters, and each letter has an average of four points. However, this isn't an accurate description of _why_ the score is 24.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

## Understanding Test Cases

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: 8f82cce6
* title: PSE
##### !question

Check out the examples again.

| Input       | Expected Output |
| ----------- | --------------- |
| `"dog"`     | `5`             |
| `"cat"`     | `5`             |
| `"cabbage"` | `14`            |
| `"quartz"`  | `24`            |
| `""`        | `0`             |
| `"Dog"`     | `5`             |
| `"DOG"`     | `5`             |
| `"dOG"`     | `5`             |

We can figure out requirements based on these examples, as long as they don't contradict each other.

Select all statements that are correct conclusions we can make from the given examples.

##### !end-question
##### !options

* Letter casing (lowercase, uppercase, mixed case) does not affect a letter's score.
* The input word can contain numbers.
* The input word can contain symbols.
* The input word can be zero letters long.
* The input word can contain duplicate letters.

##### !end-options
##### !answer

* Letter casing (lowercase, uppercase, mixed case) does not affect a letter's score.
* The input word can be zero letters long.
* The input word can contain duplicate letters.

##### !end-answer
##### !explanation

* The examples "dog," "Dog," "DOG," and "dOg," all have a score of five points, even though they're the same letters in different casing. We can conclude that letter casing doesn't affect a letter's score.

* The example `""` shows what happens when the input word is zero letters long. The total score is zero!

* The example "cabbage" shows what happens when there are duplicate letters, because "a" and "b" and repeated.

* None of the examples explore or explain what happens if the input word contains numbers or symbols.

##### !end-explanation
##### !hint

The correct answer has three options selected.

##### !end-hint
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 4 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: 6056255c
* title: PSE
##### !question

We can ask a lot of questions to clarify what the requirements are.

Some questions we ask are answered already by the problem statement and the given examples.

Which of these questions are _unanswered_ by the problem statement or examples?

##### !end-question
##### !options

* Can the input word be an empty string?
* Does the input word need to be a "real word" found in the English dictionary?
* Is there a maximum length for the input word?
* Is there a minimum length for the input word?

##### !end-options
##### !answer

* Does the input word need to be a "real word" found in the English dictionary?
* Is there a maximum length for the input word?

##### !end-answer
##### !hint

The correct answer has two options selected.

##### !end-hint
##### !explanation

The questions "Can the input word be an empty string?" and "Is there a minimum length for the input word?" are answered by the example of `""` (the empty string). The smallest length a string can have is zero, as a string can't have a length of -1 or less! The example `""` gives an answer to what happens when the input word is a length of zero.

<br/>

There are no examples that explore what happens if the input word is not found within the English dictionary, because all the examples are words in the English dictionary.

<br/>

Similarly, none of the examples include numbers or symbols found outside the English alphabet.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

Check out the score table again.

| Letter                       | Value |
| ---------------------------- | ----- |
| A, E, I, O, U, L, N, R, S, T | 1     |
| D, G                         | 2     |
| B, C, M, P                   | 3     |
| F, H, V, W, Y                | 4     |
| K                            | 5     |
| J, X                         | 8     |
| Q, Z                         | 10    |

<!-- Question 5  -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: a939f361
* title: PSE
##### !question

Read the following code.

```python
word = "cabbage"

output = score(word)
```

What is the value of `output`?

##### !end-question
##### !options

* 5
* 14
* 29
* 0
* We need to ask for more information in order to answer this question.

##### !end-options
##### !answer

* 14

##### !end-answer
##### !explanation

The value of the input parameter is `"cabbage"`. The score of this string would be `3 + 1 + 3 + 3 + 1 + 2 + 1`, which is `14`.

<br/>

Also, one of the given examples is "cabbage," which states it has an output of `14`.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

### !callout-info

## Dealing With a Lot of Scrolling?

Are you finding yourself scrolling a lot? Use your screen space and desk space to your advantage!

- Take notes on a whiteboard
- Write notes in a notebook
- Open this page in two different windows or tabs!
- Copy and paste the problem statement and the examples into a different document

Do what it takes to make the information more accessible to you!

### !end-callout

<!-- Question 6 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: eaa2611f
* title: PSE
##### !question

Read the following code.

```python
word = "lettuce"

output = score(word)
```

What is the value of `output`?

##### !end-question
##### !options

* 11
* 9
* 15
* 0
* We need to ask for more information in order to answer this question.

##### !end-options
##### !answer

* 9

##### !end-answer
##### !explanation

According to the points table, if the input word is `"lettuce"`, the score would be `1 + 1 + 1 + 1 + 1 + 3 + 1`, which `9`.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 7 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: d1b147cd
* title: PSE
##### !question

Read the following code.

```python
word = ""

output = score(word)
```

What is the value of `output`?

##### !end-question
##### !options

* 5
* 14
* 29
* 0
* We need to ask for more information in order to answer this question.

##### !end-options
##### !answer

* 0

##### !end-answer
##### !explanation

There are no letters in `""`, and no letters to score. The score is zero!

<br/>

Also, `""` is one of the given examples! The examples state that it has an output of `0`.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 8 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: 4528d120
* title: PSE
##### !question

Read the following code.

```python
word = "777"

output = score(word)
```

What is the value of `output`?

##### !end-question
##### !options

* 5
* 14
* 29
* 0
* We need to ask for more information in order to answer this question.

##### !end-options
##### !answer

* We need to ask for more information in order to answer this question.

##### !end-answer
##### !explanation

The number `7` isn't represented on the point values table, so we don't know if `"7"` has any amount of points, if it causes an error, or what the expected output is.

<br/>

Similarly, there aren't any given examples with `"7"` (or any numbers), so we can't draw any conclusions from there.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 9 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: 879a1691
* title: PSE
##### !question

Read the following code.

```python
word = "cabbage3"

output = score(word)
```

What is the value of `output`?

##### !end-question
##### !options

* 5
* 14
* 29
* 0
* We need to ask for more information in order to answer this question.

##### !end-options
##### !answer

* We need to ask for more information in order to answer this question.

##### !end-answer
##### !explanation

The number `3` isn't in the point values table, and there aren't any examples with any numbers. Even though there are other English alphabet letters in `"cabbage3"`, we don't know if `"3"` has any amount of points, if it causes an error, or what the expected output is.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

### !callout-info

## Playtesting Your Code

When we're working on a Python function, it's useful to playtest it in a separate playtest file. We can use this playtest file to implement the function, and then call the function with different examples and print its output to the terminal.

<br/>

Playtesting helps us see if our function works, raises errors, or does something unexpected! We should playtest often, especially when we need to check if we're on the right path.

### !end-callout

<!-- Question 10 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: bc31ad9d
* title: PSE
##### !question

Yaffa is working on this problem.

She's implementing the `score` function inside a file named `score.py`.

To check if her `score` function is working, she puts print statements underneath the function definition. Then, she runs the Python script in the terminal using `$ python3 score.py`.

Which of the following lines of code belongs at the bottom of the file? Pick the line of code that will help Yaffa know if her code is working.

```python
def score(word):
    # Imagine that this function is fully implemented and working
    pass

# Which line of code can Yaffa put here to
# check if her score method is working?
```
##### !end-question
##### !options

* `score("cabbage")`
* `result = score("cabbage")`
* `print(f'The result of score("cabbage") is {"cabbage"}')`
* `print(f'The result of score("cabbage") is {score("cabbage")}')`

##### !end-options
##### !answer

* `print(f'The result of score("cabbage") is {score("cabbage")}')`

##### !end-answer
##### !explanation

* `score("cabbage")` invokes the function `score`, but it doesn't do anything with its output value. Nothing will print to the terminal, and Yaffa won't see any output.

* Similarly, `result = score("cabbage")` invokes `score` and assigns the result to `result`, but `result` is never printed to the terminal. Yaffa wouldn't see anything printed.

* If Yaffa uses `print(f'The result of score("cabbage") is {"cabbage"}')`, then she'll see a sentence printed to the terminal. However, this line never invokes the function `score`! It doesn't _call_ the function we're testing, so Yaffa won't actually see the result of her work.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 11 -->
<!-- prettier-ignore-start -->
### !challenge
* type: multiple-choice
* id: 568d4963
* title: PSE
##### !question

Assume that this code is in a file named `score.py`, and that the `score` function is fully implemented and working.

What gets printed to the terminal after running this code with `$ python3 score.py`?

```python
def score(word):
    # Imagine that this function is fully implemented and working
    pass

print(f'The result of score("lettuce") is {score("lettuce")}')
```

##### !end-question
##### !options

* `9`
* `14`
* `The result of score("lettuce") is 9`
* `The result of score("lettuce") is 14`

##### !end-options
##### !answer

* `The result of score("lettuce") is 9`

##### !end-answer
##### !explanation

The line `print(f'The result of score("lettuce") is {score("lettuce")}')` will definitely print the text `The result of score("lettuce") is ` if the program gets there without errors.

<br/>

Assuming that the `score` function is implemented correctly, the function call `score("lettuce")` should return `9`. This `9` is interpolated into the string.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

## Breaking Down the Problem

<!-- Question 12 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: c5c5cbca
* title: PSE
##### !question

Every big problem is made up of smaller sub-problems.

Which of these smaller questions must be answered in order to implement `score`?

Select all relevant questions.

##### !end-question
##### !options

* How do we check every letter in the input word?
* How do we check how many points one letter is?
* How do we map the letter to the correct number of points?
* How do we add up the total score?

##### !end-options
##### !answer

* How do we check every letter in the input word?
* How do we check how many points one letter is?
* How do we map the letter to the correct number of points?
* How do we add up the total score?

##### !end-answer
##### !hint

The correct answer has four options selected.

##### !end-hint
##### !explanation

In this problem, we will need to check how many points each letter is worth. We'll need to add up the points of each letter to a total score.

<br/>

The question "How do we map the letter to the correct number of points?" is another way to ask "How do we check how many points one letter is?" In programming, ["mapping](https://en.wikipedia.org/wiki/Map_(mathematics)) can mean "transforming." In this problem, we need to _transform_ a letter to the correct number of points.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 13 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: f1eeab0a
* title: PSE
##### !question

Select the different ways we could check every letter in the input word.

##### !end-question
##### !options

* Use a `for` loop, iterating on every character in a string
* Use a `while` loop, and using an index variable to index into the string
* Use a `for` loop, iterating on every integer in the `range()` between zero and the length of the word, and using an index variable to index into the string
* Use a dictionary, and make the input word a key in the dictionary

##### !end-options
##### !answer

* Use a `for` loop, iterating on every character in a string
* Use a `while` loop, and using an index variable to index into the string
* Use a `for` loop, iterating on every integer in the `range()` between zero and the length of the word, and using an index variable to index into the string

##### !end-answer
##### !hint

The correct answer has three options selected.

##### !end-hint
##### !explanation

All of these loops are valid ways to check each character in a string. In this problem, putting the input word itself into the dictionary wouldn't help us check each character.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 14 -->
<!-- prettier-ignore-start -->
### !challenge
* type: checkbox
* id: 35e25734
* title: PSE
##### !question

Select the different ways we could check how many points one letter is.

##### !end-question
##### !options

* Use `if`, `elif`, and `else` clauses. For example, if the letter is `"J"`, then letter is worth `8` points.
* Use a dictionary. For every key-value pair, the key is the letter, and the value is the point value.
* Use one of the arithmetic operators, `+`, `-`, `*`, `/`, `%`, or `**`. Add the letters and the point values together.

##### !end-options
##### !answer

* Use `if`, `elif`, and `else` clauses. For example, if the letter is `"J"`, then letter is worth `8` points.
* Use a dictionary. For every key-value pair, the key is the letter, and the value is the point value.

##### !end-answer
##### !hint

The correct answer has two options selected.

##### !end-hint
##### !explanation

In this problem, for one given letter, we need to see how many points it's worth. For example, if a given `letter` is `"A"`, and we know that `"A"` is worth one point, then we know that the given `letter` is one point.

<br/>

We can use `if`, `elif`, and `else` clauses to check if any given letter is equal to specific characters. If the given letter is equal to a specific character, then we know how many points it's worth.

<br/>

We can also use a dictionary. We can create a dictionary that contains key-value pairs, where each key is a letter, and the value is its point value. Then, we can use any given `letter` as a key to this dictionary, and get back its point value.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

## Reflection

<!-- Question 15 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 95b42ddd
* title: PSE
##### !question

What was one of the major themes of the questions in this PSE?

Examples include:

* Asking questions about edge cases
* How to use dictionaries
* Writing examples
* Using readable variable names

##### !end-question
### !end-challenge
<!-- prettier-ignore-end -->
