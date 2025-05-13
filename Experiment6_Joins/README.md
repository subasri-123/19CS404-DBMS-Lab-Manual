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

![image](https://github.com/user-attachments/assets/ab14bfa5-1855-4c9f-aac1-97f0526b07da)


SELECT 
     p.first_name AS patient_name,
     d.specialization AS Doctor_specialization
FROM
     patients p
INNER JOIN
     doctors d ON p.doctor_id=d.doctor_id
WHERE 
     p.admission_date BETWEEN '2024-01-01' AND '2024-01-31';

**Output:**

![image](https://github.com/user-attachments/assets/21617668-c297-4c04-a360-f04af35dbd50)

**Question 2**

![image](https://github.com/user-attachments/assets/1f943158-3cf3-48ea-83c1-79ca33ba8679)

SELECT 
    p.*,
    d.specialization AS doctor_specialization
FROM
    patients p
INNER JOIN 
    doctors d ON P.doctor_id=d.doctor_id;

**Output:**

![image](https://github.com/user-attachments/assets/390803a0-3b25-4df4-8654-0d01721144d8)

**Question 3**

![image](https://github.com/user-attachments/assets/d4b124a9-742e-4254-a12e-d22326aaa71c)

SELECT 
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.commission
FROM
    customer c
JOIN
    salesman s ON c.salesman_id=s.salesman_id;

**Output:**

![image](https://github.com/user-attachments/assets/293c9224-5df1-4db1-9acf-5fea828f2a22)

**Question 4**

![image](https://github.com/user-attachments/assets/863fc1fa-e673-495c-bac3-37347882bd1b)

SELECT 
    c.*
FROM
    customer c
LEFT JOIN
     orders o ON c.customer_id=o.customer_id
WHERE
    o.ord_date BETWEEN '2012-08-01' AND '2012-08-30';

**Output:**

![image](https://github.com/user-attachments/assets/19cd7b7c-d0e5-436c-a250-9f4f0a7518ec)

**Question 5**

![image](https://github.com/user-attachments/assets/627ac686-b960-42f2-bf04-a78b3c9a0d22)

SELECT 
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.commission
FROM
    customer c
JOIN 
    salesman s ON c.salesman_id=s.salesman_id
WHERE
    s.commission > 0.12;
    
**Output:**

![image](https://github.com/user-attachments/assets/0db58182-bca8-4410-ac70-d742cded404b)

**Question 6**

![image](https://github.com/user-attachments/assets/d42da5fb-af0a-4c45-aa86-49d293bd1760)

SELECT 
    p.first_name AS patient_name
FROM
    patients p
INNER JOIN 
    TEST_RESULT tr ON p.patient_id=tr.patient_id
WHERE 
    tr.test_name='Blood Pressure';

**Output:**

![image](https://github.com/user-attachments/assets/2fd3ba29-8bfe-4943-9ba0-df7d8b2c5e97)

**Question 7**

![image](https://github.com/user-attachments/assets/e0d1a5a2-2f27-4b1b-870a-3c09033c5bc8)

SELECT 
    p.first_name AS patient_name,
    d.first_name AS doctor_name
FROM
    patients p
INNER JOIN
    doctors d ON p.doctor_id = d.doctor_id
WHERE
    p.date_of_birth > '1990-01-01';

**Output:**

![image](https://github.com/user-attachments/assets/ec570cf2-5d8e-45a5-b1ee-1076f0ffe9e3)

**Question 8**

![image](https://github.com/user-attachments/assets/58bb4887-d8b4-4c5d-8ce4-0961dd8084af)

SELECT
    c.cust_name
FROM
    customer c
LEFT JOIN
    orders o ON c.customer_id =o.customer_id
WHERE
    o.purch_amt < 100;

**Output:**

![image](https://github.com/user-attachments/assets/95e46868-898d-4071-8e8c-a724f5c203f0)

**Question 9**

![image](https://github.com/user-attachments/assets/6bd037db-5286-4f92-8d42-3e61ae046f6d)

SELECT
    p.first_name AS patient_name,
    t.*
FROM
    patients p
INNER JOIN 
    test_results t ON p.patient_id = t.patient_id
WHERE
    p.admission_date BETWEEN '2024-01-01' AND '2024-01-31';

**Output:**

![image](https://github.com/user-attachments/assets/2df01bfe-b8dc-4cf8-8dfc-2eee58114958)

**Question 10**

![image](https://github.com/user-attachments/assets/d96434ca-22a5-4554-9b4b-bc743ed5658d)

SELECT
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM
    orders o
JOIN
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;

**Output:**

![image](https://github.com/user-attachments/assets/e10e68f5-3c5a-49d5-95da-44c8543a25b3)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
