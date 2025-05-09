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
![image](https://github.com/user-attachments/assets/7de5c4d0-a91d-4b48-99b7-34ba86219a76)

```sql
create table Customers(
CustomerID INTEGER,
Name TEXT,
Email TEXT,
JoinDate DATETIME);
```

**Output:**
![image](https://github.com/user-attachments/assets/ee872218-c819-4131-9436-a8fa798fe93b)

**Question 2**
---
![image](https://github.com/user-attachments/assets/37ea9645-2f1f-41ea-a8c9-7deec7a01d7f)


INSERT INTO Products (ProductID, Price)
VALUES (106, 10.00);
INSERT INTO Products(ProductID, Name, Category, Price, Stock)
VALUES(107,'Laptop','Electronics',999.99,50);
INSERT INTO products(ProductID, Name, Category)
VALUES(108,'Wireless Earbuds','Accessories');

**Output:**

![image](https://github.com/user-attachments/assets/608ae1f9-7a0b-4388-8a86-131a7e959cca)


**Question 3**
![image](https://github.com/user-attachments/assets/3d0bfa90-b0d1-42f2-831b-7453d131b73d)


create table Members(
MemberID INTEGER,
MemberName TEXT,
JoinDate DATE);

**Output:**

![image](https://github.com/user-attachments/assets/907d4743-d926-42af-9952-f16008bce74c)


**Question 4**
![image](https://github.com/user-attachments/assets/3bcd65d7-9b9a-4149-9043-5a1cfd9d5930)

insert into Student_details(RollNo, Name,Gender,Subject,MARKS)
values
(202,'Ella King','F','Chemistry',87),

(203,'James Bond','M','Literature',78);


**Output:**

![image](https://github.com/user-attachments/assets/39c1986f-4947-4011-8c24-0ce740c064e0)

**Question 5**
![image](https://github.com/user-attachments/assets/23bbdeee-1f65-4ddf-933b-41f5604f822a)


ALTER TABLE  customers
ADD column email TEXT;
**Output:**

![image](https://github.com/user-attachments/assets/4a2ef0d1-c83c-4fa3-a976-bd05d81f116b)


**Question 6**
![image](https://github.com/user-attachments/assets/2aca926f-ed49-4be8-b2da-e29c6ce7d33f)

CREATE TABLE Shipments(
ShipmentID INTEGER  primary key,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
foreign key (SupplierID) REFERENCES Suppliers(SupplierID),
foreign key (OrderID) REFERENCES Orders(OrderID)

);

**Output:**

![image](https://github.com/user-attachments/assets/7b041728-4b16-4ed2-af93-b1499ecfff75)


**Question 7**
![image](https://github.com/user-attachments/assets/7f1d3d4b-8f08-471a-9924-edf166cf57c1)

create table Invoices(
InvoiceID INTEGER primary key,
InvoiceDate DATE,
DueDate DATE,
Amount REAL,
CHECK (DueDate>InvoiceDate),
CHECK (Amount>0)
);

**Output:**

![image](https://github.com/user-attachments/assets/70992c79-2872-45f1-a829-da9c15cfb296)

**Question 8**
![image](https://github.com/user-attachments/assets/2ce480f1-3f72-4634-9e63-f7cc879fa5b1)

create table orders(
ord_id TEXT NOT NULL CHECK(LENGTH(ord_id)=4),
item_id TEXTNOT NULL,
ord_date DATE,
ord_qty INTEGER,
cost INTEGER,
PRIMARY KEY (item_id,ord_date)
);
**Output:**

![image](https://github.com/user-attachments/assets/77606cfb-c48c-48ed-a3f0-0554d04e8a70)


**Question 9**

![image](https://github.com/user-attachments/assets/c8f2d3fe-f6a3-4e21-8552-551eea75b427)

INSERT INTO Customers(CustomerID,Name,Address)
VALUES(304,'Peter Parker','Spider St');
**Output:**

![image](https://github.com/user-attachments/assets/3120f0b0-dfae-4b55-9c1b-394fda2fd44b)


**Question 10**

![image](https://github.com/user-attachments/assets/5777ff75-bcfe-4cfa-9798-1e86b9037f2d)


ALTER TABLE Employees
ADD COLUMN Date_of_joining Date;

ALTER TABLE Employees
RENAME COLUMN job_title TO Designation;

**Output:**


![image](https://github.com/user-attachments/assets/bb2421e0-03f9-49e9-ae37-5b96683270eb)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
