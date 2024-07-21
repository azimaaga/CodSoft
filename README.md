# CodSoft
Internship Tasks

TASK 1 - RANDOM NO GAME

import java.util.Random;
import java.util.Scanner;
public class TASK1 {
    public static void main (String[] args){

        int ans,guess;
        final int MAX = 10;

        Scanner keyboard = new Scanner(System.in);
        Random ran=new Random();

        ans = ran.nextInt(MAX)+1;
        System.out.print("Guess a number between 1 and 10: ");
        guess=keyboard.nextInt();

        if(guess==ans){
            System.out.println("Good job, the number was" + ans);

        }
        else
        {
            System.out.println("Sorry, but the number was" + ans);
        }
    }
        
    }

TASK2- STUDENT GRADE SYSTEM

import java.util.Scanner;
public class TASK2 {
public static void main(String[] args) {
    Scanner scan = new Scanner(System.in);

    
    System.out.println("Enter total number of subjects: ");
    int numofSubjects = scan.nextInt();

    int totalMarks = 0;

    for (int i = 1; i <= numofSubjects; i++) {
        System.out.println("Enter marks for subject " + i + "(out of 100): ");
        int marks = scan.nextInt();

      
        while (marks < 0 || marks > 100) {
            System.out.println("Invalid marks. Please enter marks between 0 and 100.");
            System.out.println("Enter marks for subject " + i + "out of 100): ");
            marks = scan.nextInt();
        }
        totalMarks += marks;
    }
    System.out.println("Student Result: ");
    System.out.println("Total marks obtained in all subjects: " + totalMarks);

    

    int AveragePercentage = totalMarks / numofSubjects;

    System.out.println("Average Percentage: " + AveragePercentage);


    if (AveragePercentage >= 90) {
        System.out.println("Your grade: A+");
    }

    else if (AveragePercentage >= 80) {
        System.out.println("Your grade: B+");
    }

    else if (AveragePercentage >= 70) {
        System.out.println("Your grade: B");
    }

    else if (AveragePercentage >= 60) {
        System.out.println("Your grade: C+");
    }

    else if (AveragePercentage >= 50) {
        System.out.println("Your grade: C");
    }

    else if (AveragePercentage >= 40) {
        System.out.println("Your grade: D+");
    }

    else if (AveragePercentage >= 30) {
        System.out.println("Your grade: D");
    }

    else {
        System.out.println("Your grade is: E");
    }

    scan.close();
}
}

TASK3- ATM INTERFACE


package codsoft_project;
import java.util.Scanner;

		class BankAccount {
		    private double balance;

		    public BankAccount(double initialBalance) {
		        this.balance = initialBalance;
		    }

		    public double getBalance() {
		        return balance;
		    }

		    public void deposit(double amount) {
		        if (amount > 0) {
		            balance += amount;
		            System.out.println("Deposit successful. New balance: " + balance);
		        } else {
		            System.out.println("Invalid amount for deposit.");
		        }
		    }

		    public void withdraw(double amount) {
		        if (amount > 0 && amount <= balance) {
		            balance -= amount;
		            System.out.println("Withdrawal successful. New balance: " + balance);
		        } else {
		            System.out.println("Insufficient funds or invalid amount for withdrawal.");
		        }
		    }
		}

		class ATM {
		    private BankAccount account;
		    private Scanner scanner;

		    public ATM(BankAccount account) {
		        this.account = account;
		        this.scanner = new Scanner(System.in);
		    }

		    public void showMenu() {
		    	
		        
		        System.out.println("1. Check Balance");
		        System.out.println("2. Deposit");
		        System.out.println("3. Withdraw");
		        System.out.println("4. Exit");
		        System.out.println("********************");
		    }

		    public void run() {
		        int choice;
		        do {
		            showMenu();
		            System.out.print("Enter your choice: ");
		            choice = scanner.nextInt();
		            switch (choice) {
		                case 1:
		                    checkBalance();
		                    break;
		                case 2:
		                    deposit();
		                    break;
		                case 3:
		                    withdraw();
		                    break;
		                case 4:
		                    System.out.println("Thank you visit again!");
		                    break;
		                default:
		                    System.out.println("Invalid choice. Please select a valid option.");
		            }
		        } while (choice != 4);
		    }

		    private void checkBalance() {
		        System.out.println("Your current balance is: " + account.getBalance());
		    }

		    private void deposit() {
		        System.out.print("Enter the amount to deposit: ");
		        double amount = scanner.nextDouble();
		        account.deposit(amount);
		    }

		    private void withdraw() {
		        System.out.print("Enter the amount to withdraw: ");
		        double amount = scanner.nextDouble();
		        account.withdraw(amount);
		    }
		}

		public class ATM_Interface {

			public static void main(String[] args) {
				System.out.println("Welcome to the ATM!");
				Scanner sc =new Scanner (System.in);
				 System.out.print("Enter your four Digit PIN: ");
			        int enteredPin = sc.nextInt();
			
		        BankAccount userAccount = new BankAccount(10000.0); // Initial balance
		        ATM atm = new ATM(userAccount);
		        atm.run();
		    }
		
		}

	

