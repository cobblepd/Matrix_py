### Пример 1: Декоратор для проверки размерности матриц

Этот декоратор будет использоваться для проверки, имеют ли две матрицы одинаковую размерность перед выполнением операций сложения и вычитания.

```
def check_matrix_dimension(func):
    def wrapper(matrix1, matrix2):
        if len(matrix1) != len(matrix2) or len(matrix1[0]) != len(matrix2[0]):
            raise 
        return func(matrix1, matrix2)
    return wrapper
```

### Пример 2: Функция сложения матриц

Эта функция будет использовать декоратор check_matrix_dimension для проверки размерности матриц перед их сложением.

```
@check_matrix_dimension
def sum_matrices(matrix1, matrix2):
    result = [[matrix1[i][j] + matrix2[i][j] for j in range(len(matrix1[0]))] for i in range(len(matrix1))]
    return result
```
### Пример 3: Декоратор для проверки квадратности матрицы

Этот декоратор будет использоваться для проверки, является ли матрица квадратной перед выполнением операций, таких как вычисление определителя и обратной матрицы.
```
def check_square_matrix(func):
    def wrapper(matrix):
        if len(matrix) != len(matrix[0]):
            raise ValueError("Матрица должна быть квадратной.")
        return func(matrix)
    return wrapper
```
### Пример 4: Функция вычисления определителя матрицы

Эта функция будет использовать декоратор check_square_matrix для проверки, является ли матрица квадратной перед вычислением определителя.
```
@check_square_matrix
def determinant(matrix):
    # Простой случай для 2x2 матрицы
    if len(matrix) == 2:
        return matrix[0][0] * matrix[1][1] - matrix[0][1] * matrix[1][0]
    
    # Рекурсивный случай для матриц большего размера
    det = 0
    for c in range(len(matrix)):
        minor = [row[:c] + row[c+1:] for row in matrix[1:]]  # Удаляем первую строку и c-й столбец
        det += ((-1) ** c) * matrix[0][c] * determinant(minor)
    return det
```
