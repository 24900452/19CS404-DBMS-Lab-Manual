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
Create a table named Locations with the following columns:

LocationID as INTEGER
LocationName as TEXT
Address as TEXT
For example:

Test	Result
pragma table_info('Locations');
cid       name             type        notnull     dflt_value  pk
--------  ---------------  ----------  ----------  ----------  ----------
0         LocationID       INTEGER     0                       0
1         LocationName     TEXT        0                       0
2         Address          TEXT        0                       0


```sql
CREATE TABLE Locations (
    LocationID INTEGER,
    LocationName TEXT,
    Address TEXT
);
```

**Output:**
<img width="1487" height="984" alt="Screenshot 2025-09-27 091324" src="https://github.com/user-attachments/assets/701e97fe-b0f5-46e0-81fe-67301c5f446f" />


**Question 2**
Write a SQL Query  to change the name of attribute "name" to "first_name"  and add mobilenumber as number ,DOB as Date in the table Companies. 

 

```sql
ALTER TABLE Companies RENAME COLUMN name TO first_name;
ALTER TABLE Companies ADD COLUMN mobilenumber number;
ALTER TABLE Companies ADD COLUMN DOB Date;
```

**Output:**

<img width="1466" height="1000" alt="Screenshot 2025-09-27 091344" src="https://github.com/user-attachments/assets/785215d7-6c8f-4ebc-896b-7c90b2604e14" />


**Question 3**
Create a new table named products with the following specifications:
product_id as INTEGER and primary key.
product_name as TEXT and not NULL.
list_price as DECIMAL (10, 2) and not NULL.
discount as DECIMAL (10, 2) with a default value of 0 and not NULL.
A CHECK constraint at the table level to ensure:
list_price is greater than or equal to discount
discount is greater than or equal to 0
list_price is greater than or equal to 0
For example:

Test	Result
INSERT INTO products (product_id, product_name, list_price) VALUES (2, 'Product B', 50.00);
SELECT * FROM products;

```sql
CREATE TABLE products (
    product_id INTEGER PRIMARY KEY,
    product_name TEXT NOT NULL,
    list_price DECIMAL(10, 2) NOT NULL,
    discount DECIMAL(10, 2) NOT NULL DEFAULT 0,
    CHECK (
        list_price >= discount AND
        discount >= 0 AND
        list_price >= 0
    )
);
```

**Output:**

<img width="1567" height="1013" alt="Screenshot 2025-09-27 091358" src="https://github.com/user-attachments/assets/87f627d5-ed22-4724-80b9-423665f2909c" />


**Question 4**
Create a table named Department with the following constraints:
DepartmentID as INTEGER should be the primary key.
DepartmentName as TEXT should be unique and not NULL.
Location as TEXT.
For example:

Test	Result
INSERT INTO Department (DepartmentID, DepartmentName, Location) VALUES (1, 'Human Resources', 'New York');
select * from Department;


```sql
CREATE TABLE Department (
    DepartmentID INTEGER PRIMARY KEY,
    DepartmentName TEXT NOT NULL UNIQUE,
    Location TEXT
);
```

**Output:**

<img width="1504" height="910" alt="Screenshot 2025-09-27 091412" src="https://github.com/user-attachments/assets/9c9ab24f-08c5-407f-840f-4040858eff2c" />


**Question 5**
In the Books table, insert a record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.

ISBN             Title                      Author           Publisher   Year
---------------  -------------------------  ---------------  ----------  ----------
978-1234567890   Introduction to AI         John Doe
978-9876543210   Deep Learning              Jane Doe         TechPress   2022
978-1122334455   Cybersecurity Essentials   Alice Smith                  2021
For example:

Test	Result
SELECT * FROM Books;
ISBN             Title                      Author           Publisher   Year
---------------  -------------------------  ---------------  ----------  ----------
978-1234567890   Introduction to AI         John Doe
978-9876543210   Deep Learning              Jane Doe         TechPress   2022
978-1122334455   Cyber
```sql
INSERT INTO Books (ISBN, Title, Author) 
VALUES ('978-1234567890', 'Introduction to AI', 'John Doe');


INSERT INTO Books (ISBN, Title, Author, Publisher, Year) 
VALUES ('978-9876543210', 'Deep Learning', 'Jane Doe', 'TechPress', 2022);

INSERT INTO Books (ISBN, Title, Author, Year) 
VALUES ('978-1122334455', 'Cybersecurity Essentials', 'Alice Smith', 2021);



```

**Output:**


<img width="1581" height="925" alt="Screenshot 2025-09-27 091425" src="https://github.com/user-attachments/assets/1418fc4c-af8b-469c-b565-7834d747020b" />

**Question 6**
Write a SQL query to Add a new column named "discount" with the data type DECIMAL(5,2) to the "customer" table.

