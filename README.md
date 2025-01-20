# Matrix_py
### Техническое задание: Библиотека для работы с матрицами на Python

#### Описание проекта

Разработать библиотеку на Python для выполнения операций над матрицами. Библиотека должна поддерживать основные операции, такие как сложение, вычитание, умножение, транспонирование, вычисление определителя и обратной матрицы. Все функции должны быть реализованы в функциональном стиле
#### Операции над матрицами

Ниже представлено описание операций, которые необходимо реализовать в библиотеке. Каждая операция должна обрабатывать исключительные ситуации с использованием механизма исключений.

| Операция                          | Описание                                                                 | Исключительные ситуации                                           |
|-----------------------------------|--------------------------------------------------------------------------|------------------------------------------------------------------|
| `eq_matrices(matrix1, matrix2)`  | Проверяет матрицы на равенство между собой.                            | Различная размерность матриц.                                   |
| `sum_matrices(matrix1, matrix2)` | Прибавляет вторую матрицу к первой.                                     | Различная размерность матриц.                                   |
| `sub_matrices(matrix1, matrix2)` | Вычитает из первой матрицы вторую.                                     | Различная размерность матриц.                                   |
| `mul_number(matrix, num)`         | Умножает матрицу на число.                                             | -                                                                |
| `mul_matrices(matrix1, matrix2)` | Умножает первую матрицу на вторую.                                     | Число столбцов первой матрицы не равно числу строк второй.     |
| `transpose(matrix)`               | Создает новую транспонированную матрицу из текущей и возвращает ее.    | -                                                                |
| `calc_complements(matrix)`        | Вычисляет матрицу алгебраических дополнений текущей матрицы.           | Матрица не является квадратной.                                  |
| `determinant(matrix)`             | Вычисляет и возвращает определитель текущей матрицы.                   | Матрица не является квадратной.                                  |
| `inverse_matrix(matrix)`          | Вычисляет и возвращает обратную матрицу.                               | Определитель матрицы равен 0.                                   |

#### Дополнительные функции

- `create_matrix(rows, cols)`: Создает матрицу заданной размерности и инициализирует ее нулями.
- `copy_matrix(matrix)`: Создает копию матрицы.

#### Исключения

Для обработки ошибок необходимо создать собственные исключения, например, `MatrixError`, которые будут использоваться для сигнализации о проблемах, связанных с операциями над матрицами.

#### Пример использования

```python
from matrix_library import (
    create_matrix,
    sum_matrices,
    sub_matrices,
    mul_number,
    mul_matrices,
    transpose,
    calc_complements,
    determinant,
    inverse_matrix,
    eq_matrices
)

# Пример создания матриц
matrix1 = create_matrix(2, 3)  # Создание матрицы 2x3
matrix2 = create_matrix(2, 3)  # Создание матрицы 2x3

# Пример операций
result_sum = sum_matrices(matrix1, matrix2)
result_sub = sub_matrices(matrix1, matrix2)
result_mul_num = mul_number(matrix1, 5)
result_transpose = transpose(matrix1)
det = determinant(matrix1)
inverse = inverse_matrix(matrix1)
```

### Заключение

Данное техническое задание направлено на создание функциональной библиотеки для работы с матрицами на Python. Проект должен помочь учащимся освоить основы работы с матрицами, исключениями и функциональным программированием.

