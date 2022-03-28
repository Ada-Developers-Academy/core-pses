# Instructor: Implement Reshape Matrix



Sample solution:

```py
def reshape_matrix(matrix, r, c):
    '''
    INPUT: Two dimensional list, and number of rows and columns of reshaped matrix
    OUTPUT: Reshaped matrix
    '''
    rows = len(matrix)
    columns = len(matrix[0])

    if rows*columns != r*c:
        return matrix

    reshaped_matrix = []
    for i in range(r):
        new_row = []
        for j in range(i*columns, (i+1)*columns):
            new_row += matrix[j]
        reshaped_matrix.append(new_row)
        
    return reshaped_matrix
```