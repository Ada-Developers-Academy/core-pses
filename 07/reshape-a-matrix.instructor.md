# Instructor: Implement Reshape Matrix



Sample solution:

```py
def reshape_matrix(matrix, rows, columns):
    '''
    INPUT: Two dimensional list, and number of rows and columns of reshaped matrix
    OUTPUT: Reshaped matrix
    '''
    originalRows = len(matrix)
    originalColumns = len(matrix[0])
    
    # if rows * cols of original matrix is not 
    # equal to given rows * columns
    # not possible to transform matrix into desired shape 
    if originalRows * originalColumns != rows * columns:
        raise ValueError("Matrix cannot be reshaped to desired size")

    # flatten the original matrix
    flattened = []
    for row in matrix:
        for element in row:
            flattened.append(element)
    
    # create result matrix
    new_matrix = []
    for index in range(rows):
        row_start = columns * index
        row_end = columns * (index + 1)
        new_row = flattened[row_start:row_end]
        new_matrix.append(new_row)
    return new_matrix
```