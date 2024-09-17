# Instructor: Implement Calculate Cart Total

An example of a working implementation:

```python
def calculate_total(cart):
    total = 0.0

    for item in cart:
        item_lowercase = item.lower()
        if item_lowercase == "apple":
            total += 0.75
        elif item_lowercase == "beans":
            total += 2.0
        elif item_lowercase == "cheese":
            total += 2.5
        elif item_lowercase == "chicken":
            total += 4
        elif item_lowercase == "flour":
            total += 1.75
        elif item_lowercase == "onion":
            total += 0.5
        elif item_lowercase == "orange":
            total += 0.85
        elif item_lowercase == "lettuce":
            total += 1.25
        elif item_lowercase == "milk":
            total += 3.0
        elif item_lowercase == "tomato":
            total += 0.45

    return total
```

Another example of a working implementation:

```python
def calculate_total(cart):
    prices = {
        "apple": 0.75,  "beans": 2.0, "cheese": 2.5, "chicken": 4.0, 
        "flour": 1.75, "onion": 0.5, "orange": 0.85, "lettuce": 1.25, 
        "milk": 3.0, "tomato": 0.45
    }
    total = 0
    
    for item in cart:
        item_lowercase = item.lower()
        if item_lowercase in prices:
            total += prices[item_lowercase]

    return total
```