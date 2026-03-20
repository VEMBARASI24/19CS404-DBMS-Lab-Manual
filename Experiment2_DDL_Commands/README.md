# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
<img width="944" height="429" alt="image" src="https://github.com/user-attachments/assets/144a6b60-aa0a-4df6-9969-d116b4934f04" />
```
INSERT INTO Student_details (RollNo, Name, Gender)
VALUES (204, 'Samuel Black', 'M');
```

**Output:**
<img width="1085" height="265" alt="image" src="https://github.com/user-attachments/assets/e7baebc0-be69-40ab-84b4-15af3e176316" />


**Question 2**
<img width="1222" height="363" alt="image" src="https://github.com/user-attachments/assets/c7cbecd5-be23-4c19-9a39-3e5b26f3957c" />

```
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL,
    Email VARCHAR(100) UNIQUE,
    Salary DECIMAL(10,2) CHECK (Salary > 0),
    DepartmentID INT,
    FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID)
);
```

**Output:**
<img width="1223" height="389" alt="image" src="https://github.com/user-attachments/assets/b0f64214-5c28-4523-8652-78123e0ba34a" />


**Question 3**
<img width="930" height="421" alt="image" src="https://github.com/user-attachments/assets/d9e11ff4-b2d1-4702-9277-eedd7dafa400" />
```
ALTER TABLE books
ADD COLUMN ISBN varchar(30);

ALTER TABLE books
ADD COLUMN domain_dept varchar(30);
```

**Output:**
<img width="1172" height="407" alt="image" src="https://github.com/user-attachments/assets/39714186-684c-4306-8f54-ee0d948f40e8" />


**Question 4**
<img width="866" height="412" alt="image" src="https://github.com/user-attachments/assets/b5b2b0b4-aa90-45f2-90f6-ef7bf99f4cb1" />
```CREATE TABLE Products (
    ProductID INTEGER,
    ProductName TEXT,
    Price REAL,
    Stock INTEGER
);
```

**Output:**
<img width="1191" height="338" alt="image" src="https://github.com/user-attachments/assets/1ed00dd8-6419-445f-8517-0beee03609d2" />


**Question 5**
<img width="1180" height="372" alt="image" src="https://github.com/user-attachments/assets/37716508-20d0-4702-ad29-d4529a3854c0" />
```
CREATE TABLE Attendance (
    AttendanceID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    AttendanceDate DATE,
    Status TEXT CHECK (Status IN ('Present', 'Absent', 'Leave')),
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
```

**Output:**
<img width="1204" height="336" alt="image" src="https://github.com/user-attachments/assets/b050083e-3a52-4080-ab72-75ed8eed498e" />


**Question 6**
<img width="1164" height="426" alt="image" src="https://github.com/user-attachments/assets/491befa5-1416-4597-8eb6-5884f96d88a1" />
```

ALTER TABLE Companies
RENAME COLUMN name TO first_name;

ALTER TABLE Companies
ADD COLUMN mobilenumber number;

ALTER TABLE Companies
ADD COLUMN DOB Date;
```

**Output:**
<img width="1234" height="419" alt="image" src="https://github.com/user-attachments/assets/37387554-5d35-4096-9d56-728a8dbef2de" />

**Question 7**
<img width="1118" height="226" alt="image" src="https://github.com/user-attachments/assets/b4db268e-76b2-4f8c-8062-2c03a4a630e7" />
```
INSERT INTO Customers (CustomerID, Name, Address, City, ZipCode)
VALUES (301, 'Michael Jordan', '123 Maple St', 'Chicago', 60616);
```
**Output:**
<img width="1241" height="296" alt="image" src="https://github.com/user-attachments/assets/8128cf45-5d86-4589-9c02-27c0b869e510" />


**Question 8**
<img width="1239" height="343" alt="image" src="https://github.com/user-attachments/assets/bea62a4b-4600-4052-bfca-f995557c5b80" />
```
CREATE TABLE Bonuses (
    BonusID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    BonusAmount REAL CHECK (BonusAmount > 0),
    BonusDate DATE,
    Reason TEXT NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
```
**Output:**
<img width="1228" height="309" alt="image" src="https://github.com/user-attachments/assets/7ac0e076-49b1-4a18-bd3b-2f2aab31434d" />


**Question 9**
<img width="1005" height="226" alt="image" src="https://github.com/user-attachments/assets/6cf61df7-3fa1-4d54-8183-bcefa15d4250" />
```
INSERT INTO Employee (EmployeeID, Name, Position, Department, Salary)
VALUES (001, 'Sarah Parker', 'Manager', 'HR', 60000);
```

**Output:**
<img width="1231" height="269" alt="image" src="https://github.com/user-attachments/assets/8509642d-9b58-4989-8786-c23befa86601" />


**Question 10**
<img width="855" height="371" alt="image" src="https://github.com/user-attachments/assets/6899aa42-c689-4c47-ad8c-025e62fc24d4" />
```
CREATE TABLE Orders (
    OrderID INTEGER,
    OrderDate TEXT,
    CustomerID INTEGER
);
```
**Output:**
<img width="1255" height="401" alt="image" src="https://github.com/user-attachments/assets/4bb3383c-e188-4405-892c-0fe1a4f9a110" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
