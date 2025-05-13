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
![image](https://github.com/user-attachments/assets/bab96939-8ecc-471a-967e-2b35af4b9e25)

SELECT MAX (purch_amt) AS MAXIMUM
FROM orders;

**Output:**

![image](https://github.com/user-attachments/assets/9c9f1f61-27be-4fda-a7a3-c4f990d71afc)


**Question 2**

![image](https://github.com/user-attachments/assets/d2005891-1a55-433e-844e-ab83db352508)

SELECT MIN(purch_amt) AS MINIMUM
FROM orders;

**Output:**

![image](https://github.com/user-attachments/assets/08751e68-d8ba-48da-abfd-d290f96e1ccf)

**Question 3**

![image](https://github.com/user-attachments/assets/2969f972-2ef6-42b8-b58f-abfe7dbb6d7a)

SELECT SUM(purch_amt) AS TOTAL
FROM orders;

**Output:**

![image](https://github.com/user-attachments/assets/c72e4dc6-727a-464d-a819-7347b21727f6)

**Question 4**

![image](https://github.com/user-attachments/assets/44bbdadb-455d-4bf0-a15e-7966c7869a2a)

SELECT patientID,
    COUNT(Medication) AS TotalMedications
FROM prescriptions
GROUP BY patientID;

**Output:**

![image](https://github.com/user-attachments/assets/f3d224d2-a0b3-48f9-b4da-18a2a527715c)

**Question 5**

![image](https://github.com/user-attachments/assets/50a80468-8a90-48cc-8650-1ee49aea58a5)


SELECT
    "Insurance Company",
    COUNT(patientID) AS TotalExpiredPatients
FROM
    Insurance
WHERE
    STRFTIME('%Y'-'%m'-'%d','now')>SUBSTR(ValidityPeriod,10,10)
GROUP BY
    "Insurance Company";

**Output:**

![image](https://github.com/user-attachments/assets/873ced95-633a-4383-b821-58aa37ec8b85)

**Question 6**

![image](https://github.com/user-attachments/assets/839c2bae-e59f-43c2-8c3a-fb6b82ca9df8)

SELECT
    STRFTIME('%H',AppointmentDateTime)AS HourOfDay,
    COUNT(*) AS TotalAppointments
FROM
    Appointments
GROUP BY
    HourOfDay
ORDER BY
    HourOfDay;

**Output:**

![image](https://github.com/user-attachments/assets/0d6e549d-e085-4b44-8546-422c2d30845e)

**Question 7**

![image](https://github.com/user-attachments/assets/642d5da5-24da-411c-9d66-3aa5084911de)

SELECT
    jdate,
    AVG(workhour) 
FROM
    employee1
GROUP BY
    jdate
HAVING
    AVG(workhour)<10;

**Output:**

![image](https://github.com/user-attachments/assets/ecbd47f7-fc2f-4b03-9071-ea07ff4ba3d9)


**Question 8**

![image](https://github.com/user-attachments/assets/b0780ceb-7d55-4ea7-b5c3-07c408af4c1e)

SELECT
    category_id,
    SUM(price*category_id) AS Revenue
FROM 
    products
GROUP BY  
    category_id
HAVING
    SUM(price*category_id)>25;
    
**Output:**

![image](https://github.com/user-attachments/assets/d06c12c2-a558-413b-bb0e-e25ef1e094e0)


**Question 9**

![image](https://github.com/user-attachments/assets/7b5f0ac5-5e59-446a-a693-ff28cc2c7547)

SELECT
    city,
    AVG(income) 
FROM
    employee
GROUP BY
    city
HAVING
    AVG(income)>500000;

**Output:**

![image](https://github.com/user-attachments/assets/fb4e7b4a-c8f7-48a7-97a1-0ef701eceb71)


**Question 10**

![image](https://github.com/user-attachments/assets/b6d30440-7337-42d8-9f30-51245a6f799f)

SELECT
    city,
    SUM(Income) AS Income
FROM
    employee
GROUP BY
    city
HAVING
    SUM(Income)>200000;
    
**Output:**

![image](https://github.com/user-attachments/assets/faa9c239-6c1f-4c7a-a433-42e8994d001c)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
