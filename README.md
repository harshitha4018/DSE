

---> Introduction to SQL
   What I Learned
      - SQL stands for Structured Query Language.
      - SQL is used to communicate with relational databases.
      - SQL helps to Create, Read, Update, and Delete (CRUD) data.
      - SQL is case-insensitive.
       - Every SQL statement ends with a semicolon (;).

    Common SQL Commands
      - CREATE
      - INSERT
      - SELECT
      - UPDATE
      - DELETE
      - DROP
      - ALTER
      - TRUNCATE
  
    Key Points
   - Databases store data in tables.
   - Rows represent records.
   - Columns represent attributes.
   - SQL is supported by MySQL, Oracle, SQL Server, PostgreSQL, etc.

---> Creating Databases & Tables

    Objective
        Learned how to create databases, create tables, use SQL data types, and apply constraints to maintain data integrity.

     Topics Covered

     1. CREATE DATABASE:Creates a new database.
         sql: CREATE DATABASE StudentDB;
      
     2. USE DATABASE: Selects the database to work on.
          sql: USE StudentDB;
      
      3. CREATE TABLE: Creates a table with columns and their data types.
           sql: CREATE TABLE Students (
                                        StudentID INT PRIMARY KEY,
                                         Name VARCHAR(50) NOT NULL,
                                          Age INT,
                                          Department VARCHAR(30),
                                          City VARCHAR(30) DEFAULT 'Guntur'
                                         );
     
 ->Common SQL Data Types
   
       INT : Stores whole numbers 
       VARCHAR(n) : Stores variable-length text 
       CHAR(n)` : Stores fixed-length text 
       FLOAT` : Stores decimal values 
       DATE` : Stores dates (YYYY-MM-DD) 
       BOOLEAN` : Stores TRUE or FALSE values 

 -> SQL Constraints

         PRIMARY KEY: Uniquely identifies each record.
                      Cannot contain duplicate or NULL values.
         NOT NULL: Prevents NULL (empty) values.

         UNIQUE: Ensures all values in a column are different.
         
         DEFAULT: Assigns a default value if no value is provided.

 -> Example

              CREATE DATABASE StudentDB;
              USE StudentDB;
               CREATE TABLE Students (
                                          StudentID INT PRIMARY KEY,
                                           Name VARCHAR(50) NOT NULL,
                                            Age INT,
                                             Department VARCHAR(30),
                                             City VARCHAR(30) DEFAULT 'Guntur'
                                          );

--->  Inserting Data into Tables

        Objective : Learned how to insert records into SQL tables using the `INSERT INTO` statement.

        Topics Covered

             1. INSERT INTO : Used to add new records to a table.
             
             sql: INSERT INTO table_name (column1, column2, column3)
                                   VALUES (value1, value2, value3);
             2. Insert a Single Record
             
             sql: INSERT INTO Students (StudentID, Name, Age, Department, City)
                                   VALUES (101, 'Harshitha', 20, 'CSE', 'Guntur');
             3. Insert Multiple Records 
             
             sql : INSERT INTO Students (StudentID, Name, Age, Department, City)
                             VALUES(102, 'Rahul', 21, 'ECE', 'Vijayawada'),
                                   (103, 'Anjali', 20, 'CSE', 'Guntur'),
                                    (104, 'Ravi', 22, 'EEE', 'Nellore');
             4. NULL Values : If a column allows `NULL`, you can insert it like this:

             sql : INSERT INTO Students (StudentID, Name, Age, Department, City)

---> Retrieving Data with SELECT
    
    objective : Learned how to retrieve data from tables using the `SELECT` statement and apply different clauses to filter and organize results.
  
   Topics Covered:
           1. SELECT Statement : Used to retrieve data from one or more columns in a table
               sql : SELECT * FROM Students;
           
           Retrieve specific columns:
              sql: SELECT Name, Department FROM Students;
          
          2. WHERE Clause : Filters records based on a given condition.
              sql:SELECT * FROM Students WHERE Department = 'CSE';
           
          3. DISTINCT : Returns only unique values.
              sql:SELECT DISTINCT Department FROM Students;
         
          4. ORDER BY : Sorts the result in ascending or descending order.
              Ascending (Default):
                 sql : SELECT * FROM Students ORDER BY Name ASC;
              Descending:
                  sql : SELECT * FROM Students ORDER BY Age DESC;
          5. LIMIT 

