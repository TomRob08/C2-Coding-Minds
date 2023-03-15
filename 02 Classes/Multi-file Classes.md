# Splitting classes into different files

## Why should you do this?
C++ classes can become quite large and complex, especially in larger programs. Splitting a class up into different files can make the code more organized and easier to manage. Here are a few reasons why C++ classes should be split up into different files:

- Modularity: By splitting a class up into different files, you can create smaller, more modular pieces of code. This can make it easier to read and understand the code, and can also make it easier to test and maintain.

- Reusability: Splitting a class up into different files can make it easier to reuse pieces of code in other parts of your program or in other programs. You can also share these files with other developers who may want to use your code.

- Compilation: Large classes can take a long time to compile, which can slow down the development process. By splitting a class up into different files, you can compile only the files that have been changed, which can save time.

- Collaboration: If you are working on a team, splitting a class up into different files can make it easier for multiple developers to work on the same code at the same time without causing conflicts.

- Readability: Splitting a class up into different files can make it easier to read and understand the code. It can also make it easier to find specific pieces of code if you need to make changes or add new features.

## Header files

In C++, a class header file is a file that declares the class, its member functions, and member variables. The header file typically has a ".h" extension and is included in other C++ files that use the class.

The purpose of a class header file is to separate the declaration of the class from its implementation. By separating these two aspects of the class, it makes it easier to read and maintain the code.

Here's an example of what a class header file might look like:
**File name:** myClass.h
```
#ifndef MYCLASS_H
#define MYCLASS_H

class MyClass {
public:
    MyClass(); // default constructor
    MyClass(int a); // constructor with one argument
    int getValue(); // public member function
    void setValue(int a); // public member function
private:
    int value; // private member variable
};

#endif
```

The first two lines of the header file prevent multiple includes of the same file. After the class declaration, the header file ends with an ```#endif``` directive, which closes the header file.
