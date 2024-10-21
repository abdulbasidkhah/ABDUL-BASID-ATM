# ABDUL-BASID-ATM
Atm system.clas 
import java.util.Scanner;

public class ATMSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int balance = 1000; // Initial balance
        int choice;
        
        do {
            System.out.println("Welcome to the ATM System!");
            System.out.println("1. Check Balance");
            System.out.println("2. Deposit");
            System.out.println("3. Withdraw");
            System.out.println("4. Exit");
            System.out.print("Please select an option: ");
            choice = scanner.nextInt();
            
            switch (choice) {
                case 1:
                    // Check balance
                    System.out.println("Your current balance is: $" + balance);
                    break;
                case 2:
                    // Deposit money
                    System.out.print("Enter amount to deposit: $");
                    int deposit = scanner.nextInt();
                    if (deposit > 0) {
                        balance += deposit;
                        System.out.println("You've successfully deposited $" + deposit);
                    } else {
                        System.out.println("Invalid deposit amount.");
                    }
                    break;
                case 3:
                    // Withdraw money
                    System.out.print("Enter amount to withdraw: $");
                    int withdraw = scanner.nextInt();
                    if (withdraw > 0 && withdraw <= balance) {
                        balance -= withdraw;
                        System.out.println("You've successfully withdrawn $" + withdraw);
                    } else if (withdraw > balance) {
                        System.out.println("Insufficient funds.");
                    } else {
                        System.out.println("Invalid withdrawal amount.");
                    }
                    break;
                case 4:
                    // Exit the system
                    System.out.println("Thank you for using the ATM. Goodbye!");
                    break;
                default:
                    System.out.println("Invalid option. Please try again.");
            }
            System.out.println();
        } while (choice != 4);

        scanner.close();
    }
}
