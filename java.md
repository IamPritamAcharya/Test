Java Code
Step 1: Create a Package atmapp and Add Classes
We'll create an ATMInterface, User, and implement the functionalities.
1. Interface ATMInterface.java
java
CopyEdit
package atmapp;

public interface ATMInterface {
    void withdraw(double amount) throws InsufficientFundException;
    void fastWithdraw(double amount) throws InsufficientFundException;
    void deposit(double amount) throws InsufficientCurrentBalanceException;
    void changePin(int newPin);
}
________________________________________
2. Custom Exceptions ATMExceptions.java
java
CopyEdit
package atmapp;

class IncorrectPinException extends Exception {
    @Override
    public String toString() {
        return "Incorrect PIN! Access Denied.";
    }
}

class InsufficientFundException extends Exception {
    @Override
    public String toString() {
        return "Insufficient funds! Cannot process withdrawal.";
    }
}

class InsufficientCurrentBalanceException extends Exception {
    @Override
    public String toString() {
        return "Balance is below ₹3000. 10% of the deposit is kept as pending.";
    }
}
________________________________________
3. User Class User.java
java
CopyEdit
package atmapp;

public class User {
    private String userId;  // Phone Number
    private int pin;        // Birth Year
    private double balance;
    private double pendingBalance = 0.0;

    public User(String userId, int pin, double balance) {
        this.userId = userId;
        this.pin = pin;
        this.balance = balance;
    }

    public boolean verifyPin(int enteredPin) {
        return this.pin == enteredPin;
    }

    public double getBalance() {
        return balance;
    }

    public double getPendingBalance() {
        return pendingBalance;
    }

    public void updateBalance(double amount) {
        this.balance += amount;
    }

    public void updatePendingBalance(double amount) {
        this.pendingBalance += amount;
    }

    public void changePin(int newPin) {
        this.pin = newPin;
    }

    public String getUserId() {
        return userId;
    }
}
________________________________________
4. ATM Implementation ATM.java
java
CopyEdit
package atmapp;

import java.util.Scanner;

public class ATM implements ATMInterface {
    private User user;
    private Scanner scanner = new Scanner(System.in);

    public ATM(User user) {
        this.user = user;
    }

    @Override
    public void withdraw(double amount) throws InsufficientFundException {
        if (amount > user.getBalance()) {
            throw new InsufficientFundException();
        }
        if (user.getBalance() - amount < 3000) {
            System.out.print("Balance will drop below ₹3000. Do you want to contribute ₹500 to pending? (yes/no): ");
            String choice = scanner.next();
            if (choice.equalsIgnoreCase("yes")) {
                user.updatePendingBalance(500);
            }
        }
        user.updateBalance(-amount);
        System.out.println("Withdrawal successful! New balance: ₹" + user.getBalance());
    }

    @Override
    public void fastWithdraw(double amount) throws InsufficientFundException {
        System.out.println("Fast Withdraw: ₹" + amount);
        withdraw(amount);
    }

    @Override
    public void deposit(double amount) throws InsufficientCurrentBalanceException {
        if (user.getBalance() < 3000) {
            double pendingAmount = amount * 0.10;
            user.updatePendingBalance(pendingAmount);
            user.updateBalance(amount - pendingAmount);
            throw new InsufficientCurrentBalanceException();
        }
        user.updateBalance(amount);
        System.out.println("Deposit successful! New balance: ₹" + user.getBalance());
    }

    @Override
    public void changePin(int newPin) {
        user.changePin(newPin);
        System.out.println("PIN successfully changed!");
    }
}
________________________________________
5. Main ATM Execution MainATM.java
java
CopyEdit
import atmapp.*;
import java.util.Scanner;

public class MainATM {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Create a user
        System.out.print("Enter Phone Number (User ID): ");
        String userId = scanner.next();
        System.out.print("Enter Birth Year (PIN): ");
        int pin = scanner.nextInt();
        System.out.print("Enter Initial Balance: ₹");
        double balance = scanner.nextDouble();

        User user = new User(userId, pin, balance);
        ATM atm = new ATM(user);

        System.out.println("\nWelcome to the ATM!");
        System.out.print("Enter User ID: ");
        String enteredUserId = scanner.next();
        System.out.print("Enter PIN: ");
        int enteredPin = scanner.nextInt();

        // Verify PIN
        if (!user.verifyPin(enteredPin)) {
            try {
                throw new IncorrectPinException();
            } catch (IncorrectPinException e) {
                System.out.println("Error: " + e);
                return;
            }
        }

        while (true) {
            System.out.println("\n1. Withdraw\n2. Fast Withdraw\n3. Deposit\n4. Change PIN\n5. Exit");
            System.out.print("Select an option: ");
            int choice = scanner.nextInt();

            try {
                switch (choice) {
                    case 1:
                        System.out.print("Enter amount to withdraw: ₹");
                        double withdrawAmount = scanner.nextDouble();
                        atm.withdraw(withdrawAmount);
                        break;

                    case 2:
                        System.out.println("Fast Withdraw Options: ₹500, ₹1000, ₹2000");
                        System.out.print("Enter amount: ₹");
                        double fastWithdrawAmount = scanner.nextDouble();
                        atm.fastWithdraw(fastWithdrawAmount);
                        break;

                    case 3:
                        System.out.print("Enter deposit amount: ₹");
                        double depositAmount = scanner.nextDouble();
                        atm.deposit(depositAmount);
                        break;

                    case 4:
                        System.out.print("Enter new PIN: ");
                        int newPin = scanner.nextInt();
                        atm.changePin(newPin);
                        break;

                    case 5:
                        System.out.println("Thank you for using our ATM!");
                        return;

                    default:
                        System.out.println("Invalid option! Try again.");
                }
            } catch (InsufficientFundException | InsufficientCurrentBalanceException e) {
                System.out.println("Error: " + e);
            }
        }
    }
}
________________________________________
📌 Sample Input & Output
Case 1: Incorrect PIN
yaml
CopyEdit
Enter User ID: 9876543210
Enter PIN: 2002
Error: Incorrect PIN! Access Denied.
Case 2: Deposit with Low Balance
vbnet
CopyEdit
Enter deposit amount: ₹1000
Error: Balance is below ₹3000. 10% of the deposit is kept as pending.
Case 3: Withdraw
vbnet
CopyEdit
Enter amount to withdraw: ₹4000
Error: Insufficient funds! Cannot process withdrawal.
Case 4: Successful Withdrawal with Contribution Prompt
pgsql
CopyEdit
Enter amount to withdraw: ₹2000
Balance will drop below ₹3000. Do you want to contribute ₹500 to pending? (yes/no): yes
Withdrawal successful! New balance: ₹2800




