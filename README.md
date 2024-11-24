# Тема 11.  Итераторы и генераторы
Отчет по Теме #9 выполнил(а):
- Герасимов Никита Викторович
- ПИЭ-22-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | 
| Задание 4 | + |
| Задание 5 | + |


знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1
### 1)	Простой итератор, но у него нет гибкой настройки, например его нельзя развернуть. Он работает просто как next(), но нет prev()
```python
numbers = [0, 1, 2, 3, 4, 5]
for item in numbers:
    print (item)
```

### Результат
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/(8).png)

## Выводы
Создание простого итератора.

## Лабораторная работа №2
### 2)	Класс итератор с гибкой настройкой и удобными применением
```python
class CountDown:
    def __init__(self, start):
        self.count = start + 1

    def __iter__(self):
        return self

    def __next__(self):
        self.count -= 1
        if self.count < 0:
            raise StopIteration
        return self.count


if __name__ == '__main__':
    counter = CountDown(5)
    for i in counter:
        print(i)
```
### Результат
![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/2t9.png)

## Выводы
Создание класса итератора.
## Лабораторная работа №3
### 3)	Генератор списка
```python
a = [i ** 2 for i in range(1, 5)]
print('a - ', a)
for i in a:
    print(i)
print('iter(a) - ', iter(a))
for i in a:
    print(i)
```

### Результат
![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/3t9.png)

## Выводы
Простой генератор списка.
  
## Лабораторная работа №4
### Выражения генераторы
```python
b= (i ** 2 for i in range(1, 5))
print(b) #вывод не такой, как у генератора списков
print('first')
for i in b:
    print(i)
print('second')
# из-за осбенностей выражения генераторов,
# они не будут выводиься больше одного раза
for i in b:
    print(i)
```

### Результат

![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/4t9.png)
## Выводы
Генратор с вырвжением.
## Лабораторная работа №5
### Такой же счетчик, как и в первом задании, только это генератор и использует yield
```python
def countdown(count):
    while count >= 0:
        yield count
        count -= 1
if __name__ == '__main__':
    counter = countdown(5)
    for i in counter:
        print(i)
```

### Результат
![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/5t9.png)

## Выводы
Счетчик с выражением yield.

## Самостоятельная работа №1
### Вас никак не могут оставить числа Фибоначчи, очень уж они вас заинтересовали. Изучив новые возможности Python вы решили реализовать программу, которая считает числа Фибоначчи при помощи итераторов. Расчет начинается с чисел 1 и 1. Создайте функцию fib(n), генерирующую n чисел Фибоначчи с минимальными затратами ресурсов. Для реализации этой функции потребуется обратиться к инструкции yield (Она не сохраняет в оперативной памяти огромную последовательность, а дает возможность “доставать” промежуточные результаты по одному). Результатом решения задачи будет листинг кода и вывод в консоль с числом Фибоначчи от 200.
```python
# Функция-генератор для чисел Фибоначчи
def fib(n):
    a, b = 1, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

# Генерация первых 200 чисел Фибоначчи
n = 200
fib_sequence = list(fib(n))

# Вывод 200-го числа Фибоначчи
print(f"200-е число Фибоначчи: {fib_sequence[-1]}")
```

### Результат
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/screen1.png)

## Выводы 
Программа вычисляет n-ое число Фибаначчи.

## Самостоятельная работа №2
### К коду предыдущей задачи добавьте запоминание каждого числа Фибоначчи в файл “fib.txt”, при этом каждое число должно находиться на отдельной строчке. Результатом выполнения задачи будет листинг кода и скриншот получившегося файла.
```python
def fib(n):
    a, b = 1, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

# Генерация первых 200 чисел Фибоначчи
n = 200
fib_sequence = list(fib(n))

# Запись чисел Фибоначчи в файл
with open("fib.txt", "w") as file:
    for index, number in enumerate(fib_sequence, start=1):
        file.write(f"{index}: {number}\n")

print("Числа Фибоначчи записаны в файл 'fib.txt'.")

```
### Результат
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/l4_screen12.jpg)

## Вывод
Программа выводит n чисел последовательности Фибоначчи в тестовый файл.
## Общий вывод
В данной работе успешно реализованы две задачи:

Создана эффективная функция-генератор для расчета последовательности чисел Фибоначчи с использованием минимальных ресурсов.
Реализован процесс сохранения данных в текстовый файл, что упрощает хранение и обработку результатов.
Подход с использованием генераторов демонстрирует, как экономить память и повышать производительность программ. Запись в файл делает решение удобным для анализа и работы с большими объемами данных.
