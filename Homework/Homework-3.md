# Spliting a class into multiple files

Using the code below, split this class into multiple files. 

The class declaration should go in a file named **calculator.h** and the class definition should go in a file named **calculator.cpp**. The main fuction should stay in main.cpp.

```
#include <iostream>
using namespace std;

class Calculator {
    private:
        double num1, num2;
    public:
        Calculator(double n1, double n2) {
            num1 = n1;
            num2 = n2;
        }
        double add() {
            return num1 + num2;
        }
        double subtract() {
            return num1 - num2;
        }
        double multiply() {
            return num1 * num2;
        }
        double divide() {
            if (num2 == 0) {
                cout << "Error: cannot divide by zero.\n";
                return 0;
            }
            else {
                return num1 / num2;
            }
        }
};

int main() {
    double num1, num2;
    cout << "Enter two numbers: ";
    cin >> num1 >> num2;

    Calculator calc(num1, num2);

    cout << "Addition: " << calc.add() << "\n";
    cout << "Subtraction: " << calc.subtract() << "\n";
    cout << "Multiplication: " << calc.multiply() << "\n";
    cout << "Division: " << calc.divide() << "\n";

    return 0;
}
```
