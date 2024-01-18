# MM-DSS

## Лабораторная работа 9 - Обработка экспертных оценок

**Цель работы:** развить навыки обработки экспертных оценок, заданных для объектов числовыми значениями.

**Задача**: Разработать на языке программирования высокого уровня программу, которая будет вычислять обобщенные экспертные оценки по объектам и коэффициентам компетентности экспертов.

**Входные данные**

| Объект/эксперт |  1  |  2  |  3  |  4  |  5  |
|----------------|-----|-----|-----|-----|------
|       1        | 1.5 | 2.0 | 3.5 | 3.0 | 4.0 |
|       2        | 2.5 | 3.0 | 1.5 | 2.0 | 1.0 |
|       3        | 2.5 | 2.0 | 3.0 | 3.5 | 2.0 |
|       4        | 3.0 | 3.5 | 2.5 | 4.0 | 1.0 |


### Алгоритм работы:

1. Вычисляем матрицы $B = AA^T$ и $C = A^TA$
2. Для вычисления вектора оценки собственных векторов двух матриц, удовлетворяющим максимальным собственным числам, воспользуемся приближенным методом: найдем произведение всех элементов строк матрицы и вычислим корень n-ной степени для каждого произведения, где n - количество элементов в строке:
$prod_B = (prod(b_{ij}))^{1/n},$
$prod_C = (prod(c_{ij}))^{1/n}$
5. Нормируем вектора с помощью деления каждого элемента вектора на сумму всех элементов:
$norm_{esimations} = prod_B/sum(prod_B)$, $norm_{competence} = prod_C/sum(prod_C)$
6. Итоговый вектор $norm_{esimations}$ - вектор коэффициентов обобщенных экспертных оценок и вектор $norm_{competence}$ - вектор коэффициентов компетентности экспертов


**Результаты**

Коэффициенты обобщенной оценки объектов:  [0.264, 0.197, 0.256, 0.282]

Коэффициенты компетентности экспертов:  [0.181, 0.200, 0.210, 0.246, 0.161]
​

**Вывод**: реализованная программа позволяет вычислить векторы коэффициентов обобщенных экспертных оценок и компетентности экспертов.
