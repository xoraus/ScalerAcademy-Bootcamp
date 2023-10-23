# DBMS-Fundamentals
Exploring the core principles and concepts of Database Management Systems.


- [DBMS-Fundamentals](#dbms-fundamentals)
   * [SQL 1: Intro to DBMS ](#sql-1-intro-to-dbms)
   * [SQL 2: Keys](#sql-2-keys)
      + [Class Notes](#class-notes)
      + [SQL Lab](#sql-lab)
      + [Extra Notes](#extra-notes)
      + [Resources](#resources)
   * [SQL 3: CRUD - I](#sql-3-crud---i)
   * [SQL 4: CRUD - II](#sql-4-crud---ii)
   * [SOL 5: Joins - I](#sol-5-joins---i)
   * [SQL 6: Joins - II](#sql-6-joins---ii)
   * [SQL 7: Aggregate Queries](#sql-7-aggregate-queries)
   * [SQL 8: Subqueries and Views](#sql-8-subqueries-and-views)
   * [SQL 9: Indexing](#sql-9-indexing)
      + [Class Notes](#class-notes-1)
      + [Problem Set](#problem-set)
      + [References](#references)
   * [SQL 10: Transactions - I](#sql-10-transactions---i)
   * [SQL 10: Transactions - II](#sql-10-transactions---ii)
   * [SQL 11: Schema Design - I](#sql-11-schema-design---i)
   * [SQL 12: Schema Design • - I](#sql-12-schema-design----i)

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

## SQL 2: Keys
   
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

###  Resources
- GitHub Rep: https://github.com/rahulgrover99/Aug22Beg-SQL/blob/main/sql-1.md 
- String Functions: https://drive.google.com/file/d/1znbgY0xCCg1gKg2VBdbqEGb6sxmqZ-ud/view?usp=sharing
- Number Functions: https://drive.google.com/file/d/1jR1O-02BFZdWZNdrEvaG2ZZq9E9TlNaL/view?usp=sharing
- Data Types: https://drive.google.com/file/d/1GHeBM4nEB-CCZ3SMbRJxhjIwrZ_2TAZx/view?usp=drive_link

## SQL 3: CRUD - I

## SQL 4: CRUD - II

## SOL 5: Joins - I

## SQL 6: Joins - II

## SQL 7: Aggregate Queries

## SQL 8: Subqueries and Views

## SQL 9: Indexing

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

### References
  - gist.github.com/jboner/2841832 

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

## SQL 11: Schema Design - I

## SQL 12: Schema Design • - I
