# Bank-Management-System
#include<iostream>
using namespace std;

class BankAccount {
private:
    string name;
    int accountNumber;
    float balance;

public:
    // Create account
    void createAccount() {
        cout << "Enter your name: ";
        cin >> name;
        cout << "Enter account number: ";
        cin >> accountNumber;
        cout << "Enter initial balance: ";
        cin >> balance;
        cout << "Account created successfully!\n\n";
    }

    // Deposit money
    void deposit() {
        float amount;
        cout << "Enter amount to deposit: ";
        cin >> amount;
        balance += amount;
        cout << "Amount deposited successfully!\n\n";
    }

    // Withdraw money
    void withdraw() {
        float amount;
        cout << "Enter amount to withdraw: ";
        cin >> amount;
        if(amount <= balance) {
            balance -= amount;
            cout << "Amount withdrawn successfully!\n\n";
        } else {
            cout << "Insufficient balance!\n\n";
        }
    }

    // Display details
    void display() {
        cout << "\n--- Account Details ---\n";
        cout << "Name: " << name << endl;
        cout << "Account Number: " << accountNumber << endl;
        cout << "Balance: ₹" << balance << endl << endl;
    }
};

int main() {
    BankAccount account;
    int choice;

    while(true) {
        cout << "====== Bank Menu ======\n";
        cout << "1. Create Account\n";
        cout << "2. Deposit\n";
        cout << "3. Withdraw\n";
        cout << "4. Display Details\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch(choice) {
            case 1: account.createAccount(); break;
            case 2: account.deposit(); break;
            case 3: account.withdraw(); break;
            case 4: account.display(); break;
            case 5: cout << "Thank you for using the Bank System.\n"; return 0;
            default: cout << "Invalid choice!\n";
        }
    }

    return 0;
}