Sample table: customer

 customer_id |   cust_name    |    city    | grade | salesman_id 
-------------+----------------+------------+-------+-------------
        3002 | Nick Rimando   | New York   |   100 |        5001
        3007 | Brad Davis     | New York   |   200 |        5001
        3005 | Graham Zusi    | California |   200 |        5002
 

For example:

Test	Result
pragma table_info('customer');
cid         name         type                               notnull     dflt_value  pk
----------  -----------  ---------------------------------  ----------  ----------  ----------
0           customer_id  integer primarykey auto increment  0                       0
1           cust_name    varchar2(30)                       0                       0
2           city         varchar(30)                        0                       0
3           grade        number                             0                       0
4           salesman_id  number                             0                       0
5           discount 
```sql
ALTER TABLE customer 
ADD COLUMN discount DECIMAL(5,2);
```

**Output:**

<img width="1533" height="1029" alt="Screenshot 2025-09-27 091440" src="https://github.com/user-attachments/assets/288efdd4-97cc-41a7-bf3b-fb200e5f12df" />


**Question 7**
Insert all books from Out_of_print_books into Books

Table attributes are ISBN, Title, Author, Publisher, YearPublished

For example:

Test	Result
select * from Books;
ISBN            Title           Author              Publisher      YearPublished
--------------  --------------  ------------------  -------------  -------------
978-1234567890  The Lost World  Arthur Conan Doyle  Vintage Books  1912
978-0987654321  Gone with the   Margaret Mitchell   Macmillan      1936
978-1122334455  Moby
```sql
INSERT INTO Books (ISBN, Title, Author, Publisher, YearPublished)
SELECT ISBN, Title, Author, Publisher, YearPublished
FROM Out_of_print_books;
```

**Output:**
<img width="1479" height="905" alt="Screenshot 2025-09-27 091456" src="https://github.com/user-attachments/assets/7ca36e7e-aa16-466a-8c97-fa1425ed64b6" />



**Question 8**
---
Insert a customer with CustomerID 301, Name Michael Jordan, Address 123 Maple St, City Chicago, and ZipCode 60616 into the Customers table.

For example:

Test	Result
SELECT * FROM Customers WHERE CustomerID = 301;
CustomerID  Name            Address       City        ZipCode
-----

```sql
INSERT INTO Customers (CustomerID, Name, Address, City, ZipCode)
VALUES (301, 'Michael Jordan', '123 Maple St', 'Chicago', 60616);
```

**Output:**

<img width="1507" height="805" alt="Screenshot 2025-09-27 091509" src="https://github.com/user-attachments/assets/c2412086-7a43-471e-b2d2-807a7fc82696" />


**Question 9**
Create a table named Shipments with the following constraints:
ShipmentID as INTEGER should be the primary key.
ShipmentDate as DATE.
SupplierID as INTEGER should be a foreign key referencing Suppliers(SupplierID).
OrderID as INTEGER should be a foreign key referencing Orders(OrderID).
For example:

Test	Result
INSERT INTO Shipments (ShipmentID, ShipmentDate, Supp

```sql
CREATE TABLE Shipments (
    ShipmentID INTEGER PRIMARY KEY,
    ShipmentDate DATE,
    SupplierID INTEGER,
    OrderID INTEGER,
    FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID),
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)
);
```

**Output:**
<img width="1487" height="838" alt="Screenshot 2025-09-27 091524" src="https://github.com/user-attachments/assets/5fcc12c6-a71f-43b4-81f3-43ba35109dc0" />



**Question 10**
Create a table named Invoices with the following constraints:
InvoiceID as INTEGER should be the primary key.
InvoiceDate as DATE.
Amount as REAL should be greater than 0.
DueDate as DATE should be greater than the InvoiceDate.
OrderID as INTEGER should be a foreign key referencing Orders(OrderID).
For example:

Test	Result
INSERT INTO Orders (OrderID, OrderDate, CustomerID) VALUES (1, '2024-08-01', 1);
INSERT INTO Invoices (InvoiceID, InvoiceDate, Amount, DueDate, OrderID) VALUES (1, '2024-08-01', 100.0, '2024-09-01', 1);
SELECT * FROM Invoices;

```sql
CREATE TABLE Invoices (
    InvoiceID INTEGER PRIMARY KEY,
    InvoiceDate DATE,
    Amount REAL CHECK (Amount > 0),
    DueDate DATE,
    OrderID INTEGER,
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID),
    CHECK (DueDate > InvoiceDate)
);
```

**Output:**

<img width="1546" height="1017" alt="Screenshot 2025-09-27 091539" src="https://github.com/user-attachments/assets/c3708dd8-7b2c-4da1-8505-686e236323d4" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
