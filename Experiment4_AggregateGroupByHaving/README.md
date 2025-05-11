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


![image](https://github.com/user-attachments/assets/cf2d9e38-2523-4008-804e-6b616a71e28f)

SELECT MAX (purch_amt) AS MAXIMUM
FROM orders;

**Output:**

![image](https://github.com/user-attachments/assets/ff7f4557-8f0f-4997-afc5-55d6d2b7784c)


**Question 2**


![image](https://github.com/user-attachments/assets/80b8ba6c-cf51-450c-9f9b-774a85895e22)

SELECT MIN(purch_amt) AS MINIMUM
FROM orders;

**Output:**

![image](https://github.com/user-attachments/assets/162550ac-1d35-42cc-bd70-38a58730bc4c)


**Question 3**


![image](https://github.com/user-attachments/assets/4660b417-938b-472c-baa7-3f2f4938af7e)

SELECT SUM(purch_amt) AS TOTAL
FROM orders;

**Output:**

![image](https://github.com/user-attachments/assets/039de0a4-9072-4f11-8066-51f85d5f0af1)

**Question 4**


![image](https://github.com/user-attachments/assets/44f9a01a-4014-44f8-bf97-d2b8528c7150)

SELECT patientID,
    COUNT(Medication) AS TotalMedications
FROM prescriptions
GROUP BY patientID;

**Output:**

![image](https://github.com/user-attachments/assets/e9a6e72e-e2fc-4fd8-9fda-d554ebf93d70)

**Question 5**


![image](https://github.com/user-attachments/assets/00659b23-adbd-42d4-b86f-d8e8c608dae6)


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

![image](https://github.com/user-attachments/assets/ecef4178-4183-4790-ae8b-df2d3e6367b4)


**Question 6**


![image](https://github.com/user-attachments/assets/60f1c66a-8af5-4ac7-80a1-2b58e5275344)

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

![image](https://github.com/user-attachments/assets/55bb6bb8-6182-41ed-9bfa-f4b00e37c458)

**Question 7**


![image](https://github.com/user-attachments/assets/877971ac-9866-449c-878b-f224685c1986)

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

![image](https://github.com/user-attachments/assets/f4425dbe-1b9d-462b-b98b-9b11aeed794e)

**Question 8**


![image](https://github.com/user-attachments/assets/7bc532a2-64c8-4b33-b134-9ca0c6e6c573)

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

![image](https://github.com/user-attachments/assets/14282ea0-a4dd-446d-934f-55c9209db23c)


**Question 9**


![image](https://github.com/user-attachments/assets/059ad87c-5bb8-4d06-842f-b83e85ee6c99)

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

![image](https://github.com/user-attachments/assets/38ac572d-7510-4f47-8000-3e8c6b1ed75a)

**Qustion 10**


![image](https://github.com/user-attachments/assets/f6ce0bf6-7a94-4faa-bafd-2716780ee233)

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

![image](https://github.com/user-attachments/assets/ff1e5f5d-1887-4f9a-b0e9-f92f5a87b685)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
