### Лабораторна робота №13: Tasks for Data Processing in Python

#### Мета роботи:
Ознайомлення з різними методами обробки даних у Python за допомогою функцій з різними типами параметрів.

#### Очікуваний результат:
Набуття практичних навичок виконання завдань, пов’язаних з обробкою даних у Python.

#### Опис завдання:

У цій лабораторній роботі вам необхідно реалізувати кілька завдань, кожне з яких вимагає написання функції для вирішення конкретної задачі з обробки даних. Нижче наведено короткий опис кожного завдання та приклад його використання.

#### Виконання роботи:

##### Структура проекту:
Кожне завдання виконане у вигляді окремої функції з відповідною назвою.

##### Опис файлів:
- **student_main.py**: містить реалізації функцій для кожного з завдань.
- **README.md**: описує структуру проекту, призначення кожного файлу, опис основних функцій та їх приклади використання.

#### Опис основних функцій та методів з поясненням їх роботи:
     ```python
          import re
          import numpy as np
         
         def interpolate_missing(numb):
             interpolated = []
             for i, num in enumerate(numb):
                 if num is None:
                     leftind = i - 1
                     rightind = i + 1
                     leftval = None
                     rightval = None
                     while leftind >= 0:
                         if numb[leftind] is not None:
                             leftval = numb[leftind]
                             break
                         leftind -= 1
                     while rightind < len(numb):
                         if numb[rightind] is not None:
                             rightval = numb[rightind]
                             break
                         rightind += 1
             
                 if leftval is not None and rightval is not None:
                     distance = rightind - leftind
                     interpolatedval = leftval + ((rightval - leftval) / distance) * (i - leftind)
                     interpolated.append(round(interpolatedval))
                 elif leftval is not None:
                     interpolated.append(leftval)
                 elif rightval is not None:
                     interpolated.append(rightval)
                 else:
                     interpolated.append(None)
             else:
                 interpolated.append(num)
         return interpolated
         # Приклад використання функції interpolate_missing
         nums = [1, None, None, 4, None, 6]
         interpolated_nums = interpolate_missing(nums)
         print(interpolated_nums)
          ```
#### Результат:
![image](https://github.com/yatagarasu123/lab13/assets/145234911/04ec671d-3957-40c6-aeae-752cd2b81421)


#### Висновки:
Мета роботи була досягнута: були розглянуті та реалізовані різні методи обробки даних у Python, що дозволяє отримати практичні навички у цій області.

#### Інструкції з запуску:
Відкрити файл `student_main.py`, додайте необхідні виклики функцій для обробки даних, які присутні у файлі README.md, виконайте файл для отримання необхідних результатів.
