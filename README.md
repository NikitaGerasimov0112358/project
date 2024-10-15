# Тема 6. Базовые коллекции: словари, кортежи
Отчет по Теме #6 выполнил(а):
- Герасимов Никита Викторович
- ПИЭ-22-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |



знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1
### В школе, где вы учились, узнали, что вы крутой программист и попросили написать программу для учителей, которая будет при вводе кабинета писать для него ключ доступа и статус, занят кабинет или нет. 
request = int(input('Введите номер кабинета: '))

dictionary = {

101: {'key': 1234, 'access': True},

102: {'key': 1337, 'access': True},

103: {'key': 8943, 'access': True},

104: {'key': 5555, 'access': False},

None: {'key': None, 'access': False},

}

response = dictionary.get(request)

if not response:

response = dictionary[None]

key = response.get('key')

access = response. get('access')

print(key, access)

### Результат
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/Снимок%20экрана%20(46).png)
## Выводы
Код запрашивает у пользователя номер кабинета и проверяет, есть ли такой кабинет в словаре. Если номер существует, то программа выводит ключ и значение параметра access для этого кабинета.

## Лабораторная работа №2
### Алексей решил создать самый большой словарь в мире. Для этого он придумал функцию dict_maker (**kwargs), которая принимает неограниченное количество параметров «ключ: значение» и обновляет созданный им словарь my_dict, состоящий всего из одного элемента «first» со значением «so easy». Помогите Алексею создать данную функцию.
from pprint import pprint

my_dict = {'first': 'so easy'}

def dict_maker(**kwargs) :

my_dict.update(**kwargs)

dict_maker(a1=1, a2=20, a3=54, a4=13)

dict_maker(name='Михаил', age=31, weight=70, eyes_color='blue')

pprint(my_dict)
### Результат
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/Снимок%20экрана%20(47).png)

## Выводы
Код создаёт словарь с помощью функции dict_maker(), которая принимает произвольное количество именованных аргументов (**kwargs) и добавляет их в существующий словарь my_dict с помощью метода .update().

## Лабораторная работа №3
### Для решения некоторых задач бывает необходимо разложить строку на отдельные символы. Мы знаем что это можно сделать при помощи split(), у которого более гибкая настройка для разделения для этого, но если нам нужно посимвольно разделить строку без всяких условий, то для этого мы можем использовать кортежи (tuple). 
input_string = 'HelloWorld'

result = tuple(input_string)

print(result)

print (list (result))

### Результат
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/Снимок%20экрана%20(48).png)

## Выводы
Код принимает строку 'HelloWorld' и преобразует её в кортеж с помощью функции tuple(), а затем выводит полученный кортеж, после снова печатает преобразованный кортеж, но уже как список с помощью функции list(), которая преобразует кортеж в список.
  
## Лабораторная работа №4
### Вовочка решил написать крутую функцию, которая будет писать имя, возраст и место работы, но при этом на вход этой функции будет поступать кортеж. Помогите Вовочке написать эту программу.
def personal_info(name, age, company='unnamed' ):

print(f"Имя: {name} Возраст: {age} Компания: {company}")

tom = ("Григорий", 22)

personal_info(*tom)

bob = ("Георгий", 41, "Yandex")

personal_info(*bob)

### Результат

![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/Снимок%20экрана%20(49).png)
## Выводы
Функция выводит на экран строку с информацией о человеке, используя переданные аргументы.

## Лабораторная работа №5
### Для сопровождения первых лиц государства X нужен кортеж, но никто не может определиться с порядком машин, поэтому вам нужно написать функцию, которая будет сортировать кортеж, состоящий из целых чисел по возрастанию, и возвращает его. Если хотя бы один элемент не является целым числом, то функция возвращает исходный кортеж.
def tuple_sort(tpl):

for elm in tpl:
    
if not isinstance(elm, int):
        
return tpl
            
return tuple(sorted(tpl))

if __name__ == '__main__':

print (tuple_sort((5, 5, 3, 1, 9)))
    
