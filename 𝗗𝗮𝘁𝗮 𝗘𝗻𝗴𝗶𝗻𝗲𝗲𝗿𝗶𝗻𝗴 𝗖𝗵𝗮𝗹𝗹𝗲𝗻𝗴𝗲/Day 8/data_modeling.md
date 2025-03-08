## Data Modeling Challenge: Data Normalization

### Which normal form removes partial dependencies on a primary key?

- A) 1NF
- B) 2NF
- C) 3NF
- D) BCNF
- 
**Ans:** B) 2NF (Second Normal Form)

**Explanation:**

A table is in **Second Normal Form (2NF)** if:  
1. It is already in **First Normal Form (1NF)** (i.e., no repeating groups or arrays).  
2. **It has no partial dependencies**—meaning **all non-key attributes must depend on the entire primary key, not just a part of it**.  

#### **Example of Partial Dependency (Violation of 2NF)**  
Consider a table with a **composite primary key** (`Student_ID, Course_ID`):  

| Student_ID | Course_ID | Student_Name | Course_Name |
|------------|-----------|--------------|-------------|
| 101        | C01       | Rohish       | Math        |
| 102        | C02       | Chandra      | Science     |

Here, `Student_Name` **only depends on** `Student_ID`, and `Course_Name` **only depends on** `Course_ID`.  
This is a **partial dependency**, violating **2NF**.

#### **How to Fix This?**
- **Decompose** the table into separate tables:
  1. **Student Table** (`Student_ID`, `Student_Name`)
  2. **Course Table** (`Course_ID`, `Course_Name`)
  3. **Enrollment Table** (`Student_ID`, `Course_ID`) → Resolves many-to-many relationships.

Now, each **non-key column depends on the full primary key**, achieving **2NF**.

#### **Why Not the Others?**
- **1NF** → Removes repeating groups but **doesn’t address partial dependencies**.  
- **3NF** → Eliminates **transitive dependencies**, but **partial dependencies must already be removed** (i.e., must be in 2NF first).  
- **BCNF** → A stricter version of 3NF but doesn’t specifically focus on partial dependencies.  