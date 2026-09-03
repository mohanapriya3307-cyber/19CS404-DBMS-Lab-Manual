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
--
<img width="675" height="450" alt="image" src="https://github.com/user-attachments/assets/36063447-26c2-429c-94f2-dd9ed9c1330b" />


```sql
select * from customer
where city !=(select city from customer order by id desc);
```

**Output:**

<img width="690" height="467" alt="image" src="https://github.com/user-attachments/assets/b12a7165-0257-46ee-aa65-133a8c9fa6bc" />



**Question 2**
---
<img width="727" height="398" alt="image" src="https://github.com/user-attachments/assets/7a4da027-99cf-4705-b64d-a63ed46e8a86" />


```sql
select * from Medications
where dosage = (select min(dosage) from Medications );
```

**Output:**

<img width="686" height="382" alt="image" src="https://github.com/user-attachments/assets/3cbceced-b935-42bb-b3c2-df0031afa2a0" />


**Question 3**
---
<img width="690" height="490" alt="image" src="https://github.com/user-attachments/assets/9777c2cc-9a50-4c29-977f-d37390ae3909" />


```sql
select * from Employee
where age<(select avg(age) from Employee where income>1000000);
```

**Output:**

<img width="698" height="406" alt="image" src="https://github.com/user-attachments/assets/134a82b9-872f-4073-938c-d26688e50a00" />


**Question 4**
---
<img width="693" height="442" alt="image" src="https://github.com/user-attachments/assets/9b7d9b0c-d2d6-4dd1-837d-59a966a84392" />


```sql
select name,city from customer
where city IN(select city from customer where id IN(3,7));
```

**Output:**

<img width="677" height="418" alt="image" src="https://github.com/user-attachments/assets/cbca8c3d-1c32-419c-85e0-e1841a64c16a" />


**Question 5**
---
<img width="697" height="510" alt="image" src="https://github.com/user-attachments/assets/832a783a-93ff-4c63-b6f7-75c66c6453c1" />


```sql
select * from  grades g1
where grade = (select min(grade) from grades g2 where g1.subject = g2.subject);

```

**Output:**

<img width="707" height="446" alt="image" src="https://github.com/user-attachments/assets/932ebecf-949f-4288-8375-5ec6e324a3a4" />


**Question 6**
---
<img width="682" height="543" alt="image" src="https://github.com/user-attachments/assets/829ae103-27f7-42ce-b9be-df8720d8bf9d" />


```sql
select * from customers
where salary <2500;
```

**Output:**

<img width="713" height="457" alt="image" src="https://github.com/user-attachments/assets/48913e4a-01cd-4770-aa2b-346e3da0b996" />


**Question 7**
---
<img width="697" height="510" alt="image" src="https://github.com/user-attachments/assets/9b459f02-abca-4c6d-87e0-d60058335cf2" />


```sql
select * from grades g1
where grade =(select max(grade) from grades g2 where g1.subject = g2.subject);
```

**Output:**
<img width="702" height="437" alt="image" src="https://github.com/user-attachments/assets/1a217c07-a6dc-4cbb-905f-756662330418" />


**Question 8**
---
<img width="658" height="652" alt="image" src="https://github.com/user-attachments/assets/6004752a-87ed-46a7-a09f-577c4f4ebf28" />


```sql
select ord_no ,purch_amt,ord_date,salesman_id from orders
where salesman_id IN ( select salesman_id from salesman where  commission = (select max(commission) from salesman));
```

**Output:**

<img width="713" height="472" alt="image" src="https://github.com/user-attachments/assets/035803b3-0c33-471c-acda-425a97a73de8" />


**Question 9**
---
<img width="670" height="491" alt="image" src="https://github.com/user-attachments/assets/305fde99-c4ee-4c02-a1ac-3f7c33c719b6" />


```sql
select * from orders
where purch_amt>(select avg(purch_amt) from orders where ord_date = '2012-10-10' );
```

**Output:**
<img width="702" height="408" alt="image" src="https://github.com/user-attachments/assets/c5c68e32-99e7-48f3-9e53-f2cb4f265a10" />


**Question 10**
---
<img width="686" height="512" alt="image" src="https://github.com/user-attachments/assets/ed485f9d-9ed8-467e-a68a-561a0d513628" />


```sql
select student_name,grade from GRADES g1
where grade  =(select max(grade) from GRADES g2 where g1.subject = g2.subject);
```

**Output:**

<img width="712" height="442" alt="image" src="https://github.com/user-attachments/assets/4b6fa548-6d0b-411e-bb8d-c4f1c61e02ce" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
