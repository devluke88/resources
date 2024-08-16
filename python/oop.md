---
description: >-
  Object-oriented programming (OOP) concepts using Python pseudocode and UML
  diagrams.
---

# OOP

#### Aggregation

Aggregation represents a "has-a" relationship where the child can exist independently of the parent.

```
+----------------+       +----------------+
|    Library     |<>---->|     Book       |
+----------------+       +----------------+
| - books: List  |       | - title: str   |
| + add_book()   |       | - author: str  |
+----------------+       +----------------+

class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author

class Library:
    def __init__(self):
        self.books = []

    def add_book(self, book):
        self.books.append(book)

# Example usage
library = Library()
book1 = Book("1984", "George Orwell")
library.add_book(book1)
```

#### Composition

Composition represents a "contains-a" relationship where the child cannot exist independently of the parent.



```
+----------------+       +----------------+
|     Car        |<>---->|    Engine      |
+----------------+       +----------------+
| - engine: Engine|      | - horsepower: int|
| + start()       |      +----------------+
+----------------+

class Engine:
    def __init__(self, horsepower):
        self.horsepower = horsepower

class Car:
    def __init__(self, horsepower):
        self.engine = Engine(horsepower)

    def start(self):
        print(f"Car with {self.engine.horsepower} HP started")

# Example usage
car = Car(150)
car.start()
```

#### Uses (Dependency)

A "uses" relationship indicates that one class uses another class as a parameter or local variable.

```
+----------------+       +----------------+
|    Printer     |<-----|    Document     |
+----------------+       +----------------+
| + print(doc: Document)| | - content: str |
+----------------+       +----------------+

class Document:
    def __init__(self, content):
        self.content = content

class Printer:
    def print(self, document):
        print(f"Printing document: {document.content}")

# Example usage
doc = Document("Hello, World!")
printer = Printer()
printer.print(doc)

```

#### Inheritance

Inheritance represents an "is-a" relationship where one class inherits the attributes and methods of another class.

```
+----------------+       +----------------+
|    Animal      |<|-----|     Dog        |
+----------------+       +----------------+
| - name: str    |       | - breed: str   |
| + speak()      |       +----------------+
+----------------+

class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        pass

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)
        self.breed = breed

    def speak(self):
        return "Woof!"

# Example usage
dog = Dog("Buddy", "Golden Retriever")
print(dog.speak())
```
