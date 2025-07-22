# Database Query Processing Exercise Solutions

## 10.1 Relational Operators Implementation

**Projection, Selection, Join** - Implement to remove duplicate tuples:
- **Set-merge approach**: Sort results and merge to eliminate duplicates
- **Hashing approach**: Use hash table to track seen tuples, only output new ones

## 10.2 & 10.3 Repeat Exercises 4.3 & 4.4

These reference exercises from Chapter 4 regarding efficient relational algebra expressions and corresponding query trees. Without the original exercises, the solution would involve:
- Converting SQL to relational algebra
- Optimizing the expression tree
- Drawing the corresponding query execution tree

## 10.4 Optimal Relational Algebra Expression

For the given query referencing Chapter 4 Exercise 4.12:
- Apply selection operations as early as possible (push selections down)
- Apply projections early to reduce tuple size
- Choose efficient join order based on selectivity
- Use appropriate join algorithms (nested loop, sort-merge, or hash join)

## 10.5 Join Computation - R(A,B,C) and S(B,C,D)

**Given**: R has 1,000 tuples, 30 tuples/page, 100 pages; S has 10,000 tuples/page
**Buffers**: 3 for R, 5 for S

**Method**: Use hash join or sort-merge join
- **Hash Join**: Partition smaller relation R, probe with S
- **Sort-Merge**: Sort both relations on join attributes B,C then merge

## 10.6 Equivalence Rules Usage

**Without knowledge of relation schemas**:
- σ(R ∪ S) = σR ∪ σS (selection distributes over union)
- π(R ∩ S) = πR ∩ πS (projection distributes over intersection)

These can be used for query modification to improve evaluation efficiency.

## 10.7 Query Tree Generation

For queries with R(A,B,C), S(B,C,D,E):
- Draw initial query tree from SQL parse
- Apply optimization procedures:
  - Push selections down toward leaves
  - Push projections down when possible
  - Reorder joins for efficiency
  - Choose appropriate join algorithms

## 10.8 Database Query Analysis

For the given STUDENT/COURSE database query:
```sql
select S.Std#, S.Std_Name  
from STUDENT s, Grade g, Requisition r, COURSE c
where s.Course# = c.Course# and
      c.Course_Name = "Database" and  
      g.Grade = "A" and
      s.Std# = r.Std# and
      r.Course_Name = "Database Design"
```

**Strategy**: 
1. Join STUDENT and Grade on common key
2. Filter for Grade = "A" 
3. Join with COURSE on Course#
4. Filter for Course_Name = "Database"
5. Join with Requisition on Std#
6. Filter for Course_Name = "Database Design"
7. Project Std#, Std_Name

## 10.9 Optimal Query Tree

Generate optimal tree for Exercise 5.10 from Chapter 5:
- Identify most selective conditions
- Apply selections first
- Choose join order based on intermediate result sizes
- Use appropriate join algorithms

## 10.10 Algebraic Optimization

Use algebraic rules for modification process:
- Commutativity of joins
- Associativity of joins  
- Selection pushdown
- Projection pushdown
- Join reordering based on selectivity

## 10.11 Access Strategies

**Indexing and Hashing considerations**:
- **B+ tree indexes**: Good for range queries and equality
- **Hash indexes**: Excellent for equality, poor for ranges
- **Clustered vs unclustered**: Clustered reduces I/O for sequential access
- Choose strategy based on query patterns and data distribution

## 10.12 Nested Join with Block Access

**Modify algorithm for joins with multiple attributes**:
- Use block nested loop join
- Load outer relation in blocks to maximize buffer utilization
- For each block of outer relation, scan entire inner relation
- Join condition involves multiple attributes from both relations
- **Optimization**: If possible, use indexes on join attributes
