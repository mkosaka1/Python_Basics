# Basics of Python Objects and Classes

Python is an object oriented programming language, which as you can guess, stresses on objects whereas procedure oriented programming stresses on functions. Objects are simply a collection of attributes (variables) and methods (functions) that act on those data and a class is a blueprint for that object. Python classes can be thought of as blueprints of a house, and objects can be thought of as a particular instance of that house (there can be multiple objects for one class, while they all may differ in number of bedrooms/bathrooms/etc., they will all have the same blueprint of the class).

In computer programming, classes are a great way to organize attributes (variables) and methods (functions) so that they are easy to reuse and extend later. In this post, we will walk through how to build a basic class in python. Specifically, we will discuss the example of implementing a class that represents company employees.

```
class Employee:
    pass

employee1=Employee()
employee2=Employee()

print("Employee 1 is", employee1)
print("Employee 2 is", employee2)
```

We have created an Employee class, then instantiated an *employee1* and *employee2* object using the Employee class.

```
class Employee:
    pass

employee1=Employee()
employee1.name='Matt'
employee1.income=50000

print(employee1.name)
print(employee1.income)

employee2=Employee()
employee2.name='Penelope'
employee2.income=90000

print(employee2.name)
print(employee2.income)
```

Here we created attributes **name** and **income** for our *employee1* and *employee2* objects. This is however not ideal as it is not efficient, to correct this, we can use the ```__init__()``` method to define attributes automatically as we instantiate objects.

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

We can have multiple methods within a class, so let's also create a method that determines an employees level of earning based on their **income**. Let's see what level of earning Matt and Penelope are by calling the *earning* method.
```
class Employee:
    def __init__(self, name, income):
        self.name=name
        self.income=income
        
    def earning(self):
        if self.income >= 80000:
            return 'High Earning'
        elif (self.income<8000) & (self.income>50000):
            return "Medium Earning"
        else:
            return "Low Earning"
employee1=Employee('Matt',50000)
level_earning=employee1.earning()
print(employee1.name, "=", level_earning)
employee2=Employee('Penelope',90000)
level_earning=employee2.earning()
print(employee2.name, "=", level_earning)
# Output
Matt = Low Earning
Penelope = High Earning

#OUTPUT
Matt = Low Earning
Penelope = High Earning
```

As you can see, calling the earning method on the employee1 and employee2 objects tells us what level of earning each employee is at.
To review, we have created a class with two methods, an **__init__()** method that initializes attributes of name and income and an earning method that return the level of earning depending on a persons income. We then created two objects, *employee1* with the parameters “Matt” and 50000, when these objects were created the **__init__()** method is called and name and income of the *employee1* object are now “Matt” and 50000. Then we checked what level of earning *employee1* is at and printed the results. We followed the same procedure when creating the *employee2* object.
