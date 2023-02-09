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
    
    # if rows * cols of original matrix is not 
    # equal to given r * c
    # not possible to transform matrix into desired shape 
    if originalRows * originalColumns != r * c:
        # return original matrix
        return matrix

    # flatten the original matrix
    flattened = []
    for row in matrix:
        for elt in row:
            flattened.append(elt)
    
    # create result matrix
    new_matrix = []
    for i in range(r):
        row_start = c * i
        row_end = c *(i + 1)
        new_row = flattend[row_start : row_end]
        new_matrix.append(new_row)
    return new_matrix
```