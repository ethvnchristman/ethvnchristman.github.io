---
layout: project
type: project
image: img/how-to-draw-a-bank-step-9.jpg
title: "Simple Banking System"
date: 2023
published: true
labels:
  - C
  - Self Project
  - ICS 212
summary: "A program which functions as a simplistic banking system."
---
This project was an endeavor to create a program which could function as a banking system. 
This meant it had to have the basic functions of checking the account balance, depositing a certain amount, and withdrawing a certain amount. Checking the account balance consisted of returning the value of a global balance value, initialized at 0 right at the beginning of the program. Depositing and withdrawing are straight forward as well, which adds or subtracts to the global balance value, based on the users choice in the menu display.

I had the role of both planning out and developing the code for this project, since it was a solo project. Recieving a prompt of what the program has to do was all that was given, so it was challenging to come up with a reasonable choice of action and then implement it into code. I learned a lot from this specific project because at first I found it much more challenging, and that was because I overthought more than I needed to. This project and its ups and downs through its creation taught me valuable lessons about reviewing prompts / requirements and finding the balance of efficiency and quality; a program that did what was required but also add some sense of thoughtfulness whether it be in the users interface or maybe a choice in code which runs more efficiently than another. 

The following is a snapshot of the code.

<hr>

<pre>

#include <stdio.h>

//simple banking system
float balance = 0; //global value of balance, to be altered throughout program

void checkBalance(){
    printf("Your balance is: $%.2f\n", balance); //simply prints global balance value
}

void deposit(){
    float amount; //temporary user input as amount
    printf("Enter the amount to deposit: ");
    scanf("%f", &amount); 
    balance += amount; //adds amount to current balance
    printf("Deposit successful. Your balance is now $%.2f\n", balance); //prints

}

void withdraw(){
    float amount; //temp user input as amount
    printf("Enter the amount to withdraw: ");
    scanf("%f", &amount);
    balance -= amount; //subtracts amount from current balance
    printf("Withdrawal successful. Your balance is now: $%.2f\n", balance); //prints

}

int menuDisplay(){ //display function so it can call itself to repeat the menu after each task until user selects to exit.
    int choice; //holds user input of what function they want
    printf("\nSimple Banking System Menu:\n");
    printf("1. Check balance\n");
    printf("2. Deposit funds\n");
    printf("3. Withdraw funds\n");
    printf("4. Exit\n");
    printf("Enter your choice: ");
    scanf("%d", &choice); //scans choice
    switch (choice) { //switch case which calls specific functions according to what value the user entered.
        case 1:  //checks the balance
            checkBalance();
            menuDisplay();
            break;
        case 2: //deposits funds
            deposit();
            menuDisplay();
            break;
        case 3: //withdraws funds
            withdraw();
            menuDisplay();
            break;
        case 4: //exits the program
            printf("Exiting the banking system. Goodbye!");
            return 0;
        default: //throws an error and ends code if user inputs anything other than the given options.
            printf("Invalid option, exiting system.");
            return 0;

    }

    

}
int main(){
    menuDisplay();
    return 0;
}
  
</pre>

<hr>
