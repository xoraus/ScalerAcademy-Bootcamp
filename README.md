<!-- TOC start (generated with https://github.com/derlin/bitdowntoc) -->

# DBMS-SQL : Learning Just Enough DBMS & SQL for Tech Interviews

- [DBMS-Fundamentals](#dbms-fundamentals)
   * [SQL 1: Intro to DBMS ](#sql-1-intro-to-dbms)
   * [SQL 2: Keys](#sql-2-keys)
      + [Class Notes](#class-notes)
      + [SQL Lab](#sql-lab)
      + [Extra Notes](#extra-notes)
      + [Resources](#resources)
   * [SQL 3: CRUD - I](#sql-3-crud-i)
      + [Class Notes](#class-notes-1)
      + [Problem Set](#problem-set)
   * [SQL 4: CRUD - II](#sql-4-crud-ii)
      + [Class Notes](#class-notes-2)
      + [SQL Lab](#sql-lab-1)
   * [SOL 5: Joins - I](#sol-5-joins-i)
      + [Class Notes](#class-notes-3)
   * [SQL 6: Joins - II](#sql-6-joins-ii)
      + [Class Notes](#class-notes-4)
      + [Problem Set](#problem-set-1)
   * [SQL 7: Aggregate Queries](#sql-7-aggregate-queries)
      + [Class Notes](#class-notes-5)
      + [Problem Set](#problem-set-2)
      + [References](#references)
   * [SQL 9: Indexing](#sql-9-indexing)
      + [Class Notes](#class-notes-6)
      + [Problem Set](#problem-set-3)
      + [References](#references-1)
   * [SQL 10: Transactions - I](#sql-10-transactions-i)
   * [SQL 10: Transactions - II](#sql-10-transactions-ii)
   * [SQL 11: Schema Design - I 🚧 (This will be updated soon)](#sql-11-schema-design-i-this-will-be-updated-soon)
   * [SQL 12: Schema Design  - I 🚧 (This will be updated soon)](#sql-12-schema-design-i-this-will-be-updated-soon)

<!-- TOC end -->

## SQL 1: Intro to DBMS 
  - What is a database? 
      - A database is a structured collection of data that is organized and stored for efficient retrieval, management, and manipulation.
      - Example: An online retail store's database that stores information about products, customers, and orders.
  - Why do we use DBMS? 
      - A Database Management System (DBMS) is used to efficiently manage and interact with databases, providing features like data retrieval, insertion, modification, and security.
      - Example: Using a DBMS like MySQL to manage a database of employee records in a company.
  - What are the different types of databases? 
      - Databases can be categorized into different types, such as relational and non-relational (NoSQL), based on their data structure and storage mechanism.
      - Example: Relational databases like PostgreSQL and non-relational databases like MongoDB.
  - Database and the relational model 
      - The relational model organizes data into tables with rows and columns, fostering relationships between data entities.
      - Example: A relational database for a library system with tables for books, authors, and borrowers.
  - Key terms 
      - Data: Raw facts and figures.
      - Database: Organized collection of related data.
      - DBMS: Software for managing databases.
      - Relational Database: Database using tables to store data.
      - Non-relational Database: Database not using tables.
  - Brute Force way of storage - Files 
      - Issues with file-based storage
          - Storing data in flat files can lead to inefficiencies, lack of data integrity, and limited querying capabilities.
          - Example: Using text files to store customer information without indexing.
      - Limitations of using files for real applications
          - Files are inadequate for real-world applications due to difficulties in managing and querying data.
          - Example: Attempting to build a complex e-commerce platform using text files to store product information.
  - Types of DBMS 
      - Relational DBMS
          - Relational DBMS uses tables to store data and enforces data integrity using relationships.
          - Example: MySQL used to manage customer data for an online forum.
      - Non-Relational (NoSQL) DBMS
          - NoSQL databases store data in various ways, such as documents, key-value pairs, or graphs, and are often used for flexible data structures.
          - Example: MongoDB for storing unstructured user-generated content like social media posts.
  - Relational DBMS 
      - Advantages and use cases
          - Relational DBMS excels in maintaining data integrity, supporting complex queries, and ensuring data consistency.
          - Example: Using PostgreSQL to manage financial data in a banking system.
      - Examples of popular relational DBMS
          - Mention some widely used relational DBMS systems.
          - Example: PostgreSQL, Oracle, Microsoft SQL Server.
  - Relational Model 
      - Tables (Relations)
          - Tables are the fundamental structure of the relational model, representing entities and attributes.
          - Example: A "Students" table with columns for "StudentID," "Name," and "GPA."
      - Rows (Tuples) and Columns (Attributes)
          - Rows contain individual data records, while columns represent specific data attributes.
          - Example: In a "Customers" table, a row represents a single customer, and columns may include "CustomerID" and "Address."
      - Primary Keys and Foreign Keys
          - Primary keys uniquely identify rows, while foreign keys establish relationships between tables.
          - Example: In an "Orders" table, "OrderID" can be a primary key, and "CustomerID" can be a foreign key connecting to the "Customers" table.
  - Properties of the Relational Model 
      - Data Integrity
          - Ensuring data accuracy and consistency through constraints like unique values and data types.
          - Example: Enforcing that all email addresses in a database are unique.
      - Data Consistency
          - Maintaining data consistency across tables and relationships.
          - Example: Ensuring that if a product is deleted, related order records are updated or deleted.
      - Data Security
          - Protecting data from unauthorized access and ensuring only authorized users can modify it.
          - Example: Implementing role-based access control to restrict access to sensitive financial data.
      - ACID Properties (Atomicity, Consistency, Isolation, Durability)
          - ACID properties guarantee the reliability and robustness of database transactions.
          - Example: In a banking system, ensuring that a transfer of funds from one account to another is both atomic and consistent, even in the event of a system crash.
  - SQL as the query language for relational databases 
      - SQL (Structured Query Language) is the standard language for interacting with relational databases, allowing users to perform operations like SELECT, INSERT, UPDATE, and DELETE.
      - Example: Writing SQL queries to retrieve customer information from a database or update inventory levels in an e-commerce system.

<!-- TOC --><a name="sql-2-keys"></a>
## SQL 2: Keys
   
<!-- TOC --><a name="class-notes"></a>
### Class Notes
  - Keys: Keys are essential in database management and play crucial roles in organizing and linking data. Let's explore various types of keys and their significance:
  - Uniquely Identifying Tuples: Keys are used to uniquely identify a tuple in a relation (table) or to describe relationships between relations (tables).
      - Example - Identifying a Student: 
          - Consider the "Student" relation with attributes (name, age, address, phone, email).
          - To uniquely identify a student:
              - Name alone might not be unique.
              - Either phone or email would be sufficient, as each student has a unique phone or email address.
  - Super Keys: Super keys are sets of attributes that uniquely identify a tuple in a relation.
      - Super Keys for "Student" Relation: 
          - For the "Student" relation, some super keys include:
              - {id, name}
              - {id, name, phone}
              - {id, name, email}
              - {id, name, email, phone}
              - {id, name, email, phone, age, address}
              - {id}
  - Candidate Keys: Candidate keys are minimal sets of attributes that uniquely identify a tuple in a relation.
      - Removing any attribute from a candidate key would no longer ensure unique identification.
      - Candidate Keys for "Student" Relation: 
          - A set of candidate keys for the "Student" relation:
              - id
              - phone
              - email
  - Primary Keys: A primary key is a specific choice of a minimal set of attributes that uniquely specify a tuple in a relation.
      - Each relation can have only one primary key.
      - Primary keys are selected from the set of candidate keys, and any other candidate key is considered an alternate key.
  - Composite Keys: Composite keys use multiple attributes to uniquely identify a tuple.
      - Useful when a single attribute is insufficient.
      - Commonly used in mapping tables to establish relationships between tables.
  - Foreign Keys: A foreign key is a set of attributes in a table that refers to the primary key of another table.
      - Used to link two tables together based on common attributes.
      - Helps maintain data integrity and relationships between related data.
      - Example - Using Foreign Keys: 
          - To add a batch to a student, instead of duplicating all batch-related columns in the student relation, we can use a foreign key.
          - For example, "Batch Id" in the "Student" relation can reference the primary key of the "Batch" table.      

<!-- TOC --><a name="sql-lab"></a>
### SQL Lab

- Database Creation and Show Databases:
```sql
    - -- Creating a new database named 'aug22beg'.
CREATE DATABASE aug22beg;

-- Displaying the list of databases.
SHOW DATABASES;  
    - Explanation: This section creates a new database named 'aug22beg' and lists all the available databases using the SHOW DATABASES command.

- Table Creation and Foreign Key Constraint:
```

```sql
    - -- Creating a 'batches' table with 'id' as the primary key.
CREATE TABLE aug22beg.batches (
    id INT PRIMARY KEY NOT NULL,
    name VARCHAR(50)
);

-- Inserting data into the 'batches' table.
INSERT INTO aug22beg.batches (id, name) VALUES (1, 'Aug22 Beg');
INSERT INTO aug22beg.batches (id, name) VALUES (2, 'Aug23 Beg');


-- Creating a 'students' table with 'id' as the primary key and 'batch_id' as a foreign key.
CREATE TABLE aug22beg.students (
    id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(45) NULL,
    batch_id INT,
    PRIMARY KEY (id),
    FOREIGN KEY (batch_id) REFERENCES aug22beg.batches(id)
);

-- Inserting data into the 'students' table with foreign key constraints.
-- Note: The third INSERT statement will produce an error due to a foreign key constraint.
INSERT INTO aug22beg.students (id, name, batch_id) VALUES (1, 'Rahul', 1);
-- The next line will produce an error because 'batch_id' 3 does not exist in the 'batches' table.
-- INSERT INTO aug22beg.students (id, name, batch_id) VALUES (2, 'Sujay', 3);
-- Error: Cannot add or update a child row: a foreign key constraint fails.

-- Inserting data into the 'students' table without specifying 'batch_id'.
-- Make sure to specify a valid 'batch_id' to avoid foreign key constraint errors.
INSERT INTO aug22beg.students (id, name, batch_id) VALUES (4, 'Naman', 1);
INSERT INTO aug22beg.students (id, name, batch_id) VALUES (3, 'Vishal', 2); 
    - Explanation: This section creates two tables, 'batches' and 'students', with proper primary key and foreign key constraints. It also demonstrates inserting data into these tables with and without specifying the 'batch_id' column, resulting in a foreign key constraint error for the third INSERT statement.
```

- Selecting Data from 'students' Table:
```sql
    - -- Selecting all records from the 'students' table in the 'aug22beg' database.
SELECT * FROM aug22beg.students;  
    - Explanation: This query retrieves all records from the 'students' table in the 'aug22beg' database.
```
**Complete Code Snippet**

```sql
- -- RDBMS 
-- MySql -> RDBMS
-- Workbench -> IDE helps us interact with MySql Server

CREATE DATABASE aug22beg;

show databases;

-- Not case sensitive

-- Execute the command Cmd+Enter

-- Backticks are used to separate out db names, table names
-- from the SQL reserved keywords
-- CREATE DATABASE `database` -> Would work.

-- Deleting a database. 
-- DROP DATABASE aug22Beg;


-- INSERT INTO `aug22beg`.`students` (`id`, `name`) VALUES (2, 'Sandipan');
-- Error Code: 1062. Duplicate entry '2' for key 'students.PRIMARY'

CREATE TABLE `aug22beg`.`batches`(
	`id` INT PRIMARY KEY NOT NULL,
    `name` varchar(50)
);

INSERT INTO `aug22beg`.`batches` (`id`, `name`) VALUES (1, 'Aug22 Beg');
INSERT INTO `aug22beg`.`batches` (`id`, `name`) VALUES (2, 'Aug23 Beg');


CREATE TABLE `aug22beg`.`students` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `name` VARCHAR(45) NULL,
  `batch_id` INT,
  PRIMARY KEY (`id`),
  FOREIGN KEY (`batch_id`) REFERENCES `aug22beg`.`batches`(`id`)
  );
-- DROP TABLE aug22beg.students;


-- Inserting values into the table
INSERT INTO `aug22beg`.`students` (`id`, `name`, `batch_id`) VALUES (1, 'Rahul', 1);
INSERT INTO `aug22beg`.`students` (`id`, `name`, `batch_id`) VALUES (2, 'Sujay', 3);
-- Error Code: 1452. Cannot add or update a child row: 
-- a foreign key constraint fails (`aug22beg`.`students`, 
-- CONSTRAINT `students_ibfk_1` FOREIGN KEY (`batch_id`)
--  REFERENCES `batches` (`id`))

INSERT INTO `aug22beg`.`students` (`id`, `name`) VALUES (4, 'Naman');
INSERT INTO `aug22beg`.`students` (`id`, `name`) VALUES (3, 'Vishal');


SELECT * FROM aug22beg.students;
```

<!-- TOC --><a name="extra-notes"></a>
### Extra Notes

- Data Types 
  - In SQL, data types define the kind of data that can be stored in a database table's columns. Each database management system (DBMS) may have its own set of data types, but there are some common data types that are widely used across different SQL database systems. 
- Here are some common SQL data types:

- 1. INTEGER (INT):
    - The INTEGER data type is used for whole numbers. It typically occupies 4 bytes and can store values ranging from -2,147,483,648 to 2,147,483,647 (signed) or 0 to 4,294,967,295 (unsigned).
    - Used to store whole numbers (positive and negative).
    - Example:
```sql
CREATE TABLE employees (
employee_id INT,
age INT
);
```

- 2. FLOAT:
    - FLOAT data types are used for approximate numeric values with decimal places. They are used when you need to store numbers with fractional parts. FLOATs are approximate because they can't represent all real numbers precisely.
    - Used to store floating-point numbers (real numbers) with a decimal point.
    - Example:

```sql
CREATE TABLE products (
price FLOAT
);
```

- 3. CHARACTER (CHAR):
    - The CHAR data type stores fixed-length character strings. It requires a specified length when defining the column. For example, CHAR(10) will always occupy 10 characters, padding with spaces if the text is shorter.
    - Stores fixed-length character strings.
    - Example:
```sql
CREATE TABLE customers (
first_name CHAR(50),
last_name CHAR(50)
);
```

- 4. VARCHAR (VARCHAR2):
    - VARCHAR (or VARCHAR2 in some databases) is used to store variable-length character strings. It only uses as much storage as needed for the data, making it more space-efficient compared to CHAR.
    - Stores variable-length character strings.
    - Example:
```sql
CREATE TABLE orders (
order_id INT,
description VARCHAR(255)
);
```

- 5. DATE:
    - The DATE data type is used to store date values. It doesn't include time information. Commonly used for representing calendar dates, e.g., birthdates, order dates.
    - Stores date values (YYYY-MM-DD).
    - Example:
```sql
CREATE TABLE events (
event_id INT,
event_date DATE
);
```

- 6. TIME:
    - TIME data type is used to store time values. It doesn't include date information. Useful for representing time of day, e.g., appointment times.
    - Stores time values (HH:MM:SS).
    - Example:
```sql
CREATE TABLE appointments (
appointment_id INT,
appointment_time TIME
);
```

- 7. DATETIME (TIMESTAMP):
    - DATETIME (or TIMESTAMP) data type stores both date and time information. It's used when you need to work with date and time as a single entity, e.g., event timestamps.
    - Stores both date and time values.
    - Example:
```sql
CREATE TABLE messages (
message_id INT,
sent_at DATETIME
);
```

- 8. BOOLEAN (BOOL):
    - The BOOLEAN data type stores binary values, often representing true/false, yes/no, or 1/0. It's useful for logical decisions and conditions.
    - Stores boolean values (TRUE or FALSE).
    - Example:
```sql
CREATE TABLE settings (
setting_name VARCHAR(50),
is_enabled BOOLEAN
);
```

- 9. BLOB (Binary Large Object):
    - BLOB is used to store binary data, such as images, audio, video, or any other large binary object. It's designed for large, unstructured data.
    - Stores binary data such as images, documents, or other large files.
    - Example:
```sql
CREATE TABLE attachments (
attachment_id INT,
file_data BLOB
);
```

- 10. NUMERIC (DECIMAL):
    - NUMERIC (or DECIMAL) data type is used to store fixed-point or floating-point numbers with a specified precision and scale. It's commonly used for financial and monetary values where precision is crucial.
    - Stores fixed-point or floating-point numbers with a specified precision and scale.
    - Example:
```sql
CREATE TABLE transactions (
transaction_id INT,
amount NUMERIC(10, 2)
);
```

<!-- TOC --><a name="resources"></a>
###  Resources
- GitHub Rep: https://github.com/rahulgrover99/Aug22Beg-SQL/blob/main/sql-1.md 
- String Functions: # Refer Correspoding lecture for gdrive link.
- Number Functions: # Refer Correspoding lecture for gdrive link.
- Data Types: # Refer Correspoding lecture for gdrive link.

<!-- TOC --><a name="sql-3-crud-i"></a>
## SQL 3: CRUD - I

<!-- TOC --><a name="class-notes-1"></a>
### Class Notes
  -   **Create (C):**
      -   SQL INSERT statement is commonly used to create (insert) new records in a database table.
      -   Below is an example of inserting a new record into an "Employees" table:
          -   ```sql
              -- Insert a new employee record
              INSERT INTO Employees (EmployeeID, FirstName, LastName, Department)
              VALUES (101, 'John', 'Doe', 'HR');
              ```
              
  -   **Read (R):**
      -   SQL SELECT statement is used to read (retrieve) data from a database table.
      -   Below is an example of retrieving employee information from the "Employees" table:
          -   ```sql
              -- Retrieve employee information
              SELECT EmployeeID, FirstName, LastName, Department
              FROM Employees
              WHERE Department = 'HR';
              ```
              
      -   In the "Create" example, we use the INSERT INTO statement to create a new record in the "Employees" table with specific values for each column. This action creates a new employee entry.
      -   In the "Read" example, we use the SELECT statement to read data from the "Employees" table. We specify the columns we want to retrieve and include a WHERE clause to filter the results, in this case, selecting only employees in the HR department. The result is a set of records matching the specified criteria.
      -   These SQL examples illustrate how to perform the "Create" and "Read" operations in a relational database. Depending on the programming language and database system you're using, the exact syntax may vary, but the fundamental principles remain the same.
  -   **Update (U):**
      -   The "Update" operation is used to modify existing records or data entries in a database table.
      -   It is associated with the SQL UPDATE statement.
      -   Below is an example of updating an employee's department in the "Employees" table:
          -   ```sql
              -- Update an employee's department
              UPDATE Employees
              SET Department = 'Finance'
              WHERE EmployeeID = 101;
              ```
              
              -   We use the UPDATE statement to modify records in the "Employees" table.
              -   The SET clause specifies the column to be updated (Department) and the new value ('Finance').
              -   The WHERE clause is used to specify which records should be updated. In this case, it identifies the employee with EmployeeID equal to 101.
          -   After executing this SQL statement, the employee's department is updated from 'HR' to 'Finance' in the database.
  -   **Delete (D):**
      -   The "Delete" operation is used to remove records or data entries from a database table.
      -   It is associated with the SQL DELETE statement.
      -   Below is an example of deleting an employee record from the "Employees" table:
          -   ```sql
              -- Delete an employee record
              DELETE FROM Employees
              WHERE EmployeeID = 101;
              ```
              
          -   We use the DELETE statement to remove a record from the "Employees" table.
          -   The FROM clause specifies the table from which records should be deleted (Employees).
          -   The WHERE clause is used to specify which records should be deleted. In this case, it identifies the employee with EmployeeID equal to 101.
      -   After executing this SQL statement, the employee with EmployeeID 101 is removed from the database.

<!-- TOC --><a name="problem-set"></a>
### Problem Set

  -   01. Find Customer Referee
      -   Write an SQL query to fetch the **names** of the customer that are **not referred** by txhe customer with **id = 102**_._
          -   ```sql
              SELECT name 
              FROM customer 
              WHERE referee_id != 102
              ```
              
  -   02. Find Customers With Positive Revenue this Year
      -   Write an SQL query to report the **unique** **customers** with **postive revenue** in the **year 2021**.
          -   ```sql
              SELECT DISTINCT customer_id 
              FROM customers 
              WHERE revenue > 0 AND year = 2021;
              ```
              
  -   Q3. New Salary
      -   Write a query to calculate the salary of all employees after an increment of **20%**. Save the newly calculated salary column as '**New_salary**'.
          -   ```sql
              SELECT emp_id, name, salary, 
              ROUND(((salary * 20)/100) + salary) AS New_salary
              FROM employees 
              ORDER BY emp_id;
              ```
              
  -   04. Total Amount
      -   Write a query to calculate the sub_total for each order, return the details of the **orderNumber**, **productCode**, and **sub_total**.
          -   ```sql
              SELECT orderNumber, productCode, 
              ROUND((quantityOrdered * priceEach), 2) AS sub_total
              FROM orderdetails
              ORDER BY orderNumber ASC, sub_total DESC;
              ```
              
  -   Q5. Employee 101
      -   Write a query to get all the details of all the employees from **job_history** except for the employee with id **101** Return all the fields oder by employee_id and job_id in ascending order.
          -   ```sql
              SELECT *
              FROM job_history 
              WHERE employee_id != 101
              ORDER BY employee_id ASC, job_id ASC;
              ```
              
  -   01. Movies released after 2014
      -   Write a query to display the titles of the movies that are released (i.e., release_year) after **2014** and have an average vote rating (i.e.,vote_average) **greater than 7.** Return the column '**original_title**'. Return the result ordered by **original_title** in ascending order.
          -   ```sql
              SELECT original_title
              FROM movies
              WHERE release_year > 2014 AND vote_average > 7
              ORDER BY original_title ASC
              ```
              
  -   02. Horror genre
      -   Display the details of the movies which belong to the '**Horror**' genre. Return the columns '**original_title**', and '**popularity**'. Return the result ordered by the **popularity** in descending order.
          -   ```sql
              SELECT original_title, popularity
              FROM movies 
              WHERE genres = 'Horror'
              ORDER BY popularity DESC
              ```
              
  -   03. Selected Departments
      -   Write a query to find the details of those employees who work in the departments with numbers included in **30**, **40**, or **90**. Return the result ordered by **employee_id** in ascending order.
          -   ```sql
              SELECT employee_id, first_name, job_id, department_id  
              FROM employees
              WHERE department_id IN (30, 40, 90)
              ORDER BY employee_id
              ```
              
  -   04. Office Codes
      -   Write a query to find the employees whose officeCodes are not included in **4,6,7**. Return the result ordered by **firstName** and **lastName** in ascending order.
          -   ```sql
              SELECT firstName, lastName, jobTitle
              FROM employees
              WHERE officeCode NOT IN (4, 6, 7)
              ORDER BY firstName ASC, lastName ASC
              ```
              
### SQL Lab
  -   **Insertion of Data into Database**
      -   ```sql
          -- Inserting a single row into sakila.film with specified values.
          INSERT INTO sakila.film 
          (film_id, title, description, release_year, language_id, rental_duration, rental_rate, length, replacement_cost, rating, special_features, last_update)
          VALUES
          (1001, 'The Dark Knight', 'Batman fights Joker', 2008, 1, 3, 4.99, 152, 19.99, 'PG-13', 'Trailers', SYSDATE());
          
          -- Inserting multiple rows into sakila.film with specified values.
          INSERT INTO sakila.film 
          (title, description, release_year, language_id, rental_duration, rental_rate, length, replacement_cost, rating)
          VALUES
          ('The Dark Knight - 5', 'Batman fights Joker', 2010, 1, 3, 4.99, 152, 19.99, 'PG-13'),
          ('The Dark Knight - 3', 'Batman fights Joker', 2010, 1, 3, 4.99, 152, 19.99, 'PG-13'),
          ('The Dark Knight - 4', 'Batman fights Joker', 2010, 1, 3, 4.99, 152, 19.99, 'PG-13'); 
          ```
          
      -   **Explanation:** The code inserts data into the sakila.film table, both a single row and multiple rows. It specifies the columns and their corresponding values for each insertion.
  -   **Use and Basic Select Query:**
      -   ```sql
          -- Sets the default database in use.
          USE sakila;
          
          -- Basic select query to retrieve all columns from film.
          SELECT * FROM film;
          
          -- Select query to retrieve selected columns with aliases.
          SELECT title AS film_title, description AS film_description, release_year FROM film; 
          ```
          
      -   **Explanation:** This section demonstrates setting the default database and running basic SELECT queries to retrieve all columns and specific columns with aliases.
  -   **Using DISTINCT Keyword:**
      -   ```sql
          -- Select distinct values from the 'rating' column.
          SELECT DISTINCT rating FROM sakila.film;
          
          -- Select distinct values from multiple columns.
          SELECT DISTINCT rating, release_year FROM sakila.film; 
          ```
          
      -   **Explanation:** These queries showcase the usage of the DISTINCT keyword to retrieve **unique values** from columns, both **individually** and in **combination**.
  -   **Applying Functions and Operators:**
      -   ```sql
          -- Applying functions and operators to columns.
          SELECT ROUND(length/60, 2) AS length_in_hrs FROM film;
          SELECT CONCAT(title, ": ", description) FROM film; 
          ```
          
      -   **Explanation:** These queries demonstrate the use of functions (ROUND and CONCAT) and operators to manipulate column values in the SELECT statement.
  -   **Insert Data into Another Table:**
      -   ```sql
          -- Inserting data into the 'film_copy' table from the 'film' table.
          INSERT INTO film_copy
          (title, description, release_year, language_id, rental_duration, rental_rate, length, replacement_cost, rating)
          SELECT title, description, release_year, language_id, rental_duration, rental_rate, length, replacement_cost, rating FROM film; 
          ```
          
      -   **Explanation:** This query inserts data from the film table into the film_copy table by selecting specific columns.
  -   **Filtering Data with WHERE Clause:**
      -   ```sql
          -- Display records of films with rating as 'PG-13'.
          SELECT * FROM film WHERE rating = 'PG-13';
          
          -- Display records of films with rating as 'PG-13' and release year 2008.
          SELECT * FROM film WHERE rating = 'PG-13' AND release_year = 2008;
          
          -- Display records of films where release year is not 2006.
          SELECT * FROM film WHERE NOT release_year = 2006;
          
          -- Display records of films where release year is less than 2006.
          SELECT * FROM film WHERE release_year < 2006;
          
          -- Display records of films where rating is 'PG-13', 'R', or 'G'.
          SELECT * FROM film WHERE rating IN ('PG-13', 'R', 'G'); 
          ```
          
      -   **Explanation:** These queries demonstrate the use of the WHERE clause to filter records based on specified conditions.
  -   ```sql
      INSERT INTO sakila.film VALUES
      (1001, 'The Dark Knight', 'Batman fights joker', 2008, 1, NULL,  3, 4.99, 152, 19.99, 'PG-13', 'Trailers', SYSDATE());
      
      -- note that it is not recommended
      -- avoided setting value for primary key because auto-generated
      -- last updated date is also auto-generated.alter
      -- there might be some columns for which you can avoid setting values
      
      
      INSERT INTO `sakila`.`film` 
      (`title`, `description`, release_year, language_id, rental_duration, rental_rate, `length`, replacement_cost, rating)
      VALUES
      ('The Dark Knight - 5', 'Batman fights joker', 2010, 1, 3, 4.99, 152, 19.99, 'PG-13'),
      ('The Dark Knight - 3', 'Batman fights joker', 2010, 1, 3, 4.99, 152, 19.99, 'PG-13'),
      ('The Dark Knight - 4', 'Batman fights joker', 2010, 1, 3, 4.99, 152, 19.99, 'PG-13');
      
      
      -- In this manner, you will able to:
      -- 1. Specify values for columns you actually need to.
      -- 2. You can specify the values in your own order.
      
      
      -- Sets the default database in use.
      USE sakila;
      
      -- Basic select query
      SELECT * FROM film;
      
      -- Only print out selected columns. 
      SELECT title as film_title, description as film_description, release_year FROM film;
      -- `as` keyword prints out columns with alias names
      --  This keyword is used to rename a column or table with an alias. 
      -- It is temporary and only lasts until the duration of that particular query
      
      -- Distinct keyword helps you out selecting distinct values from a particular column
      SELECT DISTINCT rating FROM sakila.film;
      
      
      -- Note: DISTINCT keyword must be before all the column names, 
      -- as it will find the unique values for the collection of column values. 
      -- For example, if there are 2 column names, then it will find distinct pairs
      -- among the corresponding values from both the columns.
      SELECT DISTINCT rating, release_year FROM sakila.film;
      
      
      
      -- DSA LOGIC
      
      -- answer = []
      -- for each row in table:
      -- 	answer.append(row['col1'], row['col2'])
      
      -- if DISTINCT: 
      -- return set(answer)
      
      
      -- SELECT command without from clause.
      SELECT 'HELLO WORLD';
      SELECT SYSDATE();
      
      -- Applying functions over columns
      SELECT ROUND(length/60, 2) as length_in_hrs FROM film;
      SELECT CONCAT(title, ": ", description) from film;
      
      -- Insert data into table from another table
      
      -- CREATE TABLE film_copy (
      --   film_id SMALLINT UNSIGNED NOT NULL AUTO_INCREMENT,
      --   title VARCHAR(128) NOT NULL,
      --   description TEXT DEFAULT NULL,
      --   release_year YEAR DEFAULT NULL,
      --   language_id TINYINT UNSIGNED NOT NULL,
      --   original_language_id TINYINT UNSIGNED DEFAULT NULL,
      --   rental_duration TINYINT UNSIGNED NOT NULL DEFAULT 3,
      --   rental_rate DECIMAL(4,2) NOT NULL DEFAULT 4.99,
      --   length SMALLINT UNSIGNED DEFAULT NULL,
      --   replacement_cost DECIMAL(5,2) NOT NULL DEFAULT 19.99,
      --   rating ENUM('G','PG','PG-13','R','NC-17') DEFAULT 'G',
      --   special_features SET('Trailers','Commentaries','Deleted Scenes','Behind the Scenes') DEFAULT NULL,
      --   last_update TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
      --   PRIMARY KEY  (film_id)
      -- ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
      
      INSERT INTO film_copy
      (`title`, `description`, release_year, language_id, rental_duration, 
      rental_rate, `length`, replacement_cost, rating)
      SELECT `title`, `description`, release_year, language_id, rental_duration, 
      rental_rate, `length`, replacement_cost, rating FROM film;
      
      
      -- Display records of films with rating as `PG-13`
      SELECT * FROM film WHERE rating = 'PG-13';
      
      
      
      -- DSA LOGIC
      
      -- answer = []
      -- for each row in table:
      -- 	if row matches where clause:
      -- 	  answer.append(row['col1'], row['col2'])
      
      -- if DISTINCT: 
      -- return set(answer)
      
      
      -- Display records of films with rating as `PG-13` and release year 2008
      SELECT * FROM film WHERE rating = 'PG-13' AND release_year = 2008;
      
      -- Films where release year is not 2006
      SELECT * FROM film WHERE NOT release_year = 2006;
      
      -- NOT EQUAL to 
      SELECT * FROM film WHERE release_year <> 2006;
      SELECT * FROM film WHERE release_year != 2006;
      
      SELECT * FROM film WHERE release_year < 2006;
      SELECT * FROM film WHERE release_year <= 2006;
      
      -- Always use parantheses where multiple logical operators used.
      SELECT * FROM film WHERE (rating = 'PG-13' OR release_year = 2006) AND rental_rate = 0.99;
      
      -- list might grow long
      SELECT * FROM film WHERE rating = 'PG-13' OR rating = 'R' or rating = 'G';
      
      
      SELECT * FROM film WHERE rating IN ('PG-13', 'R', 'G');
      
      ```

<!-- TOC --><a name="sql-4-crud-ii"></a>
## SQL 4: CRUD - II

<!-- TOC --><a name="class-notes-2"></a>
###  Class Notes
 -   1. **BETWEEN**:
     -   **SQL Note**: The BETWEEN operator is used to filter data within a specific range of values, inclusive.
     -   **Example**:
         -   ```sql
             SELECT * FROM products
             WHERE price BETWEEN 10 AND 50;
             ```
             
 -   2. **LIKE**:
     -   **SQL Note**: The LIKE operator is used for pattern matching within text fields. You can use % as a wildcard to represent zero or more characters, and _ to represent a single character.
     -   **Example**:
         -   ```sql
             SELECT * FROM customers
             WHERE lastName LIKE 'Smith%';
             ```
             
 -   3. **NULL & IS NULL**:
     -   **SQL Note**: NULL represents missing or unknown data in a column. You can use IS NULL to filter records with NULL values.
     -   **Example**:
         -   ```sql
             SELECT * FROM orders
             WHERE shippedDate IS NULL;
             ```
             
 -   4. **ORDER BY Clause**:
     -   **SQL Note**: The ORDER BY clause is used to sort the result set based on one or more columns, in ascending (default) or descending order.
     -   **Example**:
         -   ```sql
             SELECT * FROM products
             ORDER BY price DESC;
             ```
             
 -   5. **ORDER BY Clause with DISTINCT keyword**:
     -   **SQL Note**: You can combine ORDER BY with DISTINCT to select distinct values and order the results.
     -   **Example**:
         -   ```sql
             SELECT DISTINCT category FROM products
             ORDER BY category;
             ```
             
 -   6. **LIMIT Clause**:
     -   **SQL Note**: The LIMIT clause is used to restrict the number of rows returned in the result set.
     -   **Example**:
         -   ```sql
             SELECT * FROM orders
             LIMIT 10;
             ```
             
 -   7. **Update**:
     -   **SQL Note**: The UPDATE statement is used to modify existing records in a table.
     -   **Example**:
         -   ```sql
             UPDATE employees
             SET salary = salary * 1.1
             WHERE department = 'Sales';
             ```
             
 -   8. **Delete**:
     -   **SQL Note**: The DELETE statement is used to remove one or more rows from a table based on a specified condition.
     -   **Example**:
         -   ```sql
             DELETE FROM customers
             WHERE lastPurchaseDate < '2022-01-01';
             ```
             
 -   9. **Delete vs Truncate vs Drop**:
     -   **SQL Note**:
         -   DELETE removes rows based on a condition and can be rolled back.
         -   TRUNCATE removes all rows from a table, can't be rolled back, and resets identity columns.
         -   DROP is used to delete a table or database completely.
     -   **Examples**:
         -   ```sql
             -- DELETE
             DELETE FROM products WHERE stock < 10;
             
             -- TRUNCATE
             TRUNCATE TABLE employees;
             
             -- DROP
             DROP TABLE customers;
             ```
             
###  Problem Set

 -   Q1. Top 5 popular movies
     -   Find the movie titles, taglines, and directors for the top 5 popular movies. Return the columns '**original_title**', '**tagline**', and '**director**'.
         -   ```sql
             SELECT original_title, tagline, director
             FROM movies
             ORDER BY popularity DESC LIMIT 5;
             ```
             
 -   02. Low Fat & Recyclable Products
     -   Write a query to find the ids of products that are both **low-fat** **and recyclable**. Return the result table ordered by product_id in ascending order.
         -   ```sql
             SELECT product_id
             FROM products
             WHERE (low_fats= 'Y' AND recyclable= 'Y')
             order by product_id;
             ```
             
 -   03. Germany
     -   Write a query to fetch customer details like customerName, phone, addressLine1, city, state, and postalCode who are not from **Germany**. Return the result ordered by **customerName** in ascending order.
         -   ```sql
             select customerName, phone, addressline1, city, state, postalcode
             from customers
             where country <> 'Germany'
             order by customerName;
             
             
             ```
             
 -   04. Patients With a Condition
     -   Write an SQL query to report the **patient_id** who have Type I Diabetes. Type I Diabetes always starts with **DIAB1** prefix.
         -   ```sql
             SELECT patient_id
             FROM patients
             WHERE conditions LIKE 'DIAB1%' OR conditions LIKE '% DIAB1%'
             ```
             
 -   Q5. 2012-2015
     -   ```sql
         SELECT original_title, genres, vote_average, revenue
         FROM movies
         WHERE release_year 
         BETWEEN 2012 AND 2015
         ORDER BY original_title ASC
         ```
         
 -   06. Olympic Table
     -   Write a SQL query to sort the olympic table according to the following rules: The country with more gold medals should come first. If there is a tie in the no. of gold medals, the country with more silver medals should come first. If there is a tie in the no. of silver medals, the country with more bronze medals should come first. If there is a tie in the no. of bronze medals as well, then the countries with the tie are sorted in ascending order lexicographically.
         -   ```sql
             SELECT * FROM olympic
             ORDER BY gold_medals DESC, silver_medals DESC, bronze_medals DESC, country ASC;
             ```
             
 -   Q7. Keywords
     -   Write a query to list down all the movies along with their details that have **keywords** like 'sport' or 'sequel' or 'suspense'. **Note:** Return the columns '**original_title**', '**director**', '**genres**', '**cast**', '**budget**', '**revenue**', '**runtime**', and '**vote_average**'. Return the columns ordered by **original_title** in ascending order.
         -   ```sql
             SELECT original_title, director, genres, cast, budget, revenue, runtime, vote_average
             FROM movies
             WHERE 
             	keywords Like '%sport%' or 
             	keywords Like '%sequel%' or 
             	keywords Like '%suspense%'
             ORDER BY original_title ASC;
             ```
             
 -   01. Cities starting with vowels
     -   Write a query to get the list of city names starting with vowels (i.e., a, e, i, o, or u) from station table. The result should not contain duplicate values. Return the result table ordered by cityin **ascending** order.
         -   ```sql
             SELECT DISTINCT city 
             FROM station
             WHERE 
                 city LIKE 'a%' OR 
                 city LIKE 'e%' OR 
                 city LIKE 'i%' OR 
                 city LIKE 'o%' OR 
                 city LIKE 'u%'
             ORDER BY city ASC;
             ```
             
 -   Q2. Problems that are low quality
     -   Write a query to report the IDs of the **low-quality** problems. A problem is low-quality if the **like** percentage of the problem (the number of likes divided by the total number of votes) is strictly **less than 60%**. Return the result table ordered by problem_idin **ascending order**.
         -   ```sql
             SELECT problem_id 
             FROM problems
             WHERE (likes / (likes + dislikes)) <  0.60
             ORDER BY problem_id ASC
             ```
             
 -   03. Human Resources
     -   Write a query to find details of the employees who work in the '**Human** **Resources**' department. Return the columns '**employee_id**', '**department_id**', '**first_name**', '**last_name**', '**job_id**', and '**department_name**'. Return the result ordered by **employee_id** in ascending order.
         -   ```sql
             SELECT 
                 e.employee_id, 
                 e.department_id, 
                 e.first_name, 
                 e.last_name, 
                 e.job_id, 
                 d.department_name 
             FROM employees e
             INNER JOIN departments d
             ON e.department_id = d.department_id
             WHERE d.department_name = 'Human Resources'
             ORDER BY e.employee_id;
             ```
             
 -   Q4. Article Views II
     -   Write a query to find all the people who viewed **more than one** article on the **same** date. Save the **viewer_id** as the **id**. Return the result sorted by **id** in ascending order.
         -   ```sql
             SELECT DISTINCT v1.viewer_id AS id
             FROM views v1
             JOIN views v2
             ON 
                 v1.viewer_id = v2.viewer_id
                 AND v1.view_date = v2.view_date
                 AND v1.article_id != v2.article_id
             ORDER BY id;
             ```
             
         -   JOIN views v2: The query performs a self-join on the **views** table by joining it with itself, creating a second alias **v2**. This is done to compare the views of different articles by the same viewer on the same date.
         -   N v1.viewer_id = v2.viewer_id AND v1.view_date = v2.view_date AND v1.article_id != v2.article_id: This is the condition for the join. It specifies that we want to match rows where both **v1** and **v2** have the same **viewer_id** and the same **view_date**, but they must be viewing different articles (**v1.article_id** must not be equal to **v2.article_id**). This condition ensures that we're looking for viewers who viewed more than one article on the same date.

<!-- TOC --><a name="sql-lab-1"></a>
###  SQL Lab

 -   **Using Database:**
     -   ```sql
         -- Selecting the 'sakila' database for further operations.
         USE sakila;
         ```
         
     -   **Explanation:** This command switches to the 'sakila' database, allowing subsequent queries to be executed within that database.
 -   **Using BETWEEN Operator:**
     -   ```sql
         -- Using the BETWEEN operator to filter films released between 2007 and 2010.
         SELECT * FROM film
         WHERE release_year BETWEEN 2007 AND 2010;
         ```
         
     -   **Explanation:** This query retrieves films with release years between 2007 and 2010 inclusive using the BETWEEN operator.
 -   **Using LIKE Operator:**
     -   ```sql
         -- Using the LIKE operator to search for films with 'love' in the title.
         SELECT * FROM film
         WHERE title LIKE '% love' OR title LIKE 'love %' OR title LIKE '% love %';
         
         -- Query for an exact title match.
         SELECT * FROM film
         WHERE title = 'love';
         
         -- Query for a title starting with 'love' and ending with 'love'.
         -- 'love%love'
         ```
         
     -   **Explanation:** These queries demonstrate the use of the LIKE operator for searching and filtering films with titles containing the word 'love' in various ways.
 -   **Using IS NULL and NOT LIKE:**
     -   ```sql
         -- Using NOT LIKE to filter out records with 'Trailers' in special features or null values.
         SELECT * FROM film
         WHERE special_features NOT LIKE '%Trailers%' OR special_features IS NULL;
         
         -- Using IS NULL to check for null values.
         ```
         
     -   **Explanation:** These queries show how to filter records that do not contain 'Trailers' in the special features column or have null values in that column.
 -   **Using ORDER BY:**
     -   ```sql
         -- Sorting records by release year in descending order and title in ascending order.
         SELECT * FROM film
         ORDER BY release_year DESC, title ASC;
         
         -- Sorting with DISTINCT incompatibility.
         -- Error: Expression #1 of ORDER BY clause is not in SELECT list.
         SELECT DISTINCT title FROM film
         ORDER BY release_year;
         
         -- Sorting distinct release years in descending order.
         SELECT DISTINCT release_year FROM film
         ORDER BY release_year DESC;
         
         -- Limiting the number of records displayed.
         SELECT * FROM film
         ORDER BY film_id DESC
         LIMIT 5;
         
         -- Pagination: Displaying records 5 to 10.
         SELECT * FROM film
         WHERE release_year > 2006
         LIMIT 6 OFFSET 2; 
         ```
         
     -   **Explanation:** These queries showcase sorting records using the ORDER BY clause and limiting the number of records displayed, as well as implementing pagination.
 -   **Using UPDATE:**
     -   ```sql
         -- Updating the release year for a specific movie (film_id = 1).
         UPDATE film
         SET release_year = 2011
         WHERE film_id = 1;
         
         -- Updating multiple columns for a specific movie (film_id = 1).
         UPDATE film
         SET release_year = 2012, rating = 'G'
         WHERE film_id = 1;
         ```
         
     -   **Explanation:** These queries demonstrate how to update specific records in the 'film' table.
 -   **Using DELETE:**
     -   ```sql
         -- Deleting a specific record from the 'film' table.
         DELETE FROM film
         WHERE film_id = 1005;
         ```
         
     -   **Explanation:** This query shows how to delete a specific record from the 'film' table.
 -   **Using SQL_SAFE_UPDATES:**
     -   ```sql
         -- Attempting to update all rows in the 'batches' table without a WHERE clause.
         -- This triggers a safe update mode error.
         UPDATE aug22beg.batches
         SET name = "temp";
         
         -- Disabling safe update mode.
         SET SQL_SAFE_UPDATES = 0;
         
         -- Truncating the 'temp' table.
         TRUNCATE temp;
         
         -- Dropping the 'temp' table.
         DROP TABLE temp;
         
         -- Recreating the 'temp' table.
         CREATE TABLE temp (
             id INT PRIMARY KEY
         ); 
         ```
         
     -   **Explanation:** These commands demonstrate how to deal with safe update mode, truncate a table, and drop/recreate a table in MySQL.

<!-- TOC --><a name="sol-5-joins-i"></a>
## SOL 5: Joins - I
<!-- TOC --><a name="class-notes-3"></a>
### Class Notes

  -   **Joins**
      -   In SQL, joins are used to combine rows from two or more tables based on a related column between them.
      -   Joins are a fundamental aspect of relational databases, enabling you to retrieve data from multiple tables and combine it to create a comprehensive dataset.
      -   There are several types of joins, including INNER JOIN, LEFT JOIN (or LEFT OUTER JOIN), RIGHT JOIN (or RIGHT OUTER JOIN), and FULL JOIN (or FULL OUTER JOIN).
  -   **Self Join**
      -   A self join is a specific type of join where a table is joined with itself. It's used when you want to compare rows within the same table, often when there's a hierarchical or parent-child relationship in the data. You give different aliases to the same table to distinguish between the parent and child records.
      -   Example - Finding employees who are managers:
      -   ```sql
          SELECT e1.employee_name AS manager, e2.employee_name AS employee
          FROM employees e1
          INNER JOIN employees e2 ON e1.employee_id = e2.manager_id;
          ```
          
          -   This query returns a list of employees and their respective managers.
  -   **Exploring the Order of SQL Query Execution**
      -   SQL query execution follows a specific order, which can be summarized in the following way:
          -   1. **FROM**: The first part of the query specifies the source tables. The database engine reads the tables involved and creates a temporary working set, often referred to as the "result set."
          -   2. **JOIN**: If there are any join operations, the database engine combines rows from the tables as per the join conditions, narrowing down the working set.
          -   3. **WHERE**: The WHERE clause filters the working set to include only rows that meet the specified conditions.
          -   4. **GROUP BY**: If there's a GROUP BY clause, the working set is grouped by the specified columns, resulting in a summary of data.
          -   5. **HAVING**: The HAVING clause filters the grouped data, similar to the WHERE clause but applied to groups of rows.
          -   6. **SELECT**: The SELECT clause specifies the columns to include in the final result set.
          -   7. **DISTINCT**: If the DISTINCT keyword is used, duplicate rows are removed from the result set.
          -   8. **ORDER BY**: The ORDER BY clause sorts the result set based on the specified columns and the desired order.
          -   9. **LIMIT/OFFSET (optional)**: If you want to limit the number of rows returned or skip some rows, you can use the LIMIT and OFFSET clauses.
      -   Acronym - **Frogs Jump Wildly, Grinning Hilariously, Snatching Delicious Orbs Lavishly**

### Problem Set

  -   Q1. Joined first
      -   Display the details of the employees who joined the company before their managers joined the company. Return the columns '**employee_id**', '**first_name**', and '**last_name**'. Return the result ordered by **employee_id** in ascending order.
          -   ```sql
              SELECT E1.employee_id, E1.first_name, E1.last_name
              from employees E1
              JOIN employees E2
              	ON E1.manager_id = E2.employee_id
              WHERE E1.hire_date < E2.hire_date
              ORDER BY E1.employee_id;
              ```
              
  -   Q2. Human Resources
      -   Write a query to find details of the employees who work in the '**Human** **Resources**' department. Return the columns '**employee_id**', '**department_id**', '**first_name**', '**last_name**', '**job_id**', and '**department_name**'. Return the result ordered by **employee_id** in ascending order.
          -   ```sql
              SELECT e.employee_id, d.department_id, e.first_name, e.last_name, e.job_id, d.department_name
              FROM employees e 
              JOIN departments d
              	ON e.department_id = d.department_id
              AND d.department_name = 'Human Resources'
              ORDER BY employee_id
              ```
              
  -   03. Article Views Il 🔸
      -   Write a query to find all the people who viewed **more than one** article on the **same** date. Save the **viewer_id** as the **id**. Return the result sorted by **id** in ascending order.
          -   ```sql
              # Approach 1: Joins
              
              SELECT DISTINCT v1.viewer_id AS id 
              FROM views v1
              JOIN views v2
              	ON v1.viewer_id = v2.viewer_id
              		AND v1.view_date = v2.view_date
              		AND v1.article_id != v2.article_id
              ORDER BY id;
              
              # Approach 2: Subquery
              
              SELECT DISTINCT viewer_id AS id
              FROM views
              WHERE (viewer_id, view_date) IN (
                  SELECT viewer_id, view_date
                  FROM views
                  GROUP BY viewer_id, view_date
                  HAVING COUNT(DISTINCT article_id) > 1
              )
              ORDER BY id;
              
              ```
              
          -   Approach 2: Subquery
              -   This query works as follows:
                  -   In the subquery, it first groups the views by **viewer_id** and **view_date** and counts the distinct **article_id** for each group.
                  -   The **HAVING** clause filters the groups to include only those where the count of distinct **article_id** is greater than 1. This means the same viewer viewed more than one article on the same date.
                  -   The outer query then selects the **viewer_id** values where the combination of **viewer_id** and **view_date** matches the subquery's result, ensuring that we only get the viewer_id values that meet the criteria.
                  -   Finally, it orders the result by "id" (viewer_id) in ascending order.
  -   Q4. Department in US
      -   Display the details of those employees who have a **manager** working in the department that is **US** (i.e., country_id) based. **Note:** Return the columns **employee_id**, **first_name**, and **last_name**. Return the result ordered by **employee_id** in ascending order.
          -   ```sql
              SELECT e.employee_id, e.first_name, e.last_name
              FROM employees e
              JOIN employees em
                  on e.manager_id = em.employee_id
              JOIN departments d
                  on em.department_id = d.department_id
              JOIN locations l
                  on d.location_id = l.location_id 
              WHERE l.country_id = 'US'
              ORDER BY e.employee_id ASC
              ```
              
  -   05. Job like sales
      -   Display the details of the employees who **had** job titles like 'sales' in the **past** and the **min_salary** is greater than or equal to **6000**. Return the columns '**employee_id**', '**department_name**', '**job_id**', '**job_title**', and '**min_salary**'. Return the employee's current information for the columns 'employee_id_',_ and _'_department_name'. Return the employee's past information for the columns 'job_id_', '_job_title', and 'min_salary'. Return the output ordered by **employee_id** and **min_salary** in ascending order.
          -   ```sql
              SELECT e.employee_id, d.department_name, h.job_id, j.job_title, j.min_salary
              FROM employees e
              JOIN departments d
                  on e.department_id = d.department_id
              JOIN job_history h
                  on e.employee_id = h.employee_id
              JOIN jobs j 
                  on h.job_id = j.job_id 
              WHERE j.job_title LIKE '%sales%' AND j.min_salary >= 6000
              ORDER BY e.employee_id, j.min_salary
              
              ```
              
  -   Q1. Product Sales Analysis V
      -   Write an SQL query that reports the spending of each user. Return the resulting table ordered by **spending** in **descending order**. In case of a tie, order them by **user_id** in **ascending order**.
          -   ```sql
              SELECT s.user_id, SUM(s.quantity * p.price) as spending
              FROM sales s
              INNER JOIN product p
              ON s.product_id = p.product_id
              GROUP BY s.user_id
              ORDER BY spending DESC, user_id ASC;
              
              ```
              
  -   02. Same manager
      -   Extract the details of the employees who work under the **same manager**. Return the details along with the manager's full name (first name, last name separated by space) as 'Manager' and the employee's full name (first name, last name separated by space) as 'Employee'. Order the output based on manager_id and 'Employee' in ascending order. Return the columns '**manager_id**', '**Manager**', '**Employee**'.
          -   ```sql
              SELECT e.manager_id AS manager_id,
                     CONCAT(em.first_name, ' ', em.last_name) AS Manager,
                     CONCAT(e.first_name, ' ', e.last_name) AS Employee
              FROM employees e
              INNER JOIN employees em ON e.manager_id = em.employee_id
              WHERE e.manager_id IS NOT NULL
              ORDER BY e.manager_id ASC, Employee ASC;
              ```
              
  -   Q3. Three months
      -   Display the details of those employees who were hired between the given date '**1998-01-01**' and **three** months after from the given date. Return the columns '**employee_id**', '**first_name**', '**last_name**', '**salary**', '**department_name**', '**hire_date**', '**city'.** Return the result ordered by employee_id in ascending order.
          -   ```sql
              SELECT e.employee_id, e.first_name, e.last_name, e.salary, d.department_name, e.hire_date, l.city
              FROM employees e
              INNER JOIN departments d ON e.department_id = d.department_id
              INNER JOIN locations l ON d.location_id = l.location_id
              WHERE e.hire_date >= '1998-01-01' AND e.hire_date <= DATE_ADD('1998-01-01', INTERVAL 3 MONTH)
              ORDER BY e.employee_id ASC; ```

<!-- TOC --><a name="sql-6-joins-ii"></a>
## SQL 6: Joins - II

<!-- TOC --><a name="class-notes-4"></a>
### Class Notes

-  **INNER JOIN:**
   -   An INNER JOIN retrieves records that have matching values in both tables. It combines rows where the specified column(s) have matching values in both tables.
       -   ```sql
           SELECT employees.name, departments.department_name
           FROM employees
           INNER JOIN departments ON employees.department_id = departments.department_id;
           ```
           
-   **LEFT JOIN (LEFT OUTER JOIN):**
   -   A LEFT JOIN retrieves all records from the left (first) table and the matching records from the right (second) table. If there's no match in the right table, NULL values are returned.
   -   ```sql
       SELECT customers.name, orders.order_date
       FROM customers
       LEFT JOIN orders ON customers.customer_id = orders.customer_id;
       ```
       
-   **RIGHT JOIN (RIGHT OUTER JOIN):**
   -   A RIGHT JOIN retrieves all records from the right (second) table and the matching records from the left (first) table. If there's no match in the left table, NULL values are returned.
   -   ```sql
       SELECT products.product_name, inventory.quantity
       FROM inventory
       RIGHT JOIN products ON inventory.product_id = products.product_id;
       ```
       
-   **FULL JOIN (FULL OUTER JOIN):**
   -   SQL databases like MySQL, PostgreSQL, or Oracle don't support a FULL JOIN keyword. Instead, you achieve the same result using a combination of LEFT JOIN and RIGHT JOIN, as follows:
   -   ```sql
       SELECT employees.name, projects.project_name
       FROM employees
       LEFT JOIN projects ON employees.employee_id = projects.employee_id
       
       UNION ALL
       
       SELECT employees.name, projects.project_name
       FROM employees
       RIGHT JOIN projects ON employees.employee_id = projects.employee_id;
       
       ```
       
<!-- TOC --><a name="problem-set-1"></a>
###   Problem Set
-   Q1. Department (No employee)
   -   Write a query to display the details of all those departments that **don't** have any working employees. Return the columns '**department_id**', and '**department_name**'.
       -   ```sql
           SELECT d.department_id, d.department_name
           FROM departments d
           Left JOIN employees e
           on d.department_id = e.department_id
           WHERE e.department_id is NULL
           ORDER BY department_id
           ```
           
-   Q2. Manager left
   -   Write a query to find the **employee_id** of the employees whose salary is strictly **less than** $15000 and whose manager left the company. When a manager leaves the company, their information is deleted from the employees table, but the reports still have their manager_id set to the manager that left. **Note**: Return the result ordered by **employee_id** in ascending order.
       -   ```sql
           SELECT e.employee_id
           FROM employees e
           LEFT JOIN employees em
           on e.manager_id = em.employee_id
           WHERE e.manager_id is NOT NULL and e.salary < 15000 and em.employee_id is NULL
           order by e.employee_id 
           ```
           
-   Q3. Handles No Customers
   -   Write a SQL query to find the employee details who handles **no** customers. **Note:** Use the given **customers** table. Return the output ordered by **employeeNumber** in ascending order. The **salesRepEmployeeNumber** column to the **employeeNumber** who made sales to the customers.
       -   ```sql
           SELECT E.employeeNumber, E.firstName, E.lastName
           FROM employees E 
           LEFT JOIN customers C
           ON E.employeeNumber = C.salesRepEmployeeNumber
           WHERE C.salesRepEmployeeNumber is NULL
           ORDER BY E.employeeNumber; 
           ```
           
-   Q4. Employees & Offices
   -   Write a SQL query to get **all** the possible combinations of **employees** and **offices**. Return the output ordered by **employeeNumber** and **officeCode** in ascending order.
       -   ```sql
           SELECT e.employeeNumber, e.firstName, e.lastName, o.officeCode, o.city
           FROM employees e
           CROSS JOIN offices o
           ORDER BY e.employeeNumber ASC, o.officeCode ASC;
           ```
           
-   Q5. Combine Two Tables
   -   Write an SQL query to report the **city** of each person in the **Person** table. If the address of a personId is not present in the Address table, report **null** instead. Return the result table in order of city names.
       -   ```sql
           SELECT city
           FROM person
           LEFT JOIN address
           USING(personId)
           ORDER BY city ASC
           ```
           
-   Q6. Queries (NPV) 🔺
   -   Write a query to find the npv of each query of the queries table. Return the output order by id and year in the ascending order
       -   ```sql
           SELECT q.*, IFNULL(npv, 0) AS npv
           FROM queries q
           LEFT JOIN npv n
           	ON n.id = q.id 
           	AND n.year = q.year
           ORDER BY id, year;
           ```
           
-   Q1. Employee Bonus Query
   -   Write a query to report the name of each employee with a bonus of less than 1000. Return the bonus as 'NULL' if an employee doesn’t have a bonus of less than 1000. Return the result table sorted w.r.t. **name** of the employees in ascending order.
       -   ```sql
           SELECT e.name, b.bonus
           FROM employee AS e
           LEFT JOIN Bonus AS b ON e.empId = b.empId
           WHERE b.bonus < 1000 OR b.bonus IS NULL
           ORDER BY e.name;
           
           ```
           
-   Q2. Replace Employee ID With The Unique Identifier
   -   Write an SQL query to show the **unique** **ID** of each user, If a user does not have a unique ID replace just show **null**_._
       -   ```sql
           SELECT em.unique_id
           FROM employees AS e
           LEFT JOIN employeeUNI AS em
           ON e.id = em.id
           ```
           
-   Q3. Ad-Free Sessions
   -   Write a query to report all the sessions that **did not** get shown any ads. Return the resultant table ordered by **session_id** in **ascending order**.
-   ```sql
    select session_id
    from Playback p
    left join Ads a 
    	on a.customer_id = p.customer_id 
    	and a.timestamp between p.start_time and p.end_time
    where a.customer_id is null
    order by session_id; ```

<!-- TOC --><a name="sql-7-aggregate-queries"></a>
## SQL 7: Aggregate Queries

<!-- TOC --><a name="class-notes-5"></a>
###   Class Notes
  -   **Aggregate Queries:**
      -   Aggregate queries are SQL queries that involve the use of aggregate functions to perform operations on groups of rows.
      -   They are used to summarize, analyze, and calculate data in a database table.
  -   **Aggregate Functions:**
      -   Aggregate functions are SQL functions used to perform calculations on a set of values and return a single value.
      -   Common aggregate functions include:
          -   COUNT(): Counts the number of rows.
          -   SUM(): Calculates the sum of values.
          -   AVG(): Calculates the average of values.
          -   MIN(): Finds the minimum value.
          -   MAX(): Finds the maximum value.
  -   **GROUP BY Clause:**
      -   The GROUP BY clause is used to group rows that have the same values in specified columns into summary rows.
      -   It is often used in conjunction with aggregate functions.
      -   Example:
          -   ```sql
              SELECT department, AVG(salary) as avg_salary
              FROM employees
              GROUP BY department;
              ```
              
  -   **HAVING Clause:**
      -   The HAVING clause is used in combination with the GROUP BY clause to filter the results of grouped rows.
      -   It is used to specify a condition that must be satisfied by groups, typically involving aggregate functions.
      -   Example:
          -   ```sql
              SELECT department, AVG(salary) as avg_salary
              FROM employees
              GROUP BY department
              HAVING AVG(salary) > 50000;
              ```
              
<!-- TOC --><a name="problem-set-2"></a>
###   Problem Set
  -   Q1. SQL_Question_1
      -   Write a SQL query to print department name along with department wise average salary. The average salary should be rounded to 2 decimal places. **Output Schema:**department_name,average_salary
          -   ```sql
              SELECT d.deptname AS department_name, ROUND(AVG(e.salary), 2) AS average_salary
              FROM employee e
              INNER JOIN department d  ON e.deptid = d.deptid
              GROUP BY d.deptid, d.deptname;
              
              ```
              
  -   Q2. Average Employee Salary
      -   Write a query to get the details of the average salary of the employees for each department. Save the new column as 'avg_employee_salary' Return the result order by avg_employee_salary in descending order and **department_id** in ascending order.
          -   ```sql
              SELECT e.department_id AS department_id, AVG(e.salary) AS avg_employee_salary
              FROM employees e
              GROUP BY e.department_id
              ORDER BY
                  avg_employee_salary DESC,
                  e.department_id ASC;
              
              ```
              
  -   Q3. Customer Placing the Largest Number of Orders
      -   Write an SQL query to find the **customer_number** for the customer who has placed the **largest number of orders**_._
          -   ```sql
              SELECT customer_number
              FROM Orders
              GROUP BY customer_number
              ORDER BY COUNT(order_number) DESC
              LIMIT 1;
              ```
              
  -   **Q4. Classes More Than 5 Students**
      -   Write an SQL query to report all the **classes** that have at **least five students**_._ Return the result table **ordered by class** in **descending order**.
          -   ```sql
              SELECT class
              FROM courses
              GROUP BY class
              HAVING COUNT(student) >= 5
              ORDER BY class DESC;
              
              ```
              
  -   **Q5. Cost for each category**
      -   For the given table of sales in the diagram, select the query which gives the total cost for each category.
          -   ```sql
              SELECT cate_id, SUM(receive_qty * purch_price)   
              FROM purchase
              GROUP BY cate_id;
              ```
              
  -   **Q6. Duplicate Emails**
      -   Write a SQL query to find people with more than 1 email ids
          -   ```sql
              SELECT email
              FROM Person
              GROUP BY email
              HAVING COUNT(email) > 1
              ORDER BY email;
              
              ```
              
  -   Q1. Northern Latitudes
      -   Write a query to get the greatest value of the Northern Latitudes (lat_n) as **max** from the **station** table which is **less** than 138.2523. Round off the maximum value to **4** decimal places.
          -   ```sql
              SELECT ROUND(MAX(lat_n), 4) AS max
              FROM station
              WHERE lat_n < 138.2523;
              ```
              
  -   Q2. Income greater than 2000
      -   Write a query to find the cities where employees have a minimum income greater than $2000. Save the new column as '**Minimum_Income**' Round Minimum_Income up to **two** decimal places. Return the result order by the **City** in ascending order.
          -   ```sql
              SELECT City, ROUND(MIN(Income), 2) AS Minimum_Income
              FROM employees
              GROUP BY City
              HAVING MIN(Income) > 2000
              ORDER BY City ASC;
              ```
              
  -   Q3. Students in Departments
      -   Write a query to report the respective department name and number of students majoring in each department for all departments in the Department table (even ones with no current students). Return the result table ordered by student_number in descending order. In case of a tie, order them by dept_name alphabetically.
          -   ```sql
              SELECT d.dept_name AS dept_name, COUNT(s.student_id) AS student_number
              FROM department d
              LEFT JOIN student s ON d.dept_id = s.dept_id
              GROUP BY dept_name
              ORDER BY student_number DESC, dept_name ASC;
              ```
              
  -   Q4. Products Recommendation 🔺
      -   Write a query to find the **customer_id** and **customer_name** of customers who bought products "**Bread**" and "**Milk**" but did not buy the product "**Eggs**". Return the output ordered by **customer_name** in ascending order
          -   ```sql
              SELECT c.customer_id, c.customer_name
              FROM customers c
              INNER JOIN orders o ON c.customer_id = o.customer_id
              WHERE o.product_name IN ('Bread', 'Milk')
              AND c.customer_id NOT IN (
                  SELECT customer_id
                  FROM orders
                  WHERE product_name = 'Eggs'
              )
              GROUP BY c.customer_id, c.customer_name
              HAVING COUNT(DISTINCT o.product_name) = 2
              ORDER BY c.customer_name ASC;```

## SQL 8: Subqueries and Views


###   Class Notes
  -   **Subqueries:**
      -   Subqueries are queries nested within another query.
      -   They can be used in various parts of a SQL statement, such as SELECT, FROM, or WHERE clauses.
      -   Example:
          -   ```sql
              SELECT employee_name
              FROM employees
              WHERE department_id = (SELECT department_id FROM departments WHERE department_name = 'Sales');
              ```
              
  -   **IN Clause:**
      -   The IN clause is used to check if a value matches any value in a list.
      -   It is often used with subqueries.
      -   Example:
          -   ```sql
              SELECT product_name
              FROM products
              WHERE category_id IN (SELECT category_id FROM categories WHERE category_name = 'Electronics');
              ```
              
  -   **FROM Clause:**
      -   The FROM clause is used to define a derived table or subquery in the FROM clause of a query.
      -   It allows you to treat the result of a subquery as a table.
      -   Example:
          -   ```sql
              SELECT AVG(salary)
              FROM (SELECT DISTINCT department_id, salary FROM employees) AS subquery;
              ```
              
  -   **ALL, ANY:**
      -   ALL and ANY are used in conjunction with comparison operators.
      -   ALL returns true if a condition is true for all values in a subquery.
      -   ANY returns true if a condition is true for at least one value in a subquery.
      -   Example:
          -   ```sql
              SELECT employee_name
              FROM employees
              WHERE salary > ALL (SELECT salary FROM employees WHERE department_id = 101);
              ```
              
  -   **Correlated Subqueries:**
      -   A correlated subquery refers to an outer query from within the subquery.
      -   It uses values from the outer query in the subquery.
      -   Example:
          -   ```sql
              SELECT employee_name
              FROM employees e
              WHERE salary > (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id);
              ```
              
  -   **EXISTS:**
      -   The EXISTS keyword in SQL is used to check whether the result of a correlated nested query is empty (contains no tuples) or not
      -   For example, if you want to fetch the first and last name of the customers who placed at least one order, you can use the EXISTS keyword like this:
          -   SELECT fname, lname FROM Customers WHERE EXISTS ( SELECT * FROM Orders WHERE Customers.customer_id = Orders.c_id );
  -   **Subqueries in WHERE Clause:**
      -   Subqueries in the WHERE clause are used to filter rows based on a condition from a subquery.
      -   They can be used for complex filtering and comparisons.
      -   Example:
          -   ```sql
              SELECT customer_name
              FROM customers
              WHERE customer_id IN (SELECT customer_id FROM orders WHERE order_date > '2023-01-01');
              ```
              
###   Problem Set
  -   Q1. No Job history
      -   Display all the details of the employees who did **not work** at any job in the **past**. Return **all** the columns from the employee's table. Return the result ordered by **employee_id** in ascending order. **NOTE:** To get the details of the employee's previous jobs refer to the job_history table. An employee is present in the job_history table if has worked before.
      -   ```sql
          SELECT e.*
          FROM employees e
          LEFT JOIN job_history jh ON e.employee_id = jh.employee_id
          WHERE jh.employee_id IS NULL
          ORDER BY e.employee_id ASC;
          ```
          
  -   Q2. Customers order
      -   Write a query to find all the customers who have not ordered anything. Return the name of the customers as '**Customers**'.
      -   Approach 1
          -   ```sql
              select Name as 'Customers' 
              from customers 
              where Id not in 
              (select Cust_id from orders);
              ```
              
      -   Approach 2
          -   ```sql
              select Name as 'Customers' 
              from customers c 
              left join
              orders o
              on c.Id = o.Cust_id
              where o.Cust_id is null;
              ```
              
  -   Q3. 4 or More employees
      -   Write a query to display the "**full_name**" (first name and last name separated by space) of a manager who manages **4 or more employees**. **Note:** Return the result ordered by **full_name** in ascending order. The column **manager_id** in the **employees** table represents the **employee_id** of the manager.
      -   ```sql
          SELECT CONCAT(e.first_name, ' ', e.last_name) AS full_name
          FROM employees e
          WHERE e.employee_id IN (
              SELECT manager_id
              FROM employees
              GROUP BY manager_id
              HAVING COUNT(*) >= 4
          )
          ORDER BY full_name ASC;
          ```
          
  -   Q4. Department name
      -   Find the details of the employees who are working in the departments '**Administration**', '**Marketing**', and '**Human Resources**'. Return the columns '**employee_id**', '**full_name**'(first and last name separated by space), and '**salary**'. Return the result ordered by **employee_id** in ascending order.
      -   ```sql
          SELECT 
              e.employee_id AS employee_id,
              CONCAT(e.first_name, ' ', e.last_name) AS full_name,
              e.salary AS salary
          FROM 
              employees e
          JOIN 
              departments d ON e.department_id = d.department_id
          WHERE 
              d.department_name IN ('Administration', 'Marketing', 'Human Resources')
          ORDER BY 
              e.employee_id ASC;
          ```
          
  -   Q5. 3rd highest
      -   Write a SQL query to find all the details of those employees who earn the **third-highest salary**. Return **all** the columns from the employees table. **Follow-Up:** Avoid using LIMIT keyword in the query.
      -   Approach 1:
          -   ```sql
              SELECT *
              FROM employees
              WHERE salary = (
                  SELECT DISTINCT salary
                  FROM employees
                  ORDER BY salary DESC
                  LIMIT 1 OFFSET 2
              );
              ```
              
      -   Approach 2: Follow-up
          -   ```sql
              SELECT *
              FROM employees
              WHERE salary IN (
                  SELECT MAX(salary)
                  FROM employees
                  WHERE salary < (
                      SELECT MAX(salary)
                      FROM employees
                      WHERE salary < (
                          SELECT MAX(salary)
                          FROM employees
                      )
                  )
              );
              ```
              
      -   Approach 3:
          -   ```sql
              SELECT e1.*
              FROM employees e1
              WHERE 2 = (
                  SELECT COUNT(DISTINCT e2.salary)
                  FROM employees e2
                  WHERE e2.salary > e1.salary
              );
              
              ```
              
          -   The outer query (**SELECT e1.***) selects all employees (**e1.***) from the "employees" table where the count from the subquery is equal to 2.
          -   The subquery (**SELECT COUNT(DISTINCT e2.salary) FROM employees e2 WHERE e2.salary > e1.salary**) counts the number of distinct salaries that are greater than the salary of the employee represented by **e1**.
          -   If exactly two distinct salaries are greater than the salary of the employee **e1**, it means that the salary of **e1** is the third-highest salary in the table. This is because there are two employees with higher salaries than **e1**, and that places **e1** in the third position in terms of salary ranking.
  -   Q1. Request Confirmation Messages
      -   ```sql
          SELECT DISTINCT user_id
          FROM (
              SELECT C.user_id, 
                     TIMESTAMPDIFF(SECOND, LAG(C.time_stamp) OVER(PARTITION BY user_id ORDER BY time_stamp ASC), C.time_stamp) AS difference
              FROM confirmations AS C
          ) AS A
          WHERE A.difference <= 86400
          ORDER BY user_id;
          
          ```
          
  -   Q2. Candidates Skills
      -   Given a list of candidates and their skills, you're asked to find the candidates best suited for an open Data Science job. We want to find candidates who are proficient in '**Python**', '**Tableau**', and '**MySQL**'. Write a query to list the candidates who possess all three required skills for the job. **Note:** There are no duplicates in the candidates table. Return the result ordered by **candidate_id** in ascending order.
      -   ```sql
          SELECT candidate_id
          FROM candidates
          WHERE skill IN ('Python', 'Tableau', 'MySQL')
          GROUP BY candidate_id
          HAVING COUNT(DISTINCT skill) = 3
          ORDER BY candidate_id ASC;
          ```
          
  -   Q3. Seattle
      -   Display the details of all the employees whose department location is in **Seattle**. Return the columns '**employee_id**', '**first_name**', '**last_name**', and **job_id**'. Return the table ordered by **employee_id** in ascending order.
      -   ```sql
          SELECT e.employee_id, e.first_name, e.last_name, e.job_id
          FROM employees e
          JOIN departments d ON e.department_id = d.department_id
          JOIN locations l ON d.location_id = l.location_id
          WHERE l.city = 'Seattle'
          ORDER BY e.employee_id ASC;
          ```
          
  -   Q4. Employee 107
      -   ```sql
          SELECT 
              CONCAT(first_name, ' ', last_name) AS full_name,
              salary,
              department_id,
              job_id
          FROM employees
          WHERE job_id = (
              SELECT job_id
              FROM employees
              WHERE employee_id = 107
          )
          ORDER BY full_name;  ```
          
  -   **Q5. Consecutive Available Seats**

<!-- TOC --><a name="references"></a>
###   References
  -   Leetcode
      -   [https://leetcode.com/problems/find-customer-referee/](https://leetcode.com/problems/find-customer-referee/) [https://leetcode.com/problems/big-countries/](https://leetcode.com/problems/big-countries/) [https://leetcode.com/problems/not-boring-movies/](https://leetcode.com/problems/not-boring-movies/)
      -   [https://leetcode.com/problems/article-views-i/](https://leetcode.com/problems/article-views-i/) [https://leetcode.com/problems/patients-with-a-condition/](https://leetcode.com/problems/patients-with-a-condition/)
      -   [https://leetcode.com/problems/combine-two-tables/](https://leetcode.com/problems/combine-two-tables/) [https://leetcode.com/problems/employees-earning-more-than-their-managers/](https://leetcode.com/problems/employees-earning-more-than-their-managers/)
      -   [https://leetcode.com/problems/delete-duplicate-emails/](https://leetcode.com/problems/delete-duplicate-emails/) [https://leetcode.com/problems/rising-temperature/](https://leetcode.com/problems/rising-temperature/) [https://leetcode.com/problems/employee-bonus/](https://leetcode.com/problems/employee-bonus/)
      -   [https://leetcode.com/problems/product-sales-analysis-i/](https://leetcode.com/problems/product-sales-analysis-i/) [https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/](https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/)
      -   [https://leetcode.com/problems/npv-queries/](https://leetcode.com/problems/npv-queries/)
      -   [https://leetcode.com/problems/employees-earning-more-than-their-managers/](https://leetcode.com/problems/employees-earning-more-than-their-managers/)
  -   [https://docs.google.com/spreadsheets/d/1KmWlnuAdf0gJtjB-E-HJn2rchqG9xgdWQHHM6LcXVdA/edit#gid=0](https://docs.google.com/spreadsheets/d/1KmWlnuAdf0gJtjB-E-HJn2rchqG9xgdWQHHM6LcXVdA/edit#gid=0)
  -   [https://blog.akjn.dev/correlated-subqueries-and-why-you-need-to-know-them](https://blog.akjn.dev/correlated-subqueries-and-why-you-need-to-know-them)
  -   [https://github.com/rahulgrover99/Aug22Beg-SQL](https://github.com/rahulgrover99/Aug22Beg-SQL)

<!-- TOC --><a name="sql-9-indexing"></a>
## SQL 9: Indexing

<!-- TOC --><a name="class-notes-6"></a>
### Class Notes
  - Introduction to Indexing 
      - Indexing is a database optimization technique used to enhance query performance.
      - It involves creating data structures that provide fast access to rows in a table.
      - Indexes are typically based on the values in one or more columns.
  - How Indexes Work 
      - Indexes are like an ordered list of values with pointers to the actual rows in the table.
      - They work by allowing the database engine to quickly locate the desired rows without the need to scan the entire table.
  - Indexes & Range Queries 
      - Indexes are particularly useful for speeding up range queries (e.g., WHERE clauses with greater than, less than, or between conditions).
      - They allow the database to jump directly to the relevant range of values.
  - Pros & Cons of Indexing:
      - Pros:
          - Faster data retrieval for specific queries.
          - Improved query performance.
          - Supports constraints (unique, primary key).
      - Cons:
          - Increased storage space.
          - Slower data modification (INSERT, UPDATE, DELETE).
          - Maintenance overhead.
  - Indexes on Multiple Columns 
      - Composite indexes involve creating an index on multiple columns.
      - They can improve performance for queries that involve conditions on multiple columns.
      - The order of columns in the index matters, affecting query optimization.
  - Indexing on Strings 
      - Indexes can be applied to string (VARCHAR, CHAR) columns.
      - Full-text indexes are used for complex text search operations.
      - B-tree indexes work well for prefix-based string searches.
  - How to Create Indexes in SQL 
      - SQL provides the CREATE INDEX statement to create indexes on one or more columns.
      - Example: CREATE INDEX index_name ON table_name (column1, column2);
  - Data Structure Used for Indexing 
      - B-tree (Balanced Tree) and its variations are commonly used data structures for indexing.
      - Hash indexes are used for exact matching queries but not range queries.
      - Bitmap indexes are useful for low-cardinality data.
      - Full-text search indexes are designed for text-based searches.
<!-- TOC --><a name="problem-set-3"></a>
### Problem Set
  - Q1. Indexing - 1 
      - In a B-Tree index structure, what does the 'B' stand for? Balanced 
  - Q2. Indexing - 2 
      - In which of the following scenarios is a Hash Index most beneficial? When you need to perform exact match queries 
  - Q3. Indexing - 3 
      - How is the Full-Text Index in MySQL different from other indexes? It is optimized for searching large text fields  
  - Q4. Indexing - 4 
      - Which of the following statements is true about indexes in MySQL? Indexes slow down UPDATE and INSERT operations but speed up SELECT queries 
  - Q5. Indexing - 5 
      - Which type of index would NOT store the indexed data in sorted order? Hash Index
  - Q6. Indexing - 6
      - In MySQL, what does the keyword "EXPLAIN" do before a SELECT query? It provides information about the query execution plan, including how indexes are used 

<!-- TOC --><a name="references-1"></a>
### References
  - gist.github.com/jboner/2841832 

<!-- TOC --><a name="sql-10-transactions-i"></a>
## SQL 10: Transactions - I

- 1. What are Transactions?
    - A transaction in SQL is a sequence of one or more SQL statements that are executed as a single unit of work. Transactions are used to group multiple SQL operations into a single logical operation. The primary purpose of transactions is to ensure data consistency and integrity by maintaining the ACID (Atomicity, Consistency, Isolation, Durability) properties.
    - Example:
        - Suppose you want to transfer money from one bank account to another. A transaction in this context would include deducting the money from one account and adding it to another. If any part of this operation fails, the entire transaction should be rolled back to ensure that neither account is left in an inconsistent state.
- 2. Properties of Transactions
    - Transactions have the following properties:
        - Atomicity: A transaction is atomic, meaning it is treated as a single, indivisible unit. It either succeeds entirely, or it has no effect at all. If any part of the transaction fails, the entire transaction is rolled back.
        - Consistency: Transactions bring the database from one consistent state to another. This means that the integrity constraints and rules defined for the database must be maintained throughout the transaction.
        - Isolation: Transactions are executed in isolation from each other. Each transaction must appear to be the only operation occurring in the database, even when multiple transactions are running concurrently.
        - Durability: Once a transaction is committed, its changes are permanent and survive system failures. The changes should be durable, even in the face of power outages or crashes.
- 3. How Transactions Work?
    - Transactions are managed using the following SQL commands:
        - BEGIN TRANSACTION (or simply BEGIN or START TRANSACTION): This command starts a new transaction. All the SQL statements following this command are part of the transaction until it is explicitly committed or rolled back.
        - COMMIT: This command is used to save the changes made during a transaction. If no errors occur during the transaction, you can commit it, making the changes permanent.
        - ROLLBACK: If an error occurs or you want to undo a transaction, you can use the ROLLBACK command to revert all the changes made during the transaction.
- 4. Commits
    - A COMMIT statement is used to make the changes within a transaction permanent. Once a transaction is committed, the changes are saved to the database and become visible to other transactions. If any part of the transaction fails or an error occurs, you should not commit the transaction to ensure data consistency.
- 5. Rollbacks
    - A ROLLBACK statement is used to undo all the changes made within a transaction. If any part of the transaction fails or an error occurs, you can roll back the transaction to ensure that the database remains in a consistent state. Rollbacks are essential for error recovery.
- In summary, transactions are fundamental to maintaining data integrity in SQL databases. They ensure that multiple SQL operations are executed as a single, consistent unit, and provide mechanisms for committing or rolling back changes to maintain data integrity. 

<!-- TOC --><a name="sql-10-transactions-ii"></a>
## SQL 10: Transactions - II

- Concurrency 
    - Concurrency is the ability of a database management system (DBMS) to handle multiple transactions simultaneously, allowing users to perform operations concurrently without interfering with each other.
    - Concurrency control mechanisms ensure that transactions execute in a way that maintains data consistency and integrity.
    - Types of Concurrency Problems: 
        - 1. Lost Updates:
            - Description: Lost Updates occur when multiple transactions attempt to update the same data simultaneously, resulting in one update being lost. This happens when one transaction overwrites the changes made by another, leading to data loss.
            - Example:
                - Transaction A reads data.
                - Transaction B reads the same data.
                - Transaction A updates the data.
                - Transaction B updates the data, overwriting Transaction A's changes.
        - 2. Dirty Reads:
            - Description: Dirty Reads occur when one transaction reads data modified by another uncommitted transaction. This can lead to inaccuracies as the uncommitted changes may be rolled back.
            - Example:
                - Transaction A updates data.
                - Transaction B reads the uncommitted data updated by Transaction A.
                - If Transaction A fails and is rolled back, Transaction B read uncommitted and inaccurate data.
        - 3. Non-Repeatable Reads:
            - Description: Non-Repeatable Reads happen when a transaction reads the same data multiple times, and another transaction modifies the data between the reads. This can result in data inconsistency within a single transaction.
            - Example:
                - Transaction A reads data.
                - Transaction B updates the data.
                - Transaction A reads the data again and notices a change, which can lead to inconsistency.
        - These concurrency problems highlight the challenges that can arise when multiple transactions access and modify data simultaneously in a database system. Addressing these issues often requires careful consideration of isolation levels and concurrency control mechanisms to balance data consistency and performance.
- Isolation Levels 
    - Isolation levels define the degree to which one transaction must be isolated from the effects of other concurrent transactions. SQL databases offer different isolation levels to control the visibility of changes made by one transaction to other concurrent transactions.
    - Types of Isolation Levels 
        - 1. Read Uncommitted:
            - Description: The Read Uncommitted isolation level is the lowest level of isolation. In this mode, transactions can read uncommitted changes made by other transactions. It provides the least protection against concurrency issues but offers high concurrency. It allows dirty reads, non-repeatable reads, and phantom reads.
            - Advantages:
                - High concurrency, allowing multiple transactions to access and modify data simultaneously.
            - Disadvantages:
                - Dirty Reads: Transactions can read uncommitted changes made by other transactions, potentially leading to incorrect data.
            - Example: 
                - Transaction A reads the current balance of a bank account (balance = $100).
                - Transaction B updates the balance to $150 but has not committed the change.
                - Transaction A reads the balance again, mistakenly seeing the uncommitted balance of $150, resulting in a dirty read.
            - Real-Life Use Cases:
                - Real-time analytics where data accuracy is not critical, and high concurrency is essential.
                - Caching systems that can quickly update data with minimal concerns about accuracy.
        - 2. Read Committed:
            - Description: In the Read Committed isolation level, transactions can only read committed changes made by other transactions. It prevents dirty reads but still allows non-repeatable reads and phantom reads. It offers a balance between data consistency and concurrency.
            - Advantages:
                - Prevents Dirty Reads: Transactions can only read committed changes, ensuring data accuracy.
                - Balances concurrency and data consistency.
            - Disadvantages:
                - Non-Repeatable Reads and Phantom Reads: It still allows non-repeatable reads and phantom reads, which may impact certain applications.
            - Example:  
                - Transaction A reads the current price of a product (price = $50).
                - Transaction B updates the price to $60 and commits the change.
                - Transaction A reads the price again and sees the new value of $60, demonstrating a non-repeatable read.
            - Real-Life Use Cases:
                - Typical choice for applications where data consistency is important, and moderate concurrency is acceptable.
                - E-commerce systems ensuring users can only see committed changes.
        - 3. Repeatable Read (MySQL Default): 
            - Description: The Repeatable Read isolation level ensures a transaction will not see any changes made by other transactions during its execution. It prevents dirty reads and non-repeatable reads but still allows phantom reads. It provides a higher level of data consistency but may impact concurrency.
            - Advantages:
                - Prevents Dirty Reads and Non-Repeatable Reads: Ensures that transactions will not see changes made by other transactions during their execution.
                - High data consistency.
            - Disadvantages:
                - Phantom Reads: May still encounter phantom reads, impacting applications sensitive to data stability.
            - Example: 
                - Transaction A retrieves a list of available hotel rooms in a specific location.
                - Transaction B books one of the rooms, reducing the availability.
                - Transaction A retrieves the list again, finding a different number of available rooms, demonstrating a phantom read.
            - Real-Life Use Cases:
                - Inventory management systems where stock levels must remain consistent during a transaction.
                - Booking systems where reservations must be maintained throughout a transaction.
        - 4. Serializable:
            - Description: Serializable is the highest isolation level, ensuring complete isolation between transactions. It prevents all types of concurrency problems but can result in performance issues due to locking. It provides the highest level of data consistency but can be the least concurrent.
            - Advantages:
                - Ensures Complete Isolation: Provides the highest level of data consistency by preventing all types of concurrency issues.
            - Disadvantages:
                - Low Concurrency: Can lead to performance issues due to locking and reduced concurrency.
            - Example:  
                - Transaction A books a seat on a flight by acquiring an exclusive lock on it.
                - While Transaction A is in progress, no other transaction can access or book that seat.
                - This demonstrates the high level of isolation provided by Serializable, with the disadvantage of potentially blocking other transactions.
            - Real-Life Use Cases:
                - Financial systems processing transactions, ensuring complete data integrity and preventing double-spending.
                - Reservation systems for critical applications like airline booking, guaranteeing no double-bookings or overbooking.
        - The choice of isolation level should be driven by the specific requirements of your application. Consider factors such as the importance of data consistency, the volume of concurrent transactions, and the trade-offs between data accuracy and performance when selecting the appropriate isolation level for your database.
- Locks 
    - Locks: 
        - Description: Locks are mechanisms used in a database management system to control access to data and ensure the integrity of transactions in a multi-user environment. Locks are employed to prevent conflicts and maintain data consistency when multiple transactions attempt to read, modify, or write data simultaneously.
    - Types of Locks:
        - 1. Shared Lock (S-Lock):
            - Description: Shared locks allow multiple transactions to read data simultaneously, but they block any transactions attempting to modify the data until the shared lock is released.
            - Use Case: Useful when multiple transactions need to read the same data concurrently without the risk of modification conflicts.
        - 2. Exclusive Lock (X-Lock):
            - Description: Exclusive locks prevent other transactions from accessing the locked data, both for reading and writing, until the exclusive lock is released.
            - Use Case: Applied when a transaction needs to modify data and wants to ensure that no other transaction can access the data until the modification is completed.
        - 3. Intent Lock:
            - Description: Intent locks signal the intent of a transaction to acquire shared or exclusive locks on related resources. They help avoid conflicts between shared and exclusive locks.
            - Use Case: Used to indicate the future locking intentions of a transaction on higher-level resources, such as tables or pages.
        - 4. Schema Modification Lock (Sch-M Lock):
            - Description: Schema modification locks prevent other transactions from modifying the schema of a database, such as altering tables or adding columns.
            - Use Case: Essential for ensuring the consistency of database structures during schema changes.
        - 5. Bulk Update Lock (BU Lock):
            - Description: Bulk update locks are used in situations where multiple transactions may need to update the same set of rows in a table concurrently. These locks allow multiple transactions to read the data but prevent updates.
            - Use Case: Commonly used in data warehousing environments where large volumes of data are updated.
        - 6. Key-Range Lock:
            - Description: Key-range locks restrict access to a range of data within a table, allowing multiple transactions to access data outside the locked range.
            - Use Case: Useful for scenarios where transactions need to access specific ranges of data without interference from other transactions.
    - Locks play a crucial role in maintaining data integrity and controlling concurrent access to a database. The choice of lock type depends on the specific requirements of transactions and the potential for conflicts in a multi-user database environment.
- Deadlocks 
    - A deadlock is a situation where two or more transactions are unable to proceed because each holds a resource needed by the other. 
    - It results in a standstill where no progress can be made.

<!-- TOC --><a name="sql-11-schema-design-i-this-will-be-updated-soon"></a>
## SQL 11: Schema Design - I 🚧 (This will be updated soon)

<!-- TOC --><a name="sql-12-schema-design-i-this-will-be-updated-soon"></a>
## SQL 12: Schema Design  - I 🚧 (This will be updated soon)
