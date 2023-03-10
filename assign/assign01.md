---
layout: default
title: "Assignment 1: Freefalling"
---

Design due: **Tuesday, February 7th** at the beginning of class

Program due: **Thursday, February 16th by 11:59 PM**

Getting Started
===============

Start by downloading [CS101\_Assign01.zip](CS101_Assign01.zip), saving it in the directory **CS101** within your home directory.

If you are on Windows, start a **Cygwin Bash Shell** and run the following commands:

    cd h:
    cd CS101
    unzip CS101_Assign01.zip
    cd CS101_Assign01

If you are on Linux, start a terminal and run the following commands:

    cd CS101
    unzip CS101_Assign01.zip
    cd CS101_Assign01

Using **Notepad++** (or a Linux text editor such as Pluma), open the file

> **CS101/CS101\_Assign01/Freefall.cpp**

You will add your code to this file.

When you are ready to compile the program, in the Cygwin bash shell (or Linux terminal) window type the command

    make

To run the program, type the command

    ./Freefall.exe

Your Tasks
==========

## Design

Based on the requirements described below in the "Program" section, fill out a [design template](../design-template.pdf).  Consider what the input and output of the program are, and what steps are necessary to compute the output from the input.

The design is due at the beginning of class on **Tuesday, February 7th****.

## Program

Your task is to write a program that prompts the user to enter the height of an object dropped from rest (neglecting air resistance). The program should then print out the object's time to fall to the ground and velocity at impact in several different units including

-   meters/sec
-   ft/sec
-   miles per hour

Here is an example run of the program (user input in **bold**):

<pre>
Enter the initial height of the object in meters: <b>50</b>
The object took 3.19 seconds to fall.
The velocity of the object at impact was:   31.3 m/sec
                                           102.7 ft/sec
                                            70.1 mph
</pre>

The time field should have two decimal places of precision. All of the velocity values should allow for up to four digits *in front* of the decimal point and one digit *after* the decimal point such that the decimal points are aligned in the final output.

Hints
=====

Physics
-------

The basic physics (which many of you will learn this semester in PHY160) governing an object falling only under the influence of gravity (neglecting air resistance) is integration of the acceleration (which for the earth is -9.81 m/s<sup>2</sup>) with respect to time. Hence the velocity of the object as a function of time is given by

> ![image](images/assign01/veleq.png)

where *v(t)* is the velocity at time *t*, *a* is the acceleration due to gravity (-9.81 m/s<sup>2</sup>), and *v*<sub>0</sub> is the initial velocity (which for this assignment is 0).

The position of the object as a function of time is found by integrating the velocity with respect to time as follows

> ![image](images/assign01/poseq.png)

where *x(t)* is the position at time *t* and *x*<sub>0</sub> is the initial position (which for this assignment is the value entered by the user).

Therefore we can find the *time* the object falls in seconds by solving the above equation for *t* setting *x(t)* = 0, *a* = -9.81, *v*<sub>0</sub> = 0

> ![image](images/assign01/timeeq.png)

where *x*<sub>0</sub> is given in meters. Once the time is computed, the velocity at impact is computed from the velocity equation as (again setting *v*<sub>0</sub> and *a* = -9.81)

> ![image](images/assign01/finalveleq.png)

Note the velocity will be negative indicating the object is moving downward, but your output should only show the positive magnitude.

Some useful conversions

> -   3.28 feet in a meter
> -   3600 seconds in an hour
> -   1609 meters in a mile

**USE** the computer to compute the conversion factors for the velocity units by simply writing expressions in your program and storing the results in variables.

Programming
-----------

**START EARLY! And develop the program incrementally!** You should always have a working program at each step (even if only minimally) to make it easier to debug errors. For example, make sure the program obtains the user input properly and then add one computation at a time. Also make sure you follow good programming practices such as **adding comments**, **using meaningful variable names**, and **having proper indentation in the program**.

The square root function in C is

    sqrt(x)

which returns a **double** value which is the square root of *x*. You will need to include the **math.h** library by adding the following line at the top of your program

    #include <math.h>

See pages 346&ndash;353 of the textbook for details regarding the conversion specifiers for **printf**.

Grading
=======

The overall assignment is out of 100 points.

**Design**:

The design is worth up to 15 points.  The design will be graded for effort rather than correctness, so if you make a good faith effort, you should receive full credit for the design.  *However*, if your design is not correct, it will be difficult to implement the program.  We will go over a correct design in class on the day the designs are due, and it is likely that you will receive feedback on your design if you meet with your instructor or a tutor to get help on the assignment.

**Program**:

* Obtaining user input and correctly computing the time is worth up to 55 points
* Above, and computing the final velocity in m/s is worth up to 65 points
* Above, and computing the final velocity in ft/s and mph is worth up to 75 points
* Above, and output formatted correctly is worth up to 85 points

Submitting
==========

Upload your submissions in Canvas.
<b>Important</b>: It is your responsibility to verify that you submitted the correct files.  You may receive a grade of 0 for incorrectly submitted work.
</div>

<!-- vim:set wrap: -->
<!-- vim:set linebreak: -->
<!-- vim:set nolist: -->
