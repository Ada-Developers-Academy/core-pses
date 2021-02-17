# About PSEs

<iframe src="https://adaacademy.hosted.panopto.com/Panopto/Pages/Embed.aspx?id=7bde6046-2bb4-4c2b-97bd-ac2a001e5f81&autoplay=false&offerviewer=true&showtitle=true&showbrand=false&start=0&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay"></iframe>

## Introduction

For the first week of PSEs, instructors should cover:

- What are PSEs?
- What is the PSE format?
- What tips do we have for PSEs?
- What does an example PSE and submission look like? How does it get reviewed?

## Overview

Problem-Solving Exercise assignments (PSEs) are weekly assignments to practice problem-solving skills.

They are a time-boxed exercise. The exercises will touch on problem-solving skills on coding problems we've seen in the past.

### Growth Over Time

Our PSEs are designed to exercise parts of the brain that aren't often activated. They may start off feeling weird, and often challenging.

These exercises will get more familiar over time. There will be patterns in answers, repetition, and using similar techniques between different problems on different weeks. These exercises will become more smooth as problem-solving skills grow, more context with programming problems increases, and more tools, techniques, and experimentation happens.

# Format of Problem-Solving Exercises

Given this problem prompt:

> If you're given a vague description of some type of input, write code that gives a specific kind of output

Answer the following prompts:

1. List at least 5 questions whose answers would clarify the problem statement
2. List 2 sets of example inputs and their expected output
3. Divide the project prompt into at least 2 different sub-problems
4. Pick one of those problems from #3 and write a numbered list explaining how to solve that problem without using full lines of code
5. Write down on paper a solution for your answer in #4 in code

## Notes & Tips

- This is open note. You are free to use your notes, the Internet, your past projects and assignments, etc!
- For question #1, you will need to list at least five questions. This should feel like a stretch! It should feel really strange and creative to think of this many questions, or more. Sometimes, you'll come up with very weird questions, and that is totally fine, as long as the questions challenge assumptions and are relevant to the problem. Later on in the program, we will encourage you all to aim for 6, 7, or 8 questions.
- For questions #2, #3, #4, and #5, **you will need to make assumptions, and that is okay.** In other words, you will need to answer the questions you wrote in question #1.
- Your assumptions should be consistent throughout the exercise
- What is a sub-problem? Every problem has sub-problems, or smaller problems that need to be solved as part of the original problem.
  - For example, in math, for solving the problem `x = ((8 + 3) * 72) / 2`, some sub-problems would be:
    - How do you isolate problems in parentheses?
    - How do you add?
    - How do you multiply?
    - How do you divide?
- For question #3, your two sub-problems that you list do not need to make up the entire problem.
- For question #5, you are free to write down code that you are seeing from your previous notes, projects, Internet, etc.
- Answer question #5 last. If you need to leave an answer blank, let it be #5.
- These are challenging exercises!
- If your answers from last week seem similar to your answers for this week, that is okay.

## Example Problem-Solving Exercise: Ratings

Given this problem prompt:

> You are to write a method which is given an array of hashes called `restaurants`, where each hash represents the data associated with a restaurant. Each restaurant has a rating. Write code that finds the restaurant that has the highest rating.

Answer the following prompts:

1. List at least 5 questions whose answers would clarify the problem statement
2. List 2 sets of example inputs and their expected output
3. Divide the project prompt into at least 2 different sub-problems
4. Pick one of those problems from #3 and write a numbered list explaining how to solve that problem without using full lines of code
5. Write down on paper a solution for your answer in #4 in code

### Example Answers

1. At least 5 clarifying questions
   1. Should I return the restaurant's name, or the hash that represents the restaurant data, or the rating?
   1. What is the name of the key in each hash whose value is the rating?
   1. What kind of data-type is rating stored in?
   1. What should happen if there's more than one highest-rated restaurant?
   1. Is the restaurant's name included in this hash?
   1. What else is included in each hash?
   1. Will there ever be 0 restaurants? What should happen?
   1. What should I do if there is no rating?
2. 2 examples
   1. Input: `[{name: "Grillby's", rating: 1}, {name: "Crow's Nest", rating: 5}]`, Output: `{name: "Crow's Nest", rating: 5}`
   1. Input: `[{name: "Crow's Nest", rating: 1}]`, Output: `{name: "Crow's Nest", rating: 1}`
3. 2 sub-problems
   1. How do you check/iterate over all of the restaurants?
   1. How do you compare the ratings between restaurants?
4. How to solve "How do you compare the ratings between restaurants"
   1. Have a variable that stores the highest rating named `highest_rating`
   1. Have a variable that stores the rating of a specific restaurant named `rating`
   1. Use the comparison operators to find out if the new restaurant is more highly rated `rating > highest_rating`
   1. If `rating > highest_rating` is `true`, then the rating of this restaurant is rated more highly
5. ```ruby
   if rating > highest_rating
     highest_rating = rating
   end
   ```

### How to Give Feedback on the Ratings PSE

#### Reviewing #1 (list at least 5 questions):

No. 1 is used to stretch minds. It should feel like a lot of questions, and it should be really hard! Most questions are still valid even if these questions challenge very basic assumptions, like "is this a running Ruby script?" or "is this on a computer?"

- The answer is wrong if there aren't at least 5 questions
- The answer is wrong if there were no questions clarifying the structure of the restaurant hash (what are the keys in each hash, etc.)

#### Reviewing #2 (2 example input/output):

- The answer is wrong if there aren't 2 examples
- The answer is wrong if either of them aren't valid/consistent with each other
- The answer is wrong if the inputs were not arrays, (correct even the array had one or zero restaurants)

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
