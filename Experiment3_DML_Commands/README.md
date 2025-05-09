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


![image](https://github.com/user-attachments/assets/7c15808a-0314-4c9c-89c0-e0360c12d203)

update sales

set sell_price=sell_price+3
where product_id IN (SELECT product_id FROM products WHERE supplier_id=4);

**Output:**

![image](https://github.com/user-attachments/assets/de6eda63-fec3-4e3b-b94c-e60d47e78f99)


**Question 2**


![image](https://github.com/user-attachments/assets/71ae2470-749e-46e3-8617-44381491f82c)

SELECT 
    id,
    value1,
    CASE 
       WHEN value1 % 2=0 THEN 'Even'
       ELSE 'Odd'
    END AS parity
    
FROM 
    calculations;
    
**Output:**

![image](https://github.com/user-attachments/assets/47b97d68-5feb-4807-8e32-dbe136b9d172)

**Question 3**


![image](https://github.com/user-attachments/assets/5e13ee56-235f-4712-81e7-692623fdf70f)

SELECT DISTINCT city
FROM customers;

**Output:**

![image](https://github.com/user-attachments/assets/3a0428bb-a653-458c-9d1f-2b73ea8b2f57)

**Question 4**


![image](https://github.com/user-attachments/assets/585ae3e5-b0b5-44a5-b096-2d560d839f7d)

SELECT*
FROM emp
WHERE strftime('%Y',hiredate)='2022';

**Output:**

![image](https://github.com/user-attachments/assets/488a8ee3-5b78-4562-b248-2bc9bec35f5a)

**Question 5**


![image](https://github.com/user-attachments/assets/7fdc06d2-5319-43b2-b063-55a978f4c79d)

SELECT
    product_id,
    discounted_price,
    discount_percentage,
    discounted_price / (1-discount_percentage) AS original_price
FROM
    products;
    
**Output:**

![image](https://github.com/user-attachments/assets/a2e879a0-67c6-41d9-9a37-ba26ea6f00b8)

**Question 6**


![image](https://github.com/user-attachments/assets/28a650cf-d5d2-4ded-9799-c968514a648b)


SELECT 
    UPPER(FirstName) As FirstName,
    UPPER(LastName) As LastName,
    EmployeeID
FROM
    employees
ORDER BY 
    EmployeeID DESC;

**Output:**

![image](https://github.com/user-attachments/assets/32867f52-c4b7-4079-a96e-2b492915e1f4)

**Question 7**


![image](https://github.com/user-attachments/assets/e19ee9a7-6030-406e-b0c8-cea1f1231d02)


UPDATE sales
SET sell_price=sell_price*1.05
WHERE product_id=15
  AND sale_date='2023-01-31';

**Output:**

![image](https://github.com/user-attachments/assets/0d7a6576-83c6-4707-a7b3-27e12cb81db9)

**Question 8**


![image](https://github.com/user-attachments/assets/9ea937c2-10d9-4546-ac2d-ccee02010fc4)


DELETE FROM surgeries
WHERE surgery_id=3
   OR surgeon_id=4;

**Output:**

![image](https://github.com/user-attachments/assets/efc93422-c43b-4eaf-9247-d73b440e964c)

**Question 9**


![image](https://github.com/user-attachments/assets/d5956ed6-e458-4ed7-8e9b-46bfe6108877)

UPDATE Employees
SET salary=salary*2
WHERE department_id=20
  AND job_id LIKE '%MAN';

**Output:**

![image](https://github.com/user-attachments/assets/043a1d92-ad40-4763-916e-c640d5b17ac1)

**Question 10**


![image](https://github.com/user-attachments/assets/bb722975-96d3-4dae-bb43-ffbfffb8347d)

DELETE FROM Doctors
WHERE doctor_id=1;

**Output:**

![image](https://github.com/user-attachments/assets/dd953a63-7740-4191-8341-eb301f53ff0e)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
