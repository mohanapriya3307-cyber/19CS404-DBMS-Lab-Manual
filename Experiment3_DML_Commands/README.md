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
--
<img width="1216" height="212" alt="image" src="https://github.com/user-attachments/assets/80546c48-e3d0-41de-8a6e-7f1597efb2d9" />


```sql
update products
set availability=availability*2
where product_id=1;
```

**Output:**

<img width="1202" height="245" alt="image" src="https://github.com/user-attachments/assets/4cb55ec7-b3e7-4311-895c-4a24b32e0799" />


**Question 2**
---
<img width="1205" height="618" alt="image" src="https://github.com/user-attachments/assets/e7e7f472-d700-43e3-9ffb-5a7244970cc3" />

```sql
update Employees
set email='not available', commission_pct=0.55
where department_id=110;
```

**Output:**

<img width="1213" height="387" alt="image" src="https://github.com/user-attachments/assets/983b38c1-34c9-41ad-9c45-a995e8335850" />


**Question 3**
---
<img width="1205" height="631" alt="image" src="https://github.com/user-attachments/assets/c12aeaa3-f7d2-4f14-a68c-d6bfc0360640" />

```sql
select id,decimal,
case when decimal>100 then 'High'
when decimal>=50 and decimal<=100 then 'Medium'
else 'Low'
end as category
from Calculations;
```

**Output:**

<img width="1208" height="486" alt="image" src="https://github.com/user-attachments/assets/dc43eee6-b5ca-4c19-b35c-4d143b93e1d1" />

**Question 4**
---
<img width="1218" height="672" alt="image" src="https://github.com/user-attachments/assets/68e38370-289c-46a6-bf5c-97920f8e7bae" />

```sql
select *
from EmployeePosition
where dateOfJoining between '2020-01-01' and '2020-12-31';
```

**Output:**

<img width="1205" height="300" alt="image" src="https://github.com/user-attachments/assets/4a608131-8a6b-4616-8e91-afbee9c11e7e" />

**Question 5**
---
<img width="1218" height="540" alt="image" src="https://github.com/user-attachments/assets/e0e6635e-0132-42e5-9b94-47918fa5f405" />


```sql
select * from emp where ename like '__r_%';
```

**Output:**

<img width="1203" height="360" alt="image" src="https://github.com/user-attachments/assets/1d3d62f1-aacc-44d7-9d98-5360954cd0dc" />

**Question 6**
---
<img width="1206" height="529" alt="image" src="https://github.com/user-attachments/assets/b30fa53b-d9d4-4fe7-8adf-a9bb2ed66e00" />

```sql
delete from Surgeries where surgery_date='2024-02-28';
```

**Output:**

<img width="1211" height="390" alt="image" src="https://github.com/user-attachments/assets/06f68c1b-0834-45ff-bdc1-e042bfdfe363" />


**Question 7**
---
<img width="1219" height="695" alt="image" src="https://github.com/user-attachments/assets/6952e64d-7d18-4a63-9647-5f9d588313b4" />

```sql
select * from emp where hiredate between '2024-03-01' and '2024-09-01';
```

**Output:**

<img width="1206" height="366" alt="image" src="https://github.com/user-attachments/assets/3179cead-e7e4-43f9-932c-2300a360549b" />

**Question 8**
---
<img width="1204" height="482" alt="image" src="https://github.com/user-attachments/assets/db93f6d4-7122-4e6d-9b6a-0d5758fe90ba" />

```sql
update products 
set reorder_lvl=20 where quantity<10 and category='Snacks';
```

**Output:**

<img width="1191" height="539" alt="image" src="https://github.com/user-attachments/assets/8a6b465c-5dce-4c0a-bb9f-7a5c3f63ff83" />

**Question 9**
---
<img width="1206" height="371" alt="image" src="https://github.com/user-attachments/assets/689d54cf-9a74-4beb-999d-62b675872480" />

```sql
select name,commission
from salesman
limit 5;
```

**Output:**

<img width="1210" height="463" alt="image" src="https://github.com/user-attachments/assets/effdfe17-f58d-4274-bdcb-f92ce82c0dbd" />

**Question 10**
---
<img width="1205" height="594" alt="image" src="https://github.com/user-attachments/assets/a072a2f0-a1e4-4bad-bcbd-8e8e4e4b6a6e" />

```sql
select id, round(decimal,3) as rounded_value
from Calculations;
```

**Output:**

<img width="1206" height="308" alt="image" src="https://github.com/user-attachments/assets/989f0737-5d33-4d54-b1e3-1939b706a5d1" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
