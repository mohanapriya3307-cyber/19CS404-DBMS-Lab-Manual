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
--
<img width="675" height="550" alt="image" src="https://github.com/user-attachments/assets/b8cdfc1c-5971-4b29-aee2-800f7604a549" />


```sql
select s.name from salesman s
left join customer c on c.salesman_id=s.salesman_id
where c.city='London';
```

**Output:**

<img width="542" height="408" alt="image" src="https://github.com/user-attachments/assets/11d4cbbf-47f7-4c10-8315-826093122484" />


**Question 2**
---
<img width="677" height="666" alt="image" src="https://github.com/user-attachments/assets/b5ca2a32-4711-495f-b706-f5a2302d75cb" />


```sql
select p.first_name as patient_name,d.first_name as doctor_name
from patients p
inner join doctors d on d.doctor_id = p.doctor_id
where p.discharge_date  is not null;
```

**Output:**

<img width="652" height="362" alt="image" src="https://github.com/user-attachments/assets/6e730911-bcf8-46f5-945d-b0e812dfd480" />


**Question 3**
---
<img width="702" height="540" alt="image" src="https://github.com/user-attachments/assets/e73e03eb-fecd-4011-9e57-25375b9233b0" />


```sql
select p.first_name as patient_name,t.test_name 
from patients p
inner join test_results t on p.patient_id= t.patient_id;
```

**Output:**

<img width="613" height="386" alt="image" src="https://github.com/user-attachments/assets/44ed6c0b-0352-4c51-a63d-dd076e57791a" />


**Question 4**
---
<img width="682" height="652" alt="image" src="https://github.com/user-attachments/assets/8a5551bd-1b44-4082-a1bd-6098daa408c3" />


```sql
select p.admission_date,s.surgery_date from patients p
inner join surgeries s on s.patient_id = p.patient_id;
```

**Output:**

<img width="665" height="441" alt="image" src="https://github.com/user-attachments/assets/264abd06-0052-4afa-8777-54e7b7098cec" />


**Question 5**
---
<img width="678" height="658" alt="image" src="https://github.com/user-attachments/assets/41832103-c277-4903-8610-26d0e82f0407" />


```sql
select p.first_name as patient_name,d.specialization as Doctor_speciali
from patients p
inner join doctors d on  d.doctor_id = p.doctor_id
where p.admission_date between '2024-01-01' and '2024-01-31';
```

**Output:**

<img width="693" height="372" alt="image" src="https://github.com/user-attachments/assets/73dfe678-0cc5-46b8-816e-8f77b5b4746c" />


**Question 6**
---=
<img width="700" height="670" alt="image" src="https://github.com/user-attachments/assets/76d85abe-909a-4f4e-b246-0858d2915946" />


```sql
select p.first_name ,s.surgery_id,s.patient_id,s.surgeon_id ,s.surgery_date
from surgeries s
inner join patients p on s.patient_id = p.patient_id
where ( p.discharge_date between  '2024-03-01' and '2024-03-31')
and (p.admission_date not between '2024-03-01' and '2024-03-31');
```

**Output:**

<img width="721" height="405" alt="image" src="https://github.com/user-attachments/assets/70da03da-ef31-47d1-a0d7-65b263b50995" />


**Question 7**
---
<img width="690" height="703" alt="image" src="https://github.com/user-attachments/assets/fe13007d-23af-4d4b-8429-8ff188f0fa91" />


```sql
select c.cust_name,o.ord_no,o.ord_date,o.purch_amt
from customer c
left join  orders o on c.customer_id = o.customer_id;
```

**Output:**

<img width="657" height="603" alt="image" src="https://github.com/user-attachments/assets/c3e34a00-fd21-4a3f-94c0-d92e13515ad9" />


**Question 8**
---
<img width="678" height="623" alt="image" src="https://github.com/user-attachments/assets/8d2925a0-f873-4779-a29e-e33d12465b60" />


```sql
select p.first_name,p.last_name 
from patients p
inner join surgeries s on s.patient_id = p.patient_id
where s.surgery_date between '2024-01-01' and '2024-01-31';
```

**Output:**

<img width="682" height="410" alt="image" src="https://github.com/user-attachments/assets/1363f7e3-5092-493e-acd9-f944ab188132" />


**Question 9**
---
<img width="693" height="507" alt="image" src="https://github.com/user-attachments/assets/c5f1276e-f151-49a6-93e8-353c7f656523" />

```sql
select p.patient_id,p.first_name,p.last_name,p.date_of_birth,p.admission_date,p.discharge_date,p.doctor_id
from patients p
inner join appointments a on p.patient_id=a.patient_id
where a.appointment_date between '2024-01-01' and '2024-01-31';
```

**Output:**

<img width="733" height="395" alt="image" src="https://github.com/user-attachments/assets/7e5241fa-9d30-4c2a-9b27-3a41ec416946" />


**Question 10**
---
<img width="690" height="662" alt="image" src="https://github.com/user-attachments/assets/9ccefb35-c381-44b2-bc79-22df6fb14a3f" />


```sql
select c.cust_name from customer c
left join orders o on o.customer_id = c.customer_id;

```

**Output:**

<img width="512" height="620" alt="image" src="https://github.com/user-attachments/assets/2e8b9729-0c6a-4f4c-80f7-a9723bb4a491" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
