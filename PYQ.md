# Question
Discuss the factors that govern the selection of physical
storage medium to look in from the perspective of a
database application.

# Question
From the perspective of a database application, what are
the factors that govern the selection of a physical storage
medium?

- **Performance**: Evaluate speed and access times.
- **Cost**: Consider hardware and maintenance expenses.
- **Capacity**: Ensure sufficient space for data growth.
- **Reliability**: Choose mediums with high durability.
- **Compatibility**: Confirm compatibility with existing systems.

# Question
Define:

iii) **Relationship Set**:
   - *Definition*: Group of relationships of the same type.
   - *Example*: "Works_For" relationship set between Employee and Department.

iv) **Disjoint Generalization**:
   - *Definition*: Subclasses have mutually exclusive entities.
   - *Example*: Animal generalization with disjoint subclasses Mammal and Bird.

v) **Total Participation of Entity Set in Relationship**:
   - *Definition*: Every entity in set must participate in relationship.
   - *Example*: "Enrolls_In" relationship where every student must enroll in a course.

# Question
Compare the 3 layer Web application architecture with the 2 layer
web application architecture with neat diagrams for both.
What is the disadvantage of the former as compared to the latter
architecture?

**3-layer:** Separates UI (Presentation), logic (Application), and data (Data Tier).

**2-layer:** Combines UI and logic into a single layer, simplifying development.


```
3-Layer Architecture:

          +---------------+
          |   Presentation |
          +---------------+
                  |
    +-------------+      +---------------+
    | Application | ---> |   Data Tier   |
    +-------------+      +---------------+

2-Layer Architecture:

          +---------------+
          | Combined       |
          | UI and Logic  |
          +---------------+
                  |
    +---------------+
    |   Data Tier   |
    +---------------+
```

Disadvantage of 3-Layer Architecture compared to 2-Layer:
- *Involves an additional layer for business logic.*
- *Increased system complexity and development effort.*

# Question
Consider the given transaction:
Ti: read(A);
A: = A-100;
write(A);
read(B);
B: = B + 100;
write(B);
[Given: Before the transactions; account A and account B have Rs.2000 and
Rs.3000 respectively]

Suppose that a failure happened after write(A) operation but before write(B)
operation, what is the effect on the database? What are the resultant values
of accounts A and B? Will the value A+B be preserved? What is this condition
known as?

- **Effect on Database:**
  - A is deducted 100, B is not updated.

- **Resultant Values:**
  - A: 1900, B: 3000

- **Preservation of A+B:**
  - Not preserved (A+B decreases by 100).

- **Condition Known As:**
  - Inconsistent Database State.

# Question
Mention the reasons as to why concurrency is preferred. Let T1 and T2 be the
two transactions. Transaction T1 transfers $100 from account A to account B,
whereas transaction T2 transfers 10% of the balance from account A to
account B.
Assuming a serial scheduling scenario, write the transactions in the order:
a) T1 followed by T2
b) T2 followed by T1
Compare the results and comment on its consistency.
[Given: Prior to the transactions; account A and account B have $1000 and
$500 respectively]

**Reasons for Concurrency:**
- **Improved Throughput:** Accommodates multiple transactions simultaneously.
- **Reduced Response Time:** Faster completion of transactions.
- **Resource Utilization:** Efficient use of system resources.
- **Improved Performance**: Increased transaction processing.

**Serial Scheduling Scenarios:**

a) **T1 followed by T2:**
   1. T1: A -= $100 -> (A: $900, B: $600)
   2. T2: A -= 10%  -> (A: $810, B: $690)

b) **T2 followed by T1:**
   1. T2: A -= 10%  -> (A: $900, B: $600)
   2. T1: A -= $100 -> (A: $800, B: $700)

**Consistency:**
- Results differ based on scheduling.
- Lack of consistency due to scheduling order.
- Serializability is compromised.

# Question
Given the concurrent schedule below:
[Assume that, prior to the transactions; account A and account B have $100
and $200 respectively]

```
T1              | T2                |Concurrency Control Manager
lock – X(B)     |                   |                                                        
                |                   |                        
                |                   |    grant – X(B, T1)
                |                   |                        
read(B)         |                   |                                
B: = B – 50     |                   |                                    
write(B)        |                   |                                 
unlock(B)       |                   |                                  
                |                   |                        
                | lock – S(A)       |                                                           
                |                   |                        
                |                   |    grant – S(A, T2)
                |                   |                        
                | read(A)           |                                                       
                | unlock(A)         |                                                         
                | lock – S(B)       |                                                           
                |                   |                        
                |                   |    grant – S(B, T2)
                |                   |                        
                | read(B)           |                                                       
                | unlock(B)         |                                                         
                | display(A + B)    |                                                              
                |                   |                        
lock – X(A)     |                   |                                   
                |                   |                        
                |                   |    grant – X(A, T1)
                |                   |                        
read(A)         |                   |                               
A: = A – 50     |                   |                                   
write(A)        |                   |                                
unlock(A)       |                   |  
```                               


- What does transaction T2 display?
- Is the displayed result correct?
- If not, re-write the transactions as serial schedules with the necessary changes to give
a consistent state for displaying (A + B)

**Answer:**

**Transaction T2 Display:**
- Displays A + B after its operations.
  
**Correctness of Displayed Result:**
- Incorrect because it doesn't consider the changes made by T1.

**Re-written Serial Schedules for Consistency:**
a) **T1 followed by T2:**
   1. T1: lock – X(B), read(B), B = B - 50, write(B), unlock(B), lock – X(A), read(A), A = A - 50, write(A), unlock(A)
   2. T2: lock – S(A), read(A), unlock(A), lock – S(B), read(B), unlock(B), display(A + B)

b) **T2 followed by T1:**
   1. T2: lock – S(A), read(A), unlock(A), lock – S(B), read(B), unlock(B), display(A + B)
   2. T1: lock – X(B), read(B), B = B - 50, write(B), unlock(B), lock – X(A), read(A), A = A - 50, write(A), unlock(A)

**Consistent State for Displaying (A + B):**
   - Both schedules give consistent results:
     - a) A + B = $200
     - b) A + B = $250