# Animal Kingdom

## Objective:
The objective of this assignment is to reinforce the concepts of class inheritance and polymorphism in C++ programming. Students will be required to create a program that models an animal kingdom using class inheritance to create a hierarchy of classes representing different types of animals.

## Requirements:

1. The program should use class inheritance to create a hierarchy of classes representing different types of animals.
2. The base class should contain common attributes and methods that are inherited by all animals, such as:
- Member functions:
  - ```eating()```, ```sleeping()```, and ```playing()```
- Member Variables:
  - ```animal_name```, ```age```, ```weight``` 
3. Derived classes should be ```Mammal```, ```Bird```, and ```Fish```.
4. The program should create animal objects of different types with unique attributes and perform actions on animals such as feeding, sleeping, and playing.
5. The program should display information about the animals such as their name, age, weight, and type.

## Class Descriptions
### Base Class
- Member functions:
  - ```eating()```: prints "The <animal_name> is eating"
  - ```sleeping()```: prints "The <animal_name> is sleeping"
  - ```playing()```: prints "The <animal_name> is playing"
- Member Variables:
  - ```animal_name```, ```age```, ```weight``` 

### Dirvived Classes
**Mammal:**
- Member function:
  - ```describe()```: Prints a sentance containing all of the variables relating to the specific class
- Member Variable:
  - ```furColor```

**Bird**
- Member function:
  - ```describe()```: Prints a sentance containing all of the variables relating to the specific class
- Member Variable:
  - ```wingspan```

**Fish**
- Member function:
  - ```describe()```: Prints a sentance containing all of the variables relating to the specific class
- Member Variable:
  - ```size```

Note: You are encouraged to be creative in their implementation of the program and are welcome to add additional features or functionality beyond the minimum requirements listed above.
