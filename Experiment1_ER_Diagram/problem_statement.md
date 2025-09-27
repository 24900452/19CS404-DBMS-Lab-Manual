# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_fitness.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:

![DBMS Workshop_page-0001](https://github.com/user-attachments/assets/b6f3b813-3445-4e02-8e76-d2c81bd23b30)


### Entities and Attributes

| Entity     | Attributes (PK, FK)     | Notes     |
|--------    |--------------------     |-------    |
|CUSTOMER    |Customer_ID (PK), Name,Phone, Email |Each customer makes reservations.      |     
|RESERVATION |Reservation_ID (PK), Customer_ID (FK), Waiter |Reservation placed by a customer, served by a waiter.                 |
|ORDER |Order_ID (PK), Food, Date, Category |An order placed under a reservation.            |
|DISH |Dish_ID (PK), Dish_Name |Represents food items offered.            |    
|BILL |Bill_ID (PK), Order_ID (FK), TotalAmount |Bill generated for each order.            |         

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|CUSTOMER – RESERVATION |1 : M |Customer books many reservations |"books" relationship              | 
|RESERVATION – ORDER |1 : M |A reservation can have many orders |"places" relationship              |            
|ORDER – ORDER_DETAILS |1 : M |Each order can have multiple dishes |"order composition"               |    
|ORDER_DETAILS – DISH |M : 1 |Each order detail belongs to one dish |Linked via Dish_ID              |
|ORDER – BILL |1 : 1 |Each order generates one bill |Bill includes total amount               |       

### Assumptions

- Customer is uniquely identified by Customer_ID.

- Reservation needs both a customer and a waiter assigned.

- Orders are tied to reservations, not directly to customers.

- Each order produces exactly one bill.

- Categories classify orders (e.g., service type, menu type).

- Dish information is stored separately and linked via Dish_ID.


---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
