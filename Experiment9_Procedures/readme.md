# Experiment 9: PL/SQL – Procedures and Functions

## AIM
To understand and implement procedures and functions in PL/SQL for performing various operations such as calculations, decision-making, and looping.

---

## THEORY

PL/SQL (Procedural Language/SQL) extends SQL by adding procedural constructs like variables, conditions, loops, procedures, and functions. Procedures and functions are subprograms that help modularize the code and improve reusability.

### **Procedure**
A PL/SQL **procedure** is a subprogram that performs a specific action. It does not return a value directly but can return values using `OUT` parameters.

**Syntax:**
```sql
CREATE OR REPLACE PROCEDURE procedure_name (parameters)
IS
BEGIN
   -- statements
END;
```

To call the procedure

```sql
EXEC procedure_name(arguments);
```

### **Function**
A PL/SQL **function** is a subprogram that returns a single value using the RETURN keyword.

```sql
CREATE OR REPLACE FUNCTION function_name (parameters)
RETURN datatype
IS
BEGIN
   -- statements
   RETURN value;
END;
```

To call the function:

```sql
SELECT function_name(arguments) FROM DUAL;
```

Key Differences:

-A procedure does not return a value, whereas a function must return a value.
-Functions can be called from SQL queries, procedures cannot (in most cases).

## 1. Write a PL/SQL Procedure to Find the Square of a Number

### Steps:
- Create a procedure named `find_square`.
- Declare a parameter to accept a number.
- Inside the procedure, compute the square of the input number.
- Use `DBMS_OUTPUT.PUT_LINE` to display the result.
- Call the procedure with a number as input.

**Expected Output:**  
Square of 6 is 36

## Program:
```
SET SERVEROUTPUT ON;

CREATE OR REPLACE PROCEDURE find_square (num IN NUMBER)
IS
   result NUMBER;
BEGIN
   result := num * num;
   DBMS_OUTPUT.PUT_LINE('Square of ' || num || ' is ' || result);
END;
/

BEGIN
    find_square(6);
END;
/
```
## Output:
<img width="416" height="94" alt="image" src="https://github.com/user-attachments/assets/52ffab62-f047-4038-b5b2-d37c7334e0c2" />


---

## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.

**Expected Output:**  
Factorial of 5 is 120
## Program:
```
SET SERVEROUTPUT ON;

-- Function
CREATE OR REPLACE FUNCTION get_factorial(n IN NUMBER)
RETURN NUMBER
IS
    fact NUMBER := 1;
BEGIN
    FOR i IN 1..n LOOP
        fact := fact * i;
    END LOOP;

    RETURN fact;
END;
/

-- Calling the function
DECLARE
    num NUMBER := 5;
    result NUMBER;
BEGIN
    result := get_factorial(num);
    DBMS_OUTPUT.PUT_LINE('Factorial of ' || num || ' is ' || result);
END;
/
```
## Output:
<img width="374" height="90" alt="image" src="https://github.com/user-attachments/assets/8f1e0787-e439-412b-b9e3-090364c39515" />

---

## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
12 is Even
## Program:
```
CREATE OR REPLACE PROCEDURE check_even_odd(num IN NUMBER)
IS
BEGIN
    IF MOD(num, 2) = 0 THEN
        DBMS_OUTPUT.PUT_LINE(num || ' is Even');
    ELSE
        DBMS_OUTPUT.PUT_LINE(num || ' is Odd');
    END IF;
END;
/
SET SERVEROUTPUT ON;

BEGIN
    check_even_odd(12);
END;
/
```
## Output:
<img width="448" height="88" alt="image" src="https://github.com/user-attachments/assets/d23d392a-3546-414f-bdcd-d92b60fd7244" />


---

## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.

**Expected Output:**  
Reversed number of 1234 is 4321
## Program:
```
CREATE OR REPLACE FUNCTION reverse_number(n IN NUMBER)
RETURN NUMBER
IS
    num NUMBER := n;
    rev NUMBER := 0;
    digit NUMBER;
BEGIN
    WHILE num > 0 LOOP
        digit := MOD(num, 10);
        rev := rev * 10 + digit;
        num := TRUNC(num / 10);
    END LOOP;

    RETURN rev;
END;
/
SET SERVEROUTPUT ON;

DECLARE
    num NUMBER := 1234;
    result NUMBER;
BEGIN
    result := reverse_number(num);
    DBMS_OUTPUT.PUT_LINE('Reversed number of ' || num || ' is ' || result);
END;
/
```
## Output:
<img width="501" height="96" alt="image" src="https://github.com/user-attachments/assets/74af02b2-2589-4162-b4da-907b64b7940a" />

---

## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50
## Program:
```
CREATE OR REPLACE PROCEDURE print_table(num IN NUMBER)
IS
BEGIN
    DBMS_OUTPUT.PUT_LINE('Multiplication table of ' || num || ':');

    FOR i IN 1..10 LOOP
        DBMS_OUTPUT.PUT_LINE(num || ' x ' || i || ' = ' || (num * i));
    END LOOP;
END;
/
SET SERVEROUTPUT ON;

BEGIN
    print_table(5);
END;
/
```
## Output:
<img width="577" height="275" alt="image" src="https://github.com/user-attachments/assets/f197ae26-c1ec-4ac3-b60c-91cdbd61646a" />


## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
