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
# 📚 DBMS — Keys

> **Lecture Topic:** Keys in DBMS
> **Goal:** Understand how keys identify records and connect tables.

---

## 1. 🔑 What is a Key?

A **key** is an attribute or combination of attributes used to **uniquely identify a record (row)** in a table.

### Example

| Student_ID | Name  | Email                             |
| ---------- | ----- | --------------------------------- |
| 101        | Rahul | [r@gmail.com](mailto:r@gmail.com) |
| 102        | Aman  | [a@gmail.com](mailto:a@gmail.com) |
| 103        | Priya | [p@gmail.com](mailto:p@gmail.com) |

`Student_ID` can uniquely identify each student.

---

# 2. ⭐ Super Key

A **Super Key** is **any attribute or combination of attributes that can uniquely identify a row**.

Example:

```text
{Student_ID}          → Super Key
{Email}               → Super Key
{Student_ID, Name}    → Super Key
{Student_ID, Email}   → Super Key
```

### Important

A Super Key may contain **unnecessary attributes**.

Example:

```text
{Student_ID, Name}
```

If `Student_ID` alone is enough, then `Name` is unnecessary.

### 🧠 Memory Trick

> **Super Key = Unique + Maybe Extra**

---

# 3. 🎯 Candidate Key

A **Candidate Key** is a **minimal Super Key**.

It must:

1. Uniquely identify a row.
2. Have **no unnecessary attribute**.

Example:

```text
{Student_ID} → Candidate Key ✅
{Email}      → Candidate Key ✅
```

But:

```text
{Student_ID, Name}
```

is **not** a Candidate Key because `Name` is unnecessary.

### 🧠 Memory Trick

> **Candidate Key = Super Key − Extra Attributes**

---

# 4. 🏆 Primary Key

A **Primary Key** is the **Candidate Key selected by the database designer** as the main key.

Suppose:

```text
Candidate Keys:
Student_ID
Email
Aadhaar_No
```

If we choose:

```text
Email → Primary Key
```

then `Email` becomes the Primary Key.

### Important properties

* Uniquely identifies each row.
* Cannot contain NULL values.
* Only one Primary Key is selected for a table.

### 🧠 Memory Trick

> **Candidate Keys = Choices**
> **Primary Key = Selected Choice**

---

# 5. 🔄 Alternate Key

The Candidate Keys that are **not selected as the Primary Key** are called **Alternate Keys**.

Example:

```text
Candidate Keys:
Student_ID
Email
Aadhaar_No
```

If:

```text
Email → Primary Key
```

then:

```text
Student_ID → Alternate Key
Aadhaar_No  → Alternate Key
```

### 🧠 Memory Trick

> **Primary = Selected**
> **Alternate = Remaining Candidates**

---

# 6. 🔗 Foreign Key (FK)

A **Foreign Key** is an attribute in one table that **refers to a key in another table**, commonly the Primary Key.

### Example

### Student

| Student_ID | Name  |
| ---------- | ----- |
| 101        | Rahul |
| 102        | Aman  |

`Student_ID` → Primary Key

### Enrollment

| Enrollment_ID | Student_ID | Course |
| ------------- | ---------- | ------ |
| 1             | 101        | DBMS   |
| 2             | 101        | OOP    |
| 3             | 102        | DBMS   |

Here:

```text
Enrollment.Student_ID
          ↓
   refers to
          ↓
Student.Student_ID
```

Therefore:

> `Enrollment.Student_ID` = **Foreign Key**

### What does `101` mean?

It means:

> "This enrollment belongs to the student whose ID is 101."

And:

```text
101 → Rahul
```

So `101` refers to **Rahul**.

### Important

A Foreign Key **can repeat**:

```text
101 → DBMS
101 → OOP
```

That's valid because the same student can have multiple enrollments.

### 🧠 Memory Trick

> **PK = Identifies**
> **FK = References / Connects**

---

# 7. 🧩 Composite Key

A **Composite Key** consists of **two or more attributes together** that uniquely identify a row.

### Example

| Student_ID | Course_ID | Marks |
| ---------- | --------- | ----: |
| 101        | C01       |    80 |
| 101        | C02       |    75 |
| 102        | C01       |    90 |

Neither column alone is unique:

```text
Student_ID → repeats ❌
Course_ID  → repeats ❌
```

But together:

```text
(Student_ID, Course_ID)
```

uniquely identifies each row.

Therefore:

> `(Student_ID, Course_ID)` = **Composite Key**

---

## 🔥 Composite Key Can Have More Than 2 Columns

Example:

| Student_ID | Course_ID | Semester |
| ---------- | --------- | -------- |
| 101        | C01       | 1        |
| 101        | C01       | 2        |
| 101        | C02       | 1        |
| 102        | C01       | 1        |

Here:

```text
(Student_ID, Course_ID)
```

is **not enough** because:

```text
(101, C01)
(101, C01)
```

repeats.

But:

```text
(Student_ID, Course_ID, Semester)
```

is unique.

Therefore, all three together can form a **Composite Key**.

