# 📘 Day 1: Classes and Objects

## 🎯 Objective

Learn how to create a class, create objects, and access members using the dot operator.

---

# 🔄 Flow Diagram

```text
Problem
↓
Create Class
↓
Declare Data Members
↓
Write Member Function
↓
Create Object
↓
Assign Values
↓
Call Function
↓
Display Output
```

---

# 📖 Definition

### Class

A class is a user-defined data type that combines data members and member functions into a single unit.

### Object

An object is an instance of a class.

---

# 🏗 Program Building Approach

## Step 1: Create Class

```cpp
class Student
{
};
```

Purpose:

- Create a blueprint for objects.

---

## Step 2: Declare Data Members

```cpp
string studentName;
int rollNo;
double cgpa;
```

Purpose:

- Store information about a student.

---

## Step 3: Write Member Function

```cpp
void display()
{
    cout<<"Student Name: "<<studentName<<endl;
    cout<<"Roll No: "<<rollNo<<endl;
    cout<<"CGPA: "<<cgpa<<endl;
}
```

Purpose:

- Display object data.

---

## Step 4: Create Object

```cpp
Student s1;
```

Purpose:

- Create an instance of the class.

---

## Step 5: Assign Values

```cpp
s1.studentName="Bablu";
s1.rollNo=20;
s1.cgpa=5.66;
```

Purpose:

- Initialize data members.

---

## Step 6: Call Member Function

```cpp
s1.display();
```

Purpose:

- Print object information.

---

# 💻 Complete Program

```cpp
#include<iostream>
#include<string>
using namespace std;

class Student
{
public:
    string studentName;
    int rollNo;
    double cgpa;

    void display()
    {
        cout<<"Student Name: "<<studentName<<endl;
        cout<<"Roll No: "<<rollNo<<endl;
        cout<<"CGPA: "<<cgpa<<endl;
    }
};

int main()
{
    Student s1;

    s1.studentName="Bablu";
    s1.rollNo=20;
    s1.cgpa=5.66;

    s1.display();

    return 0;
}
```

---

# ⚙ Execution Flow

```text
Program Starts
↓
Class Created
↓
Object Created
↓
Memory Allocated
↓
Values Assigned
↓
display() Called
↓
Output Displayed
↓
Program Ends
```

---

# 📌 Important Points

- Class = Blueprint
- Object = Instance of class
- Memory is allocated when object is created
- Members are accessed using dot operator (.)
- Data members store information
- Member functions operate on data

---

# 🧠 Syntax Summary

## Create Class

```cpp
class ClassName
{
};
```

## Create Object

```cpp
ClassName objectName;
```

## Access Members

```cpp
objectName.variableName;
objectName.functionName();
```

---

# ❓ Viva Questions

### What is a class?

A class is a user-defined data type that combines data and functions.

---

### What is an object?

An object is an instance of a class.

---

### When is memory allocated?

Memory is allocated when an object is created.

---

### Why do we use public?

To access members outside the class.

---

### How are members accessed?

Using the dot operator (.).

---

# 🪞 Mirror Explanation

A class is a user-defined data type that combines data members and member functions. An object is an instance of a class. Memory is allocated when an object is created. Members are accessed using the dot operator. Member functions are used to perform operations on data.

---

# 📝 Practice Questions

### Question 1

Create an Employee class containing:

- empName
- empId
- salary

Write a display() function.

---

### Question 2

Create a Book class containing:

- bookName
- price

Display book information.

---

# ⏭ Next Topic

**Day 2: Constructors**
