---
layout: project
type: project
image: img/Area-of-a-Square-1.png
title: "Area Calculator"
date: 2023
published: true
labels:
  - C
  - Solo Project
  - ICS 212
summary: "A lone project for my ICS 212 course which the objective is to calculate the areas of shapes."
---

This program written in C has the objective of calculating the area of shapes. The user would input their choice of shape they would like to find an area of, and must provide some dimension of value for the program to use in its calculations. Returned would be the area of the shape of their choice. This was one of my midterm projects for my ICS 212 course, and was reflective of all I had learned so far until that point.  

The following code is the entirety of the project. 

<hr>

<pre>

#include <stdio.h>
//calculate function takes input from main and calculates and prints the result.
void calculate (int d, int c){
    float result;
    if(c==1){ //if c==1, then it will calculate circle
        result = 3.1415926535*(d*d);
        printf("\nThe Area of a circle of radius %d is equal to:\n%.1f", d, result);
    }
    else if(c==2){ //if c==2, then it will calculate square
        result = d*d;
        printf("\nThe Area of a square with sides of %d is equal to:\n%.1f", d, result);
    }
    else { //if c==1, then it will calculate sphere
        result = 4*3.1415926535*(d*d);
        printf("\nThe Area of a sphere of radius %d is equal to:\n%.1f", d, result);
    }
}

void main(){
    
    //part II. Area Calculator Menu Driven Program
    int choice, dimension;
    printf("Press 1 to calculate the area of a circle.\n");
    printf("Press 2 to calculate the area of a square.\n");
    printf("Press 3 to calculate the area of a sphere.\n");

    printf("Enter your choice: ");
    scanf("%d", &choice);

    if(choice==1){ //prints out accordingly for circle
        printf("Enter radius: ");
        scanf("%d", &dimension);
        calculate(dimension, choice);
    }
    else if(choice==2){ //prints out accordingly for square
        printf("Enter side: ");
        scanf("%d", &dimension);
        calculate(dimension, choice);
    }
    else { //prints out accordingly for sphere
        printf("Enter radius: ");
        scanf("%d", &dimension);
        calculate(dimension, choice);
    }

}

  
</pre>

<hr>
