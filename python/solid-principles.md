---
description: This is what ChatGPT provided.
---

# SOLID Principles

#### SOLID Principles Examples

**Single Responsibility Principle (SRP)**

This principle states that a class should have only one reason to change. In other words, it should have only one responsibility.

```
class Employee:
    def __init__(self, name: str, salary: float):
        self.name = name
        self.salary = salary
    
    def get_name(self):
        return self.name
    
    def get_salary(self):
        return self.salary

class SalaryCalculator:
    def calculate_salary(self, employee: Employee):
        # Calculate salary based on employee's position, experience, etc.
        pass

```

In the above example, `Employee` class has only one responsibility - to store information about an employee. `SalaryCalculator` class has only one responsibility - to calculate the salary of an employee based on their information.

**Open/Closed Principle (OCP)**

This principle states that a class should be open for extension but closed for modification.

```
class Shape:
    def draw(self):
        pass
    
class Circle(Shape):
    def draw(self):
        print("Drawing a circle")
    
class Rectangle(Shape):
    def draw(self):
        print("Drawing a rectangle")
    
class ShapeDrawer:
    def __init__(self, shapes: List[Shape]):
        self.shapes = shapes
    
    def draw_all_shapes(self):
        for shape in self.shapes:
            shape.draw()

```

In the above example, `Shape` class is open for extension as we can add new shapes by creating new subclasses of `Shape`. However, `Shape` class is closed for modification as we don't need to modify the `draw` method when we add a new shape.

**Liskov Substitution Principle (LSP)**

This principle states that a subclass should be able to substitute its superclass without any problems.

```
class Animal:
    def move(self):
        pass
    
class Dog(Animal):
    def move(self):
        print("Walking")
    
class Bird(Animal):
    def move(self):
        print("Flying")
    
def make_animal_move(animal: Animal):
    animal.move()

```

In the above example, we can substitute `Dog` and `Bird` for `Animal` without any problems as they both have implemented the `move` method.

**Interface Segregation Principle (ISP)**

This principle states that a client should not be forced to implement methods which it does not use.

```
class Document:
    def open(self):
        pass
    
    def save(self):
        pass
    
class Editor:
    def __init__(self, document: Document):
        self.document = document
    
    def edit(self):
        self.document.open()
        # Edit the document
        self.document.save()

class PrintableDocument:
    def print(self):
        pass
    
class PrintableEditor:
    def __init__(self, document: PrintableDocument):
        self.document = document
    
    def print(self):
        self.document.print()

```

In the above example, `Editor` class uses only the `open` and `save` methods of `Document` class. `PrintableEditor` class uses only the `print` method of `PrintableDocument` class. Therefore, we can split `Document` and `PrintableDocument` into two separate interfaces - `Openable` and `Printable`, respectively.

**Dependency Inversion Principle (DIP)**

This principle states that high-level modules should not depend on low-level modules. Instead, both should depend on abstractions.

```
class UserService:
    def __init__(self, user_repository: UserRepository):
        self.user_repository = user_repository
    
    def get_user(self, user_id: int

```

**Dependency Injection Principle (DIP)**

This principle is a natural consequence of the Dependency Inversion Principle (DIP). It says that dependencies should be injected into an object from the outside, rather than created inside the object.

```
class MyService:
    def __init__(self, my_dependency: MyDependency):
        self.my_dependency = my_dependency
    
    def do_something(self):
        self.my_dependency.do_something_else()

```

In the above example, `MyService` depends on `MyDependency`, but it is not responsible for creating it. Instead, `MyDependency` is injected from the outside, which makes `MyService` more flexible and easier to test.

**Composition Over Inheritance Principle**

This principle states that you should prefer composition over inheritance. In other words, you should use object composition to achieve code reuse, rather than inheriting from a base class.

```
class Engine:
    def start(self):
        pass

class Car:
    def __init__(self, engine: Engine):
        self.engine = engine
    
    def start(self):
        self.engine.start()

```

In the above example, `Car` uses composition to reuse the functionality of `Engine`, rather than inheriting from it.

**Don't Repeat Yourself Principle (DRY)**

This principle states that you should not repeat yourself. In other words, you should avoid duplicating code, and instead, use abstraction and modularization to keep your code clean and maintainable.

```
class MyService:
    def __init__(self, my_dependency: MyDependency):
        self.my_dependency = my_dependency
    
    def do_something(self):
        self.my_dependency.do_something_else()
    
    def do_something_else(self):
        self.my_dependency.do_something_else()

```

In the above example, `do_something` and `do_something_else` both call `my_dependency.do_something_else`. Instead of duplicating the code, we can call `do_something_else` from `do_something`.
