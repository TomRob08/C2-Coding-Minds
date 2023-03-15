# Splitting classes into different files

## Why should you do this?
C++ classes can become quite large and complex, especially in larger programs. Splitting a class up into different files can make the code more organized and easier to manage. Here are a few reasons why C++ classes should be split up into different files:

- Modularity: By splitting a class up into different files, you can create smaller, more modular pieces of code. This can make it easier to read and understand the code, and can also make it easier to test and maintain.

- Reusability: Splitting a class up into different files can make it easier to reuse pieces of code in other parts of your program or in other programs. You can also share these files with other developers who may want to use your code.

- Compilation: Large classes can take a long time to compile, which can slow down the development process. By splitting a class up into different files, you can compile only the files that have been changed, which can save time.

- Collaboration: If you are working on a team, splitting a class up into different files can make it easier for multiple developers to work on the same code at the same time without causing conflicts.

- Readability: Splitting a class up into different files can make it easier to read and understand the code. It can also make it easier to find specific pieces of code if you need to make changes or add new features.

## Class Declaration File

In C++, a class header file is a file that declares the class, its member functions, and member variables. The header file typically has a ".h" extension and is included in other C++ files that use the class.

The purpose of a class header file is to separate the declaration of the class from its implementation. By separating these two aspects of the class, it makes it easier to read and maintain the code.

Here's an example of what a class header file might look like:

**File name:** myClass.h

```
#ifndef MYCLASS_H
#define MYCLASS_H

class MyClass {
public:
    MyClass(int a); // constructor with one argument
    int getValue(); // public member function
    void setValue(int a); // public member function
private:
    int value; // private member variable
};

#endif
```

The first two lines of the header file prevent multiple includes of the same file. After the class declaration, the header file ends with an ```#endif``` directive, which closes the header file.

## Class Definition file

In C++, a class definition file contains the implementation of the class member functions. The definition file typically has a ".cpp" extension.

The purpose of a class definition file is to separate the implementation of the class from its declaration which continues to help with the readability of code.

Here's an example of what a class definition file might look like:

**File name:**  myClass.cpp

```
#include "MyClass.h"

MyClass::MyClass(int value) 
 : value(value)
{
}

int MyClass::getValue() {
    return value;
}

void MyClass::setValue(int value) {
    this->value = value;
}
```

In this example, we are implementing the member functions of the ```MyClass``` class that was declared in the header file ```MyClass.h```.

The first line of the definition file includes the header file that declares the class. The rest of the file defines the member functions of the class.

The member function definitions must specify the scope of the function using the class name followed by the scope resolution operator ```::```. This indicates that the function belongs to the class ```MyClass```. The definitions of the member functions follow the same names as the declarations in the header file.

## Using the class in main

```
#include <iostream>
using namespace std;
#include "MyClass.h"

int main() {
    MyClass obj2(20); // initialize an object of MyClass using constructor with one argument
    cout << "obj2 value: " << obj2.getValue() << endl;

    return 0;
}

```

In this example, we first include the header file for the MyClass class. Then ```obj2```, is initialized using the constructor that takes one integer as the argument. We then use the ```getValue()``` function to retrieve the value of ```obj2``` and print it.

## Rules
1. Never, ever ```#include``` a source (.cpp) file
2. Each class declaration is put into its own header (.h) file
3. Each class definition is put into its own source (.cpp) file
4. Other functions, including the ```main``` function are put into their own source (.cpp) file

## Exercises
**1.** What are some reasons for splitting a class into different files?

**2.** What is the class declaration file?

**3.** What is the class definition file?

**4.** Using the code below, create declaration and definition files for the class. Make sure to have ```#include <string>``` and ```using namespace std``` in your declaration file and ```#include <iostream>``` and ```using namespace std``` in your definition file.
```
#include <iostream>
using namespace std;

class Car {
  public:
    // Constructor
    Car(string make, string model, int year, double price) 
    : make(make), model(model), year(year), price(price) {}

    void printDetails() {
        cout << "Make: " << make << endl;
        cout << "Model: " << model << endl;
        cout << "Year: " << year << endl;
        cout << "Price: $" << price << endl;
      }

  private:
    string make;
    string model;
    int year;
    double price;
};


int main() {
  Car sedan("Honda", "Accord", 2010, 10000);
  sedan.printDetails();

  return 0;
}
```

**5.** Using the code below, create declaration and definition files for the class. Make sure to have ```#include <string>``` and ```using namespace std``` in your declaration file and ```#include <iostream>``` and ```using namespace std``` in your definition file.

```
#include <iostream>
using namespace std;

class Student {
  public:
    // Constructor
    Student(std::string name, int age, std::string major, double gpa) 
    : name(name), age(age), major(major), gpa(gpa) {}

    void printInfo() const {
        cout << "Name: " << name << endl;
        cout << "Age: " << age << endl;
        cout << "Major: " << major << endl;
        cout << "GPA: " << gpa << endl;
    }

    bool isHonorsStudent() const {
        return gpa >= 3.5;
    }
    
  private:
    string name;
    int age;
    string major;
    double gpa;
};

int main()
{
  Student s1("Todd", 19, "Computer Science", 3.4);
  Student s2("Christine", 20, "Math", 3.9);

  s1.printInfo();
  if(s1.isHonorsStudent()) cout << "Dean's List" << endl;

  cout << endl;
  
  s2.printInfo();
  if(s2.isHonorsStudent()) cout << "Dean's List" << endl;
  return 0;
}
```
