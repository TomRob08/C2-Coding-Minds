# Class Inheritance

C++ class inheritance is a mechanism that allows a new class, known as the derived class, to be based on an existing class, known as the base class. In this way, the derived class can inherit the properties and behaviors of the base class, which can be used to extend or modify the behavior of the derived class.

To create a derived class in C++, you declare it with the class keyword followed by the class name and the keyword public, private, or protected followed by the name of the base class. For example:

```
class DerivedClass : public BaseClass {
  // class definition here
};
```

Once the derived class is defined, it can access the members of the base class. For example:
```
class BaseClass {
public:
  void print() {
    cout << "Hello World" << endl;
  }
};

class DerivedClass : public BaseClass {
public:
  void hello() {
    print(); // calls the print() method of the BaseClass
  }
};
```

## Subclass constructor
Here's an example of a C++ base class with a constructor and a subclass with its own constructor:
```
class Animal {
public:
    Animal(string animalName) :
    name(animalName) {}
    string name;
};

class Dog : public Animal {
private:
    string breed;
public:
    Dog(string dogName, string dogBreed) : 
    Animal(dogName), breed(dogBreed) {}
};

int main() {
    Dog myDog("Buddy", "Labrador Retriever");
    return 0;
}
```

In this example, ```Animal``` is the base class with a constructor that initializes the ```name``` member variable. The ```Dog``` class is derived from ```Animal``` and has its own constructor that initializes the ```breed``` member variable. Notice how the Dog constructor calls the Animal constructor using the syntax ```:``` ```Animal(dogName)``` to pass the ```dogName``` parameter to the Animal constructor.

### Exercises
**1.** What is a derived class?

**2.** What is a base class?

**3.** When a derived class object is created, what does it inherit?

**4.** Create a ```Country``` class that has ```name```, ```population```, and ```capital``` attributes and a ```describeCountry()``` method that prints out the name, population, and capital of the country. Create a ```State``` class that inherits from the Country class and has a ```governor``` member and a ```describeState()``` method that prints out the name, population, and capital of the state and the name of the governor. Create constructors for the base class and subclass. For now just have all code in public for both classes. Finally, create a country and state object relating to where you're from with relevant information and use the describe function for both objects.

## Access Specifiers
Access specifiers in C++ class inheritance are used to control the accessibility of base class members in the derived class. The three access specifiers in C++ are public, protected, and private.

- Public: Public members of the base class are accessible to the derived class and also to code outside the derived class.

- Protected: Protected members of the base class are accessible to the derived class and its subclasses, but not to code outside the derived class.

- Private: Private members of the base class are not accessible to the derived class or code outside the base class.

### Example
```
#include <iostream>
using namespace std;

class Shape {
  public:
    Shape(float width, float height) :
    width(width), height(height) {}
    float area() {
      return width * height;
    }

  protected:
    float width;
    float height;
};

class Rectangle : public Shape {
  public:
    Rectangle(float rectWidth, float rectHeight) : 
      Shape(rectWidth, rectHeight) {}
};

class Triangle : public Shape {
  public:
    Triangle(float triWidth, float triHeight) : 
      Shape(triWidth, triHeight) {}
      
    float area() {
        return 0.5 * width * height;
    }
};

int main() {
  Rectangle myRect(3, 4);
  cout << "Area of rectangle: " << myRect.area() << endl;
  Triangle myTri(5, 6);
  cout << "Area of triangle: " << myTri.area() << endl;
  Shape myShape(4,5);
  cout << "Area of triangle: " << myShape.area() << endl;
  return 0;
}
```

In the example, the class shape has two protected member variables; ```width``` and ```height```. These two member variable can be use within the rectangle and triangle classes. Also notice how in the triangle class we redefined the ```area()``` member function and overrided the one in the Shape class because derived classes can override their base classes functions to suit what is needed.

### Exercises
**1.** Explain what things can access each of the terms below:

       1. Public
       2. Protected
       3. Private
       
