# Instructor: Implement pairs_with_given_sum

An example of a working implementation, with time complexity O(n^2):

```python
def pairs_with_given_sum(numbers, target):
    total = 0
    for i in range(len(numbers)-1):
        for j in range(i+1, len(numbers)):
            if numbers[i]+numbers[j] == target:
                total += 1
    return total
```

An example of a working implementation, with time complexity O(n).
This solution handles the edge case test where there are dplicate numbers/pairs in the list.

```python
def pairs_with_given_sum(numbers, target):
    numbers_dict = {}
    total = 0
    for number in numbers:
        difference = target-number
        if difference in numbers_dict and numbers_dict[difference] > 0:
            total += 1
            numbers_dict[difference] -= 1
            if number in numbers_dict:
                numbers_dict[number] -= 1
            else:
                numbers_dict[number] = 0
        elif number in numbers_dict:
            number += 1
        else:
            numbers_dict[number] = 1

    return total
```

Edge case tests with duplicate numbers/pairs:

```python
def test_finds_three_pairs_when_one_number_duplicated():
    # Arrange
    numbers = [97, 51, 49, 35, 3, 65, 3]
    target = 100

    # Act
    result = pairs_with_given_sum(numbers, target)

    # Assert
    assert result == 3

def test_finds_four_pairs_when_pair_duplicated():
    # Arrange
    numbers = [97, 51, 49, 35, 3, 65, 3, 97]
    target = 100

    # Act
    result = pairs_with_given_sum(numbers, target)

    # Assert
    assert result == 3
```