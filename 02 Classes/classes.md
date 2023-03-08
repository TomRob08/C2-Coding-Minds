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

Notice how in ```set_name```, ```set_color```, and ```set_age``` it has ```this->```. ```this->``` is a reference to the classes member variables and is required when the function parameter has the same name as the member functions. If the function parameter is a different name then ```this->``` is not required and also notice how the ```get_``` functions don't have ```this->``` because it is not required.

### Exercises
**1.** Create a class called Person that has two private member variables name and age. Define public member functions get_name(), get_age(), set_name(), and set_age() to access and modify the values of name and age. Also, define a public member function print_info() that prints the name and age of the person. Finally, write a program that creates two Person objects, sets their names and ages, and prints their information.