**2.** Create a ```Vehicle``` class that has a constructor, a ```start()``` and a ```stop()``` method with ```num_Wheels``` as a member variable. Create a ```Car``` class that inherits from the ```Vehicle``` class and has a ```drive()``` method. Create a ```Bicycle``` class that also inherits from the ```Vehicle class``` and has a ```pedal()``` method. The ```start()``` method will print "Starting to roll", ```stop()``` method will print "Stopping", ```drive()``` method will print "This car is using <num_Wheels> to drive", ```pedal()``` method will print "This bike uses <num_Wheels> and a person pedaling to move". Create an object of each class and call their methods. 

**3.** 
Create a base class called ```FantasyCharacter``` with the following protected member variables:

- ```string name```: the name of the fantasy character
- ```int healthPoints```: the health points of the fantasy character
- ```int manaPoints```: the mana points of the fantasy character

The ```FantasyCharacter``` class should also have a constructor that takes three parameters to initialize the member variables, as well as public getter methods for each of the member variables.

Create a derived class called ```Knight``` that inherits from FantasyCharacter. The Knight class should have an additional private member variable called ```armorPoints```, which represents the armor points of the knight. The Knight class should also have a constructor that takes four parameters to initialize the member variables, as well as a public getter method for armorPoints. The Knight class should also have a method called ```Attack``` which prints, "Knight takes out their sword".

Create a second derived class called ```Wizard``` that also inherits from FantasyCharacter. The Wizard class should have an additional private member variable called ```spellPower```, which represents the spell power of the wizard. The Wizard class should also have a constructor that takes four parameters to initialize the member variables, as well as a public getter method for spellPower. The Wizard class should also have a method called ```cast_Spell``` that prints "Wizard activates their spell".

Finally, create a ```main()``` function that creates an object of each class and prints out the values of all the member variables using the public getter methods. You should also use the methods to cast a spell for the Wizard class and the method to attack for the Knight class.


## Multi-level Class Inheritance

Multi-level inheritance is a type of inheritance in C++ where a derived class is derived from another derived class, which in turn is derived from a base class. This creates a hierarchical structure of classes, with each derived class inheriting the properties and behaviors of its parent classes.

Think of it as a type of family structure. A family has a grandparent, a parent, and a child and each generation inherits commonalities from the previous generations so this can be related to classes by comparing the base class to the grandparent, the derived class to the parent, and the second generation derived class to the child.

### Example
```
// Base Class
class Grandparent {
  public:
    Grandparent(string name, int age) : 
      name(name), age(age) {}

    void sleep() {
        cout << name << " is sleeping" << endl;
    }

    void print_age() {
      cout << name << " is " << age << " years old" << endl;
    }
  protected:
    string name;
    int age;
};

// Derived class of Grandparent
class Parent : public Grandparent {
  public:
    Parent(string name, int age, string city) :
       Grandparent(name, age), city(city) {}

    void residence() {
        cout << name << " lives in " << city << endl;
    }
  protected:
    string city;
};

// Derived class of Parent
class Child : public Parent {
  public:
    Child(string name, int age, string city ,string favoriteToy) : Parent(name, age, city), favoriteToy(favoriteToy) {}
    void play() {
        cout << name << " is playing with " << favoriteToy << endl;
    }
  private:
    string favoriteToy;
};

int main()
{
  Child person("Ben", 12, "Los Angeles", "Legos"); // Creates a Child object
  person.sleep();
  person.print_age();
  person.residence();
  person.play();
}
```

### Exercises
**1.** Using the table below that has a family structure and access specifiers, list the variables the child has access to.
|             | Public | Protected | Private |
|:-----------:|:------:|:---------:|:-------:|
| Grandparent | int a; |   int b;  |  int c; |
|    Parent   | int d; |   int e;  |  int f; |
|    Child    | int g; |   int h;  |  int i; |

