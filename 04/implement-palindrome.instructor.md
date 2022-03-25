# Instructor: Palindrome

An example of a working implementation, with time complexity O(n):

```python
def palindrome(s):
    reverse = sequence[::-1]
    return sequence == reverse
```

An example of a working implementation, with time complexity O(n). This solution accepts only strings as input, ignores case, and considers only alphanumeric characters. 

```python
def palindrome(s):
    if type(s) != str:
        raise TypeError('Input must be a string')
    start = 0
    end = len(s) - 1
    while start < end:
        if not s[start].isalnum():
            start += 1
        if not s[end].isalnum():
            end -= 1
        elif s[start].lower() != s[end].lower():
            return False
        else:
            start += 1
            end -= 1
    return True
```
Edge case tests for validating input, ignoring case, and considering only alphanumeric characters.

```python

    def test_raise_type_error_when_non_string_input():
        # Arrange
        s = []

        # Assert
        with pytest.raises(TypeError):
            palindrome(s) # Act

    def test_ignores_case():
        # Arrange
        s = 'Kayak'

        # Act
        result = palindrome(s)

        # Assert
        assert result == True

    def test_ignores_non_alphanumeric_chars():
        # Arrange
        s = '5kayak .5'

        # Act
        result = palindrome(s)

        # Assert
        assert result == True
```