print(tuple_sort((5, 5, 2.1, '1', 9)))

### Результат
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/Снимок%20экрана%20(50).png)

## Выводы
Сортировка и возвращение кортежа

## Самостоятельная работа №1
### 1) При создании сайта у вас возникла потребность обрабатывать данные пользователя в странной форме, а потом переводить их в нужные вам форматы. Вы хотите принимать от пользователя последовательность чисел, разделенных пробелом, а после переформатировать эти данные в список и кортеж. Реализуйте вашу задумку. Для получения начальных данных используйте input(). Результатом программы будет выведенный список и кортеж из начальных данных.

user_input = input("Введите последовательность чисел, разделенных пробелом: ")

numbers_list = user_input.split()

numbers_tuple = tuple(numbers_list)

print("Список:", numbers_list)
print("Кортеж:", numbers_tuple)


### Результат.
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/(40).png)
## Выводы

Программа преобразует введенную пользователем строку чисел, разделенных пробелами, в список и кортеж. Код успешно создает требуемые структуры данных и выводит их на экран. Задача решена с использованием простого преобразования данных и функций ввода/вывода.

## Самостоятельная работа №2
### 2)	Николай знает, что кортежи являются неизменяемыми, но он очень упрямый и всегда хочет доказать, что он прав. Студент решил создать функцию, которая будет удалять первое появление определенного элемента из кортежа по значению и возвращать кортеж без него. Попробуйте повторить шедевр не признающего авторитеты начинающего программиста. Но учтите, что Николай не всегда уверен в наличии элемента в кортеже (в этом случае кортеж вернется функцией в исходном виде).

for def remove_first_occurrence(tpl, value):
    if value in tpl:
        temp_list = list(tpl)
        temp_list.remove(value)
        return tuple(temp_list)
    else:
        return tpl

test_1 = remove_first_occurrence((1, 2, 3), 1)
test_2 = remove_first_occurrence((1, 2, 3, 1, 2, 3, 4, 5, 2, 3, 4, 2, 4, 2), 3)
test_3 = remove_first_occurrence((2, 4, 6, 6, 4, 2), 9)


print(test_1)  # Ожидаемый результат: (2, 3)
print(test_2)  # Ожидаемый результат: (1, 2, 1, 2, 3, 4, 5, 2, 3, 4, 2, 4, 2)
print(test_3)  # Ожидаемый результат: (2, 4, 6, 6, 4, 2)


### Результат.
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/(41).png)
## Выводы

Задача решена с использованием метода удаления первого вхождения элемента в неизменяемом кортеже. Программа корректно удаляет элемент или возвращает исходный кортеж, если элемент не найден. Код продемонстрировал работу с неизменяемыми структурами данных и модификацией их через преобразование.

## Самостоятельная работа №3
### 3)	Ребята поспорили кто из них одним нажатием на numpad наберет больше повторяющихся цифр, но не понимают, как узнать победителя. Вам им нужно в этом помочь. Дана строка в виде случайной последовательности чисел от 0 до 9 (длина строки минимум 15 символов). Требуется создать словарь, который в качестве ключей будет принимать данные числа (т. е. ключи будут типом int), а в качестве значений – количество этих чисел в имеющейся последовательности. Для построения словаря создайте
 
функцию, принимающую строку из цифр. Функция должна возвратить словарь из 3-х самых часто встречаемых чисел, также эти значения нужно вывести в порядке возрастания ключа.


from collections import Counter

def find_top_three_frequent_numbers(number_string):
    number_counts = Counter(map(int, number_string))
    
    top_three = number_counts.most_common(3)
    
    top_three_dict = {k: v for k, v in sorted(top_three)}
    
    return top_three_dict

number_string = "12345678901234567890123456789012345"  # Пример последовательности чисел
result = find_top_three_frequent_numbers(number_string)

print(result)  # Словарь из 3 самых часто встречающихся чисел


### Результат.
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/(42).png)
## Выводы

