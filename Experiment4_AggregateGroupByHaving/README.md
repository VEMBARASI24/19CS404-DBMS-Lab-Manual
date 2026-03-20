# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**

<img width="830" height="416" alt="image" src="https://github.com/user-attachments/assets/f78a387d-41ef-45fc-836b-ac6ae588507d" />

```
SELECT COUNT(*) AS COUNT
FROM employee
WHERE age > 32;
```

**Output:**

<img width="464" height="322" alt="image" src="https://github.com/user-attachments/assets/d5810f7d-da3f-41e6-9697-ed97e88d6d07" />


**Question 2**

<img width="836" height="439" alt="image" src="https://github.com/user-attachments/assets/ac46457c-e723-4985-a544-21adb4637429" />

```
SELECT COUNT(*) AS COUNT
FROM customer
WHERE city <> 'Noida';
```

**Output:**

<img width="504" height="339" alt="image" src="https://github.com/user-attachments/assets/386261dd-624c-481d-9017-1c12b10e85b7" />


**Question 3**

<img width="695" height="414" alt="image" src="https://github.com/user-attachments/assets/d1e27ad1-1bfc-450d-8ce4-85eff1272011" />

```
SELECT COUNT(*) AS employees_count
FROM employee
WHERE income > 50000;
```

**Output:**

<img width="488" height="336" alt="image" src="https://github.com/user-attachments/assets/269ccda1-98f5-4352-96fa-d89beebafb6f" />


**Question 4**

<img width="904" height="479" alt="image" src="https://github.com/user-attachments/assets/c1444856-0639-4be6-9acc-45222d130e2d" />

```
SELECT DoctorID, COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID;
```

**Output:**

<img width="683" height="626" alt="image" src="https://github.com/user-attachments/assets/187aebf3-7417-41a3-8046-b05bad695e1e" />


**Question 5**

<img width="905" height="441" alt="image" src="https://github.com/user-attachments/assets/82870752-4330-4fc1-ad9d-fbef26201ede" />

```
SELECT PatientID, COUNT(*) AS AvgMedications
FROM MedicalRecords
GROUP BY PatientID;
```

**Output:**

<img width="763" height="608" alt="image" src="https://github.com/user-attachments/assets/54748460-72f0-4484-99e5-8f462ba5672b" />


**Question 6**

<img width="948" height="580" alt="image" src="https://github.com/user-attachments/assets/c5f5a4bb-8d1e-44c0-beea-8c3badaa7bad" />

```
SELECT PatientID, COUNT(*) AS TotalMedications
FROM Prescriptions
GROUP BY PatientID;
```

**Output:**

<img width="720" height="340" alt="image" src="https://github.com/user-attachments/assets/0b17133e-c18a-49f8-b58d-e2b28d8500c7" />


**Question 7**

<img width="1064" height="410" alt="image" src="https://github.com/user-attachments/assets/47a1d976-a48f-4c82-87d9-1544922b02a2" />

```
SELECT address, AVG(salary)
FROM customer1
GROUP BY address
HAVING AVG(salary) > 5000;
```

**Output:**

<img width="813" height="387" alt="image" src="https://github.com/user-attachments/assets/8eb0e79a-1307-412c-b3f6-60f3eec06fc0" />


**Question 8**

<img width="1227" height="414" alt="image" src="https://github.com/user-attachments/assets/76cdd073-a6e4-49dc-8ab9-4256f18762c1" />

```
SELECT (age/5)*5 AS age_group, AVG(age)
FROM customer1
GROUP BY (age/5)*5
HAVING AVG(age) < 24;
```

**Output:**

<img width="559" height="304" alt="image" src="https://github.com/user-attachments/assets/3a9daed3-e7f0-42a7-9e7a-9dbd1e5c225a" />


**Question 9**

<img width="1206" height="427" alt="image" src="https://github.com/user-attachments/assets/e9b421e9-77bf-47a6-97a3-0ce735c13ad4" />

```
SELECT age, MAX(income)
FROM employee
GROUP BY age
HAVING MAX(income) > 2000000;
```

**Output:**

<img width="574" height="395" alt="image" src="https://github.com/user-attachments/assets/cea3a09b-3272-4ae9-aaa7-8a3150d29b07" />


**Question 10**

<img width="1218" height="450" alt="image" src="https://github.com/user-attachments/assets/f9a77040-2043-4382-8a3e-2a8052daf526" />

```
SELECT occupation, AVG(workhour)
FROM employee1
GROUP BY occupation
HAVING AVG(workhour) BETWEEN 10 AND 12;
```

**Output:**

<img width="695" height="400" alt="image" src="https://github.com/user-attachments/assets/af671aec-8882-4ecc-be17-ce91a0b25c67" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
