# Fall 2024 Principles of Databases — Assignment 4

* **Do not start this project until you’ve read and understood these instructions. If something is not clear, ask.**

---

## ❖ Introduction ❖

For this assignment, you will write responses to nine questions based on different topics from our textbook, *Database Systems — The Complete Book* and to one question based on your notes. Reply to each question in the provided region using Markdown syntax.

---

## ❖ Questions ❖

### 1. [2.4] What is the difference between a Cartesian Product, a Natural Join, and Theta-Joins?

The primary difference between a Cartesian Product, Natural Join, and Theta-Join is the way tuples from the two relation are paired. The Cartesian Product will always produce a relation that combines all elements of the first relation with all elements of the second relation. This type of join does not attempt to unify any part of the two relations, or match a component/tuple. As such, a relation produced by a cartesian product will have a number of tuples equal to the number of tuples in the first relation multiplied by the number of tuples in the second relation. The schema for this relation will have a number of attributes equal to the number of attributes in the first relation plus the number of attributes in the second relation. Additionally, any attributes that have the same name in both relations will use dot notation to avoid ambiguity. Conversely, both Natural Joins and Theta Joins attempt to unify two relations on a certain condition. For the Natural Join, two relations are joined using on common component values in common attributes between the two relations. As such, for a Natural Join to work, two relations must have the same name for at least one of their attributes, and at least one of the tuples in each relation must have the same value for that common attribute. For these common attributes, they are present only once in the relation produced by a Natural Join, and thus avoid dot notation. Theta-Joins pair tuples using an arbitrary condition that is defined in the join statement. This means Theta-Joins are more flexible than Natural Joins, but are more specific than a Cartesian Product (typically). Theta-Joins also employ dot notation to display attributes that have the same name across two relations, as the arbitrary condition used for the join does not always avoid ambiguity. 

### 2. [2.5] What is a Referential Integrity Constraint?

A Referential Integrity Constraint is a type of restriction that can be placed on information stored in a relation. This constraint aims to ensure consistency within a database by connecting two relations. A referential integrity constraint says that a value appearing in a certain context (or relation) must appear in another related context (or relation). Generally, referential integrity constraints are used in two relations that have a semantic relationship. For example, two relations exist in database: Employee and Manager. If the Employee relation has an attribute ManagerName, then intuitively any tuple in Employee must contain a value in ManagerName that exists in the Name attribut of Manager. This can be expressed in relational algebra as follows: $\pi_{ManagerName}(Employee) \subseteq \pi_{Name}(Manager)$. This ensures that any value in the ManagerName attribute of any tuple in Employee also exists in the Name attribute of the Manager relation. In this case, it is not possible for an employee to have no manager, as every employee needs a supervisor.

###  3. [2.5] What is a Key Constraint?

A Key Constraint expresses the concept of uniqueness in a database. For an attribute in a relation, if it is a key, then no two different tuples will have the same value for that key attribute. Typically, key constraints are useful in queries because each key is unique. As such, queries that select specific key values will always return 1 or 0 tuples. In relational algebra, a key constraint is validated by taking the Cartesian Product of two copies of the same relation and checking that if there are any tuples where the key attributes match, but any other attribute does not. For example, in the Employee(name, jobTitle) relation, a key constraint can be expressed using two renamings of that relation, E1 and E2 as follows. In this example, name is the key. $\sigma_{E1.name=E2.name AND E1.jobTitle=E2.jobTitle}(E1 \times E2)=\emptyset$. Here, if E1 and E2 match in name, they must also match in jobTitle, meaning they are the same tuple. Any tuples with the same name, but different title would be returned in the select statement, invalidating the constraint.

### 4. [4.1] What is an Entity/Relationship Model? What purpose does it serve in the process of creating/designing databases?

The Entity/Relationship model is way of graphically representing the connections between data in a database. E/R models are comprised of three primary elements: Entity sets, attributes, and relationships. These elements are used to organize the information stored in a database, as well as illustrating connections between entity sets (via relationships), and what information an entity set might contain (via attributes). As a graphical model, entity sets are represented by rectangles, relationships are represented by diamonds, and attributes are represented by ovals. Edges can connect entity sets to each other via relationships, as well as connecting attributes to entity sets and relationships. The E/R model also allows for the illustration of key constraints (via underlines), referential integrity, and cardinality. There are also more complex structures that exist in the E/R model, such as weak entity sets and subclasses. The E/R model is typically used for designing the schema of a database. The model itself does not contain any information, but instead is used to define the high-level structure of the database. This conceptual model can then be implemented in a language like SQL. Effectively, the E/R model provides a blueprint for a database designer on how to design their database.

### 5. [4.4] What is a Weak Entity Set?

A weak entity set is an enetity set who's key contains attributes which belong to another entity set. In SQL, this would mean that the weak entity set has a foreign key as part of its primary key. By definition, a weak entity set's key must contain: zero or more of its own attributes, and attributes acquired through many-one relationships from that entity set to another entity set (a supporting entity set). For an entity set to be weak, the supporting relationship connecting it to a supporting entity set must be both binary and many-one. Additionally, there must be referential integrity from the weak entity set to the supporting entity set, and the referenced attribute must be a key attribute in the supporting entity set. Weak entity sets are denoted in the E/R model using double-bordered rectangles, with supporting relationships expressed as double-bordered diamonds. In the E/R model, weak entity sets typically arise either in simplifying relationships so that they are binary, or to express hierarchy in cases where "isa hierarchy" does not make sense. For example, an entity set Contract might be a weak entity set supported by Employee, since an Employee has a contract (and a contract cannot exist without an employee). The supporting relation connecting the two might be called Works-for.

### 6. [5.2.7; 6.3.8] Explain the concepts of Outerjoin, Natural Right Outer Joins, Natural Left Outer Joins, and Full Outer Joins.

An outerjoin produces the result of a theta-join or natural join, but includes any dangling tuples in the relation produced. A dangling tuple occurs when a tuple cannot match with another tuple in the other relation. When these dangling tuples are representing in the output of an outerjoin, any attributes not present in that tuple (but are present in the result of the join) are padded with a null symbol. This facilitates their representation in the resulting relation, while still reflecting the fact that they do not unify with another tuple. As such, outjoins fully represent the information stored in the two relations being joined. An outerjoin can be more useful than a natural join or theta join if there is value in assessing which tuples are capable of pairing, as well as which tuples may not pair. Knowing that these dangling tuples exist in a join may be useful for a database designer or in queries, but they would not be shown in a natural join or theta-join. Natural right outer joins are similar to natural outerjoins (natural joins that preserve dangling tuples), but only the dangling tuples of the right argument are presented in the output. Conversely, a natural left outerjoin

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
