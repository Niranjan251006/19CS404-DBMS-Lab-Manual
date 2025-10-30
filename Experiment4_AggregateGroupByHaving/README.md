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
--
<img width="1220" height="517" alt="438625577-36ff204e-3f8b-416d-82fe-eb1d8f89b143" src="https://github.com/user-attachments/assets/92efc77d-28ef-4397-bb49-7e3bc5895e88" />


```sql
 select date(AppointmentDateTime) as AppointmentDate, count(*) as  TotalAppointments
from Appointments
group by AppointmentDate;
```

**Output:**

<img width="1253" height="556" alt="438625779-47d1740e-89ab-4a74-b978-2dd156b5452a" src="https://github.com/user-attachments/assets/e0e8ae20-119b-4733-a963-345fc1e4d46d" />


**Question 2**
---
<img width="1253" height="368" alt="438626791-458094fb-3ec1-464b-a0b1-0e599bf83844" src="https://github.com/user-attachments/assets/e63d88f0-daf4-4a1f-a88a-e0feae6cd160" />


```sql
 select name,email,length(email) as  min_email_length
from customer
order by length(email)
limit 1;
```

**Output:**
<img width="1192" height="266" alt="438626832-7ff52baa-ed62-4bbd-8ecd-103d7fc949f4" src="https://github.com/user-attachments/assets/f812cdd3-a250-4de2-8c54-2447f3969400" />



**Question 3**
---
<img width="1268" height="483" alt="438627161-d054f243-ab5a-49e1-bdd9-071c29ff5199" src="https://github.com/user-attachments/assets/8e2d4134-40ce-4844-9063-3b332f4071f7" />

```sql
 select avg(length(email)) as avg_email_length
from customer
order by length(email)
limit 1;
```

**Output:**

<img width="1258" height="297" alt="438627215-c279b3db-a9e8-4dcf-b38a-cd467996b4f9" src="https://github.com/user-attachments/assets/ee1ed032-23a5-4c8b-b331-e9ebd98f98e9" />


**Question 4**
---
<img width="1177" height="372" alt="438628107-08bb463d-4280-40ab-9aa0-44359d76ce0a" src="https://github.com/user-attachments/assets/ae2db71d-2d46-42e3-925f-dfd875b3766e" />

```sql
select sum(purch_amt) as TOTAL
from orders

```

**Output:**
<img width="1243" height="297" alt="438628183-2eaa2a23-41eb-4ebe-874d-f3cb8da408dc" src="https://github.com/user-attachments/assets/2c9a359a-f8a0-4fc0-8c51-3203266cd898" />



**Question 5**
---

<img width="1248" height="396" alt="438628502-dac02082-7b58-437f-b882-6a4a8577855e" src="https://github.com/user-attachments/assets/995c12aa-131b-4b6b-a85d-694e0da178ad" />

```sql
select jdate,MIN(workhour)
from employee1
group by jdate
having MIN(workhour) <10 ;
```

**Output:**
<img width="1241" height="377" alt="438628581-7fb2af83-d2fc-4b63-afdc-155a15b9ed1f" src="https://github.com/user-attachments/assets/312709fe-377c-4935-8f07-e99b3143943b" />

**Question 6**
---
<img width="823" height="392" alt="438629014-60415fd3-634c-495a-8976-6e0c69331fc7" src="https://github.com/user-attachments/assets/1311a8d6-1e84-443d-8d58-df7cbbb1e210" />

```sql
select max(purch_amt) as MAXIMUM
from orders
order by purch_amt;
```

**Output:**

<img width="1133" height="285" alt="438629367-7856ad29-281c-46cd-b4cf-9b0317ccaaa3" src="https://github.com/user-attachments/assets/6c2911d0-998a-4a7a-836e-a037d73d3e76" />


**Question 7**
---
<img width="1090" height="355" alt="438629967-69505d3d-ec33-4ddb-ad2a-bc32a6897b2d" src="https://github.com/user-attachments/assets/3d70e0b4-0e20-44a6-ab63-492397d040d1" />


```sql
 select address,AVG(salary)
from customer1
group by address
having avg(salary) > 5000
```

**Output:**
<img width="1049" height="344" alt="438630070-2b6c1fe5-e596-478e-9bf8-6815e4b0244c" src="https://github.com/user-attachments/assets/b863ddcb-76a9-4a2d-bc89-7fad8dfd27e2" />


**Question 8**
---
<img width="1265" height="384" alt="438630271-338964ef-b49c-4a0c-8da4-e748cfac32a8" src="https://github.com/user-attachments/assets/293d7f06-01c1-44ff-8f1a-e3719d1501af" />


```sql
 select category_id,count(product_name)
from products
group by category_id
having min(category_id) <3
```

**Output:**
<img width="1234" height="325" alt="438630320-10b3464b-e56c-47a0-97e5-9c196fbbfc27" src="https://github.com/user-attachments/assets/fdd0cee2-4da7-4d6c-be52-fe88aa0b0a82" />


**Question 9**
---

<img width="1001" height="419" alt="438630761-475ab1a2-c99e-491c-8eaf-59d85ffe746d" src="https://github.com/user-attachments/assets/ae5458d1-64af-439a-8007-0cad7dd768dc" />

```sql
select sum(inventory) as total
from fruits
where unit ='LB'
```

**Output:**
<img width="996" height="289" alt="438630798-6a62558f-388d-4e8c-ba0b-8b2802c8642d" src="https://github.com/user-attachments/assets/e6081086-4840-4cdf-ac76-033112e995cc" />


**Question 10**
---
<img width="870" height="386" alt="438631726-31812179-ff28-4a67-ae56-1348dbb07d93" src="https://github.com/user-attachments/assets/ce967f50-430c-4c81-af82-34ac4e2ab025" />

```sql
select count(distinct salesman_id) as COUNT
from orders

```

**Output:**

<img width="629" height="244" alt="438631758-a87afd7f-b9d4-45fa-a6ea-86cd136bd9fd" src="https://github.com/user-attachments/assets/48363a21-744c-420c-a29c-4953928291e4" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
