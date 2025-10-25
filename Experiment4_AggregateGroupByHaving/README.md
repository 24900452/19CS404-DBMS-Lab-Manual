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

Developed By : Lokeshwaran S

Register No : 212224240080

**Question 1**
--
<img width="1173" height="788" alt="image" src="https://github.com/user-attachments/assets/3cbfee8c-c897-413c-aff4-356d50a13774" />


```sql
select patientID , count(Medication) as TotalMedications from Prescriptions group by patientID;

```

**Output:**

<img width="934" height="929" alt="image" src="https://github.com/user-attachments/assets/d7406935-53f1-43e9-b0eb-014e127a2cbe" />


**Question 2**
---
<img width="1204" height="818" alt="image" src="https://github.com/user-attachments/assets/94092cda-d3a7-41e4-b230-d6aa5004aee7" />


```sql
select date(AppointmentDateTime) as AppointmentDate , count(AppointmentID) as TotalAppointments from Appointments group by date(AppointmentDateTime) order by AppointmentDate;
```

**Output:**

<img width="977" height="865" alt="image" src="https://github.com/user-attachments/assets/f5c8d7d8-f9ce-4d43-9b65-7176bbcdb7ce" />


**Question 3**
---
<img width="1451" height="834" alt="image" src="https://github.com/user-attachments/assets/6ade48ca-c84a-4089-a16c-4e402ce37978" />


```sql
select DoctorID , count(PrescriptionID) as TotalPrescriptions from Prescriptions group by DoctorID;

```

**Output:**

<img width="946" height="934" alt="image" src="https://github.com/user-attachments/assets/9a2a4f62-7ac4-4b12-b4bb-69366576ad1a" />


**Question 4**
---
<img width="1436" height="652" alt="image" src="https://github.com/user-attachments/assets/9778dd6d-7c9c-4e50-b0fe-3aaed8efb57a" />


```sql
select avg(purch_amt) as AVERAGE from orders;
```

**Output:**

<img width="617" height="477" alt="image" src="https://github.com/user-attachments/assets/4b405dd3-0d4a-43b6-bbb9-f2dfa0276bee" />


**Question 5**
---
<img width="1432" height="625" alt="image" src="https://github.com/user-attachments/assets/99b01dc8-afb5-457b-aa09-c4b0f6deaade" />


```sql
select count(distinct salesman_id) as COUNT from orders;
```

**Output:**

<img width="546" height="471" alt="image" src="https://github.com/user-attachments/assets/16b490a1-08f4-43b5-a3fa-a37aea2992f9" />


**Question 6**
---
<img width="1260" height="676" alt="image" src="https://github.com/user-attachments/assets/85140116-7459-4d52-b438-0933f9ec9c32" />


```sql
select sum(inventory) as total from fruits where unit = 'LB';
```

**Output:**

<img width="517" height="492" alt="image" src="https://github.com/user-attachments/assets/0d48d9ae-5f3b-4cd0-9304-66e2fb5a07f1" />


**Question 7**
---
<img width="1271" height="585" alt="image" src="https://github.com/user-attachments/assets/92128531-0c71-4f53-8238-825a517a7d09" />


```sql
select count(id) as employees_count from employee where income > 50000;
```

**Output:**

<img width="609" height="472" alt="image" src="https://github.com/user-attachments/assets/f1b381ca-2db1-4ae3-8a55-66e33ff4580d" />


**Question 8**
---
<img width="1414" height="652" alt="image" src="https://github.com/user-attachments/assets/41d14c5f-03ec-490f-8a94-cf9220ecd9a9" />


```sql
select occupation , AVG(workhour) from employee1 group by occupation having avg(workhour) >= 10 and avg(workhour) <= 12;
```

**Output:**

<img width="870" height="574" alt="image" src="https://github.com/user-attachments/assets/0a6498f6-39d9-41d5-8c22-0b014f8a291e" />


**Question 9**
---
<img width="1413" height="676" alt="image" src="https://github.com/user-attachments/assets/2a7e276c-8461-4922-9668-ffa3c1af8f47" />


```sql
select city , AVG(income) from employee group by city having avg(income) > 500000;
```

**Output:**

<img width="859" height="626" alt="image" src="https://github.com/user-attachments/assets/debf6d20-7d44-4469-ae00-35e32b2be1df" />


**Question 10**
---
<img width="1415" height="668" alt="image" src="https://github.com/user-attachments/assets/ba06500e-a503-4319-9d7f-a656deca7d20" />


```sql
select age , AVG(income) from employee group by age having avg(income) >= 300000 and avg(income) <= 500000;
```

**Output:**

<img width="837" height="501" alt="image" src="https://github.com/user-attachments/assets/964a4fb2-93ae-4faf-8878-fb6c6752de17" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
