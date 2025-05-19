# Experiment 9: PL/SQL – Procedures and Functions

## AIM
To understand and implement procedures and functions in PL/SQL for performing various operations such as calculations, decision-making, and looping.

---

## THEORY

PL/SQL (Procedural Language/SQL) extends SQL by adding procedural constructs like variables, conditions, loops, procedures, and functions. Procedures and functions are subprograms that help modularize the code and improve reusability.

### **Procedure**
A PL/SQL **procedure** is a subprogram that performs a specific action. It does not return a value directly but can return values using `OUT` parameters.

**Syntax:**
```sql
CREATE OR REPLACE PROCEDURE procedure_name (parameters)
IS
BEGIN
   -- statements
END;
```

To call the procedure

```sql
EXEC procedure_name(arguments);
```

### **Function**
A PL/SQL **function** is a subprogram that returns a single value using the RETURN keyword.

```sql
CREATE OR REPLACE FUNCTION function_name (parameters)
RETURN datatype
IS
BEGIN
   -- statements
   RETURN value;
END;
```

To call the function:

```sql
SELECT function_name(arguments) FROM DUAL;
```

Key Differences:

-A procedure does not return a value, whereas a function must return a value.
-Functions can be called from SQL queries, procedures cannot (in most cases).

## 1. Write a PL/SQL Procedure to Find the Square of a Number

### Steps:
- Create a procedure named `find_square`.
- Declare a parameter to accept a number.
- Inside the procedure, compute the square of the input number.
- Use `DBMS_OUTPUT.PUT_LINE` to display the result.
- Call the procedure with a number as input.

**PROGRAM**
~~~

CREATE OR REPLACE PROCEDURE find_square (p_num IN NUMBER) AS
   v_square NUMBER;
BEGIN
   -- Compute the square of the input number
   v_square := p_num * p_num;

   -- Display the result using DBMS_OUTPUT.PUT_LINE
   DBMS_OUTPUT.PUT_LINE('Square of ' || p_num || ' is ' || v_square);
END;
~~~

**OUTPUT**


![image](https://github.com/user-attachments/assets/13a837f3-2234-41f8-b93f-4fb22ed2a891)

**Expected Output:**  
Square of 6 is 36

---

## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.

**PROGRAM**
~~~

DECLARE
   v_result NUMBER;
BEGIN
   -- Step 3: Call the function with input 5
   v_result := get_factorial(5);

   -- Step 4: Display the result
   DBMS_OUTPUT.PUT_LINE('Factorial of 5 is ' || v_result);
END;
~~~

**OUTPUT**


![image](https://github.com/user-attachments/assets/cf2b7e09-761f-4925-9476-66fde1b9d953)

**Expected Output:**  
Factorial of 5 is 120

---

## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.

**PROGRAM**
~~~

CREATE OR REPLACE PROCEDURE check_even_odd (p_num IN NUMBER) AS
BEGIN
   -- Step 2: Use MOD function to check if the number is even or odd
   IF MOD(p_num, 2) = 0 THEN
      DBMS_OUTPUT.PUT_LINE(p_num || ' is Even');
   ELSE
      DBMS_OUTPUT.PUT_LINE(p_num || ' is Odd');
   END IF;
END;
~~~

**OUTPUT**


![image](https://github.com/user-attachments/assets/f21252fa-dd6c-4060-b6d7-bba58d5cec4c)

**Expected Output:**  
12 is Even

---

## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.

**PROGRAM**
~~~

DECLARE
   v_result NUMBER;
BEGIN
   -- Call the function with input 1234
   v_result := reverse_number(1234);

   -- Display the result
   DBMS_OUTPUT.PUT_LINE('Reversed number of 1234 is ' || v_result);
END;
~~~

**OUTPUT**


![image](https://github.com/user-attachments/assets/858ed115-7953-4065-9dfe-c0dd8f8cf4d7)

**Expected Output:**  
Reversed number of 1234 is 4321

---

## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.

**PROGRAM**
~~~
CREATE OR REPLACE PROCEDURE print_table (p_num IN NUMBER) AS
BEGIN
   -- Step 2: Loop from 1 to 10 to display the multiplication table
   FOR i IN 1..10 LOOP
      DBMS_OUTPUT.PUT_LINE(p_num || ' x ' || i || ' = ' || (p_num * i));
   END LOOP;
END;
~~~

**OUTPUT**

![image](https://github.com/user-attachments/assets/a34ab921-954b-43d0-80e6-f90de9f1b9f2)

**Expected Output:**  
Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50

## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