Программа создает словарь, в котором ключами являются цифры, а значениями — частота их появления в строке. Затем она возвращает три наиболее часто встречающиеся цифры в порядке возрастания ключей. Задача решена с помощью использования коллекции Counter и сортировки ключей, что обеспечило корректную обработку данных.
## Самостоятельная работа №4
### 4)	Ваш хороший друг владеет офисом со входом по электронным картам, ему нужно чтобы вы написали программу, которая показывала в каком порядке сотрудники входили и выходили из офиса. Определение сотрудника происходит по id. Напишите функцию, которая на вход принимает кортеж и случайный элемент (id), его можно придумать самостоятельно. Требуется вернуть новый кортеж, начинающийся с первого появления элемента в нем и заканчивающийся вторым его появлением включительно.
Если элемента нет вовсе – вернуть пустой кортеж.
Если элемент встречается только один раз, то вернуть кортеж, который начинается с него и идет до конца исходного.

def process_entry_exit(tpl, employee_id):
    if employee_id not in tpl:
        return ()  # Возвращаем пустой кортеж, если элемента нет вовсе

    first_index = tpl.index(employee_id)

    if tpl.count(employee_id) > 1:
        second_index = tpl.index(employee_id, first_index + 1)
        return tpl[first_index:second_index + 1]
    else:
        return tpl[first_index:]

test_1 = process_entry_exit((1, 2, 3), 8)
test_2 = process_entry_exit((1, 8, 3, 4, 8, 8, 9, 2), 8)
test_3 = process_entry_exit((1, 2, 8, 5, 1, 2, 9), 8)

print(test_1)  # Ожидаемый результат: ()
print(test_2)  # Ожидаемый результат: (8, 3, 4, 8)
print(test_3)  # Ожидаемый результат: (8, 5, 1, 2, 9)



### Результат.
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/(43).png)

## Выводы

Программа находит первую и последнюю позицию определенного элемента в кортеже и возвращает соответствующий срез. Если элемент отсутствует или встречается только один раз, результат формируется в соответствии с условиями. Программа корректно обрабатывает различные входные данные, включая случаи, когда элемент встречается только один раз или не встречается вовсе.

## Самостоятельная работа №5
### 5) 5)	Самостоятельно придумайте и решите задачу, в которой будут обязательно использоваться кортеж или список. Проведите минимум три теста для проверки работоспособности вашей задачи.

def find_intersection(list1, list2):
    # Преобразуем списки во множества, чтобы найти пересечение и исключить повторения
    intersection = list(set(list1) & set(list2))
    return intersection

list1_test1 = [1, 2, 3, 4, 5, 6, 6, 2]
list2_test1 = [4, 5, 6, 7, 8, 4]
result_test1 = find_intersection(list1_test1, list2_test1)
print(f"Test 1 Result: {result_test1}")  # Ожидаемый результат: [4, 5, 6]

list1_test2 = [10, 20, 30]
list2_test2 = [40, 50, 60]
result_test2 = find_intersection(list1_test2, list2_test2)
print(f"Test 2 Result: {result_test2}")  # Ожидаемый результат: []

list1_test3 = [9, 8, 7, 6]
list2_test3 = [6, 7, 8, 9]
result_test3 = find_intersection(list1_test3, list2_test3)
print(f"Test 3 Result: {result_test3}")  # Ожидаемый результат: [6, 7, 8, 9]



### Результат.
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/(44).png)
## Выводы
Задача на нахождение пересечения двух списков без повторений решена с использованием множеств. Программа верно находит общие элементы в списках и исключает повторяющиеся значения. Были проведены три успешных теста, подтверждающие корректную работу кода.
## Общий вывод 
Задания 1–5 демонстрируют различные аспекты работы с кортежами, списками, словарями и их комбинациями. Программы успешно решают поставленные задачи, используя как базовые, так и более сложные методы обработки данных, такие как работа с неизменяемыми структурами (кортежами), пересечение множеств и подсчет частоты встречаемости элементов. Все решения корректно реализованы и протестированы на нескольких примерах.
