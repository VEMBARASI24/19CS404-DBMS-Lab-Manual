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

<img width="820" height="408" alt="image" src="https://github.com/user-attachments/assets/d3c43a39-2144-493e-90db-2274bf605b16" />

```
UPDATE suppliers
SET supplier_name = UPPER(supplier_name)
WHERE contact_person LIKE '% Singh';
```

**Output:**

<img width="1217" height="378" alt="image" src="https://github.com/user-attachments/assets/c3debae7-e6cf-4971-91d3-b7b035d31fce" />


**Question 2**

<img width="1235" height="455" alt="image" src="https://github.com/user-attachments/assets/4db4e82e-cf7c-48e5-8317-da09b69e2066" />

```
DELETE FROM Customer
WHERE 
    (GRADE > 2 
     AND PAYMENT_AMT < (SELECT AVG(PAYMENT_AMT) FROM Customer))
    OR OUTSTANDING_AMT > 8000;
```

**Output:**

<img width="1256" height="664" alt="image" src="https://github.com/user-attachments/assets/a9ce9527-76f4-4e2a-94c0-e783dd009836" />


**Question 3**

<img width="747" height="365" alt="image" src="https://github.com/user-attachments/assets/7f4c3857-3ddd-4bce-bf70-225561d5fdb5" />

```
SELECT CategoryName, Description
FROM Categories
ORDER BY CategoryName;
```

**Output:**

<img width="1103" height="542" alt="image" src="https://github.com/user-attachments/assets/d6351d17-0e84-4068-ac51-48d8bacbf8cb" />


**Question 4**

<img width="1225" height="427" alt="image" src="https://github.com/user-attachments/assets/bb7a7c01-7f83-40b5-ae00-6ff9a2acaeb0" />

```
SELECT customer_id, cust_name, city, grade, salesman_id
FROM customer
WHERE city = 'New York'
   OR grade <= 100
   OR grade IS NULL;
```

**Output:**
<img width="1201" height="437" alt="image" src="https://github.com/user-attachments/assets/2238d4d3-8ac1-4bd0-857e-160f3c41b272" />


**Question 5**

<img width="920" height="454" alt="image" src="https://github.com/user-attachments/assets/ea746b3e-27ee-461c-ad0c-4688d2ef9b05" />

```
SELECT EmpID, EmpFname, EmpLname, Department, Project, Address, DOB, Gender
FROM EmployeeInfo
ORDER BY EmpID DESC
LIMIT 5;
```

**Output:**
<img width="1249" height="385" alt="image" src="https://github.com/user-attachments/assets/051ce5aa-3ead-43d4-aa13-a00e6b1d620f" />


**Question 6**

<img width="820" height="484" alt="image" src="https://github.com/user-attachments/assets/c84b4254-5377-4b3a-a657-336d7a19363c" />

```
SELECT
    first_name,
    last_name,
    (julianday(discharge_date) - julianday(admission_date) + 1) AS no_of_days
FROM Patients
WHERE (julianday(discharge_date) - julianday(admission_date) + 1) > 3;
```

**Output:**
<img width="823" height="369" alt="image" src="https://github.com/user-attachments/assets/f3423baf-7014-4792-bf36-35d1cd4eb28a" />


**Question 7**


<img width="1153" height="444" alt="image" src="https://github.com/user-attachments/assets/a762faeb-eb3f-451f-a0fa-801401e497f0" />

```
SELECT 
    product_id,
    original_price,
    discount_percentage,
    original_price * discount_percentage AS discount_amount
FROM Products;
```

**Output:**
<img width="1198" height="301" alt="image" src="https://github.com/user-attachments/assets/116e24d2-048f-462b-a464-62b4f7f7981a" />

**Question 8**

<img width="921" height="485" alt="image" src="https://github.com/user-attachments/assets/c7d3e030-ee9b-4c33-9b4b-527044abacea" />

```
SELECT ename
FROM emp
WHERE LOWER(SUBSTR(ename, 1, 2)) = LOWER(SUBSTR(ename, -2));
```

**Output:**

<img width="586" height="367" alt="image" src="https://github.com/user-attachments/assets/0c96666c-bdec-4e36-a579-47eb54400410" />


**Question 9**

<img width="908" height="196" alt="image" src="https://github.com/user-attachments/assets/4688e3ce-3e11-4694-b940-9a1d9a2a2e40" />

```
UPDATE products
SET product_name = 'Grapefruit'
WHERE product_id = 4;
```
**Output:**
<img width="1196" height="251" alt="image" src="https://github.com/user-attachments/assets/584f4c73-766a-4a7c-873e-e78b29140e89" />


**Question 10**

<img width="880" height="479" alt="image" src="https://github.com/user-attachments/assets/bad1072d-fabb-4ebd-8a92-5238bf701e38" />

```
DELETE FROM doctors
WHERE specialization IS NULL;
```

**Output:**
<img width="1155" height="314" alt="image" src="https://github.com/user-attachments/assets/ada322f8-c488-43f7-9135-0d38a41f5075" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
