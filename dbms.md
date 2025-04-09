I'll solve the database management system lab assignments, providing both SQL commands and explanations for each question. I'll include the question text along with my solutions.

## Assignment 1: Creating Tables

```sql
-- Creating DEPT table
CREATE TABLE DEPT (
    Dno NUMBER(3) PRIMARY KEY,
    Dname VARCHAR(10)
);

-- Creating EMP table
CREATE TABLE EMP (
    Eno VARCHAR(5) PRIMARY KEY,
    Ename VARCHAR(10) NOT NULL,
    City CHAR(10) CHECK (City IN ('delhi', 'kolkata', 'chennai', 'mumbai')),
    Salary INTEGER,
    JoinDate DATE,
    Dno NUMBER(3),
    CONSTRAINT fk_dept FOREIGN KEY (Dno) REFERENCES DEPT(Dno),
    CONSTRAINT chk_eno CHECK (Eno LIKE 'E%')
);

-- Creating PROJECT table
CREATE TABLE PROJECT (
    Pno VARCHAR(5),
    Eno VARCHAR(5),
    PRIMARY KEY (Pno, Eno),
    CONSTRAINT fk_emp FOREIGN KEY (Eno) REFERENCES EMP(Eno),
    CONSTRAINT chk_pno CHECK (Pno LIKE 'P%')
);
```

## Assignment 2: Inserting Data

```sql
-- Inserting data into DEPT table
INSERT INTO DEPT VALUES (1, 'research');
INSERT INTO DEPT VALUES (2, 'finance');

-- Inserting data into EMP table
INSERT INTO EMP VALUES ('E1', 'ashim', 'kolkata', 18000, TO_DATE('01-jan-14', 'DD-MON-YY'), 1);
INSERT INTO EMP VALUES ('E2', 'kamal', 'mumbai', 10000, TO_DATE('01-jun-14', 'DD-MON-YY'), 2);
INSERT INTO EMP VALUES ('E3', 'tamal', 'chennai', 7000, TO_DATE('01-jan-15', 'DD-MON-YY'), 1);
INSERT INTO EMP VALUES ('E4', 'asha', 'kolkata', 8000, TO_DATE('01-jun-15', 'DD-MON-YY'), 2);
INSERT INTO EMP VALUES ('E5', 'timir', 'delhi', 7000, TO_DATE('01-jan-16', 'DD-MON-YY'), 1);

-- Inserting data into PROJECT table
INSERT INTO PROJECT VALUES ('P1', 'E1');
INSERT INTO PROJECT VALUES ('P2', 'E3');
INSERT INTO PROJECT VALUES ('P1', 'E5');
INSERT INTO PROJECT VALUES ('P2', 'E1');
```

## Assignment 3: Table Structure and Modification

a) Display the structure of table EMP.
```sql
DESCRIBE EMP;
```

b) Modify the data type size of Ename to varchar15.
```sql
ALTER TABLE EMP MODIFY Ename VARCHAR(15);
```

c) Display the user constraints of table EMP.
```sql
SELECT constraint_name, constraint_type, table_name
FROM user_constraints
WHERE table_name = 'EMP';
```

## Assignment 4: Adding and Removing Columns and Constraints

a) Add a new column Mobile no which is unique (candidate key) of table EMP.
```sql
ALTER TABLE EMP ADD MobileNo VARCHAR(10);
ALTER TABLE EMP ADD CONSTRAINT uk_mobile UNIQUE (MobileNo);
```

b) Add the constraint for Mobile no which is exactly of 10 digit.
```sql
ALTER TABLE EMP ADD CONSTRAINT chk_mobile CHECK (LENGTH(MobileNo) = 10);
```

c) Drop all constraints of Mobile no.
```sql
ALTER TABLE EMP DROP CONSTRAINT uk_mobile;
ALTER TABLE EMP DROP CONSTRAINT chk_mobile;
```

d) Drop the column Mobile no of table EMP.
```sql
ALTER TABLE EMP DROP COLUMN MobileNo;
```

## Assignment 5: Adding a New Column and Updating Values

a) Add a new column MgrId of data size number5 and MgrId values should reference from Eno of table EMP.
```sql
ALTER TABLE EMP ADD MgrId VARCHAR(5);
ALTER TABLE EMP ADD CONSTRAINT fk_mgr FOREIGN KEY (MgrId) REFERENCES EMP(Eno);
```

