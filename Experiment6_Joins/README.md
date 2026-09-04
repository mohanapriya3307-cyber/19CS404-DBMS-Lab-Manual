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
---

<img width="682" height="540" alt="image" src="https://github.com/user-attachments/assets/3f96cf3f-aa3d-41fb-a5b0-497d94f6aa26" />

```sql
select s.name from salesman s
left join customer c on c.salesman_id=s.salesman_id
where c.city='London';
```

**Output:**


=<img width="510" height="493" alt="image" src="https://github.com/user-attachments/assets/4c83d6ec-6451-463d-acbc-a14a55be9fa4" />


**Question 2**
---

<img width="677" height="652" alt="image" src="https://github.com/user-attachments/assets/0e6323a9-2f07-4f62-b278-0fdd0c3327ee" />


```sql
select p.first_name as patient_name,d.first_name as doctor_name
from patients p
inner join doctors d on d.doctor_id = p.doctor_id
where p.discharge_date  is not null;
```

**Output:**


<img width="682" height="430" alt="image" src="https://github.com/user-attachments/assets/6daa7ea5-8417-47b6-a1d1-1e9a44775219" />


**Question 3**
---

<img width="685" height="553" alt="image" src="https://github.com/user-attachments/assets/271243ce-db0e-4785-b173-3caec6fa0f02" />


```sql
select p.first_name as patient_name,t.test_name 
from patients p
inner join test_results t on p.patient_id= t.patient_id;
```

**Output:**


<img width="682" height="493" alt="image" src="https://github.com/user-attachments/assets/806114bd-25c6-4217-a99c-bc319745e1c6" />


**Question 4**
---

<img width="677" height="656" alt="image" src="https://github.com/user-attachments/assets/9caeb4bb-c790-4cf9-a6d3-e9c0efcc1293" />


```sql

select p.admission_date,s.surgery_date from patients p
inner join surgeries s on s.patient_id = p.patient_id;
```

**Output:**


<img width="628" height="512" alt="image" src="https://github.com/user-attachments/assets/bf3a0376-561d-44da-bc66-9917fe91c182" />


**Question 5**
---

<img width="676" height="652" alt="image" src="https://github.com/user-attachments/assets/9a3559a9-2fc5-4ab7-a92b-18a08b92c00e" />


```sql
select p.first_name as patient_name,d.specialization as Doctor_speciali
from patients p
inner join doctors d on  d.doctor_id = p.doctor_id
where p.admission_date between '2024-01-01' and '2024-01-31';
```

**Output:**


<img width="716" height="402" alt="image" src="https://github.com/user-attachments/assets/4dbd5e23-863d-4917-85c3-98a7155587ee" />


**Question 6**
---

<img width="686" height="650" alt="image" src="https://github.com/user-attachments/assets/b062d7f5-528a-4cf3-99b9-873fdfae4767" />


```sql
select p.first_name ,s.surgery_id,s.patient_id,s.surgeon_id ,s.surgery_date
from surgeries s
inner join patients p on s.patient_id = p.patient_id
where ( p.discharge_date between  '2024-03-01' and '2024-03-31')
and (p.admission_date not between '2024-03-01' and '2024-03-31');
```

**Output:**


<img width="673" height="385" alt="image" src="https://github.com/user-attachments/assets/ee7e0701-c48b-4997-9c83-3f24b6334b7a" />

**Question 7**
---

<img width="670" height="717" alt="image" src="https://github.com/user-attachments/assets/862da197-a255-4f48-a0e9-5e9eb4a04cd8" />


```sql
select c.cust_name,o.ord_no,o.ord_date,o.purch_amt
from customer c
left join  orders o on c.customer_id = o.customer_id;
```

**Output:**


<img width="671" height="630" alt="image" src="https://github.com/user-attachments/assets/8b185860-d05a-44c5-ad44-092dee5cfe04" />


**Question 8**
---

<img width="702" height="631" alt="image" src="https://github.com/user-attachments/assets/19eca0f2-73ce-4399-ae0b-9bb8f16a1fd6" />


```sql
select p.first_name,p.last_name 
from patients p
inner join surgeries s on s.patient_id = p.patient_id
where s.surgery_date between '2024-01-01' and '2024-01-31';
```

**Output:**


<img width="700" height="427" alt="image" src="https://github.com/user-attachments/assets/61693f49-6b71-46e2-bfb8-d511e58d1e87" />


**Question 9**
---

<img width="686" height="503" alt="image" src="https://github.com/user-attachments/assets/32f6c5d0-8bf3-44c0-bd33-46b551fda92e" />


```sql
select p.patient_id,p.first_name,p.last_name,p.date_of_birth,p.admission_date,p.discharge_date,p.doctor_id
from patients p
inner join appointments a on p.patient_id=a.patient_id
where a.appointment_date between '2024-01-01' and '2024-01-31';
```

**Output:**


<img width="712" height="406" alt="image" src="https://github.com/user-attachments/assets/3a70fe68-10f2-4140-916f-8f4cc150d84a" />


**Question 10**
---

<img width="695" height="703" alt="image" src="https://github.com/user-attachments/assets/9dddc0db-856b-4a7f-a9e8-a2c43ed01aa4" />

```sql
select c.cust_name from customer c
left join orders o on o.customer_id = c.customer_id;

```

**Output:**


<img width="493" height="622" alt="image" src="https://github.com/user-attachments/assets/4ebacda3-9250-4e68-b69e-2194014e4f67" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
