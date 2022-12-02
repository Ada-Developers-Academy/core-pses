# Instructor: Implement Adagrams

An example of a working implementation:

```python
def score(word):
    total_score = 0
    for character in word:
        letter = character.upper()
        if letter in "AEIOULNRST":
            total_score += 1
        elif letter in "DG":
            total_score += 2
        elif letter in "BCMP":
            total_score += 3
        elif letter in "FHVWY":
            total_score += 4
        elif letter in "K":
            total_score += 5
        elif letter in "JX":
            total_score += 8
        elif letter in "QZ":
            total_score += 10

    return total_score
```

Another example of a working implementation:

```python
def score(word):
    scores = {
        "A": 1, "E": 1, "I": 1, "O": 1, "U": 1, "L": 1, "N": 1, "R": 1, "S": 1, "T": 1, "D": 2, "G": 2, "B": 3, "C": 3, "M": 3, "P": 3, "F": 4, "H": 4, "V": 4, "W": 4, "Y": 4, "K": 5, "J": 8, "X": 8, "Q": 10, "Z": 10
    }
    total_score = 0
    for letter in word:
        if letter.upper() in scores:
            total_score += scores[letter.upper()]

    return total_score
```