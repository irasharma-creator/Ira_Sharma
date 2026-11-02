# 🌧️ Monthly Rainfall Tracker

## Project Overview
The Monthly Rainfall Tracker is a C programming mini-project that records and analyses daily rainfall data for a month. It helps users understand rainfall patterns by calculating total rainfall, average rainfall, wettest day, driest day, and the number of days with rainfall above 25 mm.

## Objectives
- To understand and implement arrays in C.
- To store daily rainfall readings.
- To perform calculations using functions.
- To analyse and compare monthly rainfall data.

## Features
1. Enter rainfall data for 1 to 31 days.
2. Store rainfall readings using an array.
3. Display daily rainfall in a formatted table.
4. Calculate total monthly rainfall.
5. Calculate average daily rainfall.
6. Identify the wettest day.
7. Identify the driest day.
8. Count days with rainfall above 25 mm.
9. Enter and compare data for two different months.

## Technologies Used
- Programming Language: C
- Concepts: Arrays, Functions, Loops and Conditional Statements.

## Functions Used

| Function | Description |
|---|---|
| `total_rainfall()` | Calculates total rainfall. |
| `average_rainfall()` | Calculates average rainfall. |
| `wettest_day()` | Finds the day with maximum rainfall. |
| `driest_day()` | Finds the day with minimum rainfall. |
| `count_above_threshold()` | Counts days above 25 mm. |
| `enter_data()` | Accepts rainfall readings. |
| `display_data()` | Displays rainfall readings. |
| `display_summary()` | Displays statistical results. |
| `compare_months()` | Compares two months. |

## How to Run the Program

1. Download or clone this repository.
2. Open the project in a C compiler.
3. Compile the program using:

```bash
gcc main.c -o rainfall
```

4. Run the program:

```bash
./rainfall
```

## Sample Output

```text
======= RAINFALL SUMMARY =======
Total Rainfall  : 57.80 mm
Average Per Day : 19.27 mm
Wettest Day     : Day 3 (45.30 mm)
Driest Day      : Day 2 (0.00 mm)
Days Above 25mm : 1
================================
```

## Conclusion

This project demonstrates how C programming concepts such as arrays, functions, loops and conditional statements can be used to store and analyse rainfall data. It provides a simple way to understand monthly rainfall patterns and compare two months.

---
**Project:** Monthly Rainfall Tracker  
**Language:** C Programming  
**Category:** Mini Project – Arrays
