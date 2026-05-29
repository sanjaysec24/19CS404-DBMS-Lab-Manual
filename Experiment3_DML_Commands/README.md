# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**

<img width="836" height="255" alt="image" src="https://github.com/user-attachments/assets/36afce62-fac3-4067-889b-b55dc7906ea8" />

```
UPDATE Products
SET sell_price =sell_price*1.10
WHERE category='Bakery'
```

**Output:**

<img width="1246" height="410" alt="image" src="https://github.com/user-attachments/assets/01fc1515-378a-4f13-bbe2-5b21ef4961d4" />



**Question 2**

<img width="1126" height="455" alt="image" src="https://github.com/user-attachments/assets/2059a261-6e1b-4933-a671-18276442ecde" />

```
UPDATE PRODUCTS
SET reorder_lvl = reorder_lvl* 0.7
WHERE product_name LIKE '%cream%' AND quantity>reorder_lvl
```

**Output:**

<img width="1247" height="389" alt="image" src="https://github.com/user-attachments/assets/6c9bc114-1fd7-4d47-976e-71d36e0d787a" />


**Question 3**

<img width="625" height="168" alt="image" src="https://github.com/user-attachments/assets/b148f53d-3ec9-4a91-8796-5cf5f9907f1e" />


```
UPDATE products
SET availability=availability*2
WHERE  product_id = 1
```

**Output:**

<img width="1246" height="167" alt="image" src="https://github.com/user-attachments/assets/3a1a2224-ba70-4fb3-8909-2336692e8c75" />


**Question 4**

<img width="1062" height="467" alt="image" src="https://github.com/user-attachments/assets/1b4963a2-cf89-4638-9929-0dcb8c9aa67a" />

```
UPDATE Employees
SET salary=8000
WHERE employee_id=105
```

**Output:**

<img width="1250" height="177" alt="image" src="https://github.com/user-attachments/assets/7b96af46-b2b1-4ca1-854a-d69d75bcb6ec" />



**Question 5**

<img width="1268" height="220" alt="image" src="https://github.com/user-attachments/assets/78ee1afe-f7b2-43e6-9a9d-8673db9b3499" />


```
DELETE FROM customer
WHERE GRADE != 3
```

**Output:**

<img width="908" height="418" alt="image" src="https://github.com/user-attachments/assets/2f886eeb-c6e1-4cb9-a53a-9a964acd6f94" />


**Question 6**

<img width="708" height="436" alt="image" src="https://github.com/user-attachments/assets/fa28fcda-5b53-4904-a211-af44b5068d87" />

```
DELETE FROM Doctors 
WHERE last_name IS NULL
```

**Output:**

<img width="1078" height="554" alt="image" src="https://github.com/user-attachments/assets/097dd0ef-67d9-4324-b838-36a6a3078709" />


**Question 7**

<img width="1272" height="376" alt="image" src="https://github.com/user-attachments/assets/8f924e1b-1912-4da5-9d95-865b8b18f07d" />


```
DELETE FROM customer 
WHERE CUST_COUNTRY NOT IN ('India', 'USA')
```

**Output:**

<img width="1246" height="426" alt="image" src="https://github.com/user-attachments/assets/98074176-07b2-4349-acb7-b877e1c5cad4" />


**Question 8**

<img width="818" height="366" alt="image" src="https://github.com/user-attachments/assets/bb145bd5-7719-4f5b-a685-2c07f0fe7ffb" />


```
SELECT * FROM EmployeePosition
ORDER BY SALARY DESC LIMIT 3
```

**Output:**

<img width="1034" height="203" alt="image" src="https://github.com/user-attachments/assets/dd64c0be-3ee3-4f90-8009-cd00c968c7c5" />


**Question 9**

<img width="757" height="434" alt="image" src="https://github.com/user-attachments/assets/313246bf-cc64-4f1c-872b-f1f412ec55ad" />


```
SELECT patient_id,first_name,admission_date,discharge_date FROM Patients
WHERE admission_date =  discharge_date
```

**Output:**

<img width="1246" height="263" alt="image" src="https://github.com/user-attachments/assets/e6ec960c-2c70-4529-b2db-6ff88a242c48" />


**Question 10**

<img width="1269" height="474" alt="image" src="https://github.com/user-attachments/assets/d2f74cb0-af91-434a-9b62-9e39c38da2a3" />


```
SELECT * FROM orders
WHERE purch_amt BETWEEN 500 AND 4000 AND purch_amt NOT IN (948.50,1983.43)
```

**Output:**

<img width="1248" height="292" alt="image" src="https://github.com/user-attachments/assets/2cb85b8e-876f-48a9-85ea-b0d8a66d4587" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
