# Instructor: Max Profit

## O(n) Solution

```py
def max_profit(prices):
    total_profit = 0
    for day in range(1, len(prices)):
        # if prices[day] - prices[day - 1] is > 0, then we have a profit
        total_profit += max(prices[day] - prices[day - 1], 0)
    return total_profit
```
