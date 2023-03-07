# Bank account

Create a program that simulates a bank account using C++ classes. 

**Your program should have a BankAccount class with the following private member variables:**
- account_number (integer)
- balance (double)

**Your BankAccount class should have the following public member functions:**
- get_account_number(): returns the account number
- get_balance(): returns the balance
- set_balance(double new_balance): sets the balance to a new value
- deposit(double amount): adds the specified amount to the balance
- withdraw(double amount): subtracts the specified amount from the balance

Your program should create a BankAccount object with an initial balance of $1000. Then, your program should prompt the user to perform one of the following operations:

- Check Balance: Prints the current balance of the account.
- Deposit: Prompts the user to enter an amount to deposit and adds it to the balance.
- Withdraw: Prompts the user to enter an amount to withdraw and subtracts it from the balance.
- Quit: Exits the program.

The user should be able to perform multiple operations until they choose to quit the program. Make sure any number entered by a user isn't negative.
