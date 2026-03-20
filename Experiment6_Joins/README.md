# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**

<img width="1232" height="571" alt="image" src="https://github.com/user-attachments/assets/2c670b4b-25a3-4e7a-813d-3a8e68b3e511" />

```
SELECT p.first_name AS patient_name,
       d.first_name AS doctor_name
FROM patients p
INNER JOIN doctors d
ON p.doctor_id = d.doctor_id
WHERE p.date_of_birth > '1990-01-01';
```


**Output:**

<img width="685" height="422" alt="image" src="https://github.com/user-attachments/assets/208f6b6e-f978-4fc7-a660-06bcc249db76" />


**Question 2**


<img width="1182" height="707" alt="image" src="https://github.com/user-attachments/assets/cf623868-407e-45b3-b08b-5aa1dc3a30a6" />

```
SELECT p.*
FROM patients p
INNER JOIN doctors d
ON p.doctor_id = d.doctor_id
WHERE d.first_name = 'John'
AND d.last_name = 'Smith';
```

**Output:**

<img width="1225" height="425" alt="image" src="https://github.com/user-attachments/assets/e082f3cd-41a5-44bc-b5ea-e932e0fa13b9" />


**Question 3**


<img width="1222" height="554" alt="image" src="https://github.com/user-attachments/assets/e87d081d-0358-4527-8f18-a311f078650a" />

```
SELECT p.first_name AS patient_name
FROM patients p
INNER JOIN doctors d
ON p.doctor_id = d.doctor_id
WHERE d.first_name = 'Emily'
AND d.last_name = 'Johnson'
AND p.discharge_date IS NOT NULL;
```

**Output:**

<img width="569" height="413" alt="image" src="https://github.com/user-attachments/assets/e0dba982-a929-46fe-8183-e0ed82a28f87" />


**Question 4**


<img width="1192" height="575" alt="image" src="https://github.com/user-attachments/assets/5dba996c-3f82-44ac-a07a-c659d931eb5d" />

```
SELECT p.first_name AS patient_name, t.*
FROM patients p
INNER JOIN test_results t
ON p.patient_id = t.patient_id
WHERE t.test_name = 'Blood Pressure';
```

**Output:**

<img width="1168" height="434" alt="image" src="https://github.com/user-attachments/assets/410680b8-5c1b-4209-bb89-022d2e449a1b" />


**Question 5**


<img width="1225" height="555" alt="image" src="https://github.com/user-attachments/assets/e025d932-f339-40ca-8f52-bc5e07e80061" />

```
SELECT p.*
FROM patients p
INNER JOIN test_results t
ON p.patient_id = t.patient_id
WHERE (t.test_name = 'Blood Test' OR t.test_name = 'Blood Pressure')
AND t.result NOT LIKE '%Normal%';
```

**Output:**

<img width="804" height="427" alt="image" src="https://github.com/user-attachments/assets/427b2a8a-febf-4c87-b401-4179ea6c189c" />


**Question 6**


<img width="1226" height="748" alt="image" src="https://github.com/user-attachments/assets/9c48769e-486b-4de1-b179-702ae6758f36" />

```
SELECT p.*, d.specialization AS doctor_specialization
FROM patients p
INNER JOIN doctors d
ON p.doctor_id = d.doctor_id;
```

**Output:**

<img width="1195" height="575" alt="image" src="https://github.com/user-attachments/assets/93a200ad-0843-4416-8943-17d28e4c1e4a" />


**Question 7**


<img width="1269" height="747" alt="image" src="https://github.com/user-attachments/assets/5ee72164-18d8-46f2-b63c-18fb04be072a" />

```
SELECT s.name AS salesman_name, c.cust_name AS customer_name
FROM salesman s
LEFT JOIN customer c
ON s.salesman_id = c.salesman_id;
```

**Output:**

<img width="676" height="284" alt="image" src="https://github.com/user-attachments/assets/faa15051-7ae9-4c13-aad1-60ce9db3eb1e" />


**Question 8**


<img width="1207" height="882" alt="image" src="https://github.com/user-attachments/assets/4461fe15-4c91-407c-acb2-7a008bb0cf7c" />

```
SELECT c.cust_name AS "Customer Name",
       c.city,
       s.name AS "Salesman",
       s.commission
FROM customer c
INNER JOIN salesman s
ON c.salesman_id = s.salesman_id;
```

**Output:**

<img width="1224" height="300" alt="image" src="https://github.com/user-attachments/assets/eaeaa571-bff7-4df2-8ece-76ca969f44bf" />


**Question 9**


<img width="1246" height="736" alt="image" src="https://github.com/user-attachments/assets/c17354f6-d19f-4c21-829a-1226c4dbb9b0" />

```
SELECT p.*, d.first_name AS doctor_name
FROM patients p
INNER JOIN doctors d
ON p.doctor_id = d.doctor_id;
```

**Output:**

<img width="1231" height="578" alt="image" src="https://github.com/user-attachments/assets/96d092e4-5070-4830-9eb7-61f28a284c4e" />


**Question 10**


<img width="1166" height="543" alt="image" src="https://github.com/user-attachments/assets/9da65cd0-f394-49e9-87b4-ebbe276d30dc" />

```
SELECT p.first_name AS patient_name
FROM patients p
INNER JOIN test_results t
ON p.patient_id = t.patient_id
WHERE t.test_name = 'Blood Pressure';
```

**Output:**

<img width="585" height="413" alt="image" src="https://github.com/user-attachments/assets/135453d6-02bf-4df9-90bf-dd8c0267f52b" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
