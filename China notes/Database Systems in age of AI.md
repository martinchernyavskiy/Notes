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
3. Import / load the data
4. Write queries & applications using DBMS and other tools