b) Update the table EMP with MgrId values.
```sql
-- First add the Mobile number column back as it's in the update table
ALTER TABLE EMP ADD MobileNo VARCHAR(10);

-- Update the MgrId values
UPDATE EMP SET MgrId = 'E1', MobileNo = '9876543211' WHERE Eno = 'E1';
UPDATE EMP SET MgrId = 'E2', MobileNo = '9876543212' WHERE Eno = 'E2';
UPDATE EMP SET MgrId = 'E1', MobileNo = '9876543213' WHERE Eno = 'E3';
UPDATE EMP SET MgrId = 'E2', MobileNo = '9876543214' WHERE Eno = 'E4';
UPDATE EMP SET MgrId = 'E1', MobileNo = '9876543215' WHERE Eno = 'E5';
```

## Assignment 6: Basic Queries

a) Display list of all employees in department no 2.
```sql
SELECT * FROM EMP WHERE Dno = 2;
```

b) Display name and salary of employees in department number 1 and 2.
```sql
SELECT Ename, Salary FROM EMP WHERE Dno IN (1, 2);
```

c) Display name of employees having 'a' as the second letter in their name.
```sql
SELECT Ename FROM EMP WHERE Ename LIKE '_a%';
```

d) Display list of all employees who have named exactly 4 characters.
```sql
SELECT * FROM EMP WHERE LENGTH(Ename) = 4;
```

e) Display employee names and department no for those who joined in the month of June.
```sql
SELECT Ename, Dno FROM EMP WHERE TO_CHAR(JoinDate, 'MON') = 'JUN';
```

f) Display the list of all employees who were joined during 2025.
```sql
SELECT * FROM EMP WHERE TO_CHAR(JoinDate, 'YYYY') = '2025';
```

g) Display the joining date of all employees in dd/mm/yy format.
```sql
SELECT Ename, TO_CHAR(JoinDate, 'DD/MM/YY') AS JoinDate FROM EMP;
```

## Assignment 7: Ordering and Filtering

a) Display names of all employees in the alphabetic order.
```sql
SELECT Ename FROM EMP ORDER BY Ename;
```

b) List the name and the salary of all employees ordered by salary descending order.
```sql
SELECT Ename, Salary FROM EMP ORDER BY Salary DESC;
```

c) List all the employee names whose salary is greater than 7000 and less than 18000.
```sql
SELECT Ename FROM EMP WHERE Salary > 7000 AND Salary < 18000;
```

d) List of all employees who have salary between 7000 and 8000.
```sql
SELECT * FROM EMP WHERE Salary BETWEEN 7000 AND 8000;
```

e) Display employee names and department nos of all employees who belong to either 'chennai', or 'kolkata', or 'mumbai'.
```sql
SELECT Ename, Dno FROM EMP WHERE City IN ('chennai', 'kolkata', 'mumbai');
```

## Assignment 8: Aggregate Functions

a) Find the average salary of all employees.
```sql
SELECT AVG(Salary) AS AverageSalary FROM EMP;
```

b) Find the difference between highest and lowest salary of employee.
```sql
SELECT MAX(Salary) - MIN(Salary) AS SalaryDifference FROM EMP;
```

c) Display the department no and no. of employees in each department.
```sql
SELECT Dno, COUNT(*) AS NumberOfEmployees FROM EMP GROUP BY Dno;
```

d) Display employee no, employee name and salary for employee with lowest salary.
```sql
SELECT Eno, Ename, Salary FROM EMP WHERE Salary = (SELECT MIN(Salary) FROM EMP);
```

e) List only the names of all other employees who get the same salary as that of 'tamal'.
```sql
SELECT Ename FROM EMP 
WHERE Salary = (SELECT Salary FROM EMP WHERE Ename = 'tamal') 
AND Ename != 'tamal';
```

## Assignment 9: Group Functions and Complex Queries

a) Find all department numbers that have more than two employees.
```sql
SELECT Dno FROM EMP GROUP BY Dno HAVING COUNT(*) > 2;
```

b) Display the names of all employees who engaged in two or more projects.
```sql
SELECT e.Ename 
FROM EMP e
JOIN (
    SELECT Eno, COUNT(*) AS ProjectCount 
    FROM PROJECT 
    GROUP BY Eno 
    HAVING COUNT(*) >= 2
) p ON e.Eno = p.Eno;
```

c) List no. of projects undertaken in the department 1.
```sql
SELECT COUNT(DISTINCT p.Pno) AS NumberOfProjects
FROM PROJECT p
JOIN EMP e ON p.Eno = e.Eno
WHERE e.Dno = 1;
```

