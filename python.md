
# 🐍 Python Шпаргалка

## 📌 Основы синтаксиса

```python
print("Hello, world!")  # Вывод в консоль
a, b = 5, 10  # множественное присваивание
```

## 🧮 Типы данных

```python
x = 10        # int
y = 3.14      # float
name = "Ada"  # str
flag = True   # bool
nums = [1, 2, 3]       # list
person = {"name": "Tom", "age": 30}  # dict
```

## 🔁 Условные операторы и циклы

```python
if a > b:
    print("a больше")
elif a == b:
    print("равны")
else:
    print("b больше")

for i in range(5):
    print(i)

while x < 10:
    x += 1
```

## 🧰 Функции

```python
def greet(name):
    return f"Привет, {name}!"

# Лямбда
square = lambda x: x**2
```

## 📦 Работа со списками

```python
lst = [1, 2, 3]
lst.append(4) # добавление элемента
lst.pop()  # удаление последнего элемента
lst.pop(0)  # удаление элемента по индексу
lst.insert(0, 0)  # добавление элемента по индексу
lst.remove(1)  # удаление элемента по значению
lst[0]  # 1
lst[-1]  # последний элемент
```

## 📑 Работа со строками

```python
s = "Python"
s.lower()     # python
s.upper()     # PYTHON
s.replace("Py", "My")  # Mython
s[0:2]  # 'Py'
```

## 🔣 Словари и множества

```python
d = {"a": 1, "b": 2}
d["a"]  # 1
d.get("c", 0)  # 0
d.keys()
d.values()

s = {1, 2, 3}
s.add(4)
```

## 🎯 Генераторы списков

```python
squares = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]
```

## 📂 Работа с файлами

```python
with open("file.txt", "r") as f:
    content = f.read()

with open("file.txt", "w") as f:
    f.write("Hello!")
```

## 🚨 Обработка ошибок

```python
try:
    x = 1 / 0
except ZeroDivisionError:
    print("Ошибка деления")
finally:
    print("Завершено")
```

## 🎁 Классы и ООП

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        return f"{self.name} издаёт звук"

dog = Animal("Шарик")
print(dog.speak())
```

## 🧪 Полезные модули

```python
import math
import random
import datetime
import os
import sys
import json
import collections
```

---

## 🧑‍💻 **Django**

### Основы Django

```bash
# Установка Django
pip install django

# Создание проекта
django-admin startproject myproject

# Создание приложения
python manage.py startapp myapp

# Запуск сервера
python manage.py runserver
```

### Модели

```python
from django.db import models

class Product(models.Model):
    name = models.CharField(max_length=100)
    price = models.DecimalField(max_digits=10, decimal_places=2)
```

### Представления и URL

```python
# views.py
from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello, World!")

# urls.py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.index),
]
```

### Админка

```python
from django.contrib import admin
from .models import Product

admin.site.register(Product)
```

---

## 🔢 **NumPy**

### Основы работы с NumPy

```bash
pip install numpy
```

```python
import numpy as np

# Создание массива
arr = np.array([1, 2, 3])

# Математические операции
arr + 2  # [3, 4, 5]
arr * 3  # [3, 6, 9]

# Генерация массива с диапазоном
arr2 = np.arange(0, 10, 2)  # [0, 2, 4, 6, 8]
```

### Многомерные массивы

```python
matrix = np.array([[1, 2], [3, 4]])

# Транспонирование
matrix.T

# Индексация
matrix[0, 1]  # 2
```

---

## ⚡ **asyncio**

### Основы async/await

```python
import asyncio

async def main():
    print("Hello")
    await asyncio.sleep(1)
    print("World")

asyncio.run(main())
```

### Асинхронные задачи

```python
async def fetch_data():
    await asyncio.sleep(2)
    return "Data"

async def main():
    task = asyncio.create_task(fetch_data())
    result = await task
    print(result)

asyncio.run(main())
```

---

## 🧠 **ООП (Продвинуто)**

### Наследование и переопределение методов

```python
class Animal:
    def speak(self):
        return "Звук животного"

class Dog(Animal):
    def speak(self):
        return "Гав!"

dog = Dog()
print(dog.speak())  # Гав!
```

### Поля и свойства

```python
class Person:
    def __init__(self, name, age):
        self._name = name
        self._age = age

    @property
    def name(self):
        return self._name

    @property
    def age(self):
        return self._age

p = Person("Tom", 30)
print(p.name)  # Tom
```

---

## 🔤 **Типизация в Python**

### Основы типизации

```python
def greet(name: str) -> str:
    return f"Hello, {name}"

x: int = 10
y: str = "Hello"
```

### Аннотации типов для коллекций

```python
from typing import List, Dict, Tuple

def process_data(data: List[int]) -> Dict[str, int]:
    return {"sum": sum(data), "count": len(data)}
```

---

## ⚙️ **Многофункциональные коллекции**

### Строки

```python
# Поиск в строках
s = "Hello, World!"
s.find("World")  # 7

# Разбиение на подстроки
s.split(", ")  # ['Hello', 'World!']
```

### Множества

```python
s = {1, 2, 3}
s.add(4)         # Добавить элемент
s.remove(3)      # Удалить элемент
```

### Множества и операции

```python
a = {1, 2, 3}
b = {3, 4, 5}

union = a | b   # Объединение: {1, 2, 3, 4, 5}
intersection = a & b  # Пересечение: {3}
difference = a - b  # Разность: {1, 2}
```
