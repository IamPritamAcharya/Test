# Chapter 4 Relational Model - Exercise Solutions

## 4.1 Relational Operations on Relations P and Q

Given relations P and Q from Figure N:

**(a) Projection of Q on attributes (B,C):**
```
B    C
b₁   c₁
b₂   c₂
b₃   c₃
b₄   c₄
b₅   c₅
```

**(b) Natural join of P and Q on common attributes:**
Since both have attribute B, natural join P ⋈ Q:
```
A    B    C    D
a₁   b₁   c₁   d₁
a₂   b₂   c₂   d₂
a₃   b₃   c₃   d₃
a₄   b₄   c₄   d₄
a₅   b₅   c₅   d₅
```

**(c) Division P ÷ π_{B,C}(σ_{D='d₁'}(Q)):**
First find tuples in Q where D='d₁', then project on B,C, then divide P by this result.

## 4.2 E-R to Relational Schema Conversion (Figure O)

**Relations:**
```
PARTS(P#, NAME, COLOR, PRICE)
SUPPLIER(S#, NAME, ADDRESS)
SUPPLIES(S#, P#, QUALITY, QTY)
```

**Primary Keys:**
- PARTS: P#
- SUPPLIER: S#  
- SUPPLIES: (S#, P#) - composite key

**Foreign Keys:**
- SUPPLIES.S# references SUPPLIER.S#
- SUPPLIES.P# references PARTS.P#

## 4.3 Relational Algebra and Calculus Queries

**(a) Get supplier details and price of bolts for suppliers who supply 'bolts':**
```
π_{S#,NAME,ADDRESS,PRICE}(SUPPLIER ⋈ SUPPLIES ⋈ σ_{NAME='bolts'}(PARTS))
```

**(b) Find details of parts that suppliers who supply 'bolts' costing less than $0.10:**
```
π_{P#,NAME,COLOR}(σ_{PRICE<0.10}(PARTS) ⋈ SUPPLIES ⋈ SUPPLIER)
```

## 4.4 University Database Queries

**Relations:**
- ENROLL(S#, C#, Section)
- TEACH(Prof, C#, Section)
- ADVISE(Prof, S#)
- PRE_REQ(C#, Pre_C#)
- GRADES(S#, C#, Grade, Year)
- STUDENT(S#, Sname)

**(a) List all students taking courses with Smith or Jones:**
```
π_{Sname}(STUDENT ⋈ ENROLL ⋈ σ_{Prof='Smith' ∨ Prof='Jones'}(TEACH))
```

**(b) List students taking at least one course their advisor teaches:**
```
π_{Sname}(STUDENT ⋈ (ENROLL ⋈_{S#,C#,Section} (TEACH ⋈_{Prof} ADVISE)))
```

**(c) List professors who teach more than one section of same course:**
```
π_{Prof}(σ_{count>1}(γ_{Prof,C#;count(Section)}(TEACH)))
```

**(d) List courses "John Doe" can enroll in (has passed prerequisites):**
```
π_{C#}(PRE_REQ) - π_{Pre_C#}(PRE_REQ ⋈ σ_{Sname='John Doe' ∧ Grade<'C'}(STUDENT ⋈ GRADES))
```

## 4.5 Orchestra Database Queries

**Relations:**
- CONDUCTS(Conductor, Composition)
- REQUIRES(Composition, Instrument)
- PLAYS(Player, Instrument)
- LIKES(Player, Composition)

**(a) List players and instruments who can be part of orchestra when Lolita Melody conducts:**
```
π_{Player,Instrument}(PLAYS ⋈ REQUIRES ⋈ σ_{Conductor='Lolita Melody'}(CONDUCTS))
```

**(b) From players list, identify those who would like the compositions they play:**
```
π_{Player}(PLAYS ⋈ REQUIRES ⋈ CONDUCTS ⋈ LIKES)
```

## 4.6 Domain Calculus Conversions

**(a) English statement:** Find relations where attribute A equals 'a₁' AND there exists a related tuple where attribute B equals 'b₁' AND attribute C equals 'c₁'.

**(b) Domain calculus:** {⟨x,y,z⟩ | R(x,y,z) ∧ x = 'a₁' ∧ ∃u,v(S(u,v) ∧ u = 'b₁' ∧ v = 'c₁')}

**(c) Tuple calculus:** {t | t ∈ R ∧ t.A = 'a₁' ∧ ∃s(s ∈ S ∧ s.B = 'b₁' ∧ s.C = 'c₁')}

## 4.7 Tuple Calculus to Relational Algebra

**Given:** {⟨A,B⟩ | ⟨A,B⟩ ∈ rel₁ ∧ B = 'B₁' ∨ B = 'B₂'}

**Conversions:**
**(a) English:** Select tuples from rel₁ where B equals 'B₁' or B equals 'B₂'
**(b) Relational algebra:** σ_{B='B₁' ∨ B='B₂'}(rel₁)
**(c) Tuple calculus:** {t | t ∈ rel₁ ∧ (t.B = 'B₁' ∨ t.B = 'B₂')}

## 4.8 Physical Implementation Investigation

**Key considerations for relational DBMS implementation:**
- **Storage structures:** B-trees, hash tables, heap files
- **Index mechanisms:** Primary, secondary, clustered indexes  
- **Query optimization:** Cost-based optimization, join algorithms
- **Concurrency control:** Locking, timestamp ordering
- **Recovery mechanisms:** Logging, checkpointing

## 4.9 Inverted File Management System

**System design for "List records where attribute_name has value X":**
- **Inverted indexes:** Map each value to list of record IDs
- **Boolean combinations:** Use set operations (union, intersection)
- **Query processing:** Retrieve record IDs, then fetch actual records
- **Advantages:** Fast value-based searches, efficient Boolean queries

## 4.10-4.11 Tuple and Domain Calculus Queries

**Use quantifier ∀ instead of ∃ and vice versa for Examples 4.44:**
- Convert existential to universal: ¬∀ ≡ ∃¬
- Convert universal to existential: ¬∃ ≡ ∀¬

## 4.12 Employee-Project Database Queries

**(a) Acquire details of projects for each employee by name:**
```
π_{Ename,Pname,Location}(EMPLOYEE ⋈ ASSIGNED_TO ⋈ PROJECT)
```

**(b) Compile names of employees for each project 107 is assigned:**
```
π_{Ename}(EMPLOYEE ⋈ σ_{P#=107}(ASSIGNED_TO))
```

**(c) Names of employees assigned to projects whose chief architect is employee 109:**
```
π_{Ename}(EMPLOYEE ⋈ ASSIGNED_TO ⋈ σ_{Chief_Architect=109}(PROJECT))
```

**(d) List of employees assigned to all projects employee 107 is assigned:**
```
π_{E#}(ASSIGNED_TO) ÷ π_{P#}(σ_{E#=107}(ASSIGNED_TO))
```

## 4.13-4.19 Advanced Query Solutions

**4.13:** Repeat 4.12 using tuple calculus
**4.14:** Repeat 4.12 using domain calculus  
**4.15:** Tuple calculus for union, intersection, difference operations
**4.16:** Driving school database with theory/practical lessons
**4.17-4.19:** Employee project assignment correctness analysis

*Solutions involve complex relational calculus expressions with quantifiers and logical operators*
