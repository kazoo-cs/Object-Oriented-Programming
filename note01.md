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
Class 
## Attributes

## Methods

## Encapsulations

## Polymorphism

## Override
```python
# Example class

class Person:
    def __init__(self, name):
        self.name = name
       
    def __str__(self):
        return f'Person Object called: {self.name}'
       
    def __repr__(self):
        return self.__str__()
    
```


