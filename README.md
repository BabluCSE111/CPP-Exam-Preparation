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
