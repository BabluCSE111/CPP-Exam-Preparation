# DBMS — SQL Advanced Notes

## 1. GROUP BY

**Definition:** Groups rows having the same value.

```sql
SELECT Dept, AVG(Salary)
FROM Employee
GROUP BY Dept;
```

**Memory:** `GROUP BY → Create groups`

---

## 2. HAVING

**Definition:** Filters groups created by `GROUP BY`.

```sql
SELECT Dept, AVG(Salary)
FROM Employee
GROUP BY Dept
HAVING AVG(Salary) > 50000;
```

**WHERE vs HAVING**

* `WHERE` → filters individual rows
* `HAVING` → filters groups

**Memory:** `WHERE → Rows | HAVING → Groups`

---

## 3. JOIN

**Definition:** Combines data from multiple tables using a related column.

### INNER JOIN

Returns only matching rows.

```sql
SELECT *
FROM Student
INNER JOIN Department
ON Student.Dept_ID = Department.Dept_ID;
```

**Memory:** `INNER → Matching only`

### LEFT JOIN

Returns all rows from the LEFT table + matching rows from RIGHT.

**Memory:** `LEFT → Protect LEFT table`

### RIGHT JOIN

Returns all rows from the RIGHT table + matching rows from LEFT.

**Memory:** `RIGHT → Protect RIGHT table`

### FULL OUTER JOIN

Returns all rows from both tables. Unmatched values become `NULL`.

**Memory:** `FULL → Nobody gets left out`

---

## 4. JOIN + WHERE

```sql
SELECT Student.Name, Department.Department
FROM Student
INNER JOIN Department
ON Student.Dept_ID = Department.Dept_ID
WHERE Department.Department = 'CSE';
```

* `ON` → tells SQL **how tables are connected**
* `WHERE` → tells SQL **which rows to keep**

---

## 5. SUBQUERY

**Definition:** A query written inside another query.

Example: Find employee(s) with the highest salary.

```sql
SELECT Name
FROM Employee
WHERE Salary = (
    SELECT MAX(Salary)
    FROM Employee
);
```

**Logic:**

1. Inner query → finds maximum salary
2. Outer query → finds employee having that salary

**Memory:** `Inner → Find value | Outer → Use value`

---

## 6. IN with Subquery

Used when the subquery can return **multiple values**.

```sql
SELECT Name
FROM Employee
WHERE Dept_ID IN (
    SELECT Dept_ID
    FROM Department
    WHERE City = 'Delhi'
);
```

If inner query returns `10, 30`, the outer query finds employees whose `Dept_ID` is 10 or 30.

**Memory:** `IN → Is this value in the list?`

---

## 7. EXISTS

Checks whether **at least one matching row exists**.

```sql
SELECT Name
FROM Employee e
WHERE EXISTS (
    SELECT 1
    FROM Department d
    WHERE d.Dept_ID = e.Dept_ID
);
```

**Memory:** `EXISTS → Does a matching row exist?`

### IN vs EXISTS

* `IN` → checks a value against a specific set/list
* `EXISTS` → checks whether a matching row exists

Example:

```sql
WHERE Dept_ID IN (10, 20, 30);
```

→ `IN`, because we have a specific list of values.

---

## 8. CORRELATED SUBQUERY ⭐ NEXT

**Definition:** A subquery that depends on a value from the outer query.

**Key Difference:**

* Normal subquery → works independently
* Correlated subquery → depends on the outer query

**Memory:** `Correlated → Inner depends on Outer`

---

# ⚡ QUICK REVISION

GROUP BY → Create groups
HAVING → Filter groups
INNER JOIN → Matching rows
LEFT JOIN → All LEFT rows
RIGHT JOIN → All RIGHT rows
FULL JOIN → All rows from both
ON → Connect tables
WHERE → Filter rows
Subquery → Query inside query
IN → Check against a list
EXISTS → Check whether row exists
Correlated Subquery → Inner depends on outer
