# XAMPP MySQL Database Guide
![XAMPP Logo](https://www.apachefriends.org/images/xampp-logo-ac950edf.svg)

## Table of Contents
1. [Installation](#installation)
2. [Database Operations](#database-operations)
3. [SQL Command Examples](#sql-command-examples)
4. [Query Results](#query-results)

## Installation

```bash
# Download and install XAMPP from:
https://www.apachefriends.org/download.html

# Basic components to install:
- Apache
- MySQL
- PHP
- phpMyAdmin
```

## Database Operations

### Create Database

```sql
CREATE DATABASE hamplus_database;
USE hamplus_database;
```

### Create Table

```sql
CREATE TABLE employees (
    emp_id VARCHAR(10) PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    department VARCHAR(50) NOT NULL,
    salary DECIMAL(10,2) NOT NULL,
    hire_date DATE NOT NULL
);
```

### Insert Data

```sql
INSERT INTO employees VALUES
('HP001', 'Omologe', 'Evans', 'oevans@hamplus.com', 'IT', 75000.00, '2020-05-15'),
('HP002', 'Ikwekwa', 'Daniel', 'idaniel@hamplus.com', 'Development', 80000.00, '2019-03-10');
```

## SQL Command Examples

```sql
-- SELECT: Retrieve data
SELECT * FROM employees;

-- INSERT: Add new records
INSERT INTO employees VALUES (...);

-- UPDATE: Modify data
UPDATE employees SET salary = 80000 WHERE emp_id = 'HP001';

-- DELETE: Remove records
DELETE FROM employees WHERE emp_id = 'HP002';

-- CREATE USER: Make new user
CREATE USER 'admin'@'localhost' IDENTIFIED BY 'password';
```

## Query Results

### Employees Table Structure

| Field       | Type         |
|-------------|--------------|
| emp_id      | varchar(10)  |
| first_name  | varchar(50)  |
| last_name   | varchar(50)  |
| email       | varchar(100) |
| department  | varchar(50)  |
| salary      | decimal(10,2)|
| hire_date   | date         |

### Sample Data Results

| emp_id | first_name | last_name | email                | department  | salary   | hire_date  |
|--------|------------|-----------|----------------------|-------------|----------|------------|
| HP001  | Omologe    | Evans     | oevans@hamplus.com   | IT          | 75000.00 | 2020-05-15 |
| HP002  | Ikwekwa    | Daniel    | idaniel@hamplus.com  | Development | 80000.00 | 2019-03-10 |

### User Privileges Example

| Username | Host      | Privileges                  |
|----------|-----------|-----------------------------|
| admin    | localhost | ALL PRIVILEGES              |
| staff    | localhost | SELECT, INSERT, UPDATE      |
| intern   | localhost | SELECT                      |
