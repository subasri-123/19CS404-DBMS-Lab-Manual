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

![image](https://github.com/user-attachments/assets/a5ebbf4d-94f2-493e-b4f3-6086010439e8)

select *
from CUSTOMERS
where SALARY>1500;

**Output:**

![image](https://github.com/user-attachments/assets/1cefdd6a-c25e-4f6a-a57c-7a0539ead328)


**Question 2**

![image](https://github.com/user-attachments/assets/3e24f76a-6105-40b5-9771-345a8aefbe73)

SELECT student_name, grade
FROM GRADES
WHERE (subject,grade)IN (
    SELECT subject, MAX(grade)
    FROM GRADES
    GROUP BY subject
);

**Output:**

![image](https://github.com/user-attachments/assets/d24855a0-fbf9-4e33-8677-5f85e955eb60)


**Question 3**

![image](https://github.com/user-attachments/assets/5140688f-a599-4ac8-9296-7645c9f9acc6)

SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi';

**Output:**

![image](https://github.com/user-attachments/assets/310fadb1-1182-41ee-8149-0f195fceb54b)


**Question 4**

![image](https://github.com/user-attachments/assets/da7128af-6612-4a2a-a8a9-568e455ac408)

SELECT DISTINCT s.commission
FROM salesman s
WHERE s.city='Paris';

**Output:**

![image](https://github.com/user-attachments/assets/4d3b2089-41fb-4f96-b02a-e59147d68ce2)

**Question 5**
![image](https://github.com/user-attachments/assets/c44ed3a8-ea3d-4957-aa39-1529a25e14ba)

SELECT o.ord_no,o.purch_amt,o.ord_date,o.customer_id,o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id=s.salesman_id
WHERE s.city='New York';

**Output:**

![image](https://github.com/user-attachments/assets/f6f28419-5687-4f5a-863e-30098c32debd)


**Question 6**

![image](https://github.com/user-attachments/assets/d809cdc2-7ed8-40a5-a6a2-664493cd6fcf)

SELECT ord_no,purch_amt,ord_date,customer_id,salesman_id
FROM orders
WHERE purch_amt > (
    SELECT AVG(purch_amt)
    FROM orders
    WHERE ord_date ='2012-10-10'
);

**Output:**

![image](https://github.com/user-attachments/assets/7b480085-85b7-44a2-96b5-908eba00bcf2)

**Question 7**

![image](https://github.com/user-attachments/assets/d97823f1-8eb3-406b-b110-bdaa6a9bb4c2)

SELECT o.ord_no,o.purch_amt,o.ord_date,o.customer_id,o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.city='New York';

**Output:**

![image](https://github.com/user-attachments/assets/d533c4d7-f3d4-4de2-8ba6-d65a70a7674c)


**Question 8**

![image](https://github.com/user-attachments/assets/b172ba52-41da-4294-97a3-5d2c092b31c1)

SELECT id,name,city,email,phone
FROM customer WHERE city!=(
    SELECT city FROM customer
    WHERE id = (SELECT MAX (id) FROM customer)
);

**Output:**

![image](https://github.com/user-attachments/assets/c62f5938-a2a3-4309-8d6e-b4db6374f4a1)


**Question 9**

![image](https://github.com/user-attachments/assets/bb8bbf10-92ac-4d91-97b2-a4e3e79f97c5)

SELECT name
FROM customer 
WHERE phone NOT IN(
     SELECT phone
     FROM customer 
     GROUP BY phone
     HAVING COUNT(phone)>1
     
);

**Output:**

![image](https://github.com/user-attachments/assets/7db69a76-8508-47de-8ccd-c6a30ed614b4)


**Question 10**

![image](https://github.com/user-attachments/assets/df7ad685-2652-4164-9f59-61d77b1ea786)


SELECT g.student_id,g.student_name,g.subject,g.grade
FROM grades g
WHERE g.grade=(
    SELECT MAX(grade)
    FROM grades
    WHERE subject=g.subject
);

**Output:**

![image](https://github.com/user-attachments/assets/f1cdb138-67e1-413b-8a93-2674dac5ffb8)


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
