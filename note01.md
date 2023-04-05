# Object Oriented Programming Notes 1

## Terms to know
- Object
- Object Oriented Programming
- Class
- Attributes
- Methods
- Encapsulations
- Polymorphism
- Override
##

## Object
#### In CS
Can be a _variable_, a _data structure_, a _function_, or a _method_  
Has a value that can be referenced by an _identifier_  
#### In OOP
It is an _instance_ of a _class_ where the object can be any of the mentioned above  
Data and functional code merged
- States; characteristics that identifies the object
- Behaviour; possible functionality of the object
```python
class Dog #this is an OBJECT
    def __init__(self,name,colour,breed):
        #Below are examples of ATTRIBUTES
        self.name = name
        self.colour = colour
        self.breed = breed
        self.is_hungry = False
        self.is_thirsty = True
        
    def bark(self): #This is a METHOD
        return "woof"
    
    def eat(self,food): #This is also a METHOD
        return f'{self.name} ate {food}!"
```
## Object Oriented Programming
Used to create 'modular reusable software programs'  
They use *objects*  
#### **Not** a procedure-oriented programming (input -> process -> output)  
- Calculations  
- Logical  
- Repetitive  
#### It is about the **definition of data**  
- What is the name?
- What is the colour?
- What is the size?  

Aim to create objects that can define and use to solve problems  
## Class
Class is essentially a blueprint, an outline, or a template for the object(s).
```python
class Test: #This how a 'class' is initialized
```

## Attributes

## Methods

## Encapsulation
Protecting information
Can hide certain attributes and methods
In python, use double underscore '__' as prefix
```python
class Test:
    def __init__(self,name,s_num):
        self.__name = name #Encapsulation
        self.__s_num = s_num #Another encapsulation
```
## Polymorphism
Method available for any class and parameter-dependent objects
Poly -> Many
Morohism -> Forms
Ex.
Two independent classes can have the same method
A method can be used throughout inherited classes
### Overloading
Type of Polymorphism
Two methods within a *single class* with *identical* method names but *different* parameters
This does not work in Python 3
### Override
Type of Polymorphism
Two methods with *identical* method names *and* parameters
```python
class Dog:
    def __init__(self,name,breed,weight):
        self.name = name
        self.breed = breed
        self.weight = weight
        
     def eat(self): #This is an example of overriding
        return f'{self.name} is now full'
   

class Cat:
    def __init__(self,name,breed,weight):
        self.name = name
        self.breed = breed
        self.weight = weight
        
    def eat(self): #This is the pair that proves overriding
        return f'{self.name} is now full'
```


