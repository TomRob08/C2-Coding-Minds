# Grocery List

Grocery lists are a great way to remember what you have to buy at the store. Let's make a program to create a grocery list for the items you have to buy.

Using the code below, complete each grocery list task (add, delete, clear, and print).

```
#include <iostream>
#include <vector>
using namespace std;

void add_to_list(vector<string>& groceryList, string item)
{
  string item = "";
  
  cout << "Please enter an item:" << endl;
  cin.ignore();
  getline(cin, item);
  // Add item
}

void del_from_list(vector<string>& groceryList, string item)
{
  string item = "";
  
  cout << "Please enter an item:" << endl;
  cin.ignore();
  getline(cin, item);
  
  // Delete item
}

void printList(vector<string> groceryList)
{
  // Print list
}

int main() 
{
  string userChoice = "";
  vector<string> groceryList;

  while(true)
  {
    cout << "Would you like to add an item, delete an item, clear all items or print the list?\n" <<
          "(Enter add, delete, clear, print or \'*' to end the program)" << endl;

    cin >> userChoice;

    if(userChoice == "*")
      break;

    else if(userChoice == "add")
    {
      // Add item to list
    }

    else if(userChoice == "delete")
    {
      // Delete item from list
    }

    else if(userChoice == "clear")
    {
      // Clear the list
    }

    else if(userChoice == "print")
    {
      // Print the list
    }

    else
      cout << "Invalid choice." << endl;
  }
  return 0;
}
```
