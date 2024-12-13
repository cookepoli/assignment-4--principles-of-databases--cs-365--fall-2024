# Fall 2024 Principles of Databases — Assignment 4

* **Do not start this project until you’ve read and understood these instructions. If something is not clear, ask.**

---

## ❖ Introduction ❖

For this assignment, you will write responses to nine questions based on different topics from our textbook, *Database Systems — The Complete Book* and to one question based on your notes. Reply to each question in the provided region using Markdown syntax.

---

## ❖ Questions ❖

### 1. [2.4] What is the difference between a Cartesian Product, a Natural Join, and Theta-Joins?

The Cartesian Product will always produce a relation that combines all elements of the first relation with all elements of the second relation. This type of join does not attempt to unify any part of the two relations, or match a component/tuple. As such, a relation produced by a cartesian product will have a number of tuples equal to the number of tuples in the first relation multiplied by the number of tuples in the second relation. The schema for this relation will have a number of attributes equal to the number of attributes in the first relation plus the number of attributes in the second relation. Additionally, any attributes that have the same name in both relations will use dot notation to avoid ambiguity. Conversely, both Natural Joins and Theta Joins attempt to unify two relations on a certain condition. For the Natural Join, two relations are joined using on common component values in common attributes between the two relations. As such, for a Natural Join to work, two relations must have the same name for at least one of their attributes, and at least one of the tuples in each relation must have the same value for that common attribute. For these common attributes, they are present only once in the relation produced by a Natural Join, and thus avoid dot notation. Theta-Joins pair tuples using an arbitrary condition that is defined in the join statement. This means Theta-Joins are more flexible than Natural Joins, but are more specific than a Cartesian Product (typically). Theta-Joins also employ dot notation to display attributes that have the same name across two relations, as the arbitrary condition used for the join does not always avoid ambiguity. 

### 2. [2.5] What is a Referential Integrity Constraint?

A Referential Integrity Constraint is a type of restriction that can be placed on information stored in a relation. This constraint aims to ensure consistency within a database by connecting two relations. A referential integrity constraint says that a value appearing in a certain context (or relation) must appear in another related context (or relation). Generally, referential integrity constraints are used in two relations that have a semantic relationship. For example, two relations exist in database: Employee and Manager. If the Employee relation has an attribute ManagerName, then intuitively any tuple in Employee must contain a value in ManagerName that exists in the Name attribut of Manager. This can be expressed in relational algebra as follows: $\pi_{ManagerName}(Employee) \subseteq \pi_{Name}(Manager)$. This ensures that any value in the ManagerName attribute of any tuple in Employee also exists in the Name attribute of the Manager relation. In this case, it is not possible for an employee to have no manager, as every employee needs a supervisor.

###  3. [2.5] What is a Key Constraint?

Replace this content with your answer

### 4. [4.1] What is an Entity/Relationship Model? What purpose does it serve in the process of creating/designing databases?

Replace this content with your answer

### 5. [4.4] What is a Weak Entity Set?

Replace this content with your answer

### 6. [5.2.7; 6.3.8] Explain the concepts of Outerjoin, Natural Right Outer Joins, Natural Left Outer Joins, and Full Outer Joins.

Replace this content with your answer

### 7. [6.6.3] What is the difference between the SQL command `TRANSACTION` and the execution of any statement in SQL?

Replace this content with your answer

### 8. [8] What is a Virtual View and what are its advantages?

Replace this content with your answer

### 9. [8.3] What is an *index* and what are its advantages?

Replace this content with your answer

### 10. Explain the concept of an MVC, or model, view, controller, framework for designing full stack applications

Replace this content with your answer

---

## ❖ Due ❖

Sunday, 15 December 2024, at 10:00 AM.

---

## ❖ Grading ❖

| Item        | Points |
|-------------|:------:|
| Question 1  | `10`   |
| Question 2  | `10`   |
| Question 3  | `10`   |
| Question 4  | `10`   |
| Question 5  | `10`   |
| Question 6  | `10`   |
| Question 7  | `10`   |
| Question 8  | `10`   |
| Question 9  | `10`   |
| Question 10 | `10`   |

---

## ❖ Submission ❖

**NO late submissions will be accepted.**

You will need to issue a pull request back into the original repo, the one from which your fork was created for this project. See the **Issuing Pull Requests** section of [this site](http://code-warrior.github.io/tutorials/git/github/index.html) for help on how to submit your assignment.

**Note**: This assignment may **only** be submitted via GitHub. **No other form of submission will be accepted**.
