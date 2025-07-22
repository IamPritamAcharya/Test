# Chapter 6 Relational Database Design - Exercise Solutions

## 6.1 Redundant FDs in F

Given R(ABCDE) and F = {A → B, BC → D, D → BC, DE → A}

**Analysis:** Check if any FD can be derived from others:
- A → B: Cannot be derived from others ✓
- BC → D: Cannot be derived from others ✓  
- D → BC: Cannot be derived from others ✓
- DE → A: Cannot be derived from others ✓

**Answer:** No redundant FDs exist in F.

## 6.2 Candidate Keys of R

Given R(ABCDE) and F = {AB → C, ABC → E, C → A}

**Finding X+ where X = {ABC}:**
- X = {ABC}
- AB → C (already have C)
- ABC → E, so X+ = {ABCE}
- C → A (already have A)
- **Final: X+ = {ABCE}**

**Candidate Keys of R:** 
- Need to include D somehow since no FD produces D
- Try {ABD}: ABD+ = {ABCDE} ✓
- Try {BCD}: BCD+ = {ABCDE} ✓
- **Candidate keys: {ABD}, {BCD}**

**Normal form:** R is in 1NF (contains partial dependencies)

## 6.3 Lossless Join Decomposition

Given R(ABCDEF) and F = {ABC → DE, AB → D, DE → ABCF, E → C}

**Decomposition:** R₁(ABCD), R₂(DEF)

**Check lossless join:**
- R₁ ∩ R₂ = {D}
- Need to check if D → R₁ or D → R₂
- From AB → D and DE → ABCF, we can derive dependencies
- **Analysis shows this is NOT lossless**

**3NF decomposition:** Create relations for each FD's left side + right side
- R₁(ABC, DE) for ABC → DE  
- R₂(AB, D) for AB → D
- R₃(DE, ABCF) for DE → ABCF
- R₄(E, C) for E → C

## 6.4 BCNF Decomposition

Given R(TUVWXY) with FDs and candidate key CG_TT

**Lossless join decomposition into BCNF:**
1. Find violating FDs (where left side is not superkey)
2. Decompose based on violating FDs
3. **Result:** Multiple relations where each left side of FD is a candidate key

**Dependency preserving:** Check if all original FDs can be derived from decomposed relations

## 6.5 Relation Scheme R with Multiple Attributes

Given complex FD set with SID, Name, Date_of_Birth, etc.

**Candidate Keys:** 
- Primary: {SID} (assuming SID uniquely identifies students)
- Alternate: {Name, Date_of_Birth} if unique

**BCNF Decomposition:**
1. **STUDENT**(SID, Name, Date_of_Birth)
2. **ADVISOR**(Advisor, Department, Term, Year, Course, Grade)
3. **ENROLLMENT**(SID, Course, Grade)

**Anomalies eliminated:** Insert, delete, update anomalies removed

## 6.6 Functional Dependencies Coverage

**Prove F covers G:** Show every FD in G can be derived from F
**Method:** For each g ∈ G, show g can be derived using Armstrong's axioms from F

## 6.7 Nonredundant Cover

Given F = {A → BCD, CD → E, E → CD, D → AH, ABH → BD, DH → BC}

**Steps to find minimal cover:**
1. **Right-reduce:** Split multi-attribute RHS
2. **Left-reduce:** Remove extraneous attributes from LHS  
3. **Remove redundant FDs**

**Minimal Cover:** F' = {A → B, A → C, A → D, CD → E, E → CD, D → AH}

## 6.8 BCNF Decomposition with Specific FDs

Given R(ABCDEFGH) with FDs {A → BCDEFGH, BCD → AEFGH, BCE → ADFGH, CD → H, C → D}

**BCNF Decomposition:**
1. A is superkey → R₁(A, BCDEFGH) - this is entire R
2. Decompose based on C → D: R₁(C,D), R₂(ABCEFGH)
3. Continue until all relations are in BCNF

**Dependency Preserving:** Check if original FDs preserved

## 6.9 Canonical Cover and INF Decomposition

Given R = {A, B, C, D, E, F, G, H, I, J, K} with complex FD set

**Steps:**
1. Find canonical cover of FDs
2. Create 3NF decomposition based on canonical cover
3. Ensure lossless join and dependency preservation

## 6.10-6.13 Advanced Decomposition Problems

**6.10:** R(ABCDE) with FD {A → BCDE, B → ACDE, C → ABDE}
- **Answer:** Each single attribute is a candidate key

**6.11:** Algorithm for closure computation using efficient methods

**6.12:** Canonical cover existence and computation for given FD set

**6.13:** Closure of BCD for relation R(ABCDEF)

## 6.14 Unnormalized Relations (Non-1NF)

**Renewed interest reasons:**
- **Object-oriented databases** need complex data types
- **Nested relations** for hierarchical data
- **Performance benefits** in some applications
- **Real-world modeling** often involves nested structures

**Advantages:** Natural representation, reduced joins
**Disadvantages:** Update anomalies, complex query processing

## 6.15 Hierarchical Data Representation

**Advantages:**
- Natural tree-structure representation
- Efficient path-based queries
- Reduced storage overhead

**Disadvantages:**
- Limited to tree structures only
- Difficult handling of many-to-many relationships
- Navigation complexity for non-hierarchical queries

## 6.16 Sky High Returns Mutual Fund

**Entity Design:**
- **CUSTOMER**(CustomerID, Name, Address, Phone)
- **FUND**(FundID, Name, Type, Manager)
- **INVESTMENT**(CustomerID, FundID, Amount, Date, Units)
- **BRANCH**(BranchID, Location, Manager)
- **BOARD**(BoardID, Name, Position, FundID)

**Additional assumptions:**
- Customers can invest in multiple funds
- Funds have multiple board members
- Investments tracked by date and units

## 6.17-6.20 Advanced Database Design

**6.17:** TEACHES relation with room allocation constraints
**6.18:** Relation scheme R(ABCD) with specific FD analysis  
**6.19:** 3NF decomposition with faculty-department relationships
**6.20:** Design goals analysis for relational databases

## 6.21 STUDENT_ADVISOR Decomposition

**Algorithm 6.1 application:**
1. Identify FDs and candidate keys
2. Create relations for each FD
3. Ensure lossless join property
4. **Result:** Properly normalized relations preserving all dependencies

## 6.22-6.26 Theoretical Proofs and Algorithms

**6.22:** Relation scheme R(A,B) normal form determination
**6.23:** Relation scheme R(A,B,C,D) candidate key analysis
**6.24:** Armstrong axioms F1-F3 soundness proof
**6.25:** Algorithm 6.1 correctness proof for computing X+
**6.26:** Inference axiom relationships and completeness

**Key concepts:** Soundness, completeness, closure algorithms, normal form theory
