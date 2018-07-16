# Database normalization

Database normalization is the process of restructuring a relational database in accordance with a series of so-called normal forms in order to reduce data redundancy and improve data integrity. It was first proposed by Edgar F. Codd as an integral part of his relational model. See the link: https://en.wikipedia.org/wiki/Database_normalization

When an attempt is made to modify (update, insert into, or delete from) a relation, the following undesirable side-effects may arise in relations that have not been sufficiently normalized:

* *Update anomaly*. The same information can be expressed on multiple rows; therefore updates to the relation may result in logical inconsistencies. For example, each record in an "Employees' Skills" relation might contain an Employee ID, Employee Address, and Skill; thus a change of address for a particular employee may need to be applied to multiple records (one for each skill). If the update is only partially successful – the employee's address is updated on some records but not others – then the relation is left in an inconsistent state. Specifically, the relation provides conflicting answers to the question of what this particular employee's address is. This phenomenon is known as an update anomaly.

* *Insertion anomaly*. There are circumstances in which certain facts cannot be recorded at all. For example, each record in a "Faculty and Their Courses" relation might contain a Faculty ID, Faculty Name, Faculty Hire Date, and Course Code. Therefore, we can record the details of any faculty member who teaches at least one course, but we cannot record a newly hired faculty member who has not yet been assigned to teach any courses, except by setting the Course Code to null. This phenomenon is known as an insertion anomaly.

* *Deletion anomaly*. Under certain circumstances, deletion of data representing certain facts necessitates deletion of data representing completely different facts. The "Faculty and Their Courses" relation described in the previous example suffers from this type of anomaly, for if a faculty member temporarily ceases to be assigned to any courses, we must delete the last of the records on which that faculty member appears, effectively also deleting the faculty member, unless we set the Course Code to null. This phenomenon is known as a deletion anomaly.

The following information is from https://www.studytonight.com/dbms/database-normalization.php

## 1NF - First normal form

* Primary key
* No repeating groups
* Atomic columns

For a table to be in the First Normal Form, it should follow the following 4 rules:

* It should only have single(atomic) valued attributes/columns.
* Values stored in a column should be of the same domain
* All the columns in a table should have unique names.
* And the order in which data is stored, does not matter.

[1NF tutorial](https://www.studytonight.com/dbms/first-normal-form.php)

## 2NF - Second normal form

* Primary key
* No repeating groups
* Atomic columns
* No partial dependencies - where an attribute in a table depends on only a part of the primary key and not on the whole key.

[2NF tutorial](https://www.studytonight.com/dbms/second-normal-form.php)

## 3NF - Third normal forms

* Primary key
* No repeating groups
* Atomic columns
* No partial dependencies
* No transitive dependencies

Transitive Dependency - when a non-prime attribute depends on other non-prime attributes rather than depending upon the prime attributes or primary key

[3NF tutorial](https://www.studytonight.com/dbms/third-normal-form.php)

## Boyce and Codd Normal Form (BCNF)

Boyce and Codd Normal Form is a higher version of the Third Normal form. This form deals with certain type of anomaly that is not handled by 3NF. A 3NF table which does not have multiple overlapping candidate keys is said to be in BCNF. For a table to be in BCNF, following conditions must be satisfied:

R must be in 3rd Normal Form and, for each functional dependency ( X → Y ), X should be a super Key.

[BCNF tutorial](https://www.studytonight.com/dbms/boyce-codd-normal-form.php)

## 4NF - Fourth Normal Form

A table is said to be in the Fourth Normal Form when:

* It is in the Boyce-Codd Normal Form
* It doesn't have Multi-Valued Dependency

[4NF tutorial](https://www.studytonight.com/dbms/fourth-normal-form.php)