### 🧠 Memory Trick

> **Composite = Combination**

---

# 🔥 Complete Key Relationship

```text
                SUPER KEY
                    ↓
          Remove unnecessary attributes
                    ↓
             CANDIDATE KEY
                    ↓
             Choose one
                    ↓
             PRIMARY KEY
                    ↓
     Remaining Candidate Keys
                    ↓
            ALTERNATE KEYS
```

And separately:

```text
PRIMARY KEY
     ↑
     │ refers to
     │
FOREIGN KEY
```

---

# 🧠 Quick Comparison

| Key               | Main Purpose                                |
| ----------------- | ------------------------------------------- |
| **Super Key**     | Uniquely identifies a row                   |
| **Candidate Key** | Minimal Super Key                           |
| **Primary Key**   | Selected Candidate Key                      |
| **Alternate Key** | Candidate Key not selected                  |
| **Foreign Key**   | References another table's key              |
| **Composite Key** | Multiple attributes together identify a row |

---

# ⚡ Memory Tricks

> **Super → Unique + Maybe Extra**

> **Candidate → Unique + No Extra**

> **Primary → Selected Candidate**

> **Alternate → Remaining Candidate**

> **Foreign → Reference another table**

> **Composite → Combination of attributes**

---

# 🎯 Quick Revision

### Q1. Can a Super Key contain unnecessary attributes?

**Yes.** ✅

### Q2. Is every Candidate Key a Super Key?

**Yes.** ✅

### Q3. Is every Super Key a Candidate Key?

**No.** ❌

### Q4. How many Primary Keys can a table have?

**One Primary Key.**

### Q5. Can a Foreign Key repeat?

**Yes.** ✅

### Q6. Can a Composite Key contain 3 attributes?

**Yes.** ✅

### Q7. What does a Foreign Key do?

**It references a key in another table and helps establish a relationship between tables.**

---

## 🏁 Today's Core Takeaway

```text
Super Key       → Any unique identifier
Candidate Key   → Minimal unique identifier
Primary Key     → Selected candidate
Alternate Key   → Unselected candidate
Foreign Key     → Reference to another table
Composite Key   → Multiple columns working together
```

**Today's DBMS topic: ✅ Keys completed**
# 📚 DBMS — SQL Commands & Constraints

> **Lecture Topic:** Constraints + SQL Command Categories
> **Goal:** Understand how SQL manages table structure and data.

---

# 1. 🛡️ Constraints

A **constraint** is a rule applied to a table/column to control what data can be stored.

> **Constraint = Rule for the data**

### Why constraints?

They help maintain **Data Integrity** and prevent invalid data.

---

## 🔹 NOT NULL

Prevents a column from containing `NULL`.

```sql
Name VARCHAR(50) NOT NULL
```

```text
Rahul → ✅
Aman  → ✅
NULL  → ❌
```

### Memory Trick

> **NOT NULL = Value is compulsory**

---

## 🔹 UNIQUE

Prevents duplicate values.

```sql
Email VARCHAR(100) UNIQUE
```

```text
rahul@gmail.com → ✅
aman@gmail.com  → ✅
rahul@gmail.com → ❌
```

### Memory Trick

> **UNIQUE = No duplicates**

---

## 🔹 PRIMARY KEY

Uniquely identifies each row.

```sql
Student_ID INT PRIMARY KEY
```

Important:

* Unique
* Cannot contain `NULL`
* One Primary Key per table

### Memory Trick

> **Primary Key = Main identity of a row**

---

## 🔹 FOREIGN KEY

A Foreign Key refers to a key in another table and helps establish a relationship.

Example:

```text
Student
Student_ID
   ↑
   │
Enrollment.Student_ID
```

```text
Student.Student_ID       → Primary Key
Enrollment.Student_ID    → Foreign Key
```

A Foreign Key **can repeat**.

### Memory Trick

> **FK = Reference / Connection**

---

## 🔹 CHECK

Ensures a value satisfies a condition.

```sql
Age INT CHECK (Age >= 18)
```

```text
17 → ❌
18 → ✅
25 → ✅
```

### Memory Trick

> **CHECK = Condition must be true**

---

## 🔹 DEFAULT

Provides a value when no value is supplied.

```sql
Status VARCHAR(20) DEFAULT 'Active'
```

If no status is given:

```text
Status → Active
```

### Memory Trick

> **DEFAULT = Automatic value**

---

# 2. 🏗️ DDL — Data Definition Language

DDL is mainly used to **define/change database structure**.

### Main DDL Commands

```text
CREATE
ALTER
DROP
TRUNCATE
```

### 🧠 Memory Trick

> **DDL → Structure**

---

## 🔹 CREATE

Creates a new table.

```sql
CREATE TABLE Student
(
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50)
);
```

> **CREATE = Build something new**

---

## 🔹 ALTER

Changes the **structure** of an existing table.

Example: Add a column.

```sql
ALTER TABLE Student
ADD Email VARCHAR(100);
```

Before:

```text
Student
├── Student_ID
└── Name
```

After:

