# **Chapter 2: Data Types and Constraints**  

---

## **2.1 Introduction to Data Types**  
Every column in an SQL table must have a specific **data type**, which defines the kind of values that can be stored in it. Choosing the right data type is essential for performance, storage efficiency, and data integrity.  

### **2.1.1 Categories of SQL Data Types**  
SQL data types are mainly divided into the following categories:  

1. **Numeric Data Types**  
2. **Character/String Data Types**  
3. **Date and Time Data Types**  
4. **Boolean Data Type**  
5. **Large Object (LOB) Data Types**  

---

## **2.2 Numeric Data Types**  
Used to store numbers (integers, decimals, and floating-point values).  

| Data Type | Description | Example |
|-----------|------------|---------|
| `INT` | Integer (whole number) | `25` |
| `SMALLINT` | Smaller integer (uses less storage) | `1000` |
| `BIGINT` | Large integer values | `9876543210` |
| `DECIMAL(p, s)` | Fixed-point decimal | `DECIMAL(10,2) → 99999999.99` |
| `NUMERIC(p, s)` | Same as `DECIMAL`, ensures precision | `NUMERIC(8,3) → 12345.678` |
| `FLOAT(n)` | Floating-point number, less precision than DECIMAL | `3.14159` |
| `REAL` | Less precise floating point | `0.123456` |  

**Example: Creating a Table with Numeric Data Types**  
```sql
CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    Salary DECIMAL(10,2),
    Age SMALLINT
);
```

---

## **2.3 Character/String Data Types**  
Used to store text and alphanumeric characters.  

| Data Type | Description | Example |
|-----------|------------|---------|
| `CHAR(n)` | Fixed-length string (up to 255 characters) | `'ABC'` |
| `VARCHAR(n)` | Variable-length string (up to 65,535 characters) | `'Hello World'` |
| `TEXT` | Large text data, unlimited size (depends on DBMS) | `'This is a long text...'` |  

**Example: Creating a Table with String Data Types**  
```sql
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    Name VARCHAR(50),
    Address TEXT
);
```

---

## **2.4 Date and Time Data Types**  
Used to store dates, times, and timestamps.  

| Data Type | Description | Example |
|-----------|------------|---------|
| `DATE` | Stores only date (YYYY-MM-DD) | `'2025-02-03'` |
| `TIME` | Stores only time (HH:MI:SS) | `'14:30:00'` |
| `DATETIME` | Stores date and time (YYYY-MM-DD HH:MI:SS) | `'2025-02-03 14:30:00'` |
| `TIMESTAMP` | Stores date and time with automatic updates | `'2025-02-03 14:30:00'` |  

**Example: Creating a Table with Date and Time Data Types**  
```sql
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    OrderDate DATE,
    DeliveryTime TIME,
    CreatedAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

## **2.5 Boolean Data Type**  
- Some SQL databases (like PostgreSQL) support the `BOOLEAN` type (`TRUE` or `FALSE`).  
- In MySQL, `BOOLEAN` is stored as `TINYINT(1)`, where `0 = FALSE` and `1 = TRUE`.  

**Example: Creating a Table with Boolean Data Type**  
```sql
CREATE TABLE Users (
    UserID INT PRIMARY KEY,
    IsActive BOOLEAN DEFAULT TRUE
);
```

---

## **2.6 Large Object (LOB) Data Types**  
Used for storing large files such as images, videos, and documents.  

| Data Type | Description | Example |
|-----------|------------|---------|
| `BLOB` | Binary Large Object (images, videos) | - |
| `CLOB` | Character Large Object (large text data) | - |  

---

# **Constraints in SQL**  
Constraints are rules applied to table columns to ensure data accuracy and integrity.  

## **2.7 Types of Constraints in SQL**  

1. **PRIMARY KEY** – Ensures each row is uniquely identified.  
2. **FOREIGN KEY** – Establishes relationships between tables.  
3. **NOT NULL** – Prevents null (empty) values.  
4. **UNIQUE** – Ensures all values in a column are different.  
5. **CHECK** – Ensures values meet specific conditions.  
6. **DEFAULT** – Assigns a default value if no value is provided.  

---

## **2.8 PRIMARY KEY Constraint**  
A **Primary Key** is a unique identifier for a row. It must be **unique and NOT NULL**.  

**Example: Creating a Table with a Primary Key**  
```sql
CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT
);
```

---

## **2.9 FOREIGN KEY Constraint**  
A **Foreign Key** links two tables, ensuring referential integrity.  

**Example: Foreign Key in SQL**  
```sql
CREATE TABLE Departments (
    DeptID INT PRIMARY KEY,
    DeptName VARCHAR(50)
);

CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    Name VARCHAR(50),
    DeptID INT,
    FOREIGN KEY (DeptID) REFERENCES Departments(DeptID)
);
```

---

## **2.10 NOT NULL Constraint**  
Prevents a column from having `NULL` values.  

**Example: NOT NULL Constraint**  
```sql
CREATE TABLE Users (
    UserID INT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    Email VARCHAR(100) NOT NULL
);
```

---

## **2.11 UNIQUE Constraint**  
Ensures all values in a column are distinct.  

**Example: UNIQUE Constraint**  
```sql
CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    Email VARCHAR(100) UNIQUE
);
```

---

## **2.12 CHECK Constraint**  
Ensures values meet specific conditions.  

**Example: CHECK Constraint**  
```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Age INT CHECK (Age >= 18)
);
```

---

## **2.13 DEFAULT Constraint**  
Sets a default value for a column if no value is provided.  

**Example: DEFAULT Constraint**  
```sql
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    Status VARCHAR(20) DEFAULT 'Pending'
);
```

---

# **Summary of Chapter 2**  
- SQL provides various **data types** (Numeric, String, Date, Boolean, LOB).  
- **Constraints** ensure **data integrity** and **accuracy** in databases.  
- Common constraints include **PRIMARY KEY, FOREIGN KEY, NOT NULL, UNIQUE, CHECK, and DEFAULT**.  
- Choosing the right data type and constraints **improves performance and prevents errors**.  

---