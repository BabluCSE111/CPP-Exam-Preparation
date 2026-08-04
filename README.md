# DBMS Notebook Notes

## Lecture 1: Introduction to DBMS

### Data

**Definition:** Raw facts and figures without meaning.

**Example:**

* 101
* Rahul
* 8.5

**Memory Trick:** Data = Raw Facts

---

### Information

**Definition:** Processed and organized data that has meaning.

**Formula:**

> Data + Meaning = Information

**Memory Trick:** Information = Meaningful Data

---

### Database

**Definition:** An organized collection of related data that can be easily stored, managed, and retrieved.

**Example:** College Database (Students, Faculty, Courses, Fees)

**Memory Trick:** Database = Organized Collection of Data

---

### DBMS (Database Management System)

**Definition:** Software used to create, store, retrieve, update, and manage databases.

**Examples:**

* MySQL
* PostgreSQL
* Oracle
* SQL Server

**Memory Trick:**

* Database = Data
* DBMS = Manager of Data

---

### Database vs DBMS

| Database           | DBMS         |
| ------------------ | ------------ |
| Collection of data | Software     |
| Stores data        | Manages data |

**Analogy:**

* Database = Library Books
* DBMS = Librarian

---

## Lecture 2: File System

### File System

**Definition:** A method of storing and managing data in separate files.

**Example:**

* Student1.txt
* Student2.txt
* Student3.txt

**Suitable For:**

* Small applications
* Small amount of data

---

### Why was DBMS introduced?

To overcome the limitations of the File System and efficiently manage large amounts of data.

---

## Lecture 3: Problems of File System

### 1. Slow Searching

Searching becomes slow when the number of files is very large.

---

### 2. Data Redundancy

**Definition:** Unnecessary duplication of the same data within the same database or information system.

**Example:**
Student, Hostel, and Library all store Rahul's phone number.

**Memory Trick:** Redundancy = Repetition

---

### 3. Data Inconsistency

**Definition:** The same data has different values in different places.

**Example:**

* Student Record → 9999999999
* Hostel Record → 9876543210

**Memory Trick:** Inconsistency = Different Values

---

### Relationship

Data Redundancy
↓
Missed Update
↓
Data Inconsistency

---

### Important Note

Using the same Aadhaar number in different organizations (Bank, College, Hospital) is **not** Data Redundancy because they are different systems with different purposes.

Data Redundancy occurs within the **same database or information system**.

---

# Quick Revision

* Data = Raw Facts
* Information = Meaningful Data
* Database = Organized Collection of Data
* DBMS = Software that manages databases
* File System = Stores data in separate files
* Data Redundancy = Unnecessary repetition of data
* Data Inconsistency = Same data has different values
* Data Redundancy can lead to Data Inconsistency
# DBMS Notebook Notes

## Lecture 4: Data Abstraction

### Data Abstraction

**Definition:** Data abstraction is the process of hiding unnecessary details of the database and showing only the required information to the user.

**Memory Trick:**

> Data Abstraction = Hide Details, Show What Is Needed

---

### Levels of Data Abstraction

There are **3 levels**:

1. Physical Level
2. Logical Level
3. View Level

```text
User
 ↓
View Level
 ↓
Logical Level
 ↓
Physical Level
 ↓
Storage
```

---

### 1. Physical Level

**Definition:** The lowest level that describes **how data is physically stored** in the computer.

**Examples:**

- Files
- Disk blocks
- Indexes
- Storage structures

**Memory Trick:**

> Physical Level = How data is stored

---

### 2. Logical Level

**Definition:** The middle level that describes **what data is stored and how the data is organized**.

**Example:**

```text
Student
├── Student_ID
├── Name
├── Age
└── Course
```

**Memory Trick:**

> Logical Level = What data is stored

---

### 3. View Level

**Definition:** The highest level that describes **what a particular user is allowed to see**.

**Example:**

A student may see:

```text
Student ID
Name
Course
Marks
```

The accounts department may see:

```text
Student ID
Name
Fees
Payment Status
```

**Memory Trick:**

> View Level = What the user sees

---

### Physical vs Logical vs View

| Level | Main Question |
|---|---|
| Physical | How is data stored? |
| Logical | What data is stored? |
| View | What does the user see? |

**Memory Trick:**

> Physical → HOW  
> Logical → WHAT  
> View → SEE

---

## Lecture 5: Data Independence

### Data Independence

**Definition:** Data independence is the ability to change the database structure at one level without requiring changes at the next higher level.