```text
Student
├── Student_ID
├── Name
└── Email
```

> **ALTER = Change structure**

---

## 🔹 DROP

Completely removes the table.

```sql
DROP TABLE Student;
```

Result:

```text
Table structure → ❌
Table data      → ❌
```

> **DROP = Destroy the table**

---

## 🔹 TRUNCATE

Removes **all rows** but keeps the table structure.

```sql
TRUNCATE TABLE Student;
```

Result:

```text
Data      → ❌
Structure → ✅
```

> **TRUNCATE = Empty the table**

---

# 3. 📝 DML — Data Manipulation Language

DML is used to **manipulate data inside tables**.

### Main DML Commands

```text
INSERT
UPDATE
DELETE
```

### 🧠 Memory Trick

> **DML → Data**

---

## 🔹 INSERT

Adds a **new row**.

```sql
INSERT INTO Student (ID, Name, Age)
VALUES (101, 'Rahul', 20);
```

> **INSERT = Add new data**

---

## 🔹 UPDATE

Changes **existing data**.

```sql
UPDATE Student
SET Age = 21
WHERE ID = 101;
```

Before:

```text
101 → Rahul → 20
```

After:

```text
101 → Rahul → 21
```

> **UPDATE = Change existing data**

### ⚠️ Important

`WHERE` determines which rows are updated.

Without a suitable `WHERE`, multiple/all rows may be updated.

---

## 🔹 DELETE

Removes rows from a table.

```sql
DELETE FROM Student
WHERE ID = 101;
```

> **DELETE = Remove data**

Without `WHERE`:

```sql
DELETE FROM Student;
```

all rows can be deleted.

---

# 4. 🔍 DQL — Data Query Language

DQL is used to **retrieve/read data**.

Main command:

```text
SELECT
```

### 🧠 Memory Trick

> **DQL → Query / Read data**

---

## 🔹 SELECT — All Columns

```sql
SELECT * FROM Student;
```

`*` means:

> **All columns**

---

## 🔹 SELECT — Specific Columns

```sql
SELECT Name, Age
FROM Student;
```

Only `Name` and `Age` are returned.

---

## 🔹 WHERE

Used to **filter rows**.

```sql
SELECT *
FROM Student
WHERE ID = 101;
```

### Example

```sql
SELECT Name
FROM Student
WHERE Age = 20;
```

Returns students whose age is exactly `20`.

### Memory Trick

> **WHERE = Which rows?**

---

## 🔹 DISTINCT

Removes duplicate values from the **result**.

```sql
SELECT DISTINCT City
FROM Student;
```

If the data is:

```text
Delhi
Mumbai
Delhi
Mumbai
Patna
```

Result:

```text
Delhi
Mumbai
Patna
```

### Memory Trick

> **DISTINCT = No duplicate results**

---

# 🔥 UPDATE vs INSERT vs ALTER

This was an important confusion we cleared today.

| Command  | What changes?               |
| -------- | --------------------------- |
| `INSERT` | Adds a new **row/data**     |
| `UPDATE` | Changes existing **data**   |
| `ALTER`  | Changes table **structure** |

### Example

```text
INSERT → Add Priya
UPDATE → Change Rahul's age
ALTER  → Add Email column
```

---

# 🔥 DROP vs TRUNCATE vs DELETE

| Command    | Result                            |
| ---------- | --------------------------------- |
| `DELETE`   | Removes rows                      |
| `TRUNCATE` | Removes all rows, keeps structure |
| `DROP`     | Removes entire table              |

### Memory Trick

```text
DELETE    → Remove data 🗑️
TRUNCATE  → Empty table 🧹
DROP      → Destroy table 💥
```

---

# 🧠 Complete SQL Command Map

```text
                    SQL
                     │
          ┌──────────┼──────────┐
          ↓          ↓          ↓
         DDL        DML        DQL
          │          │          │
          ↓          ↓          ↓
       CREATE      INSERT      SELECT
       ALTER       UPDATE
       DROP        DELETE
       TRUNCATE
```

### Remember

```text
DDL → Structure 🏗️
DML → Data 📝
DQL → Retrieve 🔎
```

---

# ⚡ Quick Revision

### Constraints

```text
NOT NULL → No NULL
UNIQUE   → No duplicates
PRIMARY  → Main row identifier
FOREIGN  → Reference another table
CHECK    → Validate condition
DEFAULT  → Automatic value
```

### SQL Commands

```text
CREATE    → Create structure
ALTER     → Modify structure
DROP      → Remove structure
TRUNCATE  → Remove all rows
INSERT    → Add row
UPDATE    → Modify data
DELETE    → Remove rows
SELECT    → Retrieve data
WHERE     → Filter rows
DISTINCT  → Remove duplicate results
```

---

# 🎯 Today's Core Takeaway

> **DDL changes the structure.**
> **DML changes the data.**
> **DQL reads the data.**

And the most important distinction:

```text
INSERT → New row
UPDATE → Existing data
ALTER  → Table structure
```

**Today's DBMS Session: ✅ Completed**
