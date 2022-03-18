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

```python
def palindrome(s):
    if type(s) != str:
        raise TypeError('Input must be a string')
    s = s.lower()
    start = 0
    end = len(s) - 1
    while start < end:
        if not s[start].isalnum():
            start += 1
        if not s[end].isalnum():
            end -= 1
        if s[start] != s[end]:
            return False
        else:
            start += 1
            end -= 1
    return True
```