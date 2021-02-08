# Basics of Python - Introduction
The primary purpose of this project is to serve as a resource for myself and others with understanding different concepts in Python with the use of examples.

## 1) [Objects and Classes](https://github.com/mkosaka1/Python_Basics/blob/master/1.Classes_%26_Objects.ipynb)

In computer programming, classes are a great way to organize attributes (variables) and methods (functions) so that they are easy to reuse and extend later. In this notebook, we walk through how to build a basic class in python. Specifically, we discuss the example of implementing a class that represents company employees.

In this simple example from our [Objects and Classes](https://github.com/mkosaka1/Python_Basics/blob/master/1.Classes_%26_Objects.ipynb) notebook, we have created an Employee class, then used the ```__init__()``` method to define attributes **name** and **income** automatically as we instantiate our *employee1* and *employee2* objects.

```
class Employee:
    def __init__(self, name, income):
        self.name=name
        self.income=income

employee1=Employee('Matt',50000)
print(employee1.name)
print(employee1.income)

employee2=Employee('Penelope',90000)
print(employee2.name)
print(employee2.income)

# OUTPUT
Matt
50000
Penelope
90000
```

## 2) [Generators](https://github.com/mkosaka1/Python_Basics/blob/master/2.Generators.ipynb)
Python generators are a simple way of creating iterators. All the work we mentioned above are automatically handled by generators in Python. Simply speaking, a generator is a function that returns an object (iterator) which we can iterate over (one value at a time).

In this simple example from our [Generators](https://github.com/mkosaka1/Python_Basics/blob/master/2.Generators.ipynb) notebook, here we create a generator function to produce odd numbers
```
def get_odds_generator():
    n=1
    
    n+=2
    yield n
    
    n+=2
    yield n 
    
    n+=2
    yield n
    
numbers=get_odds_generator()
print(next(numbers))
print(next(numbers))
print(next(numbers)) 
```
In comparison to a simple class-based iterator:
```
class get_odds:
    def __init__(self, max):
        self.n=3
        self.max=max
    def __iter__(self):
        return self
    def __next__(self):
        if self.n <= self.max:
            result = self.n
            self.n += 2
            return result
        else:
            raise StopIteration

numbers = get_odds(10)
print(next(numbers))
print(next(numbers))
print(next(numbers))
```
Generator functions are much easier and simpler to understand! 

