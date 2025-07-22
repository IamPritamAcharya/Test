# Database Management System Exercises - Solutions

## 1.1 File-oriented vs Database-oriented Systems

**File-oriented System:**
- Data stored in separate files for each application
- Data redundancy and inconsistency common
- Limited data sharing between applications
- No centralized control

**Database-oriented System:**
- Centralized data storage with DBMS
- Data independence and integrity maintained
- Controlled data sharing and access
- Reduced redundancy through normalization

## 1.2 Automatic Teller Machine Program

The ATM program communicates with:
- **User**: Through GUI interface (card reader, keypad, display, cash dispenser)
- **Database**: Via network connection to bank's central database for account verification, balance checking, transaction processing, and logging

## 1.3 Database Terms Definitions

- **Metadata**: Data about data; describes structure, constraints, and properties of database
- **Data Independence**: Ability to change database structure without affecting applications
- **Database Administrator**: Person responsible for database design, maintenance, and security
- **Query Processor**: Component that interprets and executes database queries
- **Data Manager**: Controls access to data and manages storage operations
- **External View**: User-specific view of database showing only relevant data

## 1.4 Mappings Required

**(a) Conceptual to External Mapping (Figure 1.16 → Figure 1.15):**

**Public Relations Dept External View (1.15a):**
- Maps EMPLOYEE.Name from conceptual → EMPLOYEE.Name in external
- Maps EMPLOYEE.Address from conceptual → EMPLOYEE.Address in external
- Hides: Soc_Sec_No, Department, Skill, Annual_Salary (security/privacy)

**Payroll Dept External View (1.15b):**
- Maps EMPLOYEE.Name from conceptual → EMPLOYEE.Name in external
- Maps EMPLOYEE.Soc_Sec_No from conceptual → EMPLOYEE.Soc_Sec_No in external
- Maps EMPLOYEE.Address from conceptual → EMPLOYEE.Address in external  
- Maps EMPLOYEE.Annual_Salary from conceptual → EMPLOYEE.Salary in external
- Hides: Department, Skill (not relevant for payroll)

**(b) External to Internal Mapping:**
- Both external views map to the same internal record structure
- Internal record stores all fields in 120-byte fixed-length format
- Physical storage uses EMPLOYEE.Soc_Sec_No as primary key for indexing

## 1.5 Field Replacement Changes

**Mappings requiring changes in Exercise 1.4:**
- **External to Conceptual mapping**: Must handle new field structure
- **Application programs**: Need updates to process new field format
- **Query processor**: May need modification for new data types

## 1.6 Airline Reservation Concurrent Booking

**Yes, it's possible** for two agents to book the last seat simultaneously due to:
- **Race condition**: Both agents read "seat available" before either updates
- **Lack of proper locking**: Database doesn't prevent concurrent access
- **Solution**: Implement transaction locking or optimistic concurrency control

## 1.7 Data Redundancy Problems

**Problems caused:**
- Data inconsistency when updates miss some copies
- Storage waste
- Update anomalies

**Complete elimination**: Generally not possible due to performance needs, but can be minimized through normalization and controlled duplication.

## 1.8 Importance of Data Control

**Why data is important:**
- Strategic business asset
- Enables informed decision-making
- Supports operational efficiency
- Compliance requirements

**Competitive advantage:**
- Better customer insights
- Faster response to market changes
- Improved operational efficiency
- Data-driven innovation

## 1.9 Enterprise Data Modeling

**Example: University System**

**Entities:**
- STUDENT (unique ID, name, enrollment date)
- COURSE (course code, title, credits)
- INSTRUCTOR (employee ID, name, department)
- ENROLLMENT (student-course relationship)

**Automated applications:**
- Student registration system
- Grade management
- Transcript generation
- Course scheduling

**Views:**
- Student view: Personal courses and grades
- Instructor view: Teaching assignments and student rosters
- Admin view: Complete academic records

## 1.10 Softcraft Ltd. Software Enterprise

**Entities of interest:**
- PRODUCT (software products)
- CUSTOMER (individuals/organizations buying software)
- EMPLOYEE (developers, sales, support staff)
- PROJECT (software development projects)
- LICENSE (software usage rights)
- SUPPORT_TICKET (customer service requests)

**Relationships:**
- Customers purchase Products
- Employees work on Projects
- Products have Licenses
- Customers create Support Tickets
- Projects produce Products
