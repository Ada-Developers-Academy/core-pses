# Instructor: Implement Highest Rated

An example of a working implementation:

```python
def get_highest_rated(restaurants):
    if not restaurants:
        return None

    highest_rated = restaurants[0]
    for restaurant in restaurants:
        if restaurant["rating"] > highest_rated["rating"]:
            highest_rated = restaurant

    return highest_rated
```
