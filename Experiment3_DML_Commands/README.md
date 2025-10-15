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
<img width="1193" height="354" alt="495076041-8da958c2-a907-459c-b928-d41b7855b705" src="https://github.com/user-attachments/assets/4776bc30-3ec6-4200-aea7-d6e56134d8c7" />


```sql
CREATE TABLE Employees(
    EmployeeID Integer PRIMARY KEY,
    FirstName TEXT NOT NULL,
    LastName TEXT NOT NULL,
    Email TEXT UNIQUE,
    Salary REAL CHECK (Salary > 0),
    DepartmentID INTEGER,
    FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID)
);
```

**Output:**
<img width="1603" height="396" alt="495076504-4d97faa9-0c57-4f6a-ad2b-229c524fa3b1" src="https://github.com/user-attachments/assets/bc7b1883-c980-41d4-8e4f-0f7ea9704d83" />



**Question 2**
---
<img width="1048" height="438" alt="495076767-969d9392-fbf2-4a7f-af3c-4c2369c11d55" src="https://github.com/user-attachments/assets/b0fde21c-5587-47a9-bb2f-dd8b62d942e4" />


```sql
CREATE TABLE Events(
EventID INTEGER,
EventName TEXT,
EventDate DATE
);
```

**Output:**

<img width="1612" height="366" alt="495076986-cf6d99f3-5f29-47e9-b410-7de0ac6d0501" src="https://github.com/user-attachments/assets/ce1ca98c-f0ee-47fa-b0cc-6d0faa721a89" />


**Question 3**
---
<img width="797" height="352" alt="495077141-064490b4-417b-4508-95fe-ea103e1dc7ca" src="https://github.com/user-attachments/assets/abcd026f-0f8a-48dd-8a53-7ba03f455223" />


```sql
INSERT INTO Customers (CustomerID, Name, Address)
VALUES (304,'Peter Parker', 'Spider St');
```

**Output:**

<img width="1386" height="425" alt="495077378-1e6c4a10-0338-4e6f-98bc-b9ab76d60286" src="https://github.com/user-attachments/assets/3fb54974-65db-4bc7-b40c-7566fbfb4933" />


**Question 4**
---
<img width="1008" height="345" alt="495077501-33528e68-35db-4949-84f9-f17c1729db08" src="https://github.com/user-attachments/assets/2e3c88c5-9fe5-466a-a9ca-e63d36a246e9" />


```sql
CREATE TABLE Invoices(
InvoiceID INTEGER PRIMARY KEY,
InvoiceDate DATE,
DueDate DATE,
Amount REAL CHECK (Amount > 0),
CHECK (DueDate > InvoiceDate)
);
```

**Output:**

<img width="1600" height="351" alt="495077641-03871872-aa8b-49b3-a21d-53d707ae35c9" src="https://github.com/user-attachments/assets/5af4f5be-118a-4d9c-895d-153396fbda25" />


**Question 5**
---
<img width="1066" height="612" alt="495077756-697b6d8a-df17-461a-b505-bc64e4a7c6c1" src="https://github.com/user-attachments/assets/75e49971-c3f3-4843-af07-bd546faedf77" />



```sql
ALTER TABLE Companies ADD COLUMN designation varchar(50);
ALTER TABLE Companies ADD COLUMN net_salary number;
ALTER TABLE Companies ADD COLUMN dob date;
```

**Output:**
<img width="1848" height="472" alt="495077915-35d9af50-892d-4ad4-ae74-3818de17067c" src="https://github.com/user-attachments/assets/f6bea206-6fa0-45b4-b976-61e8ed1ee249" />


**Question 6**
---
<img width="908" height="359" alt="495078032-996d0d91-0cd8-42f2-8ec4-6a680081f70b" src="https://github.com/user-attachments/assets/b68a6162-cb5f-452b-bced-b95e25be9a23" />


```sql
INSERT INTO Customers (CustomerID, Name, Address, Email)
SELECT CustomerID, Name, Address, Email
FROM Old_customers;
```

**Output:**
<img width="1689" height="368" alt="495082298-0ae8f4fd-9804-4c3a-940b-856edb1136a4" src="https://github.com/user-attachments/assets/4d4ce061-9572-4825-ba71-1a82c79977a7" />



**Question 7**
---

<img width="1513" height="390" alt="495082543-b79686f2-4799-4fe4-b145-f31da66ca347" src="https://github.com/user-attachments/assets/1e7214dd-d996-4a3d-af33-b68677c80f3d" />

```sql
CREATE TABLE Products(
ProductID INTEGER PRIMARY KEY,
ProductName TEXT UNIQUE NOT NULL,
Price REAL CHECK (Price > 0),
StockQuantity INTEGER CHECK (StockQuantity >= 0)
);
```

**Output:**

<img width="1824" height="271" alt="495078911-228e2470-f1d9-40ab-a26f-7aa052af6d86" src="https://github.com/user-attachments/assets/b6dcf54a-de9b-4249-9974-d1b8a307cbba" />


**Question 8**
---
<img width="868" height="498" alt="495079389-9612b945-3729-4a78-a0ab-9d5db48274e5" src="https://github.com/user-attachments/assets/708e85a5-c628-40fb-8daf-1d8e3558feb9" />


```sql
INSERT INTO Customers (ID, NAME, AGE, ADDRESS, SALARY) VALUES
(1, 'Ramesh', 32, 'Ahmedabad', 2000),
(2, 'Khilan', 25, 'Delhi', 1500),
(3, 'Kaushik',23, 'Kota', 2000);
```

**Output:**

<img width="1758" height="419" alt="495079551-98862823-75f6-4779-96f8-78af6be976f0" src="https://github.com/user-attachments/assets/ea97cbd1-0dab-4992-8351-c32c317ca590" />


**Question 9**
---
<img width="1597" height="315" alt="495082851-87731bc1-d025-4e35-9ce4-4e780607bf93" src="https://github.com/user-attachments/assets/e3fb373b-e3d8-4297-9bc6-091bd603ae23" />


```sql
ALTER TABLE Student_details
ADD COLUMN email TEXT NOT NULL DEFAULT 'Invalid';

```

**Output:**
<img width="1704" height="318" alt="495080298-ce4698b0-e52c-49f8-8519-d51595d1ab56" src="https://github.com/user-attachments/assets/53f3f7f2-6271-47af-95bd-0d16880a2147" />

**Question 10**
---
<img width="1648" height="397" alt="495080463-447413c7-52c8-45ec-9d19-81f1517a8e12" src="https://github.com/user-attachments/assets/6dfa0a79-a3fd-46c6-8132-269c0ab3cb63" />


```sql
CREATE TABLE ProjectAssignments (
    AssignmentID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    ProjectID INTEGER,
    AssignmentDate DATE NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
    FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)
);
    
```

**Output:**
<img width="1767" height="284" alt="495083206-3ad8c535-6e8b-4d16-aef4-76c636b7659a" src="https://github.com/user-attachments/assets/4a5d92de-329e-49fe-a854-b7028c11a3a5" />




## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
