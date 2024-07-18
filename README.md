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

    // Calculate Average Percentage: Divide the 'total marks' by the 'total number
    // of subjects' to get the average percentage.

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
