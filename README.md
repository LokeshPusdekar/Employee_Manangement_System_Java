Employee Management System

A console-based Employee Management System developed using Core Java following the MVC (Model-View-Controller) architecture.

The project is designed to demonstrate core Object-Oriented Programming concepts, layered architecture, CRUD operations, exception handling, runtime polymorphism, and data management using arrays.

📌 Project Overview

The Employee Management System is designed for managing different types of employees in an organization.

The system supports three types of employees:

Admin

HR

Sales Manager

All employee types inherit from a common Employee base class.

The application provides a menu-driven console interface through which users can:

Add employees

Update employee details

Delete employees

Search employees by ID

Display all employees

Sort employees

Calculate salaries based on employee type

🏗️ Architecture

This project strictly follows the MVC architecture.

                ┌─────────────────────┐
                │       MainApp       │
                │        (View)       │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │ EmployeeController  │
                │    (Controller)     │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │  EmployeeDAOArray   │
                │       (DAO)         │
                └──────────┬──────────┘
                           │
                           ▼
                    ┌─────────────┐
                    │ Employee[]  │
                    │   Storage   │
                    └─────────────┘

View Layer

The MainApp class is responsible for:

Displaying the menu

Taking user input using Scanner

Creating employee objects

Calling Controller methods

Displaying results

Handling exceptions using try-catch

Controller Layer

The EmployeeController class acts as a bridge between the View and DAO.

It is responsible for:

Receiving requests from the View

Calling appropriate DAO methods

Returning results to the View

Model Layer

The Model layer contains:

Employee entity classes

DAO class

The EmployeeDAOArray class is responsible for:

Storing employee data

Adding employees

Updating employees

Deleting employees

Searching employees

Retrieving employees

Sorting employees

📂 Project Structure
EmployeeManagementSystem/
│
├── src/
│   │
│   ├── MainApp/
│   │   └── MainApp.java
│   │
│   ├── Controller/
│   │   └── EmployeeController.java
│   │
│   └── Model/
│       ├── Employee.java
│       ├── Admin.java
│       ├── HR.java
│       ├── Salesmanager.java
│       └── EmployeeDAOArray.java
│
└── README.md

👨‍💼 Employee Types
Employee

Employee is the base class containing common employee information such as:

Employee ID

Employee Name

Salary

Post

It also defines the calSal() method for salary calculation.

Admin

Admin extends Employee and contains an additional:

Allowance

HR

HR extends Employee and contains an additional:

Commission

Sales Manager

Salesmanager extends Employee and contains:

Incentive

Target

🔄 CRUD Operations

The system provides the following CRUD operations:

1. Add Employee

Users can add an employee by providing:

ID

Name

Salary

Employee type

Type-specific information

The employee is then passed through the Controller to the DAO for storage.

2. Update Employee

An employee can be searched using their ID and their details can be modified.

3. Delete Employee

An employee can be deleted using their employee ID.

4. Search Employee

Employees can be searched using their ID.

5. Display All Employees

Displays all employees currently stored in the system along with their calculated salary.

🔢 Sorting

The system also supports sorting employees by:

Employee ID

Salary

Name

Post

Sorting is performed on the employee array in the DAO layer.

💰 Salary Calculation

Salary calculation is implemented using runtime polymorphism.

The application stores different employee types using an Employee reference:

Employee employee;


When calSal() is called:

employee.calSal();


Java executes the appropriate overridden method based on the actual employee object.

For example:

Employee
   │
   ├── Admin
   │     └── calSal()
   │
   ├── HR
   │     └── calSal()
   │
   └── Salesmanager
         └── calSal()


This demonstrates inheritance and runtime polymorphism.

🗄️ Data Storage

This version of the project uses a fixed-size array for data storage.

Employee[] employees = new Employee[100];


A separate count variable keeps track of the number of employees currently stored.

This implementation represents Version 1 – Array-Based Storage of the Employee Management System.

⚠️ Exception Handling

Exception handling is implemented using try-catch.

The View layer handles user input errors such as:

Invalid menu choices

Invalid employee IDs

Invalid numeric input

Runtime input errors

Example:

try {
    int choice = scan.nextInt();
}
catch (Exception e) {
    System.out.println("Invalid input!");
}

🔀 Application Flow

The general flow of the application is:

Start
  │
  ▼
Display Menu
  │
  ▼
Take User Choice
  │
  ├── Add ────────► Controller ──► DAO
  │
  ├── Update ─────► Controller ──► DAO
  │
  ├── Delete ─────► Controller ──► DAO
  │
  ├── Search ─────► Controller ──► DAO
  │
  ├── Display ────► Controller ──► DAO
  │
  ├── Sort ───────► Controller ──► DAO
  │
  └── Exit

🧠 Concepts Demonstrated

This project demonstrates the following Core Java concepts:

Object-Oriented Programming

Classes and Objects

Encapsulation

Inheritance

Method Overriding

Runtime Polymorphism

Abstract/Base Class concepts

Getters and Setters

Arrays

CRUD Operations

Exception Handling

Packages

MVC Architecture

DAO Pattern

Sorting

Console-based User Interaction

▶️ How to Run
Prerequisites

Make sure you have:

Java JDK installed

Java IDE such as Eclipse, IntelliJ IDEA, or VS Code

Steps

Clone the repository:

git clone <your-repository-url>


Open the project in your preferred Java IDE.

Make sure the package structure is maintained:

MainApp
Controller
Model


Run:

MainApp.java


Use the menu displayed in the console.

🖥️ Sample Menu
======================================
     EMPLOYEE MANAGEMENT SYSTEM
======================================
1. Add Employee
2. Update Employee
3. Delete Employee
4. Search Employee
5. Display All Employees
6. Sort All Employees
7. Exit
======================================
Enter your choice:

🎯 Project Objective

The main objective of this project is to understand how a real-world Java application can be divided into separate layers using the MVC architecture.

The project separates:

User Interaction
      ↓
    View
      ↓
 Controller
      ↓
     DAO
      ↓
   Storage


This separation makes the application more organized, maintainable, and easier to extend.

🚀 Future Enhancements

Possible future versions of this project can replace the array-based storage mechanism with:

LinkedList

ArrayList

File-based storage

Database storage using JDBC

MySQL database

The MVC structure can remain the same while changing only the data storage mechanism.

👨‍💻 Author

Your Name

GitHub: https://github.com/LokeshPusdekar

⭐ If you find this project useful, feel free to give it a star!