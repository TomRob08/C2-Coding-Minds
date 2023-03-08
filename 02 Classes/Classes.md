# Classes

Let's look at what the dog class from the intro lesson might look like:
```
#include <iostream>
using namespace std;

class Dog {
  public:
    string name;
    string color;
    int age;

    void bark(){
      cout << "Woof" << endl;
    }
};

int main() {
  Dog lab;
  lab.name = "Maggie";
  cout << lab.name << endl;
  lab.color = "Chocolate";
  cout << lab.color << endl;
  lab.age = 11;
  cout << lab.age << endl;

  lab.bark();
}
```

**Output**
```
Maggie
Chocolate
11
Woof
```

The code above works fine, it does what we intend but it doesn't take advantage of a key feature of classes which is encapsulation.

## Encapsulation
Encapsulation refers to the concept of hiding the implementation details of a class and only exposing a well-defined public interface for interacting with its objects. In C++, encapsulation is implemented by using access specifiers, namely public, private, and protected, to control the access to the members of a class.

Public members of a class can be accessed from anywhere in the program, but private members can only be accessed from within the class itself. Protected members can be accessed from within the class and its derived classes. By default, all members of a class are private. Classes usually have private member variables and public member functions.

By keeping the implementation details of a class private, we can ensure that the data and behavior of the class are not accidentally or maliciously modified from outside the class. Instead, we can define public member functions that provide a well-defined interface for interacting with the class.

### Example
```
class Dog {
  public:
    void bark(){
      cout << "Woof" << endl;
    }

    void set_name(string name) {
      this->name = name;
    }

    string get_name() {
      return name;
    }

    void set_color(string color) {
      this->color = color;
    }

    string get_color() {
      return color;
    }

    void set_age(int age) {
      this->age = age;
    }

    int get_age() {
      return age;
    }

  private:
    string name;
    string color;
    int age;
};

int main() {
  Dog lab;
  lab.set_name("Maggie");
  cout << lab.get_name() << endl;
  lab.set_color("Chocolate");
  cout << lab.get_color() << endl;
  lab.set_age(11);
  cout << lab.get_age() << endl;

  lab.bark();
}
```

This program now has functions called "Getters" and "Setters" to act as the middle man between private variables and anything outside of the class.

Notice how in ```set_name```, ```set_color```, and ```set_age``` it has ```this->```. ```this->``` is a reference to the classes member variables and is required when the function parameter has the same name as the member functions. If the function parameter is a different name then ```this->``` is not required and also notice how the ```get_``` functions don't have ```this->``` because it is not required.

### Exercises
**1.** Why should we use encapsulation?

**2.** What are the two names for functions that allow interactions with the private variables?

**3.** Create a class called ```Person``` that has two private member variables ```name``` and ```age```. Define public member functions ```get_name()```, ```get_age()```, ```set_name()```, and ```set_age()``` to access and modify the values of name and age. Also, define a public member function ```print_info()``` that prints the name and age of the person. Finally, write a program that creates two Person objects, sets their names and ages, and prints their information. The first person's name will be Kyle with an age of 15 and the second person's name will be Jessica with an age of 17.

**4.** Create a class called ```Car``` that has two private member variables ```make``` and ```model```. Define public member functions ```get_make()```, ```get_model()```, ```set_make()```, and ```set_model()``` to access and modify the values of make and model. Also, define a public member function ```print_info()``` that prints the make and model of the car. Finally, write a program that creates a three Car objects, sets their make and model, and prints their information. The first car will be Ford Mustang, the second car will be Toyota Supra, and the third car will be BMW M3.

## Constructors
A constructor is a special member function of a C++ class that is automatically called when an object of the class is created. The purpose of the constructor is to initialize the object's member variables to some initial values. The constructor has the same name as the class and no return type.

Constuctors also enable programmers to reduce the amount of setter functions in the class.

### Example
```
class Dog {
  public:
    Dog(string name, string color, int age) {
      this->name = name;
      this->color = color;
      this->age = age;
    }

    void bark(){
      cout << "Woof" << endl;
    }

    string get_name() {
      return name;
    }

    string get_color() {
      return color;
    }

    int get_age() {
      return age;
    }

  private:
    string name;
    string color;
    int age;
};

int main() {
  Dog lab("Maggie", "Chocolate", 11);
  cout << lab.get_name() << endl;
  cout << lab.get_color() << endl;

  cout << lab.get_age() << endl;

  lab.bark();
}
```

**Output**
```
Maggie
Chocolate
11
Woof
```

### Exercises
**1.** Create a class called ```Book``` that has three private member variables ```title```, ```author```, and ```pages```. Define public member functions ```get_title()```, ```get_author()```, ```get_pages()```, and ```print_info()``` to access and print the values of title, author, and pages. Also, define a public constructor that takes three parameters for title, author, and pages and initializes the corresponding member variables. Finally, write a program that creates a Book object using the constructor, and prints its information using the ```print_info()``` member function. The book will be Diary of a Wimpy Kid by Jeff Kinney which has 221 pages.

**2.** Create a class called ```Rectangle``` that has two private member variables ```width``` and ```height```. Define public member functions ```get_width()```, ```get_height()```, and a constructor that takes two parameters for width and height and initializes the corresponding member variables. Also, define a public member function ```get_area()``` that returns the area of the rectangle. Finally, write a program that creates a Rectangle object, sets its width and height to 5 and 10 respectively, and prints its area.

**3.** Create a class called ```Date``` that has three private member variables ```day```, ```month```, and ```year```. Define public member functions ```get_day()```, ```get_month()```, ```get_year()```, and a constructor that takes three parameters for day, month, and year and initializes the corresponding member variables. Also, define a public member function print_date() that prints the date in the format "day/month/year". Finally, write a program that creates a Date object, sets its day, month, and year, and prints its date.
