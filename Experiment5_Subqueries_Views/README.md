# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**

<img width="896" height="562" alt="image" src="https://github.com/user-attachments/assets/a2f46aa0-9611-4cdb-afbd-0e55f536e58c" />

```
select *
from CUSTOMERS
where salary=1500;
```

**Output:**

<img width="1092" height="362" alt="image" src="https://github.com/user-attachments/assets/402186a9-f935-44d6-b584-e6de749d5220" />


**Question 2**

<img width="939" height="476" alt="image" src="https://github.com/user-attachments/assets/ebad7014-97e8-46c7-9093-740bed381a7b" />

```
select *
from customer
where city <>(
select city
from customer
where id =(select max(id) from customer)

);
```

**Output:**

<img width="1227" height="497" alt="image" src="https://github.com/user-attachments/assets/e00b4b5c-a18b-43ae-bdd9-9aec7db31d61" />


**Question 3**

<img width="1198" height="477" alt="image" src="https://github.com/user-attachments/assets/9da6cc54-ee83-4edc-bcb8-4819d27c4217" />

```
select *
from Orders
where salesman_id = (
select salesman_id
from Orders
where customer_id = 3007

);
```

**Output:**

<img width="1119" height="457" alt="image" src="https://github.com/user-attachments/assets/6d78e8f4-c4ba-480b-84b9-7eb9a078cd28" />


**Question 4**

<img width="815" height="440" alt="image" src="https://github.com/user-attachments/assets/191f8bf8-953f-43c8-b76f-a6fe7c332815" />

```
select *
from Medications
where dosage = (
select min(dosage)
from Medications

);
```

**Output:**

<img width="882" height="430" alt="image" src="https://github.com/user-attachments/assets/694c8572-6ee5-4c4a-86ab-89b4f394048c" />


**Question 5**

<img width="872" height="602" alt="image" src="https://github.com/user-attachments/assets/e9a2d2c6-1808-4106-8494-3d5e7afa2496" />

```
select *
from CUSTOMERS
where salary < 2500;
```

**Output:**

<img width="1128" height="479" alt="image" src="https://github.com/user-attachments/assets/c6b98c20-cfa7-4da1-b3ea-e854d5ef2bb6" />


**Question 6**

<img width="1129" height="562" alt="image" src="https://github.com/user-attachments/assets/81e8588e-326c-492e-a530-3788ed0f2b95" />

```
select *
from GRADES g1
where grade = (
select max(grade)
from GRADES g2
where g1.subject=g2.subject

);
```

**Output:**

<img width="1228" height="445" alt="image" src="https://github.com/user-attachments/assets/8198b8ae-9729-40eb-b48d-c27c308a50e2" />


**Question 7**

<img width="1004" height="544" alt="image" src="https://github.com/user-attachments/assets/3226d43d-75e6-4ed4-ad10-8c53740fbd9e" />

```
select *
from Employee
where age < (
select avg(age)
from Employee
where income > 1000000

);
```

**Output:**

<img width="1215" height="372" alt="image" src="https://github.com/user-attachments/assets/7f06425a-8087-4aee-aaa6-8cb42a235b52" />


**Question 8**


<img width="1050" height="648" alt="image" src="https://github.com/user-attachments/assets/1a2255b9-82ac-49bf-9101-3a4e41c762f0" />

```
SELECT s.salesman_id, s.name
FROM salesman s
JOIN customer c
ON s.salesman_id = c.salesman_id
GROUP BY s.salesman_id, s.name
HAVING COUNT(c.customer_id) > 1;
```

**Output:**

<img width="600" height="491" alt="image" src="https://github.com/user-attachments/assets/a616f2d2-83c1-4067-bc53-bf568d75cf50" />


**Question 9**


<img width="1222" height="576" alt="image" src="https://github.com/user-attachments/assets/6fa8f3cb-9fd2-4cd3-af82-910b713d4ae4" />

```
select student_name,grade
from GRADES g1
where grade = (
select max(grade)
from GRADES g2
where g1.subject=g2.subject

);
```

**Output:**


<img width="770" height="461" alt="image" src="https://github.com/user-attachments/assets/49bcfb56-b55c-4c27-901c-71954219388c" />


**Question 10**


<img width="1173" height="562" alt="image" src="https://github.com/user-attachments/assets/7a76dc1a-d2a8-4f94-952b-8126162c77ae" />

```
select ord_no, purch_amt, ord_date, customer_id, salesman_id
from orders
where salesman_id in (
select salesman_id
from salesman
where city = 'London'
);
```

**Output:**

<img width="1162" height="436" alt="image" src="https://github.com/user-attachments/assets/0f3f62b0-a108-43db-9440-9c401ca5daaf" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
