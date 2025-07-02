### Types
- Relational Database (Calendar, table-like)
- Early DBMS store data in tree hierarchy (network database model )
- Many current database use relational database models, ones that arrange facts into sets of values which satisfy predicates


### DBSM
- Database management system, stores and manages databases
- Ensures the data is kept and not lost
- Querying interface
- Merge table data by common column
- SQL based


### Benefits of DBSM
1. Abstract, doesn't require knowledge of indices, sort orders, machine speeds, disk speeds, concurrent users, etc.
	- Instead use logical model (SQL)
2. Efficient and scalable 
	- Resilient to data format changes, efficient retrieval of necessary data
3. Management of concurrency, consistency, and reliability 
	- Crash recoverable, consistent style


### Abstraction by DBSM
- Logical Structure
	- What users/programmers see
		- Overall database design (conceptual)
		- Different views on schema for users
- Physical Structure
	- Organization on disk, indices, etc.

### Steps of building database application
1. Start with conceptual model
		E-R diagrams
		Entity (real world object), unique with specific attributes
		Relationship - association among 2 or more entities
		Diagram shows the relationship between entities
		
2. Design & Implement relational schema
		Design and codify in SQL the relations/tables
		Do physical layout - indexes

	- Schema of the table describes the information of the table (name of the table and fields/column names)
	- Instance of a table = row, with entries in each field


- Primary key - values are unique 
- Foreign key - references primary keys (relationship between primary keys (entities))
1. Import / load the data
2. Write queries & applications using DBMS and other tools


### Defining and implementing schema in DB
- SQL
- DML (data manipulation language) & DDL (data definition language) 
- DDL - for defining and implementing schema
- DML - querying data (retrieving and managing information)

### Example
```SQL
SELECT *
FROM COURSE
WHERE semester = "25 Fall"
```
Selects all rows where semester equals to 25 Fall and creates a separate table
if SELECT CID, Name, selects only specific columns

```SQL
SELECT *
FROM STUDENT s, Takes t, COURSE c
WHERE s.sid = t.sID and t.cID = c.cid and 
c.semester = "25 Fall"
```


```SQL
SELECT *
FROM COURSE c
ORDER BY CID
```

```SQL
SELECT * FROM COORSE c WHERE CID = 1

UNION

SELECT * FROM COURSE c WHERE Semester = "25 Fall"
```

### Iterator-Based Query Execution
- Has a form of a tree
- Starts at root and propagate calls to children
- May call multiple children next

### Basic Operators in Query Execution
- One-pass operators
	- Select - done while scanning a file
	- Indexing can speed up the process. Indexing can take a form of hash indexing or B+ Tree