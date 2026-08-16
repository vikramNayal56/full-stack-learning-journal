# MySQL, SQL, Database & ORM

A database is used to store, manage, retrieve, and update data efficiently. MySQL is a relational database system that stores data in tables and allows related tables to be connected.

---

# 📌 What is Data?

Data is a collection of facts or information that can be stored, processed, and managed.

### Examples

* Name
* Age
* Email
* Phone Number
* Salary

---

# 🗃️ What is a Database?

A database is an organized collection of data that allows us to **store, retrieve, update, and delete** information efficiently.

Instead of keeping large amounts of data in files or notebooks, databases provide a structured way to manage it.

### Example

A college database may store:

* Students
* Teachers
* Courses
* Marks

---

# 💾 Types of Data

## 1. Structured Data

Structured data is organized in **rows and columns** and follows a fixed format.

### Examples

* Student records
* Employee details
* Bank transactions

---

## 2. Unstructured Data

Unstructured data does not follow a fixed format.

### Examples

* Images
* Videos
* Audio files
* PDFs
* Social media posts

---

# 🏢 What is DBMS?

DBMS stands for **Database Management System**.

It is software used to create, store, update, retrieve, and manage databases.

### Responsibilities

* Store data
* Retrieve data
* Update records
* Delete records
* Manage security

### Examples

* MySQL
* PostgreSQL
* Oracle
* SQL Server

---

# 🏛️ What is RDBMS?

RDBMS stands for **Relational Database Management System**.

It stores data in **tables consisting of rows and columns**.

Different tables can be connected using relationships.

### Example

**Students Table**

| ID | Name  |
| -- | ----- |
| 1  | Rahul |

**Courses Table**

| Student_ID | Course     |
| ---------- | ---------- |
| 1          | JavaScript |

Here, both tables are connected using `Student_ID`.

---

# 🆚 File System vs Database

Imagine storing all college data in a single Excel or Notepad file.

### Problems with Plain Files

* Multiple people editing the same file can cause data loss.
* Searching through thousands of records can be slow.
* There are no strong built-in rules to prevent invalid or duplicate data.
* A crash during writing can corrupt the file.

### Advantages of a Database

* Handles multiple users reading and writing data safely.
* Can quickly search through large amounts of data using indexing.
* Allows rules such as `NOT NULL` and `UNIQUE`.
* Helps maintain data consistency.

### In Short

**File** → Like maintaining one notebook manually.

**Database** → Like an organized filing system with rules and fast searching.

---

# ⚙️ MySQL Setup

I used:

* **MySQL Server** → Actual database engine that stores and manages data.
* **MySQL Workbench** → GUI tool used to write SQL queries and view tables.

---

# 🏗️ Database Structure

A database can be understood as a hierarchy:

```text
Server
 └── Database
      └── Table
           └── Row
```

* One server can contain multiple databases.
* One database can contain multiple tables.
* One table can contain multiple rows.
* A row represents a single record.

---

# 🗄️ Creating a Database

```sql
CREATE DATABASE resume_db;

USE resume_db;
```

### Explanation

* `CREATE DATABASE` → Creates a new database.
* `USE` → Selects the database we want to work with.

---

