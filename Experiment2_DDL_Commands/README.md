# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--

<img width="1224" height="427" alt="image" src="https://github.com/user-attachments/assets/731d0733-f8eb-4725-a607-858bad2b77df" />

```sql
create table Reviews(
ReviewID INTEGER,
ProductID INTEGER,
Rating REAL,
ReviewText TEXT);
```

**Output:**

<img width="1206" height="414" alt="image" src="https://github.com/user-attachments/assets/f70f1753-b7cb-4480-959e-296942c73ea0" />


**Question 2**
---

<img width="1208" height="385" alt="image" src="https://github.com/user-attachments/assets/cd084273-81b3-454f-9621-fca0345cad69" />

```sql
CREATE TABLE Employees(
EmployeeID INTEGER PRIMARY KEY,
FirstName TEXT NOT NULL,
LastName TEXT NOT NULL,
Email TEXT UNIQUE,
Salary INTEGER CHECK(Salary>0),
DepartmentID REAL,
FOREIGN KEY(DepartmentID) REFERENCES Departments(DepartmentID)
);
```

**Output:**

<img width="1205" height="353" alt="image" src="https://github.com/user-attachments/assets/af002953-8b91-4fa2-a626-739d5f841d70" />

**Question 3**
---

<img width="1203" height="329" alt="image" src="https://github.com/user-attachments/assets/9dafa404-339d-441c-9f12-520be7e7e35a" />

```sql
CREATE TABLE Orders(
OrderID INTEGER PRIMARY KEY,
OrderDate INTEGER NOT NULL,
CustomerID INTEGER,
FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID));
```

**Output:**

<img width="1207" height="290" alt="image" src="https://github.com/user-attachments/assets/c048a7d7-6232-426d-a91b-6153a197a0c6" />


**Question 4**
---

<img width="1202" height="396" alt="image" src="https://github.com/user-attachments/assets/9dfb0ef3-685b-4099-b7c8-78d130c9040c" />

```sql
Create table Members(
MemberID INTEGER,
MemberName TEXT,
JoinDate DATE
);
```

**Output:**

<img width="1210" height="381" alt="image" src="https://github.com/user-attachments/assets/fdb2a752-2dec-468f-a260-a78028e6f0de" />


**Question 5**
---

<img width="1143" height="373" alt="image" src="https://github.com/user-attachments/assets/f51986f0-40a4-4a59-8816-0208505334f9" />


```sql
INSERT INTO Customers(CustomerId, Name, Address, City, Zipcode)
values(302, 'Laura Croft', '456 Elm St','Seattle',98101);
INSERT INTO Customers(CustomerId, Name, Address, City, Zipcode) 
values(303, 'Bruce Wayne', '789 Oak St','Gotham',10001); 
```

**Output:**

<img width="1206" height="392" alt="image" src="https://github.com/user-attachments/assets/28915942-ba4b-4748-807a-4322ffdf66c6" />


**Question 6**
---

<img width="1202" height="396" alt="image" src="https://github.com/user-attachments/assets/1d31ffea-f4d3-4d34-bde9-fd928714d1fd" />


```sql
ALTER TABLE Student_details
ADD ParentsNumber  number;
ALTER TABLE Student_details 
ADD Adhar_Number number;
```

**Output:**

<img width="1212" height="400" alt="image" src="https://github.com/user-attachments/assets/eecb4144-b35b-4813-bc45-a319c763cc09" />


**Question 7**
---

<img width="1170" height="344" alt="image" src="https://github.com/user-attachments/assets/e805eafa-8fd9-4d20-a082-5552b520e887" />


```sql
INSERT INTO Products(ProductID, ProductName, Price, Stock)
select ProductID, ProductName, Price, Stock from Discontinued_products;
```

**Output:**

<img width="1209" height="295" alt="image" src="https://github.com/user-attachments/assets/ec8850cf-e016-411a-b274-fe5e0026cddc" />


**Question 8**
---

<img width="1193" height="570" alt="image" src="https://github.com/user-attachments/assets/9488dc87-c544-439e-8ae8-911f0f676070" />


```sql
ALTER TABLE customer
Add discount DECIMAL(5,2);
```

**Output:**

<img width="839" height="370" alt="image" src="https://github.com/user-attachments/assets/95ed5993-832c-43ec-9c71-cbd5536727cc" />


**Question 9**
---

<img width="1207" height="351" alt="image" src="https://github.com/user-attachments/assets/8c9f00ec-26a5-488d-b8b5-eef42bd03e88" />


```sql
CREATE TABLE Products(
ProductID INTEGER PRIMARY KEY,
ProductName TEXT NOT NULL,
Price REAL CHECK(Price>0),
Stock INTEGER CHECK(Stock>=0));
```

**Output:**

<img width="1212" height="290" alt="image" src="https://github.com/user-attachments/assets/96375e2f-5c6b-4679-bb10-79c2259e1c48" />


**Question 10**
---
<img width="1206" height="380" alt="image" src="https://github.com/user-attachments/assets/18e66740-6761-4a28-909b-184671411192" />


```sql
Insert INTO Products(Name, Category, Price,Stock)
values('Smartphone', 'Electronics', 800, 150);
Insert INTO Products(Name, Category, Price,Stock)
values('Headphones', 'Accessories', 200, 300); 
```

**Output:**

<img width="1202" height="361" alt="image" src="https://github.com/user-attachments/assets/4bf01ede-db79-44cc-aa3d-0812d534bfe7" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
