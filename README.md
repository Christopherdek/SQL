-- 1. Creating a Database
CREATE DATABASE MyDatabase;
-- This command creates a new database named MyDatabase. 
-- A database is a container that holds tables and other database objects.

-- 2. Using a Database
USE MyDatabase;
-- This command selects the database MyDatabase for further operations. 
-- All subsequent SQL commands will be applied to this database.

-- 3. Creating a Table
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Age INT,
    Department VARCHAR(50)
);
-- This command creates a table named Employees with columns for 
-- EmployeeID, FirstName, LastName, Age, and Department. 
-- The PRIMARY KEY constraint on EmployeeID indicates that this column 
-- uniquely identifies each record in the table.

-- 4. Inserting Data
INSERT INTO Employees (EmployeeID, FirstName, LastName, Age, Department)
VALUES (1, 'John', 'Doe', 30, 'IT'),
       (2, 'Jane', 'Smith', 25, 'HR'),
       (3, 'Bob', 'Johnson', 35, 'Finance');
-- This command inserts three records into the Employees table.

-- 5. Retrieving Data
SELECT * FROM Employees;
-- This command retrieves all records (* means all columns) from the Employees table.

-- 6. Updating Data
UPDATE Employees
SET Age = 31
WHERE EmployeeID = 1;
-- This command updates the Age column for the employee with EmployeeID 1.

-- 7. Deleting Data
DELETE FROM Employees
WHERE EmployeeID = 2;
-- This command deletes the record for the employee with EmployeeID 2.

-- 8. Filtering Data
SELECT * FROM Employees
WHERE Department = 'IT';
-- This command retrieves records from the Employees table where the Department is 'IT'.

-- 9. Sorting Data
SELECT * FROM Employees
ORDER BY Age DESC;
-- This command retrieves all records from the Employees table and 
-- sorts them in descending order based on the Age column.

-- 10. Aggregating Data
SELECT Department, AVG(Age) AS AverageAge
FROM Employees
GROUP BY Department;
-- This command calculates the average age (AVG(Age)) for each Department 
-- by grouping the records based on the Department column.

-- 11. Joining Tables
CREATE TABLE Departments (
    DepartmentID INT PRIMARY KEY,
    DepartmentName VARCHAR(50)
);

INSERT INTO Departments (DepartmentID, DepartmentName)
VALUES (1, 'IT'),
       (2, 'HR'),
       (3, 'Finance');
-- This set of commands creates a new table Departments, inserts records, 
-- and then performs a JOIN operation to retrieve information from both 
-- the Employees and Departments tables.

SELECT Employees.FirstName, Employees.LastName, Departments.DepartmentName
FROM Employees
JOIN Departments ON Employees.Department = Departments.DepartmentName;
-- This query joins the Employees and Departments tables to retrieve 
-- information about employees and their respective departments.

