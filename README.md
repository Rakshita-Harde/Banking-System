# Banking-System
//2.Write a Java program to simulate a simple banking application.

// BankAccount.java
public class BankAccount {
    private double balance;

    // Constructor to initialize balance
    public BankAccount(double initialBalance) {
        if (initialBalance >= 0) {
            this.balance = initialBalance;
        } else {
            System.out.println("Initial balance cannot be negative. Setting balance to ₹0.0");
            this.balance = 0;
        }
    }

    // Method to deposit money into the account
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: ₹" + amount);
        } else {
            System.out.println("Deposit amount must be positive.");
        }
    }

    // Method to withdraw money from the account
    public void withdraw(double amount) {
        if (amount > 0) {
            if (amount <= balance) {
                balance -= amount;
                System.out.println("Withdrew: ₹" + amount);
            } else {
                System.out.println("Error: Insufficient balance. Withdrawal amount exceeds balance.");
            }
        } else {
            System.out.println("Withdrawal amount must be positive.");
        }
    }

    // Method to check the current balance
    public double getBalance() {
        return balance;
    }

    public static void main(String[] args) {
        // Create a new BankAccount object with an initial balance of ₹1000
        BankAccount account = new BankAccount(1000);

        // Display the initial balance
        System.out.println("Initial Balance: ₹" + account.getBalance());

        // Perform some transactions
        account.deposit(500);       // Deposit ₹500
        System.out.println("Current Balance: ₹" + account.getBalance());

        account.withdraw(300);      // Withdraw ₹300
        System.out.println("Current Balance: ₹" + account.getBalance());

        account.withdraw(1500);     // Attempt to withdraw ₹1500 (should trigger error)
        System.out.println("Current Balance: ₹" + account.getBalance());

        account.withdraw(-100);     // Attempt to withdraw a negative amount (should trigger error)
        System.out.println("Current Balance: ₹" + account.getBalance());
    }
}


//output

Initial Balance: ₹1000.0
Deposited: ₹500.0
Current Balance: ₹1500.0
Withdrew: ₹300.0
Current Balance: ₹1200.0
Error: Insufficient funds. Withdrawal amount exceeds balance.
Current Balance: ₹1200.0
Withdrawal amount must be positive.
Current Balance: ₹1200.0

