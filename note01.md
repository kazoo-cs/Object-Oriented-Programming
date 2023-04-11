# Object Oriented Programming Notes 1

## Terms to know
- [Object](https://github.com/kazoo-cs/Object-Oriented-Programming/edit/main/note01.md#object)
- [Object Oriented Programming](https://github.com/kazoo-cs/Object-Oriented-Programming/edit/main/note01.md#object-oriented-programming)
- [Class](https://github.com/kazoo-cs/Object-Oriented-Programming/edit/main/note01.md#class)
- [Attributes](https://github.com/kazoo-cs/Object-Oriented-Programming/edit/main/note01.md#attributes)
- [Methods](https://github.com/kazoo-cs/Object-Oriented-Programming/edit/main/note01.md#methods)
- [Encapsulation](https://github.com/kazoo-cs/Object-Oriented-Programming/edit/main/note01.md#encapsulation)
- [Polymorphism](https://github.com/kazoo-cs/Object-Oriented-Programming/edit/main/note01.md#polymorphism)
- [Inheritance](https://github.com/kazoo-cs/Object-Oriented-Programming/edit/main/note01.md#inheritance)
##

## Object
#### In Computer Science
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
A module is a file containing python code, classes, definitions, etc.  
They use *objects*  
#### Procedure-Oriented programming (input -> process -> output)  
- Calculations  
- Logical  
- Repetitive  
#### OOP (definition of data)
- What is the name?
- What is the colour?
- What is the size?  

Aim to create objects that can define and use to solve problems  
## Class
Class is essentially a blueprint, an outline, or a template for the object(s).  
A class should contain attributes and methods  
```python
class Test: #This is how a class is initialized
    def __init__(self,name):
        self.name = name #This is an attribute
        
    def yell(self): #This is a method
        return f'{self.name} yelled ???' 
```

## Attributes
Attributes are variables that exist in the class or an object  
They must be initialized under the \_\_init\_\_ method and have values given beforehand or by the user
```python
class Phone:
    def __init__(self,name,brand,battery,age):
        '''
        Attributes below are initialized based on the object initialization. 
        self.status is already given the value 'Stable'
        '''
        self.name = name
        self.brand = brand
        self.battery = battery
        self.age = age
        self.status = 'Stable'
```
## Methods
Methods are the class's/object's callable functions  
They must always have 'self' as the first argument  
```python
class Person:
    def __init__(self,name,age,number,address): #Example
        self.name = name
        self.age = age
        self.number = number
        self.address = address
        
    def birthday(self): #Another example. For methods to function, they will need self.
        return f'Happy birthday {self.name}! You are now {self.age + 1} years old!'
```

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
Two *independent* classes can have the *same* method  
A method can be used throughout *inherited* classes  
### Overloading
Type of *Polymorphism*  
Two methods within a *single class* with *identical* method names but *different* parameters  
This **does not** work in Python 3  
### Override
Type of *Polymorphism*  
Two methods with *identical* method names *and* parameters  
```python
class Dog:
    def __init__(self,name,breed,weight):
        self.name = name
        self.breed = breed
        self.weight = weight
        
     def eat(self): #First method called 'eat'
        return f'{self.name} is now full'
   
class Cat:
    def __init__(self,name,breed,weight):
        self.name = name
        self.breed = breed
        self.weight = weight
        
    def eat(self): #Second method called 'eat' in a different class. This is an override.
        return f'{self.name} is now full'
```
## Inheritance
Occurs when an *object* or *class* is based on *another* class, a *parent* class.  
An inherited class would contain *attributes and methods* that belongs in the parent class.  
### Single Inheritance 
*Subclass* inheriting from a *single* parent class
### Multiple Inheritance
*Subclass* inherting from *multiple* parent classes
### Multilevel Inheritance
*Subclass* inheriting from *another* subclass

### Notes from class
#### Multi-generation Inheritance
```python
class Animal: #Example of a class
    def __init__(self,first,last,age): #Example of a base override of the initialization method. They require 3 arguments to initialize.
        self.__fName = first #The three lines are examples of encapsulated attributes
        self.__Name = last
        self.__age
        
    def speak(self): #This is an example of a method
        return 'Noise'
        
    def __str__(self): #This is a base override of the string method. It allows the Animal object to become a string
        return f'{self.__FName},{self.__Name}'
        
class Dog(Animal): #This is an example of a single inheritance 
    mammalType = 'Dog' #mammalType is a constant that exists for all Dog objects
    
    def speak(self): #Example of override and Polymorphism. It is a method.
        return 'Bark'
        
class Corgi(Dog): #Example of multigenerational inheritance. 
    tail = 'Fluffy' #This constant only exists in Corgi objects
    
    def __init__(self.first,last,age,cuteFactor): #Corgi class needs to override the Animal initialization because class has a custom attribute 'cuteFactor'.
        super().__init__(first,last,age) #first,last,and age are required for the Animal class. Super() method accesses the parent class to initialize the attributes before initializing the new attribute 'cuteFactor'
        self.__cuteFactor = cuteFactor
        
    def speak(self): #Another example of a method that has override
        return 'Woof'
        
    def getCuteFactor(self): #Example of a method that serves as a getter method that accesses encapsulated attributes
        return self.__cuteFactor
 
#Initialize all the objects
a = Animal('First','Last',19)
b = Dog('First Dog','Last Dog',20)
c = Corgi('First Corgi','Last Corgi',3,100)

print(a.speak()) #Noise
print(b.speak()) #Bark
print(c.speak()) #Woof
#Override will give different outputs across the classes

print(a)
print(b)
print(c)
#a, b, and c are all printable because they inherited the string override from the Animal class

print(a.mammalType) #Does not work, Animal class does not have mammalType constant
print(b.mammalType) #Dog class has mammalType constant
print(c.mammalType) #Corgi inherits mammalType from dog
    
```
#### Multi-parent Inheritance
```python
class Animal:
    def __int__(self,first,last,age):
        self.__first = first
        self.__last = last
        self.__age = age
        
    def __str__(self):
        return f'{self.__first},{self.__last}'
    
class Dog:
    def __init__(self,breed):
        self.__breed = breed
       
    def speak(self):
        return 'Bark!'
        
    def getBreed(self):
        return self.__breed
        
 class Corgi1(Animal, Dog):
    
    def __init__(self,first,last,age,breed):
        Animal.__init__(self,first,last,age): #In multiparent inheritance, initialize both parents
        Dog.__init__(self,breed)
 
    def isCute(self):
        return True
        
class Corgi2(Animal, Dog):
    def __init__(self,first,last,age,breed):
        super().__init__(first,last,age) #Super method does not require self as one of its arguments. When super() has no arguments, it will target the first parent
        super(Dog).__init__(breed) #When super() has an existing class as its argument, it will initialize the class first
        
    def isCute(self):
        return True
        
c = Corgi1('Cor', 'Gi', 2, 'Corgi')
print('Corgi1:', c)
print('Is it Cute?:', c.isCute())
print('Speaking:', c.speak())
print('Breed:', c.getBreed())

c = Corgi2('Cor', 'Gi', 2, 'Corgi')
print('Corgi1:', c)
print('Is it Cute?:', c.isCute())
print('Speaking:', c.speak())
print('Breed:', c.getBreed())

```
