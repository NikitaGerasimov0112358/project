# Тема 5. Базовые коллекции: множества, списки
Отчет по Теме #5 выполнил(а):
- Герасимов Никита Викторович
- ПИЭ-22-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + |
| Задание 7 | + |
| Задание 8 | + |
| Задание 9 | + |
| Задание 10 | + |


знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1
### Друзья предложили вам поиграть в игру “найди отличия и убери повторения (версия для программистов)”. Суть игры состоит в том, что на вход программы поступает два множества, а ваша задача вывести все элементы первого, которых нет во втором. А вы как раз недавно прошли множества и знаете их возможности, поэтому это не составит для вас труда.
set_1 = {'White', 'Black', 'Red', 'Pink'}

set_2 = {f'Red', 'Green', 'Blue', 'Red'}

print(set_1 - set_2)

### Результат
![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/1t5.png)
## Выводы
Работа с множествами вычитание одного из другого

## Лабораторная работа №2
### Напишите две одинаковые программы, только одна будет использовать set(), а вторая frozenset() и попробуйте к исходному множеству добавить несколько элементов, например, через цикл.
(set())

a = set('abcdefg')

print(a)

for i in range(1, 5):

a.add(i)

print(a)

(frozenset())

a = frozenset('abcdefg')

print(a)

for i in range(1, 5):

a.add(i)

print(a)
### Результат
 ![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/2.1t5.png)
 ![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/2.2t5.png)

## Выводы
Использование set() и frozenset(), а также добавление элементов к множеству

## Лабораторная работа №3
### На вход в программу поступает список (минимальной длиной 2 символа). Напишите программу, которая будет менять первый и последний элемент списка.
def replace(input_list):

memory = input_list[0]

input_list[0] = input_list[-1]

input_list[-1] = memory

return input_list

print(replace([1, 2, 3, 4, 5]))

### Результат
![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/3t5.png)

## Выводы
Смена первого и последнего элемента в списке 
  
## Лабораторная работа №4
### На вход в программу поступает список (минимальной длиной 10 символов). Напишите программу, которая выводит элементы с индексами от 2 до 6. В программе необходимо использовать “срез”.
a = [12, 54, 32, 57, 843, 2346, 765, 75, 25, 234, 756, 23]

print(a[2:6])

### Результат

![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/4t5.png)
## Выводы
Вывод элементов из списка от 2 до 6

## Лабораторная работа №5
### Иван задумался о поиске «бесполезного» числа, полученного из списка. Суть поиска в следующем: он берет произвольный список чисел, находит самое большое из них, а затем делит его на длину списка. Студент пока не придумал, где может пригодиться подобное значение, но ищет у вас помощи в реализации такой функции useless().
def useless(lst):

return max(lst) / len(lst)

print(useless([3, 5, 7, 3, 33]))

print(useless([-12.5, 54, 77-3, 0, -36, 98.2, -63, 21.7, 47, -89.6]))

print(useless([-25.8, 86, 12.5, -86, 73.2, 0, 43, -91.5, 65.9, -7]))

### Результат
![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/5t5.png)

## Выводы
Функция useless(), которая берет из списка чисел самое большое из них, а затем делит его на длину списка.

## Лабораторная работа №6
### Ребята не могут определится каким супергероем они хотят стать. У них есть случайно составленный список супергероев, и вы должны определить кто из ребят будет каким супергероем. Необходимо использовать разделение списков.
superheroes = ['superman', 'spiderman','batman']

nikolay, vasiliy, ivan = superheroes

print('Николай - ', nikolay)

print('Василий - ', vasiliy)

print('Иван - ', ivan)

### Результат
![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/6t5.png)

## Выводы
Разделение списков для определения кто какой супергерой.

## Лабораторная работа №7
### Вовочка, насмотревшись передачи “Слабое звено” решил написать программу, которая также будет находить самое слабое звено (минимальный элемент) и удалять его, только делать он это хочет не с людьми, а со списком. Помогите Вовочке с реализацией программы. 
a = [-25.8, 86, 12.5, -56, 73.2, 0, 43, -91.5, 65.9, -7]

a.sort()

print('Отсортированный список:\n', a)

a.pop(0)

