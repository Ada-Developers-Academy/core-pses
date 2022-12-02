# Instructor: Implement Hamming

An example of a working implementation:

```python
def hamming_distance(strand1, strand2):
    distance = 0

    if len(strand1) != len(strand2):
        raise ValueError("Strands must be the same length")

    for i in range(len(strand1)):
        if strand1[i] != strand2[i]:
            distance += 1

    return distance
```

