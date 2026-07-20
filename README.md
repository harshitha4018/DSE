

--->DAY 1 - Introduction to SQL
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

---> DAY 2 Creating Databases & Tables

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

--->DAY 3 :  Inserting Data into Tables

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

--->DAY 4 : Retrieving Data with SELECT
    
    bjective : Learned how to retrieve data from tables using the `SELECT` statement and apply different clauses to filter and organize results.
  
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
         
         5. LIMIT : Returns only a specified number of