print('Отсортированный список без наименьшего элемента:\n', a)

### Результат
![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/7t5.png)

## Выводы
Программа сначала выводит отсортированный список при помощи sort(), а затем отсоритрованный список без наименьшего числа при помощи pop(0)

## Лабораторная работа №8
### Михаил решил создать большой n-мерный список, для этого он случайным образом создал несколько списков, состоящих минимум из 3, а максимум из 10 элементов и поместил их в один большой список. Он также как и Иван не знает зачем ему это сейчас нужно, но надеется на то, что это пригодится ему в будущем.
from random import randint

def List_maker():

a = [randint(1, 100)] * randint(3, 10)
   
return a

if __name__ == '__main__':
    
result = []
    
for i in range(randint(1, 5)):
      
result.append(List_maker())
        
print (result)

### Результат
![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/8t5.png)

## Выводы 
Код создает список, состоящий из нескольких списков, каждый из которых содержит случайное число, повторяющееся случайное количество раз.

## Лабораторная работа №9
### Вы работаете в ресторане и отвечает за статистику покупок, ваша задача сравнить между собой заказы покупателей, которые указаны в разном порядке. Реализуйте функцию superset(), которая принимает 2 множества.
def superset(set_1, set_2):

if set_1 > set_2:
    
print(f'Объект {set_1} является чистым супермножеством')
        
elif set_1 == set_2:
    
print(f'Множества равны')
        
elif set_1 < set_2:
    
print(f'Объект {set_2} является чистым супермножеством')
        
else:
    
print('Супермножество не обнаружено' )

if __name__ == '__main__':

superset({1, 8, 3, 5}, {3, 5})
    
superset ({1, 8, 3, 5}, {5, 3, 8, 1})
    
superset ({3, 5}, {5, 3, 8, 1})
    
superset ({90, 160}, {3, 5})
    
### Результат
![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/9t5.png)

## Выводы
Код проверяет, является ли одно множество супермножеством другого, и выводит соответствующее сообщение в зависимости от того, является ли первое множество чистым супермножеством, равны ли множества или второе множество является супермножеством.

## Лабораторная работа №10
### Предположим, что вам нужно разобрать стопку бумаг, но нужно начать работу с нижней, “переверните стопку”. Вам дан произвольный список. Представьте его в обратном порядке. Программа должна занимать не более двух строк в редакторе кода.
my_list = [1, 2, 3, 4]

print(my_list[::-1])

### Результат
![Меню](https://github.com/DanilAlexeevich/DanilKholkin/raw/main/img/10t5.png)

## Выводы
Этот код создает список my_list с элементами [1, 2, 3, 4] и выводит его развернутую версию с помощью среза [::-1], что приводит к выводу [4, 3, 2, 1].

## Самостоятельная работа №1
### Ресторан на предприятии ведет учет посещений за неделю при помощи кода работника. У них есть список со всеми посещениями за неделю. 
checks_list = [
    8734, 2345, 8201, 6621, 9999, 1234, 5678, 8201, 8888, 4321, 3365,
    1478, 9865, 5555, 7777, 9998, 1111, 2222, 3333, 4444, 5556, 6666,
    5410, 7778, 8889, 4445, 1439, 9604, 8201, 3365, 7502, 3016, 4928,
    5837, 8201, 2643, 5017, 9682, 8530, 3250, 7193, 9051, 4506, 1987,
    3365, 5410, 7168, 7777, 8734, 5678, 8201, 4445, 3016, 4506, 4506
]

total_checks = len(checks_list)

unique_visitors = len(set(checks_list))

from collections import Counter
check_counts = Counter(checks_list)
most_frequent_visitor = check_counts.most_common(1)[0]

total_checks, unique_visitors, most_frequent_visitor

### Результат
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/screen1.png)

## Выводы 
Программа вычисляет и выводит данные чеков.
## Самостоятельная работа №2
### На физкультуре студенты сдавали бег, у преподавателя физкультуры есть список всех результатов, ему нужно узнать
•	Три лучшие результата
•	Три худшие результата
•	Все результаты начиная с 10 

