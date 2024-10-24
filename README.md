
# Leap Year Checker in C#
![alt text](https://github.com/Evvol/SpaghettiCode_LeapYearCalculator/blob/main/LeapYearCalculatorScreen.png?raw=true)

This repository contains a single-line C# program that checks if the current year is a leap year by combining several redundant and inefficient logical conditions. The result of the check is printed to the console.

## How It Works

The program follows these steps to determine whether the current year is a leap year:

1.  **Basic Leap Year Conditions**:  
    The logic starts by checking if the current year is divisible by 4, but not divisible by 100 unless also divisible by 400. This is the standard leap year rule.
    
2.  **Date Validation**:  
    Using `DateTime.IsLeapYear()`, the code further verifies if the year contains 366 days by checking specific conditions like whether the day of the year is valid within the range (<= 366 for leap years, <= 365 otherwise). It also ensures that the month value is valid.
    
3.  **Counting Days**:  
    The program redundantly counts the total number of days in the current year (either 365 or 366) using `Enumerable.Range` and compares the result to determine if it is a leap year.
    
4.  **Console Output**:  
    Based on the combined conditions, the program will print:
    
    -   `"Year is a Leap year"` if the year is a leap year.
    -   `"Year is not a Leap year"` otherwise.

## Example Code

csharp

`Console.WriteLine((((((DateTime.Now.Year % 4 == 0 && DateTime.Now.Year % 100 != 0) || (DateTime.Now.Year % 400 == 0)) ? ((DateTime.IsLeapYear(DateTime.Now.Year) && DateTime.Now.DayOfYear <= 366 && DateTime.Now.Month > 0) ? true : false) : ((DateTime.IsLeapYear(DateTime.Now.Year) ? false : DateTime.Now.DayOfYear < 366) ? (DateTime.Now.Month <= 12 && DateTime.Now.Month > 0 ? false : true) : true)) || ((DateTime.Now.DayOfYear > 0 && DateTime.Now.DayOfYear <= 365) ? true : false) && DateTime.Now.Month > 0) && (DateTime.Now.Year % 400 != 200 && DateTime.Now.Year % 100 != 50) ? true : false) && (Enumerable.Range(1, DateTime.IsLeapYear(DateTime.Now.Year) ? 366 : 365).Count(day => true) == 366 ? true : false) ? "Year is a Leap year" : "Year is not a Leap year");` 

## Purpose

The purpose of this code is to demonstrate:

-   Redundant condition checks
-   Unnecessarily complex logic
-   Usage of `DateTime` and `Enumerable.Range` in an inefficient way

This program is not intended to be a practical or efficient solution but rather a fun exercise in writing overly complicated code for a simple task.

## Running the Program

You can run this program in any C# environment such as Visual Studio, Visual Studio Code, or the .NET CLI. The result will be displayed in the console, indicating whether the current year is a leap year or not.

### To run:

1.  Clone the repository.
2.  Build the project.
3.  Run the compiled code. The output will print the leap year status.

## License

This project is open-source and available under the MIT License.