#**JOINS**:
       A Join is an SQL operation used to retrieve data from two or more tables based on a related column between them. Joins help combine information stored in separate tables without duplicating data.

For example:

EMP table stores employee details.
DEPT table stores department details.
Both tables are related by the DEPTNO column.
Using a join, you can display an employee's name along with their department name.
Types of Joins
1. Inner Join

An Inner Join returns only the rows that have matching values in both tables. If there is no matching record, that row is excluded from the result.

Use when: You only need records that exist in both tables.

2. Left Outer Join

A Left Join returns all rows from the left table and the matching rows from the right table. If there is no match in the right table, Oracle returns NULL for the right table's columns.

Use when: You want all records from the first table regardless of whether a match exists.

3. Right Outer Join

A Right Join returns all rows from the right table and matching rows from the left table. If no match exists in the left table, NULL values are returned.

Use when: You want all records from the second table.

4. Full Outer Join

A Full Outer Join returns all rows from both tables. Matching rows are combined, and non-matching rows contain NULL values for the missing side.

Use when: You need every record from both tables.

5. Cross Join

A Cross Join returns the Cartesian product of two tables. Every row of the first table is combined with every row of the second table.

If Table A has 5 rows and Table B has 4 rows:

Result = 5 × 4 = 20 rows

Use when: Every combination of rows is required.

6. Self Join

A Self Join joins a table with itself. It is useful when rows in the same table have a relationship.

Example:

Employee table contains both employee IDs and manager IDs.
A self join can display each employee along with their manager's name.

#**SUB QUERIES**:
       A Subquery is a query written inside another SQL query. The inner query executes first, and its result is used by the outer query.

Subqueries make SQL statements simpler and help solve complex problems.

Example:

Find employees who earn more than SMITH.
First find SMITH's salary.
Then compare every employee's salary with that value.
Types of Subqueries
1. Single-Row Subquery

A single-row subquery returns only one row.

It is used with operators such as:

=
<

=

<=

Example:
Find employees earning more than SCOTT.

2. Multiple-Row Subquery

A multiple-row subquery returns more than one row.

It is used with:

IN
ANY
ALL

Example:
Find employees working in departments located in NEW YORK or DALLAS.

3. Correlated Subquery

A correlated subquery depends on the outer query for its values.

The inner query executes once for every row processed by the outer query.

Example:
Find employees whose salary is greater than the average salary of their own department.

4. EXISTS

The EXISTS operator checks whether the subquery returns at least one row.

If rows exist → TRUE
If no rows exist → FALSE

It is commonly used to check whether related data exists.

5. NOT EXISTS

NOT EXISTS returns TRUE only if the subquery returns no rows.

It is useful for finding records that have no matching records in another table.

Example:
Departments with no employees.

#**FUNCTIONS**:
      A Function is a built-in Oracle program that accepts input, processes it, and returns a result.

Functions help perform calculations, manipulate text, format dates, and handle NULL values without writing complex logic.

Types of SQL Functions
A. Single-Row Functions

Single-row functions process one row at a time and return one result for each row.

They are classified into:

Character Functions

These functions manipulate text values.

Examples:

Convert to uppercase
Convert to lowercase
Find string length
Extract part of a string
Replace characters
Remove spaces
Number Functions

These functions perform mathematical operations.

Examples:

Round numbers
Truncate decimal values
Find remainder
Ceiling value
Floor value
Date Functions

These functions manipulate date values.

Examples:

Current system date
Add months
Find months between dates
Find last day of a month
Find next specified weekday
Conversion Functions

These functions convert one data type into another.

Examples:

Number → Character
Character → Date
Character → Number

These are useful when data types do not match.

NULL Functions

NULL functions replace or handle NULL values.

Examples:

Replace NULL with a default value.
Return different values depending on whether NULL exists.
Return the first non-NULL value.
B. Group (Aggregate) Functions

Group functions operate on a collection of rows and return a single result.

Examples include:

Count total rows
Calculate total salary
Find average salary
Find highest salary
Find lowest salary

These functions are often used with GROUP BY.
