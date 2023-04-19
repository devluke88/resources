---
description: Examples provided by ChatGPT.
---

# Design Patterns

#### Design Patterns Examples

Here are some examples of design patterns in Python:

**Factory Pattern**

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

class ShapeFactory:
    def get_shape(self, shape_type: str):
        if shape_type == 'circle':
            return Circle()
        elif shape_type == 'rectangle':
            return Rectangle()
        else:
            raise ValueError('Invalid shape type')

```

In the above example, `ShapeFactory` creates objects of `Circle` or `Rectangle` based on the input parameter `shape_type`.

**Observer Pattern**

The Observer pattern is used to establish a one-to-many dependency between objects. When the state of one object changes, all its dependents are notified and updated automatically.

```
class Subject:
    def __init__(self):
        self.observers = []
    
    def attach(self, observer):
        self.observers.append(observer)
    
    def detach(self, observer):
        self.observers.remove(observer)
    
    def notify(self):
        for observer in self.observers:
            observer.update(self)

class Observer:
    def update(self, subject):
        pass

class ConcreteObserver(Observer):
    def update(self, subject):
        print('Subject state has changed:', subject.state)

class ConcreteSubject(Subject):
    def __init__(self):
        super().__init__()
        self.state = None
    
    def set_state(self, state):
        self.state = state
        self.notify()

```

In the above example, `Subject` maintains a list of `Observer` objects and notifies them when its...

```
class Subject:
    def __init__(self):
        self.observers = []
        self.state = None
    
    def attach(self, observer):
        self.observers.append(observer)
    
    def detach(self, observer):
        self.observers.remove(observer)
    
    def notify(self):
        for observer in self.observers:
            observer.update(self.state)
    
    def set_state(self, state):
        self.state = state
        self.notify()

class Observer:
    def update(self, state):
        pass

class ConcreteObserverA(Observer):
    def update(self, state):
        print(f'ConcreteObserverA received state: {state}')

class ConcreteObserverB(Observer):
    def update(self, state):
        print(f'ConcreteObserverB received state: {state}')

```

In the above example, `Subject` is a class that maintains a list of `Observer` objects and notifies them when its state changes. `attach` and `detach` methods are used to add and remove observers from the list. `notify` method iterates over the list of observers and calls their `update` method with the current state. `set_state` method sets the current state of the subject and calls `notify` to update all observers.

`Observer` is an abstract class that defines the interface for objects that should be notified when the subject changes. `ConcreteObserverA` and `ConcreteObserverB` inherit from `Observer` and implement the `update` method to define their own behavior when notified.

Here is an example of how to use the Observer pattern:

```
subject = Subject()
observer_a = ConcreteObserverA()
observer_b = ConcreteObserverB()

subject.attach(observer_a)
subject.attach(observer_b)

subject.set_state('new state')
# Output:
# ConcreteObserverA received state: new state
# ConcreteObserverB received state: new state

subject.detach(observer_b)

subject.set_state('another state')
# Output:
# ConcreteObserverA received state: another state

```

In the above example, we create a `Subject` object and two observers, `ConcreteObserverA` and `ConcreteObserverB`. We attach both observers to the subject and then change its state using `set_state`. Both observers are notified and print the new state. We then detach `ConcreteObserverB` from the subject and change its state again. Only `ConcreteObserverA` is notified this time.

**Singleton Pattern**

```
class Singleton:
    __instance = None
    
    def __new__(cls):
        if cls.__instance is None:
            cls.__instance = super().__new__(cls)
        return cls.__instance

```

In the above example, `Singleton` is a class that can only have one instance. The `__new__` method ensures that if an instance of `Singleton` already exists, it will return that instance instead of creating a new one.

**Decorator Pattern**

```
class Component:
    def operation(self):
        pass

class ConcreteComponent(Component):
    def operation(self):
        print('ConcreteComponent operation')

class Decorator(Component):
    def __init__(self, component: Component):
        self.component = component
    
    def operation(self):
        self.component.operation()

class ConcreteDecoratorA(Decorator):
    def operation(self):
        super().operation()
        print('ConcreteDecoratorA operation')

class ConcreteDecoratorB(Decorator):
    def operation(self):
        super().operation()
        print('ConcreteDecoratorB operation')

```

In the above example, `Component` is an interface that defines the base functionality of an object. `ConcreteComponent` implements the interface. `Decorator` is an abstract class that implements the same interface and holds a reference to a `Component`. `ConcreteDecoratorA` and `ConcreteDecoratorB` inherit from `Decorator` and add their own functionality to the base operation.

**Strategy Pattern**

```
class Strategy:
    def execute(self):
        pass

class ConcreteStrategyA(Strategy):
    def execute(self):
        print('Executing ConcreteStrategyA')

class ConcreteStrategyB(Strategy):
    def execute(self):
        print('Executing ConcreteStrategyB')

class Context:
    def __init__(self, strategy: Strategy):
        self.strategy = strategy
    
    def execute_strategy(self):
        self.strategy.execute()

```

In the above example, `Strategy` is an interface that defines the algorithm that will be used by the `Context` object. `ConcreteStrategyA` and `ConcreteStrategyB` implement the interface with different algorithms. `Context` holds a reference to a `Strategy` object and executes its algorithm using `execute_strategy`.

**Template Method Pattern**

```
class AbstractClass:
    def template_method(self):
        self.operation1()
        self.operation2()
    
    def operation1(self):
        pass
    
    def operation2(self):
        pass

class ConcreteClassA(AbstractClass):
    def operation1(self):
        print('ConcreteClassA operation1')
    
    def operation2(self):
        print('ConcreteClassA operation2')

class ConcreteClassB(AbstractClass):
    def operation1(self):
        print('ConcreteClassB operation1')
    
    def operation2(self):
        print('ConcreteClassB operation2')

```

In the above example, `AbstractClass` is an abstract class that defines a template method that calls two abstract methods, `operation1` and `operation2`. `ConcreteClassA` and `ConcreteClassB` inherit from `AbstractClass` and implement the abstract methods to define their own behavior.

**Iterator Pattern**

```
class Iterator:
    def __init__(self, collection):
        self.collection = collection
        self.index = 0
    
    def has_next(self):
        return self.index < len(self.collection)
    
    def next(self):
        value = self.collection[self.index]
        self.index += 1
        return value

class Collection:
    def __init__(self):
        self.items = []
    
    def add_item(self, item):
        self.items.append(item)
    
    def get_iterator(self):
        return Iterator(self.items)

```
