# Instructor: Implement Reshape Matrix



Sample solution:

```py
def reshape_matrix(matrix, r, c):
    '''
    INPUT: Two dimensional list, and number of rows and columns of reshaped matrix
    OUTPUT: Reshaped matrix
    '''

    originalRows = len(matrix)
    originalColumns = len(matrix[0])
    if originalRows * originalColumns != r * c:
        return matrix
    
    new_row = []
    new_matrix = []
    for i in range(originalRows):
        for j in range(originalColumns):
            new_row.append(matrix[i][j])

            if len(new_row) == c:
                new_matrix.append(new_row)
                new_row = []
    
    return new_matrix
```