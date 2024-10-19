# MSSQL with Docker

ms sql with docker

## run and connect to the db

```
docker-compose up -d

```

Connect with SQL Server Management Studio.

You can connect to the SQL Server instance using SQL Server Management Studio (SSMS), Azure Data Studio, or any other SQL client. Use the following connection details:

Server name: localhost,1433
Authentication: SQL Server Authentication
Login: sa
Password: YourStrong!Passw0rd

note: localhost is usually, 127.0.0.1

# Simple Queries

```
-- Step 1: Create a new database
CREATE DATABASE SampleDB;
GO

-- Step 2: Use the new database
USE SampleDB;
GO

-- Step 3: Create the first table (Employees)
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY IDENTITY(1,1),
    FirstName NVARCHAR(50),
    LastName NVARCHAR(50),
    Email NVARCHAR(100),
    HireDate DATE
);
GO

-- Step 4: Create the second table (Departments)
CREATE TABLE Departments (
    DepartmentID INT PRIMARY KEY IDENTITY(1,1),
    DepartmentName NVARCHAR(50)
);
GO

-- Step 5: Insert rows into Employees table
INSERT INTO Employees (FirstName, LastName, Email, HireDate) VALUES
('Amit', 'Sharma', 'amit.sharma@example.com', '2023-01-15'),
('Priya', 'Singh', 'priya.singh@example.com', '2023-02-20'),
('Rahul', 'Verma', 'rahul.verma@example.com', '2023-03-25');
GO

-- Step 6: Insert rows into Departments table
INSERT INTO Departments (DepartmentName) VALUES
('Human Resources'),
('Finance'),
('Engineering');
GO

-- Step 7: Update a row in Employees table
UPDATE Employees
SET Email = 'amit.sharma123@example.com'
WHERE FirstName = 'Amit' AND LastName = 'Sharma';
GO

-- Step 8: Delete a row from Employees table
DELETE FROM Employees
WHERE FirstName = 'Rahul' AND LastName = 'Verma';
GO

-- Step 9: Select all rows from Employees table
SELECT * FROM Employees;
GO

-- Step 10: Select specific columns from Departments table
SELECT DepartmentID, DepartmentName FROM Departments;
GO

-- Step 11: Select rows with a condition
SELECT * FROM Employees WHERE HireDate > '2023-01-01';
GO

-- Step 12: Join Employees and Departments tables (assuming a relationship)
-- Note: This example assumes you have a DepartmentID column in Employees table
-- ALTER TABLE Employees ADD DepartmentID INT;
-- UPDATE Employees SET DepartmentID = 1 WHERE FirstName = 'Amit';
-- UPDATE Employees SET DepartmentID = 2 WHERE FirstName = 'Priya';

-- SELECT with JOIN
-- SELECT e.FirstName, e.LastName, d.DepartmentName
-- FROM Employees e
-- JOIN Departments d ON e.DepartmentID = d.DepartmentID;

```

# book a session with me

1. [calendly](https://calendly.com/jaycodingtutor/30min)

# hire and get to know me

find ways to hire me, follow me and stay in touch with me.

1. [github](https://github.com/Jay-study-nildana)
1. [personal site](https://thechalakas.com)
1. [upwork](https://www.upwork.com/fl/vijayasimhabr)
1. [fiverr](https://www.fiverr.com/jay_codeguy)
1. [codementor](https://www.codementor.io/@vijayasimhabr)
1. [stackoverflow](https://stackoverflow.com/users/5338888/jay)
1. [Jay's Coding Channel on YouTube](https://www.youtube.com/channel/UCJJVulg4J7POMdX0veuacXw/)
1. [medium blog](https://medium.com/@vijayasimhabr)