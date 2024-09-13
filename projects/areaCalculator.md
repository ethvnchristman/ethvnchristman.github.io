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

This program written in C has the objective of calculating the area of shapes. The user would input their choice of shape they would like to find an area of, and must provide some dimension of value for the program to use in its calculations. Returned would be the area of the shape of their choice. For circle images, the user would input a radius value in order to calculate the area. For squares, the user would input the length of a side, and that will be used to find the area. Lastly for spheres, which had a slightly more difficult calculation, only needed the radius in order to calculate using its algorithms. 

This was a solo project, done for my midterm of my ICS 212 course. It was not very difficult, but taught me a lot about what I had learned so far in that course. It utilized every aspect that I had learned to that point, and thus was reflective about how well I was picking up both the new language as well as my problem solving skills.  

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
