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
---
<img width="1208" height="506" alt="image" src="https://github.com/user-attachments/assets/c4627c09-4d60-4186-bc9e-a9d14116439b" />


```sql
select avg(income) as Average_Salary
from employee;

```

**Output:**
<img width="1218" height="309" alt="image" src="https://github.com/user-attachments/assets/8eb44d76-2b09-4be1-a8af-92fa1dd7d742" />


**Question 2**
---
<img width="1199" height="490" alt="image" src="https://github.com/user-attachments/assets/1fe0eb32-f813-4ba1-b11d-bb65a2dacb95" />


```sql
select sum(income) as total_income
from employee
where age>=40;
```

**Output:**

<img width="1211" height="314" alt="image" src="https://github.com/user-attachments/assets/4c26f21e-92c8-4cbe-845f-8a747e92e6d5" />


**Question 3**
---
<img width="1216" height="472" alt="image" src="https://github.com/user-attachments/assets/706e2d08-3367-4e71-88f8-f41cb97bde49" />


```sql
select max(age)-min(age) as age_difference
from employee;
```

**Output:**

<img width="1203" height="319" alt="image" src="https://github.com/user-attachments/assets/62794e8f-41b7-45a8-9bbb-5d4d8a37b15e" />


**Question 4**
---
<img width="1208" height="561" alt="image" src="https://github.com/user-attachments/assets/224b6cc3-bff0-443d-b075-a328967cbc03" />

 
```sql
select specialty,count(*) as TotalDocto
from doctors
group by specialty;
```

**Output:**

<img width="1202" height="678" alt="image" src="https://github.com/user-attachments/assets/3ae99c55-aed1-4dc3-b5ba-ccadb3950670" />


**Question 5**
---
<img width="1205" height="464" alt="image" src="https://github.com/user-attachments/assets/c1c6f6bc-02a0-4ad7-9e77-e26d73d83eb2" />


```sql
select substr(email,instr(email,'@')+1) as EmailDomain, count(*) as TotalPatients
from patients
group by EmailDomain;
```

**Output:**

<img width="1220" height="362" alt="image" src="https://github.com/user-attachments/assets/000b6a9f-ac66-4826-9e97-33af57d5213f" />


**Question 6**
---
<img width="1217" height="564" alt="image" src="https://github.com/user-attachments/assets/62e47a3d-3064-4661-9864-7ec81ebe68cd" />


```sql
select  strftime('%Y',validityperiod) as ValidityYear, count(distinct patientid) as TotalPatients
from insurance
group by validityperiod
order by validityyear asc;
```

**Output:**

<img width="1211" height="390" alt="image" src="https://github.com/user-attachments/assets/6699eaec-c0c3-4971-8fc2-eb96eb3ca468" />

**Question 7**
---
<img width="1194" height="524" alt="image" src="https://github.com/user-attachments/assets/b876cc61-88d4-417c-b5b3-bb318503d561" />


```sql
select city, avg(income) as "AVG(income)"
from employee
group by city
having AVG(income)>500000;
```

**Output:**

<img width="1219" height="441" alt="image" src="https://github.com/user-attachments/assets/597ee85b-f552-4662-8a1a-8ca92436fdcb" />


**Question 8**
---
<img width="1213" height="527" alt="image" src="https://github.com/user-attachments/assets/b24264bd-3b98-4411-9be1-7728c5ac10c0" />


```sql
select category_id, count(product_name) as 'count(product_name)'
from products
group by category_id
having min(category_id)<3;
```

**Output:**

<img width="1198" height="359" alt="image" src="https://github.com/user-attachments/assets/42730198-43b5-42c2-a779-f10fbc8cc184" />

**Question 9**
---
<img width="1204" height="485" alt="image" src="https://github.com/user-attachments/assets/08b62d48-3c12-40b0-831d-22129b32f6e3" />


```sql
select category_id, sum(price) as Total_Cost
from products
group by category_id
having Total_Cost>50;
```

**Output:**

<img width="1212" height="346" alt="image" src="https://github.com/user-attachments/assets/8fddadd5-72d9-482e-8406-322bdf026e14" />


**Question 10**
---
<img width="1206" height="519" alt="image" src="https://github.com/user-attachments/assets/53152c1a-a731-429a-9978-2764dfc5e64e" />


```sql
select category_id, sum(price)*category_id as Revenue
from products
group by category_id
having Revenue>25;
```

**Output:**

<img width="1201" height="439" alt="image" src="https://github.com/user-attachments/assets/9ef1da3a-c611-4dea-8462-5ed2b2207ed4" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
