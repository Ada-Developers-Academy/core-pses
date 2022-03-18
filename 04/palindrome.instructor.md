# Instructor: Palindrome

Examples of working implementations:

```python
def palindrome(s):
    if type(s) != str:
        raise TypeError('Input must be a string')
    sequence = ''
    for char in s:
        if char.isalnum():
            sequence += char
    sequence.lower() 
    reverse = sequence[::-1]
    return sequence == reverse
```