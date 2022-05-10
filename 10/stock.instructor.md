# Instructor: Max Profit

## O(n) Solution

```py
def max_profit(prices):
    total_profit = 0
    for i in range(1, len(prices)):
        # if prices[i] - prices[i-1] is > 0, then we have a profit
        total_profit += max(prices[i]-prices[i-1], 0)
    return total_profit
```

## Brute Force O(n<sup>2</sup>)

This is a very common solution to this problem.

```py
def maxProfit(prices: List[int]) -> int:
    max_profit = 0
    for i in range(len(prices) - 1):
        for j in range(i + 1, len(prices)):
            profit = prices[j] - prices[i]
            if profit > max_profit:
                max_profit = profit
                
    return max_profit
```