**2.** Extend the ```Country``` class from the 4th exercise at the top of the page and add a derived class of the ```State``` class called ```City```. The ```City``` class should have a member variable called ```Mayor```, a constructor, and a ```describeCity``` function. Also update variables to be contained within the preferred access specifier and split up the class into different files.

## Multiple Classes inheritance
C++ multi-class inheritance refers to a situation where a derived class is derived from two or more base classes. This means that the derived class inherits properties and functionalities from all of the base classes.

### Example
```
// Define the first base class
class BaseClass1 {
public:
    void method1() {
        // Method implementation for BaseClass1
    }
};

// Define the second base class
class BaseClass2 {
public:
    void method2() {
        // Method implementation for BaseClass2
    }
};

// Define the derived class that inherits from both BaseClass1 and BaseClass2
class DerivedClass : public BaseClass1, public BaseClass2 {
public:
    void method3() {
        // Method implementation for DerivedClass
    }
};

int main() {
    DerivedClass obj;
    obj.method1(); // Call method1 from BaseClass1
    obj.method2(); // Call method2 from BaseClass2
    obj.method3(); // Call method3 from DerivedClass
    return 0;
}

```

![image](https://user-images.githubusercontent.com/111817058/228981979-8137ceb8-d5d3-41fd-bd0f-117e94c8ba53.png)

### Excersise
**1.** 
Create three classes: 
- Student
- Teacher
- Course 

The Student and Teacher classes are base classes.

**Student:** 
- Member functions:
  - Constructor
  - describeStudent()

- Member Variables:
  - studentName 
  - studentAge
  - major

**Teacher:**
- Member functions:
  - Constructor
  - describeTeacher()

- Member Variables:
  - teacherName 
  - teacherAge
  - department

The Course class inherits from both the Student and Teacher classes using multiple class inheritance.

**Course:**
- Member functions:
  - Constructor
  - describeCourse()

- Member Variables:
  - courseName

In the main function create a course object, pass the required data for the class, and call each describe function.

## Polymorphism

Inheritance is also a way to achieve polymorphism in C++. By inheriting from a base class, a derived class can have access to the base class's methods and attributes, and can override or extend them. This means that objects of the derived class can be used in the same way as objects of the base class.

### Example
```
#include <iostream>
using namespace std;

// Base class
class Animal {
public:
    virtual void speak() {
        cout << "Animal speaks!" << endl;
    }
};

// Derrived Class
class Dog : public Animal {
public:
    void speak() override {
        cout << "Bark!" << endl;
    }
};

// Derrived class
class Cat : public Animal {
public:
    void speak() override {
        cout << "Meow!" << endl;
    }
};

int main() {
    Animal animal;
    Dog dog;
    Cat cat;

    animal.speak();
    dog.speak();
    cat.speak();
}
```

The use of virtual functions is important in this example to achieve dynamic polymorphism. By declaring the ```speak()``` method as virtual in the base class, we allow derived classes to override it with their own implementation. When we call the method on a derived class object, the appropriate implementation is called based on the actual type of the object. This allows us to write code that works with objects of different classes without knowing their exact type at compile-time.

### Exercises
**1.** Create a ```Superhero``` class with a ```useSuperpower()``` method. Then create two derived classes: ```Flash``` and ```Superman```. Each derived class should implement its own version of the ```useSuperpower()``` method by printing out a statement about their super powers. Finally, create a program that creates objects of each class and calls the ```useSuperpower()``` method for each object, demonstrating the polymorphic behavior of the virtual method.

**2.** Create a ```VideoGameCharacter``` class with a ```jump()``` method. Then create two derived classes: ```Mario``` and ```Sonic```. Each derived class should implement its own version of the ```jump()``` method, but the implementation should involve different mechanics (e.g., Mario jumps higher but slower, Sonic jumps lower but faster). Finally, create a program that creates objects of each class and calls the ```jump()``` method for each object.
