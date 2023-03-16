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
**1.** Create a ```Country``` class that has ```name```, ```population```, and ```capital``` attributes and a ```describe()``` method that prints out the name, population, and capital of the country. Create a State class that inherits from the Country class and has a ```governor``` member and a ```describe()``` method that prints out the name, population, and capital of the state and the name of the governor. Create constructors for the base class and subclass. For now just have all code in public for both classes. Finally, create a country and state object relating to where you're from with relevant information and use the describe function for both objects.

## Access Specifiers
Access specifiers in C++ class inheritance are used to control the accessibility of base class members in the derived class. The three access specifiers in C++ are public, protected, and private.

- Public: Public members of the base class are accessible to the derived class and also to code outside the derived class.

- Protected: Protected members of the base class are accessible to the derived class and its subclasses, but not to code outside the derived class.

- Private: Private members of the base class are not accessible to the derived class or code outside the base class.
