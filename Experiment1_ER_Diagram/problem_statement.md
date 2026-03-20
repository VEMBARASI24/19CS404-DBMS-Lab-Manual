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
<img width="938" height="633" alt="image" src="https://github.com/user-attachments/assets/cb3df6ea-5567-49f0-a75c-35855406b2c4" />


### Entities and Attributes

<img width="399" height="259" alt="image" src="https://github.com/user-attachments/assets/2b9726a3-289d-471b-b033-a1475018b29c" />


### Relationships and Constraints

<img width="571" height="278" alt="image" src="https://github.com/user-attachments/assets/aa725d6a-3789-40b2-a9b8-a22fd7137781" />


### Assumptions

Each entity (Member, Program, Trainer) has a unique identifier, even if not explicitly shown.

A member can register for multiple programs and make multiple payments.

A trainer can handle multiple programs and sessions, but each session has only one trainer.

Attendance is recorded for each member in each session with status (Present/Absent).

Many-to-many relationships (Member–Program, Program–Trainer) are handled using junction tables.

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
<img width="900" height="931" alt="image" src="https://github.com/user-attachments/assets/a0c9383b-c09c-499d-8c38-9d6de6efd5db" />


### Entities and Attributes

<img width="468" height="236" alt="image" src="https://github.com/user-attachments/assets/2b760d47-bf0a-4a6d-8a81-ab94ec098fa2" />

### Relationships and Constraints

<img width="490" height="203" alt="image" src="https://github.com/user-attachments/assets/9f94583c-1523-4b8a-95df-c19b96305b7b" />


### Assumptions

Each main entity (Members, Event, Speaker) has a unique ID, and Room Name is treated as unique.

A member can borrow multiple books, and a book can be borrowed by multiple members over time.

A member can register for multiple events, and each event can have many members.

An event can have multiple speakers, and a speaker can participate in multiple events.

Each event is assigned to one room, but a room can host multiple events at different times.


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
*Paste or attach your diagram here*  
<img width="1023" height="685" alt="image" src="https://github.com/user-attachments/assets/e73a476d-396c-40e0-81ef-3122ca26f70a" />


### Entities and Attributes

<img width="1021" height="314" alt="image" src="https://github.com/user-attachments/assets/95af1029-7b2f-4998-90ad-bb9bbd026cbc" />


### Relationships and Constraints

<img width="517" height="316" alt="image" src="https://github.com/user-attachments/assets/c4290f23-7e51-44a5-9500-93ae313690f4" />


### Assumptions

Each entity has a unique primary key, and all foreign keys correctly reference related entities.

A customer can make multiple reservations, but each reservation is linked to one customer and one waiter.

A reservation can have multiple orders, and each order can include multiple dishes (handled using a junction table).

Each dish belongs to one category, and a category can contain many dishes.

Each reservation generates one bill, calculated based on its orders, maintaining a 1:1 relationship.


## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
