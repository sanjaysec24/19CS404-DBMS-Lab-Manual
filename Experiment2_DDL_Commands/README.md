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


<img width="1270" height="304" alt="image" src="https://github.com/user-attachments/assets/1a0c8e54-7e95-4511-921b-5b66b878a1b1" />

## Program 
```
CREATE TABLE Bonuses(
BonusID INT PRIMARY KEY,
EmployeeID INT,
BonusAmount REAL CHECK(BonusAmount>0),
BonusDate DATE,
Reason TEXT NOT NULL
);
```

**Output:**


<img width="1289" height="292" alt="image" src="https://github.com/user-attachments/assets/463c516b-8b6a-4cb5-b053-f94623d0bfab" />


**Question 2**


<img width="920" height="199" alt="image" src="https://github.com/user-attachments/assets/b83b12be-8512-4ce9-8f56-1f78cb813813" />

## Program 
```
INSERT INTO Products(ProductID,Name,Category,Price,Stock)
VALUES(101,'Laptop','Electronics',1500,50);

```

**Output:**


<img width="1243" height="174" alt="image" src="https://github.com/user-attachments/assets/c33718ef-a25e-4078-a3a2-b8b0dc54f81a" />


**Question 3**

<img width="850" height="355" alt="image" src="https://github.com/user-attachments/assets/baf6816d-0e35-412b-a80d-d51b7bb1f182" />

## Program 
```
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INT NOT NULL,
icom_id TEXT(4),
FOREIGN KEY (icom_id) REFERENCES company(com_id)
ON UPDATE CASCADE
ON DELETE CASCADE
);
```

**Output:**

<img width="1256" height="260" alt="image" src="https://github.com/user-attachments/assets/b1397ab8-35c5-4fd7-9d68-a734b4916001" />

**Question 4**


<img width="1152" height="250" alt="image" src="https://github.com/user-attachments/assets/99baf423-34d6-4860-ad27-72e3f2025a59" />

## Program 
```
CREATE TABLE ProjectAssignments(
AssignmentID INT PRIMARY KEY,
EmployeeID INT,
ProjectID INT,
AssignmentDate DATE NOT NULL,
FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)
);
```

**Output:**

<img width="1246" height="211" alt="image" src="https://github.com/user-attachments/assets/e0262cce-e522-4e84-b0f6-6574b7292508" />


**Question 5**


<img width="796" height="266" alt="image" src="https://github.com/user-attachments/assets/49bcf1eb-fccd-42b7-8e8f-52d5e24c20eb" />

## Program 
```
INSERT INTO Books(ISBN,Title,Author,Publisher,YearPublished)
SELECT  ISBN, Title, Author, Publisher, YearPublished
FROM  Out_of_print_books;
```

**Output:**

<img width="1238" height="220" alt="image" src="https://github.com/user-attachments/assets/49d9e072-40b8-4658-b8c3-de1ce952d454" />


**Question 6**


<img width="754" height="313" alt="image" src="https://github.com/user-attachments/assets/e5086602-aeee-44c9-9e55-59c924455940" />

## Program 
```
CREATE TABLE Events(
EventID INTEGER,
EventName TEXT,
EventDate DATE
);
```

**Output:**


<img width="1245" height="294" alt="image" src="https://github.com/user-attachments/assets/d03bb893-f714-4852-a055-a6b174a272a7" />


**Question 7**


<img width="1257" height="396" alt="image" src="https://github.com/user-attachments/assets/d58a95ff-2a88-4254-b6ef-6068e3fcc91c" />

## Program 
```
INSERT INTO Products(ProductID,Name,Category,Price,Stock)
VALUES(106,'Fitness Tracker','Wearables',NULL,NULL);
INSERT INTO Products(ProductID,Name,Category,Price,Stock)
VALUES(107,'Laptop','Electronics',999.99,50);
INSERT INTO Products(ProductID,Name,Category,Price,Stock)
VALUES(108,'Wireless Earbuds','Accessories',NULL,100);
```

**Output:**


<img width="1244" height="201" alt="image" src="https://github.com/user-attachments/assets/a2c5bbb2-560a-49d9-877c-281c827cd94b" />


**Question 8**


<img width="846" height="467" alt="image" src="https://github.com/user-attachments/assets/c679ba58-a4c5-438a-864d-ec4724a022de" />

## Program 
```
ALTER TABLE Companies ADD COLUMN designation varchar(50);
ALTER TABLE Companies ADD COLUMN net_salary number;
ALTER TABLE Companies ADD COLUMN dob date;
```

**Output:**


<img width="1247" height="321" alt="image" src="https://github.com/user-attachments/assets/55f94030-f010-4c9b-875d-8fff0795f06a" />


**Question 9**


<img width="1258" height="197" alt="image" src="https://github.com/user-attachments/assets/ea02c01d-8d5b-4003-ad8c-e20159a95511" />

## Program 
```
CREATE TABLE jobs(
job_id INT,
job_title TEXT DEFAULT '',
min_salary INT DEFAULT 8000,
max_salary INT DEFAULT NULL);
```

**Output:**


<img width="1249" height="252" alt="image" src="https://github.com/user-attachments/assets/87312ee4-a490-4d5e-b19e-9dd1abf97ef6" />


**Question 10**


<img width="1210" height="182" alt="image" src="https://github.com/user-attachments/assets/1b46d852-57e2-42c4-94e3-90849a9fc194" />

## Program 
```
ALTER TABLE Student_details ADD COLUMN Email VARCHAR(50);
ALTER TABLE Student_details ADD COLUMN MARKS INT DEFAULT 0;
```

**Output:**


<img width="1246" height="183" alt="image" src="https://github.com/user-attachments/assets/8e52bdd3-279b-49fc-a225-8ba783a11b24" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
