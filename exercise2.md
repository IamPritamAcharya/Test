# Chapter 2 Data Models - Exercise Solutions

## 2.1 Define the following terms:

**(a) Association**: A relationship or connection between entities in a data model that represents how they interact or relate to each other.

**(b) Relationship**: A meaningful connection between two or more entities that defines how they are related in the real world.

**(c) Aggregation**: A relationship where one entity is composed of or contains other entities (whole-part relationship).

**(d) Specialization**: Process of defining subclasses of an entity type, creating more specific entity types from a general one.

**(e) Generalization**: Process of defining a general entity type from several specialized entity types by identifying common attributes.

## 2.2 Organization E-R Diagram

**Example: University System**

**Entities and Relationships:**
- STUDENT (StudentID, Name, Address, Major)
- COURSE (CourseID, Title, Credits, Department)
- INSTRUCTOR (InstructorID, Name, Department, Office)
- DEPARTMENT (DeptID, DeptName, Building, Head)
- ENROLLMENT (enrolls relationship between STUDENT and COURSE)

**Key Relationships:**
- Student ENROLLS IN Course (M:N)
- Instructor TEACHES Course (1:N)
- Course BELONGS TO Department (N:1)
- Department HAS Instructors (1:N)

## 2.3 Weak Entities

**Weak entities are necessary when:**
- An entity cannot exist independently
- Its primary key depends on another entity's key

**Distinction:**
- **Strong Entity**: Has its own primary key, exists independently
- **Weak Entity**: Depends on strong entity for identification, uses partial key + owner's key

**Conversion**: Yes, a weak entity can become strong by adding sufficient attributes to create an independent primary key.

## 2.4 EMPLOYEE Entity Conversion

**One-to-Many Associations converted to weak entities:**
- DEPENDENT (EmpID + DepName as key, Relationship, Age)
- PROJECT_ASSIGNMENT (EmpID + ProjectID as key, Hours, StartDate)

**Many-to-Many Associations converted to relationships:**
- WORKS_ON (Employee-Project with attributes: Hours, Role)
- MANAGES (Employee-Department with attributes: StartDate)

## 2.5 E-R to Network Model Conversion

**Network Model Components:**
- **Record Types**: EMPLOYEE, DEPARTMENT, PROJECT
- **Set Types**: 
  - DEPT_EMP (Department owns Employee)
  - EMP_PROJ (Employee member of Project)
- **Owner/Member Structure**: Department owns Employees, Employees work on Projects

## 2.6 E-R to Hierarchical Model Conversion

**Hierarchical Structure:**
- **Root**: DEPARTMENT
- **Level 1 Children**: EMPLOYEE records under each department
- **Level 2 Children**: PROJECT records under each employee

**Handling Multiple Hierarchies**: Use virtual records or duplicate data when an entity appears in multiple hierarchies.

## 2.7 Association vs Relationship Representation

**Network Model**: 
- Uses set types to represent associations
- Owner-member relationships with explicit pointers
- More complex navigation through linked records

**Hierarchical Model**:
- Uses parent-child tree structure
- Relationships represented by physical containment
- Simpler navigation but limited to tree traversal

## 2.8 People's Bank E-R Diagram

**Entities:**
- CUSTOMER (CustomerID, Name, Address, Phone)
- ACCOUNT (AccountNo, Type, Balance, OpenDate)
- BRANCH (BranchID, Name, Address, Manager)
- TRANSACTION (TransID, Date, Amount, Type)

**Relationships:**
- Customer OWNS Account (1:N)
- Account BELONGS TO Branch (N:1)
- Account HAS Transaction (1:N)
- Customer CAN BE Joint owner (M:N for joint accounts)

## 2.9 Sample Tables for Exercise 2.8

**CUSTOMER Table:**
```
CustomerID | Name        | Address      | Phone
C001      | John Smith  | 123 Main St  | 555-0101
C002      | Jane Doe    | 456 Oak Ave  | 555-0102
```

**ACCOUNT Table:**
```
AccountNo | Type     | Balance | CustomerID | BranchID
A001     | Checking | 1500.00 | C001       | B001
A002     | Savings  | 5000.00 | C001       | B001
```

## 2.10 Universal Hockey League Network/Hierarchical Models

**Network Model:**
- **Record Types**: PLAYER, TEAM, GAME, STATISTICS
- **Set Types**: TEAM_PLAYER, GAME_PARTICIPATION, PLAYER_STATS
- Allows multiple relationships and efficient queries

**Hierarchical Model:**
- **Root**: LEAGUE
- **Level 1**: TEAM records
- **Level 2**: PLAYER records under teams
- **Level 3**: GAME_STATS under players
- Limited by tree structure, requires duplication for complex queries

## 2.11 UHL Career Statistics Database

**Modified E-R Diagram:**
- PLAYER entity with career attributes (TotalGoals, TotalAssists, CareerStart)
- SEASON entity (Year, StartDate, EndDate)
- PLAYER_SEASON relationship (Goals, Assists, Games) for annual stats
- Maintains both career totals and seasonal breakdowns

## 2.12 Forward/Goalie Position Relationships

**IS-A Relationships:**
- PLAYER is superclass
- FORWARD and GOALIE are subclasses
- FORWARD_POSITION (Center, Left Wing, Right Wing)
- GOAL_POSITION (specific goalie attributes)

**E-R Diagram Enhancement:**
- Add specialization hierarchy
- Position-specific attributes in subclasses
- Maintain common player attributes in superclass

## 2.13 Navigation Comparison

**Relational Model Navigation:**
- Uses SQL joins and set operations
- Declarative queries - specify what you want
- Optimizer handles execution path
- More flexible for complex queries

**Hierarchical Model Navigation:**
- Requires procedural path specification
- Must follow parent-child links explicitly
- Limited to tree traversal patterns
- More restrictive but potentially faster for simple hierarchical queries