# 📋 Creating a Table

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE
);
```

### Syntax Breakdown

| Part                 | Purpose                             |
| -------------------- | ----------------------------------- |
| `CREATE TABLE users` | Creates a table named `users`       |
| `id INT`             | Stores whole numbers                |
| `AUTO_INCREMENT`     | Automatically generates the next ID |
| `PRIMARY KEY`        | Uniquely identifies each row        |
| `VARCHAR(100)`       | Stores text up to 100 characters    |
| `NOT NULL`           | Value cannot be empty               |
| `UNIQUE`             | Prevents duplicate values           |

---

# ➕ Inserting Data

```sql
INSERT INTO users (name, email)
VALUES ('Gaurav', 'gaurav@mail.com');
```

Because `id` uses `AUTO_INCREMENT`, we don't need to manually provide the ID.

---

# 🔍 Reading Data

### Select Everything

```sql
SELECT * FROM users;
```

Returns all columns and all rows from the `users` table.

### Select a Specific Record

```sql
SELECT * FROM users
WHERE id = 1;
```

`WHERE` is used to filter the results.

---

# 🔑 Primary Key

A **PRIMARY KEY** uniquely identifies each row in a table.

Example:

```sql
id INT AUTO_INCREMENT PRIMARY KEY
```

### Important Points

* Each row has a unique ID.
* Duplicate primary key values are not allowed.
* A primary key helps MySQL search records efficiently.

---

# 🔗 Foreign Key

A **FOREIGN KEY** connects one table to another table.

Example:

```sql
CREATE TABLE resumes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    userId INT,
    title VARCHAR(100),
    FOREIGN KEY (userId) REFERENCES users(id)
);
```

Here:

```text
resumes.userId → users.id
```

The foreign key ensures that the `userId` in the `resumes` table refers to an existing user.

### Primary Key vs Foreign Key

| Key           | Purpose                                    |
| ------------- | ------------------------------------------ |
| `PRIMARY KEY` | Uniquely identifies a row in its own table |
| `FOREIGN KEY` | Connects to a primary key in another table |

---

# 🔗 SQL JOINs

A **JOIN** combines data from related tables into a single result.

Example:

```sql
SELECT users.name, resumes.title
FROM resumes
JOIN users
ON resumes.userId = users.id;
```

This retrieves the user's name along with their resume title.

---

## Types of JOINs

| Join              | Purpose                                                               |
| ----------------- | --------------------------------------------------------------------- |
| `INNER JOIN`      | Returns only matching rows from both tables                           |
| `LEFT JOIN`       | Returns all rows from the left table and matching rows from the right |
| `RIGHT JOIN`      | Returns all rows from the right table and matching rows from the left |
| `FULL OUTER JOIN` | Returns all rows from both tables                                     |

### Easy Way to Remember

* **INNER JOIN** → Only common/matching data
* **LEFT JOIN** → Keep everything from the left
* **RIGHT JOIN** → Keep everything from the right
* **FULL JOIN** → Keep everything from both sides

> MySQL does not directly support `FULL OUTER JOIN`; it requires a workaround.

---

# ⚡ Indexing

An **index** helps MySQL find data faster.

It works like the index of a textbook. Instead of checking every page, you can directly jump to the required information.

### Without Index

MySQL may need to check rows one by one.

This is called a **full table scan**.

### With Index

MySQL can find matching records much faster.

A `PRIMARY KEY` automatically creates an index.

Indexes can also be added to frequently searched columns such as `email`.

### Trade-off

Indexes make **searching faster**, but they can slightly slow down:

* `INSERT`
* `UPDATE`

This happens because MySQL also needs to update the index when data changes.

---

# 🌐 Database Languages

Database languages are used to communicate with databases.

Main categories:

* DDL
* DML
* DQL
* DCL
* TCL

---

# 💻 What is SQL?

SQL stands for **Structured Query Language**.

It is used to communicate with relational databases.

Using SQL, we can:

* Create databases
* Create tables
* Insert data
* Update data
* Delete data
* Retrieve data

---

# ⚡ SQL Commands

## DDL — Data Definition Language

Used to define the structure of a database.

### Commands

* `CREATE`
* `ALTER`
* `DROP`
* `TRUNCATE`

---

## DML — Data Manipulation Language

Used to modify data.

### Commands

* `INSERT`
* `UPDATE`
* `DELETE`

---

## DQL — Data Query Language

Used to retrieve data.

### Command

* `SELECT`

---

## DCL — Data Control Language

Used to manage permissions.

### Commands

* `GRANT`
* `REVOKE`

---

## TCL — Transaction Control Language

Used to manage transactions.

### Commands

* `COMMIT`
* `ROLLBACK`
* `SAVEPOINT`

---

# 🧩 MySQL Data Types

Choosing the correct data type helps improve storage efficiency and performance.

---

## VARCHAR

Stores variable-length text.

```sql
name VARCHAR(100)
```

### Suitable For

* Names
* Emails
* Addresses

---

## TEXT

MySQL does not use `STRING` as a data type. Instead, it provides `TEXT` types for longer text.

```sql
description TEXT
```

### Used For

* Long descriptions
* Articles
* Comments

---

## BOOLEAN

Stores `TRUE` or `FALSE` values.

```sql
isActive BOOLEAN
```

MySQL internally represents Boolean values using numeric values:

```text
TRUE  → 1
FALSE → 0
```

---

## TINYINT

Stores small integer values.

### Signed Range

```text
-128 to 127
```

### Unsigned Range

```text
0 to 255
```

Example:

```sql
age TINYINT
```

---

## ENUM

Allows only predefined values.

```sql
gender ENUM('Male', 'Female', 'Other')
```

### Benefits

* Prevents invalid values.
* Saves storage.
* Keeps data consistent.

---

# ⚔️ SQL vs NoSQL

| SQL                      | NoSQL                                                   |
| ------------------------ | ------------------------------------------------------- |
| Stores data in tables    | Stores data in documents, key-value pairs, graphs, etc. |
| Fixed schema             | Flexible schema                                         |
| Uses SQL                 | Uses different query methods                            |
| Best for structured data | Good for semi/unstructured data                         |
| Supports joins           | Usually avoids joins                                    |
| MySQL, PostgreSQL        | MongoDB, Cassandra, Redis                               |

---

# ⚙️ What is ORM?

ORM stands for **Object Relational Mapping**.

It allows developers to work with database records using programming language objects instead of writing SQL manually.

### Using Sequelize

```javascript
User.findAll();
```

Instead of manually writing:

```sql
SELECT * FROM users;
```

The ORM converts the programming language operation into SQL.

---

# 🤔 If Sequelize Writes SQL, Why Learn SQL?

Sequelize is a tool, but SQL knowledge is still important.

### Reasons to Learn SQL

* Understand what happens behind the scenes.
* Write optimized queries.
* Debug database problems.
* Work with different relational databases.
* Perform complex joins and reports.
* Prepare for technical interviews.
* Work confidently on real-world backend projects.

A good backend developer should understand **both SQL and ORMs**.

---

# 📌 Quick Revision

* **Data** → Collection of facts or information
* **Database** → Organized collection of data
* **DBMS** → Software that manages databases
* **RDBMS** → Stores related data in tables
* **SQL** → Language used to communicate with relational databases
* **DDL** → Defines database structure
* **DML** → Modifies data
* **DQL** → Retrieves data
* **DCL** → Manages permissions
* **TCL** → Manages transactions
* **PRIMARY KEY** → Uniquely identifies a row
* **FOREIGN KEY** → Connects related tables
* **JOIN** → Combines data from multiple tables
* **INDEX** → Makes searching faster
* **VARCHAR** → Variable-length text
* **TEXT** → Long text
* **BOOLEAN** → True/False
* **TINYINT** → Small integer
* **ENUM** → Predefined values
* **SQL** → Structured and relational data
* **NoSQL** → Flexible/semi-structured data
* **ORM** → Lets developers work with databases using programming language objects
* **Sequelize** → JavaScript ORM for relational databases