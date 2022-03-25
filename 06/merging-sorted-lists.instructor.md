# Instructor: Implement Merge Lists


We have a replit with tests for all edge cases if you want to further test student solutions.

[https://replit.com/@adadev/mergesortedlist#README.md](https://replit.com/@adadev/mergesortedlist#README.md)

## Example Implementations

An example of a working implementation, with time complexity `O(n)`:

```python
def merge_lists(list1, list2):
    i = 0
    j = 0
    result = []
    while i < len(list1) and j < len(list2):
        if list1[i] < list2[j]:
            result.append(list1[i])
            i += 1
        else:
            result.append(list2[j])
            j += 1
    while i < len(list1):
        result.append(list1[i])
        i += 1
    while j < len(list2):
        result.append(list2[j])
        j += 1
        
    return result
```

An example of a working implementation, with time complexity `O(nlog n)`.  Very easy to code, but not as efficient.

```python
def merge_lists(list1, list2):
    result = list1 + list2
    return sorted(result)
```