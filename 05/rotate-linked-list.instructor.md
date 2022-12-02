# Instructor: Rotate Linked List

## O(nk) solution
```python
def rotate_list(head, k):
    # determine length of list by looping until the end
    length = 1
    current = head
    while current.next:
        current = current.next
        length += 1

    # If the requested rotation is larger than the length of the list,
    # truncate the rotation
    k = k % length
    # If k is a multiple of the length of the list, nothing needs to happen
    # (e.g. doing ten rotations on a 5-element list brings us back to the start)
    if k == 0:
        return head

    # This helper function moves the last element of a list to the front
    def pop_to_front(head):
        # Iterate through the list to find the second-to-last element
        current = head
        while current.next and current.next.next:
            current = current.next

        # The element after the second-to-last is the current tail
        tail = current.next
        # Have the second-to-last point to None, marking it as the new end of the list
        current.next = None
        # Have the old tail point to the old head
        # This makes the old tail the new head
        tail.next = head

        return tail

    # Move the last element to the front k times
    for _ in range(k):
        head = pop_to_front(head)
        
    return head
```

# O(n) solution
```python
def rotate(head, k):
    '''
    Our strategy will be to split the list into two parts, and then put the 
    second part in front. E.g. rotate 1->2->3->4->5 by 2 will look like:
    - Split into 1->2->3 and 4->5
    - Swap the first and second list: 4->5 and 1->2->3
    - Recombine: 4->5->1->2->3
    '''
    
    # determine length of list by looping until the end
    length = 1
    current = head
    while current.next:
        current = current.next
        length += 1

    # The last node we visit is the tail
    tail = current

    # If the requested rotation is larger than the length of the list,
    # truncate the rotation
    k = k % length
    # If k is a multiple of the length of the list, nothing needs to happen
    # (e.g. doing ten rotations on a 5-element list brings us back to the start)
    if k == 0:
        return head

    # Find where the new list will end
    current = head
    for _ in range(length-k-1):
        current = current.next

    # The node after the new end will be the new start
    new_head = current.next
    # Make sure the new end points to None to show it's the end of the list
    current.next = None
    # Stitch the two lists back together
    tail.next = head
    
    return new_head
```