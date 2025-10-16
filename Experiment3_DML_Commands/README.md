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
Write a SQL statement to Increase the salary by 500 and email as 'updated' for employees with job ID 'SA_REP' and commission percentage greater than 0.15

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id


```sql
update Employees set salary=salary+500 , email="updated" where job_id="SA_REP" and commission_pct>0.15; 
```

**Output:**

<img width="917" height="348" alt="image" src="https://github.com/user-attachments/assets/26cc4b4d-0673-446c-a693-23ae0c598a18" />


**Question 2**
---
Write a SQL statement to update the product_name as 'Grapefruit' whose product_id is 4 in the products table.

products table

---------------
product_id
product_name
category_id
availability

```sql
update products set product_name="Grapefruit" where product_id=4;

```

**Output:**

<img width="808" height="127" alt="image" src="https://github.com/user-attachments/assets/08d25ab5-7077-4892-9129-0edb99626c15" />

**Question 3**
---
Change the supplier name to upper case where contact person contains ' Singh' in suppliers table.

name               type
-----------------  ---------------
supplier_id        INT
supplier_name      VARCHAR(100)
contact_person     VARCHAR(100)
phone_number       VARCHAR(20)
email              VARCHAR(100)
address            VARCHAR(250)

```sql
update suppliers set supplier_name= UPPER(supplier_name) where contact_person like '%singh%';
```

**Output:**

<img width="1257" height="218" alt="image" src="https://github.com/user-attachments/assets/248f7a39-4b36-4eea-a0db-a46ece56d917" />


**Question 4**
---
Write a SQL statement to Update the hire_date of employees in department 50 to 2024-01-24.

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id
```sql
update employees set hire_date='2024-01-24' where department_id=50;
```

**Output:**

<img width="577" height="165" alt="image" src="https://github.com/user-attachments/assets/6ae39954-c3e3-437b-b560-e9cfba5ee265" />


**Question 5**
---
Write a SQL query to Delete customers from 'customer' table where 'WORKING_AREA' is 'New York'.

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.00 | BBBBSBB      | A008       |

```sql
delete from customer  where working_area='New York';
```

**Output:**

<img width="1166" height="577" alt="image" src="https://github.com/user-attachments/assets/f2da721e-0ca5-414d-bfca-d0efca6d86e7" />


**Question 6**
---
Write a SQL query to Delete a Specific Surgery which was made on 28th Feb 2024.

Sample table: Surgeries

attributes: surgery_id, patient_id, surgeon_id, surgery_date
```sql
delete from Surgeries where surgery_date='2024-02-28';
```

**Output:**

<img width="768" height="245" alt="image" src="https://github.com/user-attachments/assets/65c347d5-7585-4f6e-b9db-e32d4c598b4f" />


**Question 7**
---
Write a SQL query to remove rows from the table 'customer' with the following condition -

1. 'cust_city' should begin with the letter 'L',

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.00 | BBBBSBB      | A008       |
```sql
delete from customer where cust_city like 'L%';
```

**Output:**

<img width="1171" height="812" alt="image" src="https://github.com/user-attachments/assets/49b4917c-7ca6-4167-a612-a11964e0b4cf" />


**Question 8**
---
Write a SQL query to Delete customers from 'customer' table where 'CUST_COUNTRY' is neither 'India' nor 'USA'.

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.00 | BBBBSBB      | A008       |
```sql
delete from customer where cust_country not in("India","USA");
```

**Output:**

<img width="1171" height="375" alt="image" src="https://github.com/user-attachments/assets/515198d4-ce13-443f-ad78-d654635076cb" />

**Question 9**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is exactly 2.

 
Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.00 | BBBBSBB      | A008       |

```sql
delete from customer where grade=2;
```

**Output:**

<img width="217" height="420" alt="image" src="https://github.com/user-attachments/assets/cca398e8-2a2c-4ca2-add0-d0879111fd3f" />


**Question 10**
---
Write a SQL statement to Find those salesmen with all information whose name containing the 1st character is 'N' and the 4th character is 'l' and rests may be any character.

salesman table

cid         name         type        
----------  -----------  ----------  
0           salesman_id  numeric(5)  
1           name         varchar(30)  
2           city         varchar(15)  
3           commission   decimal(5,2) 

```sql
select * from salesman where name like 'N_i%';

```

**Output:**

![Uploading image.png…]()

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
