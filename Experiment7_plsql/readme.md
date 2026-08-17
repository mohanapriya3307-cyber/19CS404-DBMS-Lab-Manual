# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Greater number is: 80

**Program :** 
```sql
DECLARE
    num1 NUMBER := 80;
    num2 NUMBER := 50;
BEGIN
    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    END IF;
END;
/
```
**Output:** 

<img width="844" height="176" alt="image" src="https://github.com/user-attachments/assets/7c30f56e-19da-4f12-b8ed-81f521bc743c" />

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55

**Program :** 
```sql
DECLARE
    n NUMBER := 10;
    sum NUMBER := 0;
    i NUMBER := 1;
BEGIN
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
/
```
**Output:** 

<img width="727" height="178" alt="image" src="https://github.com/user-attachments/assets/a88f5e98-e40a-4a23-ac49-9e8f7ef80842" />

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

**Program :** 
```sql
DECLARE
    n NUMBER := 7;
    a NUMBER := 0;
    b NUMBER := 1;
    c NUMBER;
BEGIN
    DBMS_OUTPUT.PUT('Fibonacci sequence: ');
    FOR i IN 1..n LOOP
        DBMS_OUTPUT.PUT(a);
        IF i < n THEN
            DBMS_OUTPUT.PUT(', ');
        END IF;
        c := a + b;
        a := b;
        b := c;
    END LOOP;
    DBMS_OUTPUT.NEW_LINE;
END;
/
```
**Output:**

<img width="598" height="234" alt="image" src="https://github.com/user-attachments/assets/0ab025a1-3177-4bed-bd77-4e45ef116151" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351

**Program :** 
```sql
DECLARE
    n NUMBER := 1535;
    rev NUMBER := 0;
    digit NUMBER;
BEGIN
    WHILE n > 0 LOOP
        digit := MOD(n, 10);
        rev := (rev * 10) + digit;
        n := TRUNC(n / 10);
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Reversed number is: ' || rev);
END;
/
```
**Output:** 

<img width="592" height="186" alt="image" src="https://github.com/user-attachments/assets/c84c188c-4e47-46e6-986d-7233ac0ca64b" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

**Program :** 
```sql
DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN
    IF a > b AND a > c THEN
        largest := a;
    ELSIF b > a AND b > c THEN
        largest := b;
    ELSE
        largest := c;
    END IF;
    DBMS_OUTPUT.PUT_LINE('Largest of three numbers is: ' || largest);
END;
/
```
**Output:** 

<img width="605" height="203" alt="image" src="https://github.com/user-attachments/assets/d32d8a9e-cbda-44fe-8056-04eacbce8417" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
