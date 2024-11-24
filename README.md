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
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/7.png)

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
## Самостоятельная работа 
### Создание класса.
```python
  # Класс Tomato
class Tomato:
    # Статическое свойство stages, содержащее стадии созревания
    stages = {0: "Отсутствует", 1: "Цветение", 2: "Зеленый", 3: "Красный"}

    def __init__(self, index):
        self._index = index
        self._state = 0  # начальное состояние (отсутствует)

    # Метод grow(), который переводит томат на следующую стадию созревания
    def grow(self):
        if self._state < 3:  # последняя стадия - 3 (Красный)
            self._state += 1

    # Метод is_ripe(), проверяющий, созрел ли томат
    def is_ripe(self):
        return self._state == 3

    # Метод для отображения текущей стадии томата (дополнительно для проверки)
    def get_state(self):
        return Tomato.stages[self._state]

# Класс TomatoBush
class TomatoBush:
    def __init__(self, count):
        # Создаем список объектов Tomato
        self.tomatoes = [Tomato(index) for index in range(count)]

    # Метод grow_all(), который заставляет созревать все томаты на кусте
    def grow_all(self):
        for tomato in self.tomatoes:
            tomato.grow()

    # Метод all_are_ripe(), проверяющий, все ли томаты созрели
    def all_are_ripe(self):
        return all(tomato.is_ripe() for tomato in self.tomatoes)

    # Метод give_away_all(), очищающий куст от созревших томатов
    def give_away_all(self):
        self.tomatoes = []

# Класс Gardener
class Gardener:
    def __init__(self, name, plant):
        self.name = name
        self._plant = plant

    # Метод work(), заставляющий садовника ухаживать за растением
    def work(self):
        print(f"{self.name} ухаживает за растением...")
        self._plant.grow_all()

    # Метод harvest(), позволяющий садовнику собрать урожай
    def harvest(self):
        if self._plant.all_are_ripe():
            print(f"{self.name} собирает урожай.")
            self._plant.give_away_all()
        else:
            print("Урожай еще не созрел!")

    # Метод knowledge_base(), выводящий справку
    @staticmethod
    def knowledge_base():
        print("Справка по уходу за растением: Ухаживайте за растением, пока все томаты не созреют.")


```

### Результат.
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/6.png)
## Выводы
Класс Tomato:

Класс представляет собой модель томата с различными стадиями созревания. Благодаря методам grow() и is_ripe(), томат может поэтапно созревать, и его зрелость может быть проверена.
Вывод: Класс Tomato удачно реализует концепцию состояния объекта, позволяя отслеживать и изменять стадию созревания томата.
Класс TomatoBush:

Этот класс моделирует куст с несколькими томатами. Он содержит методы для одновременного роста всех томатов (grow_all()), проверки зрелости всех томатов (all_are_ripe()) и уборки куста (give_away_all()).
Вывод: Класс TomatoBush демонстрирует умение работать с коллекцией объектов, предоставляя методы для коллективных операций.
Класс Gardener:

Этот класс отвечает за уход за растением (кустом томатов). Садовник может ухаживать за растением и собирать урожай, если все томаты созрели. Также реализован статический метод knowledge_base(), дающий справку о процессе выращивания.
Вывод: Класс Gardener эффективно взаимодействует с кустом, показывая пример управления зависимым объектом, и содержит полезную справочную информацию.

## Самостоятельная работа №1
### Тест 1.
```python
 Gardener.knowledge_base()

```

### Результат.
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/1.png)
## Выводы
Выводсправочной информации.

## Самостоятельная работа №2
### Тест 2.
```python
bush = TomatoBush(4)
```
### Результат.
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/2.png)
## Выводы
Создание куста с 4 томатами

## Самостоятельная работа №3
### Тест 3.
```python
gardener = Gardener("Иван", bush)

```

### Результат.
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/3.png)
## Выводы 
Создание садовника.


## Самостоятельная работа №4
### Тест 4.
```python
for _ in range(3):  # трёхкратный уход, чтобы достичь стадии созревания
    gardener.work()
    if gardener._plant.all_are_ripe():
        break
```

### Результат.
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/4.png)
## Выводы
Садовник ухаживает за кустом несколько раз.

## Самостоятельная работа №5
### Тест 5.
```python
gardener.harvest()
```

### Результат.
![Меню](https://github.com/NikitaGerasimov0112358/project/raw/main/scrin/5.png)
## Выводы
Садовник пытается собрать урожай

## Общий вывод 
Все три класса — Tomato, TomatoBush и Gardener — демонстрируют применение основных концепций объектно-ориентированного программирования: инкапсуляции, наследования и полиморфизма. Система моделирует процесс ухода за растением, где каждый объект выполняет свою роль и взаимодействует с другими объектами. Это задание позволяет понять принципы ООП и научиться структурировать код, разделяя ответственность между различными объектами.