d) Display name and salary for all employees who are engaged with at least one project.
```sql
SELECT DISTINCT e.Ename, e.Salary
FROM EMP e
JOIN PROJECT p ON e.Eno = p.Eno;
```

e) Display employee names and department names of all employees who belong to either 'chennai', or 'kolkata', or 'mumbai'.
```sql
SELECT e.Ename, d.Dname
FROM EMP e
JOIN DEPT d ON e.Dno = d.Dno
WHERE e.City IN ('chennai', 'kolkata', 'mumbai');
```

## Assignment 10: Advanced Joins and Queries

a) Display employee name who get the highest salary.
```sql
SELECT Ename FROM EMP WHERE Salary = (SELECT MAX(Salary) FROM EMP);
```

b) Display employee name who get the 2nd highest salary.
```sql
SELECT Ename FROM EMP 
WHERE Salary = (
    SELECT MAX(Salary) FROM EMP
    WHERE Salary < (SELECT MAX(Salary) FROM EMP)
);
```

c) Display department number having most number of employees.
```sql
SELECT Dno
FROM EMP
GROUP BY Dno
HAVING COUNT(*) = (
    SELECT MAX(emp_count)
    FROM (
        SELECT COUNT(*) AS emp_count
        FROM EMP
        GROUP BY Dno
    )
);
```

d) Display employee name along with their manager name using self-join concept.
```sql
SELECT e.Ename AS EmployeeName, m.Ename AS ManagerName
FROM EMP e
JOIN EMP m ON e.MgrId = m.Eno;
```

e) Display employee name along with their department name using natural join and inner join.
```sql
-- Using INNER JOIN
SELECT e.Ename, d.Dname
FROM EMP e
INNER JOIN DEPT d ON e.Dno = d.Dno;

-- Using NATURAL JOIN (assuming column names are identical)
-- Note: This would only work if the joining columns had identical names
-- Since we have Dno in both tables with same name, we can use:
SELECT e.Ename, d.Dname
FROM EMP e
NATURAL JOIN DEPT d;
```

f) Display student roll no, sname, company cname, campus cdate where they got job using left, right and full outer join on student and placement table.
```sql
-- For this, we would need STUDENT and PLACEMENT tables, which aren't provided.
-- Here's a generic example assuming these tables exist:

-- Using LEFT OUTER JOIN
SELECT s.rollno, s.sname, p.cname, p.cdate
FROM STUDENT s
LEFT OUTER JOIN PLACEMENT p ON s.rollno = p.rollno;

-- Using RIGHT OUTER JOIN
SELECT s.rollno, s.sname, p.cname, p.cdate
FROM STUDENT s
RIGHT OUTER JOIN PLACEMENT p ON s.rollno = p.rollno;

-- Using FULL OUTER JOIN
SELECT s.rollno, s.sname, p.cname, p.cdate
FROM STUDENT s
FULL OUTER JOIN PLACEMENT p ON s.rollno = p.rollno;
```

## Assignment 11: Set Operations

a) Display name of employees whose either salary>=8000 or resides in city Kolkata using union operation.
```sql
SELECT Ename FROM EMP WHERE Salary >= 8000
UNION
SELECT Ename FROM EMP WHERE City = 'kolkata';
```

b) Display name of employees whose salary>=8000 and resides in city Kolkata using intersect operation.
```sql
SELECT Ename FROM EMP WHERE Salary >= 8000
INTERSECT
SELECT Ename FROM EMP WHERE City = 'kolkata';
```

c) Display employees name, salary and city whose salary>=8000 but not resides in city Kolkata using minus operation.
```sql
SELECT Ename, Salary, City FROM EMP WHERE Salary >= 8000
MINUS
SELECT Ename, Salary, City FROM EMP WHERE City = 'kolkata';
```

d) Display detail of employees who work in some project.
```sql
SELECT e.* 
FROM EMP e
WHERE EXISTS (
    SELECT 1 FROM PROJECT p WHERE p.Eno = e.Eno
);
```

e) Display detail of employees who does not work in any project.
```sql
SELECT e.* 
FROM EMP e
WHERE NOT EXISTS (
    SELECT 1 FROM PROJECT p WHERE p.Eno = e.Eno
);
```

These solutions cover all the assignments from the provided document. Each SQL command is tailored to address the specific requirements of the questions.