run_results = [
    10.2, 14.8, 19.3, 22.7, 12.5, 33.1, 38.9, 21.6, 26.4, 17.1, 30.2,
    35.7, 16.9, 27.8, 24.5, 16.3, 18.7, 31.9, 12.9, 37.4
]

sorted_results = sorted(run_results)

top_3_results = sorted_results[:3]

bottom_3_results = sorted_results[-3:]

results_starting_from_10 = [time for time in run_results if time >= 10]

print(top_3_results, bottom_3_results, results_starting_from_10)

### Результат
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/l4_screen12.jpg)

## Вывод
Программа моделирует выводит результаты по физкультуре. 
 
## Самостоятельная работа №3
### Преподаватель по математике придумал странную задачку. У вас есть три списка с элементами, каждый элемент которых – длина стороны треугольника, ваша задача найти площади двух треугольников, составленные из максимальных и минимальных элементов полученных списков. Результатом выполнения задачи будет: листинг кода, и вывод в консоль, в котором будут указаны два этих значения.import time

import math

one = [12, 25, 3, 48, 71]
two = [5, 18, 40, 62, 98]
three = [4, 21, 37, 56, 84]

max_values = [max(one), max(two), max(three)]
min_values = [min(one), min(two), min(three)]

def triangle_area(a, b, c):
    s = (a + b + c) / 2
    # Area calculation
    return math.sqrt(s * (s - a) * (s - b) * (s - c))

max_triangle_area = triangle_area(*max_values)
min_triangle_area = triangle_area(*min_values)

print(max_triangle_area, min_triangle_area)

### Результат
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/l4_screen13.jpg)

## Вывод
В этой программе находится площадь меньшего и большего треугольника.

## Самостоятельная работа №4
### Никто не любит получать плохие оценки, поэтому Борис решил это исправить. Допустим, что все оценки студента за семестр хранятся в одном списке. Ваша задача удалить из этого списка все двойки, а все тройки заменить на четверкиdef calculate_average(*args):

def process_grades(grades):
    return [4 if grade == 3 else grade for grade in grades if grade != 2]

grades_list_1 = [2, 3, 4, 5, 3, 4, 5, 2, 2, 5, 3, 4, 3, 5, 4]
grades_list_2 = [4, 2, 3, 5, 3, 5, 4, 2, 2, 5, 4, 3, 5, 3, 4]
grades_list_3 = [5, 4, 3, 3, 4, 3, 3, 5, 5, 3, 3, 3, 3, 4, 4]

updated_grades_1 = process_grades(grades_list_1)
updated_grades_2 = process_grades(grades_list_2)
updated_grades_3 = process_grades(grades_list_3)

print(updated_grades_1)
print(updated_grades_2)
print(updated_grades_3)


### Результат
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/l4_screen14.jpg)

## Вывод
Реализованна программа, заменяющая плохие оценки на хорошие. 
## Самостоятельная работа №5
###	Вам предоставлены списки натуральных чисел, из них необходимо сформировать множества. При этом следует соблюдать это правило: если какое-либо число повторяется, то преобразовать его в строку по следующему образцу: например, если число 4 повторяется 3 раза, то в множестве будет следующая запись: само число 4, строка «44», строка
«444».

from collections import Counter


# Function to transform the list into a set with the described rule
def list_to_set(lst):
    counts = Counter(lst)
    result_set = set()

    for num, count in counts.items():
        result_set.add(num)  # Add the number itself
        for i in range(2, count + 1):
            result_set.add(str(num) * i)  # Add the repeated number as strings

    return result_set


# Provided lists
list_1 = [1, 1, 3, 3, 1]
list_2 = [5, 5, 5, 5, 5, 5, 5]
list_3 = [2, 2, 1, 2, 2, 5, 6, 7, 1, 3, 2, 2]

# Convert lists to sets
set_1 = list_to_set(list_1)
set_2 = list_to_set(list_2)
set_3 = list_to_set(list_3)

# Output the results
print(set_1)
print(set_2)
print(set_3)


## Вывод
Реализованы программа, создающая эти списки.

## Общие выводы по теме
Множсества и списки в phyton обладают широким функционалом, полезным в самых разных ссферах разработки. Широкие возможности языка позволяют эффективно работать с большим количеством данных.