**Memory Trick:**

> Data Independence = Change One Level Without Affecting the Higher Level

---

### Types of Data Independence

There are **2 types**:

1. Physical Data Independence
2. Logical Data Independence

---

### 1. Physical Data Independence

**Definition:** Physical data independence is the ability to change the physical storage level without changing the logical level.

**Example:**

The DBMS changes the way student records are physically stored:

```text
Storage Method A
        ↓
Storage Method B
```

But the logical structure remains:

```text
Student
├── Student_ID
├── Name
├── Course
└── Marks
```

**Memory Trick:**

> Physical Data Independence = Change HOW data is stored without changing WHAT data is stored.

---

### 2. Logical Data Independence

**Definition:** Logical data independence is the ability to change the logical structure without requiring changes to the view level.

**Example:**

A new field is added:

```text
Student
├── Student_ID
├── Name
├── Course
├── Marks
└── Email
```

But the existing student portal still shows:

```text
Name
Course
Marks
```

**Memory Trick:**

> Logical Data Independence = Change WHAT data is stored without changing what users see.

---

### Physical vs Logical Data Independence

| Physical Data Independence | Logical Data Independence |
|---|---|
| Physical level changes | Logical level changes |
| Logical level remains unaffected | View level remains unaffected |
| Changes HOW data is stored | Changes WHAT data/structure exists |

**Easy Memory Trick:**

> Physical → Change HOW  
> Logical → Change WHAT

---

## Lecture 6: Database Schema

### Database Schema

**Definition:** A database schema is the **logical structure or blueprint of a database** that defines how the data is organized.

**It describes:**

- Tables
- Columns
- Relationships
- Constraints

**Memory Trick:**

> Schema = Blueprint of the Database

---

### Example

```text
Student(Student_ID, Name, Age, Course)

Course(Course_ID, Course_Name)
```

This represents the **structure** of the database.

It does not represent the actual student records.

---

### Schema vs Data

**Schema:**

```text
Student_ID
Name
Age
Course
```

**Data:**

```text
101 | Rahul | 20 | CSE
102 | Amit  | 21 | ECE
```

**Memory Trick:**

> Schema = Structure  
> Data = Actual Values

---

## Lecture 7: Database Instance

### Database Instance

**Definition:** A database instance is the **actual data stored in the database at a particular point in time**.

**Example:**

### Schema

```text
Student(Student_ID, Name, Age, Course)
```

### Instance

```text
101 | Rahul | 20 | CSE
102 | Amit  | 21 | ECE
103 | Neha  | 20 | CSE
```

If a new student is added, the **instance changes**.

The schema can remain unchanged.

**Memory Trick:**

> Instance = Snapshot of Actual Data

---

### Schema vs Instance

| Schema | Instance |
|---|---|
| Structure of the database | Actual data at a particular time |
| Relatively stable | Changes frequently |
| Defines tables, columns, relationships, etc. | Contains actual records |
| Blueprint | Snapshot |

**Memory Trick:**

> Schema = Design  
> Instance = Data at this moment

---

### Example of Schema and Instance Change

**Monday:**

```text
Student(Student_ID, Name, Course)

101 | Rahul | CSE
102 | Amit  | ECE
```

**Tuesday:**

```text
Student(Student_ID, Name, Course)

101 | Rahul | CSE
102 | Amit  | ECE
103 | Neha  | IT
```

The **instance changed** because a new record was added.

---

**Wednesday:**

```text
Student(Student_ID, Name, Course, Email)
```

The **schema changed** because the structure was modified by adding a new column.

---

# Quick Revision

### Data Abstraction

- Data Abstraction = Hide unnecessary details.
- Physical Level = How data is stored.
- Logical Level = What data is stored.
- View Level = What users see.

### Data Independence

- Data Independence = Change one level without affecting the higher level.
- Physical Data Independence = Change physical storage without changing logical structure.
- Logical Data Independence = Change logical structure without changing user views.

### Schema & Instance

- Schema = Structure / Blueprint.
- Instance = Actual data at a particular time.
- Adding or removing records → Instance changes.
- Changing tables, columns, or structure → Schema changes.

### Golden Memory Rules

```text
Physical Level  → HOW is it stored?
Logical Level   → WHAT is stored?
View Level      → WHAT does the user see?

Physical Data Independence → Change HOW
Logical Data Independence  → Change WHAT

Schema   → Structure
Instance → Current Data
```
