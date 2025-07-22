# Database Query Processing & Recovery Exercise Solutions

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

# Recovery System Exercises

## 11.1 Crash Recovery for Partial Transactions
**Can online transactions be recovered?**
Yes, using:
- **Transaction logs**: Record all operations before execution
- **Checkpoints**: Periodic snapshots of database state
- **Rollback**: Undo partially completed transactions using log entries
- **Two-phase commit**: For distributed transactions

## 11.2 Update-in-Place Recovery System
**Recovery from system crash during log force operation:**
- Use **write-ahead logging (WAL)** protocol
- Log records written to stable storage before data pages
- During recovery: scan log backward, undo uncommitted transactions
- Maintain **LSN (Log Sequence Number)** in each data page

## 11.3 Transaction Recovery Methods
**If transactions are never committed or they're nested:**
- **Nested transactions**: Use savepoints and partial rollback
- **Cascading rollback**: Undo all dependent transactions
- **Strict 2PL**: Hold locks until commit to avoid cascading aborts
- **Log-based recovery**: Maintain undo information for all operations

## 11.4 Forwarding Address Recovery
**System crash during forwarding address updates:**
- Use **intention lists**: Record planned moves before execution
- **Atomic operations**: Ensure forwarding updates are indivisible
- **Recovery procedure**: Check intention list, complete or undo moves
- **Dual logging**: Log both old and new locations

## 11.5 Shadow Page Recovery with Updates
**Apply technique to DBMS using update-in-place:**
- **Shadow paging**: Keep current and shadow page tables
- **Copy-on-write**: Create new pages for modified data
- **Commit protocol**: Atomically switch page table pointers
- **Garbage collection**: Reclaim old pages after commit

## 11.6 Checkpointing Frequency Analysis
**Low vs. high frequency effects:**
- **Low frequency**: Faster normal operation, slower recovery
- **High frequency**: Slower normal operation, faster recovery
- **Optimal strategy**: Balance based on failure rate and performance requirements
- **Fuzzy checkpointing**: Allow concurrent transactions during checkpointing

## 11.7 Destructive vs. Non-destructive Transactions
**Recovery techniques for online systems:**
- **Non-destructive**: Use versioning, easier rollback
- **Destructive**: Requires careful logging and before-images
- **MVCC**: Multi-version concurrency control for non-destructive reads
- **Restart active transactions**: Resume from last checkpoint

## 11.8 Partial Writes and Log Entry Requirements
**Indicate head and tail of log:**
- **Log Structure**: Sequential write-ahead log with LSN
- **Head pointer**: Most recent log entry
- **Tail pointer**: Oldest required log entry (based on active transactions)
- **Circular buffer**: Reuse space after entries no longer needed

## 11.9 Two-Pass Recovery Strategy
**For database used to be logged:**
- **Pass 1 (Analysis)**: Determine which transactions were active at crash
- **Pass 2 (Redo/Undo)**: Redo committed transactions, undo active ones
- **ARIES algorithm**: Analysis, Redo, Undo phases
- **Compensation log records**: Handle undo operations properly

## 11.10 & 11.11 Checkpoint Information and Recovery Operations
**Used in recovery operation following system crash:**
- **Active transaction list**: Transactions running at checkpoint
- **Dirty page list**: Modified pages not yet written to disk
- **Transaction table**: Status of each transaction
- **Recovery operations**: Restart from checkpoint, apply redo/undo

## 11.12 Recovery Terms Definitions
- **Transaction-consistent checkpoint**: All active transactions recorded
- **Action-consistent checkpoint**: All actions of committed transactions applied
- **Transaction restart checkpoint**: Point where transaction can safely restart
- **Fuzzy checkpoint**: Checkpoint taken without stopping other transactions
- **Two-phase commit**: Protocol ensuring atomicity across multiple databases

## 11.13 Shadow Page Recovery Comparison
**Compare shadow page with update-in-place:**
- **Shadow paging**: No in-place updates, atomic commits via pointer switching
- **Update-in-place**: Direct modification with logging for recovery
- **Undo operations**: Not needed in shadow paging, required for update-in-place
- **Performance**: Shadow paging avoids undo overhead but may cause fragmentation

## 11.14 Software Errors and Volatile Storage
**What type of software errors can cause failure with loss of volatile storage:**
- **Operating system crashes**: Memory corruption, kernel panics
- **DBMS software bugs**: Buffer management errors, transaction manager failures
- **Hardware failures**: Power loss, memory failures
- **Recovery**: Requires stable storage (disk) and transaction logs

## 11.15 Transaction Termination Methods
**Write-ahead logging and checkpointing strategies:**
- **Normal termination**: Transaction commits successfully
- **Abort**: Transaction rolled back due to conflict or error
- **System crash**: External failure requiring recovery procedures
- **Write-ahead logging**: Ensures durability and enables proper recovery

## 11.16 Logging Method Advantages/Disadvantages
**Methods discussed in Section 11.6:**
- **Immediate update**: Fast commits, complex recovery
- **Deferred update**: Simple recovery, delayed durability  
- **Shadow paging**: No undo needed, potential disk fragmentation
- **Checkpointing**: Reduces recovery time, adds runtime overhead

## 11.17 Update-in-Place with Database Propagation
**Where database system defers propagation until transaction commits:**
- **Deferred update strategy**: Write to log first, database later
- **Recovery operations**: Only redo needed (no undo)
- **Transaction commit**: Triggers propagation to database
- **Failure handling**: Lost updates recovered from log entries
- **Volatile storage**: Updates lost on crash, recovered from stable log
