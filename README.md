# Employee Payroll System

## Introduction

The Employee Payroll System is a Python-based application designed to manage employee records, track attendance, and calculate payroll based on hours worked. The project uses a MySQL database to store and retrieve employee, attendance, and payroll information.

## Features

- **Add Employee:** Register new employees into the system, including their name, position, and hourly rate.
- **Record Attendance:** Log attendance for employees, recording the number of hours worked each day.
- **View Attendance:** Display attendance records for individual employees.
- **Calculate Payroll:** Calculate and display the payroll for each employee based on their recorded attendance.

## Installation and Setup

### Step 1: Download the Project Files

1. Download the zip file containing the project files from the repository.
2. Extract the contents of the zip file to a directory of your choice.

### Step 2: Set Up the MySQL Database

1. Open MySQL Workbench and connect to your MySQL server.
2. Create the necessary database and tables by running the following SQL commands:

    ```sql
    CREATE DATABASE EmployeeDB;

    USE EmployeeDB;

    CREATE TABLE Employee (
        id INT AUTO_INCREMENT PRIMARY KEY,
        name VARCHAR(100) NOT NULL,
        position VARCHAR(100),
        hourly_rate DECIMAL(10, 2) NOT NULL
    );

    CREATE TABLE Attendance (
        id INT AUTO_INCREMENT PRIMARY KEY,
        employee_id INT,
        date DATE,
        hours_worked DECIMAL(5, 2),
        FOREIGN KEY (employee_id) REFERENCES Employee(id)
    );

    CREATE TABLE Payroll (
        id INT AUTO_INCREMENT PRIMARY KEY,
        employee_id INT,
        pay_date DATE,
        total_hours DECIMAL(5, 2),
        gross_pay DECIMAL(10, 2),
        FOREIGN KEY (employee_id) REFERENCES Employee(id)
    );
    ```

### Step 3: Install Required Python Libraries

1. Install the MySQL Connector: Ensure you have the required Python packages installed. You can install the MySQL connector using pip.
2. (Optional) Verify Installation: You can use the following command to confirm that the installation was successful.
3. Run the Python Script: Finally, execute the Python script to start the application.

```bash
pip install mysql-connector-python
pip show mysql-connector-python
python main.py
```
## License

This project is open-source and available under the [MIT License](LICENSE).
