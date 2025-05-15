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
--

![Screenshot (110)](https://github.com/user-attachments/assets/f2a74190-e935-40dd-94ae-36bc2c3b1726)


```
CREATE TABLE Products(
ProductID INTEGER,
ProductName TEXT,
Price REAL,
Stock INTEGER
);
```

**Output:**

![Screenshot (111)](https://github.com/user-attachments/assets/0ce5b95a-0764-4e87-aecc-b1db39d8bdc2)


**Question 2**
---
![Screenshot (112)](https://github.com/user-attachments/assets/fd19c14a-9d94-4c88-9d97-01fd316a8067)


```
INSERT INTO Books(ISBN ,           Title                   , Author      ,Publisher   ,Year)VALUES('978-1234567890'  ,'Data Science Essentials'  ,'Jane Doe'    ,'TechBooks'   ,2024);
```

**Output:**

![Screenshot (113)](https://github.com/user-attachments/assets/3906b33d-3e3e-4346-9489-cf9199e17ba9)



**Question 3**

![Screenshot (114)](https://github.com/user-attachments/assets/1535ed3f-f207-4d75-8d29-f5c2cb882a7a)


```
CREATE TABLE Orders(
OrderID INTEGER primary key,
OrderDate DATE not NULL,
CustomerID INTEGER ,
foreign key (CustomerID)
REFERENCES Customers(CustomerID)
);
```

**Output:**

![Screenshot (115)](https://github.com/user-attachments/assets/2438cb90-f406-4967-b6a3-fbb9ba569725)


**Question 4**

![Screenshot (116)](https://github.com/user-attachments/assets/b09dd139-f305-455c-909e-1324d4450d1c)


```
ALTER TABLE Customer
ADD COLUMN birth_date timestamp;
```

**Output:**

![Screenshot (117)](https://github.com/user-attachments/assets/3bcc2170-b6ef-4b10-b8f9-f8d086f82a90)


**Question 5**

![Screenshot (118)](https://github.com/user-attachments/assets/daa47960-ee3e-4cff-94dc-f287ab98be94)


```
CREATE TABLE ProjectAssignments(
AssignmentID INTEGER primary key,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
foreign key (EmployeeID) REFERENCES Employees(EmployeeID),
foreign key (ProjectID) REFERENCES Projects(ProjectID)

);

```

**Output:**

![Screenshot (119)](https://github.com/user-attachments/assets/d9fa2cf5-0959-4db3-8a5f-b33652058e34)


**Question 6**

![Screenshot (128)](https://github.com/user-attachments/assets/f7b412f4-f65c-447e-bbf6-ae1395eb87a5)


```
ALTER TABLE employee
RENAME column id to employee_id;
```

**Output:**

![Screenshot (129)](https://github.com/user-attachments/assets/da88cd76-b3a3-4ba6-9789-bb5be9fc7a6c)


**Question 7**

![Screenshot (130)](https://github.com/user-attachments/assets/e0f7dd1a-99fd-4272-b1e8-e2729a1c5c06)


```
INSERT INTO Customers(CustomerID , Name ,         Address   ,    City     ,   ZipCode)VALUES('306'         ,'Diana Prince'  ,'Themyscira'        ,NULL,NULL),('307'         ,'Bruce Wayne'   ,'Wayne Mano'  ,'Gotham'      ,'10007'),('308',         'Peter Parker',  'Queens'                  ,NULL,'11375');
```

**Output:**

![Screenshot (131)](https://github.com/user-attachments/assets/dbfd8f59-4201-4b65-b50b-eaa20aa45d7d)


**Question 8**

![Screenshot (132)](https://github.com/user-attachments/assets/8e3ccd34-ae8c-407c-a537-f874fc0c452c)


```
CREATE TABLE contacts(
contact_id INTEGER primary key,
first_name TEXT not NULL,
last_name TEXT not NULL,
email TEXT,
phone TEXT not NULL CHECK(LENGTH(phone)>=10)
);
```

**Output:**

![Screenshot (133)](https://github.com/user-attachments/assets/4a329bb0-53f2-4c0e-bdad-df85b4d2ddb5)


**Question 9**

![Screenshot (134)](https://github.com/user-attachments/assets/e921e008-80bc-4c78-97f6-314ade3b6457)


```
CREATE TABLE Products(
ProductID primary key,
ProductName NOT NULL,
Price real CHECK(Price>0), 
Stock integer CHECK(Stock>=0) 
);
```

**Output:**

![Screenshot (135)](https://github.com/user-attachments/assets/a12647c4-5d7f-4ff4-b0e3-bcd20b7eae5c)


**Question 10**

![Screenshot (136)](https://github.com/user-attachments/assets/ced539d7-6203-4d70-8e9d-f2d6a0e0e39f)


```
INSERT INTO Books(ISBN, Title, Author, Publisher, YearPublished)
SELECT ISBN, Title, Author, Publisher, YearPublished FROM Out_of_print_books;
```

**Output:**

![Screenshot (137)](https://github.com/user-attachments/assets/a95ad92a-1225-4fdc-a343-cd4fe7b23713)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
