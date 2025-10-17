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
<img width="1295" height="715" alt="image" src="https://github.com/user-attachments/assets/22d70ad5-9274-43a3-919c-a244f9cbc949" />


sql
```
UPDATE employees
SET first_name = 'John'
WHERE department_id = 80
  AND commission_pct < 0.35;

```

**Output:**

<img width="1056" height="947" alt="image" src="https://github.com/user-attachments/assets/4ed3419e-7852-4d6f-be92-7bddcbb7d192" />

**Question 2**
--

<img width="1039" height="569" alt="image" src="https://github.com/user-attachments/assets/cb64840e-d18f-492d-ba15-3a10a1d64640" />

```sql
--UPDATE employees
SET salary = 8000
WHERE employee_id = 105
  AND salary < 5000;
```

**Output:**

<img width="1104" height="478" alt="image" src="https://github.com/user-attachments/assets/bfb0a345-5d73-49ec-84b5-bb4bc68e36c4" />


**Question 3**
---
-<img width="1203" height="558" alt="image" src="https://github.com/user-attachments/assets/150dbc1a-db7b-4fa5-b10b-09a70a69e9dd" />


```sql
UPDATE employees
SET email = 'not available',
    commission_pct = 0.55
WHERE department_id = 110;
```

**Output:**

<img width="1047" height="388" alt="image" src="https://github.com/user-attachments/assets/ed8c24db-41df-4ebe-96a4-35a70a391b50" />


**Question 4**
---
<img width="1202" height="502" alt="image" src="https://github.com/user-attachments/assets/4e6b6740-b92b-4b1e-91f6-16c38922f917" />


```sql
UPDATE products
SET reorder_lvl = reorder_lvl * 1.3
WHERE category = 'Food'
  AND quantity < (0.5 * reorder_lvl);
```

**Output:**

<img width="1068" height="342" alt="image" src="https://github.com/user-attachments/assets/a131437d-8cef-4254-9300-686e8e411a1f" />

**Question 5**
---
-- <img width="977" height="348" alt="image" src="https://github.com/user-attachments/assets/16f039a1-bda6-445a-9440-cf17971759d0" />


```sql
UPDATE customer
SET grade = 5
WHERE city = 'Chennai'; Paste your SQL code below for Question 5
```

**Output:**

<img width="1046" height="404" alt="image" src="https://github.com/user-attachments/assets/d8295462-70d1-42a1-bcea-7c8dab913112" />


**Question 6**
---
<img width="1267" height="830" alt="image" src="https://github.com/user-attachments/assets/53141347-1729-4cf9-aa5c-e93627161e8f" />


```sql
DELETE FROM customer
WHERE cust_country = 'India'
  AND cust_city <> 'Chennai';
```

**Output:**

<img width="1082" height="753" alt="image" src="https://github.com/user-attachments/assets/215ade16-6eb7-4f7a-8341-0e63c0a5e93f" />

**Question 7**
---
<img width="1231" height="578" alt="image" src="https://github.com/user-attachments/assets/e18de5ad-036d-4cce-93ab-33b3a912a0be" />


```sql
DELETE FROM customer
WHERE working_area = 'New York';
```

**Output:**

<img width="1153" height="658" alt="image" src="https://github.com/user-attachments/assets/223e9de8-cd9c-4f36-ba53-de2752592502" />


**Question 8**
<img width="853" height="440" alt="image" src="https://github.com/user-attachments/assets/f0b6be98-fe1b-42be-80e1-b2b6183970a0" />


```sql
DELETE FROM surgeries
WHERE surgery_date = '2024-02-28';
```

**Output:**

<img width="1100" height="355" alt="image" src="https://github.com/user-attachments/assets/9cb32fa3-40cf-4daf-8619-b91e07484f4a" />


**Question 9**
---

<img width="1247" height="185" alt="image" src="https://github.com/user-attachments/assets/7e7f3cbf-3d89-4ea3-8ef9-f01830b82244" />

```sql
DELETE FROM Doctors
WHERE first_name = 'Michael'
  AND specialization = 'Pediatrics';
```

**Output:**

<img width="1097" height="330" alt="image" src="https://github.com/user-attachments/assets/f6377e8a-ece5-443e-800f-6937a83a40fa" />

**Question 10**
<img width="1010" height="444" alt="image" src="https://github.com/user-attachments/assets/58ca5ca6-f01d-4e26-a0b8-1559687ea20c" />


```sql
DELETE FROM surgeries
WHERE surgery_id = 3;
```

**Output:**
<img width="1184" height="332" alt="image" src="https://github.com/user-attachments/assets/e227da45-00af-4444-9e47-59b4f55e849e" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
