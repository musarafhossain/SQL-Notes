# SQL Notes  
## Chapter 1: Introduction to SQL  

### 1.1 What is SQL?  
SQL (Structured Query Language) is a domain-specific language used to manage and manipulate relational databases. It allows users to create, read, update, and delete (CRUD) data stored in structured formats. SQL is widely used in applications, analytics, and data-driven decision-making.  

### 1.2 Features of SQL  
- **Declarative Language:** Users specify what they want, and the database engine determines how to get it.  
- **Standardized Language:** Follows ANSI and ISO standards.  
- **Data Manipulation & Retrieval:** Allows querying and modification of data.  
- **Data Integrity & Security:** Supports constraints, transactions, and access control.  
- **Scalability:** Used in small applications as well as large enterprise databases.  

### 1.3 Types of SQL Commands  
SQL commands are categorized into five types:  

1. **Data Definition Language (DDL)** – Defines database structure.  
   - `CREATE` – Creates a new table or database.  
   - `ALTER` – Modifies an existing database structure.  
   - `DROP` – Deletes a table or database.  
   - `TRUNCATE` – Removes all records from a table without logging individual row deletions.  

2. **Data Manipulation Language (DML)** – Deals with data modification.  
   - `INSERT` – Adds new records.  
   - `UPDATE` – Modifies existing records.  
   - `DELETE` – Removes specific records.  

3. **Data Query Language (DQL)** – Used to retrieve data.  
   - `SELECT` – Fetches data from one or more tables.  

4. **Data Control Language (DCL)** – Manages access permissions.  
   - `GRANT` – Gives privileges to users.  
   - `REVOKE` – Removes privileges from users.  

5. **Transaction Control Language (TCL)** – Manages transactions.  
   - `COMMIT` – Saves changes permanently.  
   - `ROLLBACK` – Reverts changes.  
   - `SAVEPOINT` – Sets a savepoint in a transaction to rollback partially.  

### 1.4 Relational Database Concepts  
A **Relational Database Management System (RDBMS)** stores data in a structured format using tables, relationships, and constraints.  

- **Table (Relation):** Collection of related data organized in rows and columns.  
- **Row (Record/Tuple):** A single entry in a table.  
- **Column (Attribute):** A specific field in a table.  
- **Primary Key:** A unique identifier for each row.  
- **Foreign Key:** A column that establishes a relationship between two tables.  

### 1.5 Basic SQL Syntax  
#### 1.5.1 Creating a Database  
```sql
CREATE DATABASE School;
```
#### 1.5.2 Creating a Table  
```sql
CREATE TABLE Students (
    ID INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT,
    Grade VARCHAR(10)
);
```
#### 1.5.3 Inserting Data  
```sql
INSERT INTO Students (ID, Name, Age, Grade) 
VALUES (1, 'John Doe', 15, '10th');
```
#### 1.5.4 Retrieving Data  
```sql
SELECT * FROM Students;
```
#### 1.5.5 Updating Data  
```sql
UPDATE Students 
SET Age = 16 
WHERE ID = 1;
```
#### 1.5.6 Deleting Data  
```sql
DELETE FROM Students 
WHERE ID = 1;
```

### 1.6 Popular RDBMS  
- **MySQL** – Open-source and widely used.  
- **PostgreSQL** – Advanced open-source database.  
- **Microsoft SQL Server** – Enterprise-level solution.  
- **Oracle Database** – High-performance database for large applications.  
- **SQLite** – Lightweight and file-based database.  

### 1.7 Advantages of SQL  
- **Easy to Learn:** Simple and intuitive commands.  
- **High Performance:** Optimized query execution.  
- **Secure:** Supports authentication and authorization.  
- **Scalable:** Used for small applications to large enterprise databases.  
- **Interoperable:** Works with multiple programming languages and tools.  

---