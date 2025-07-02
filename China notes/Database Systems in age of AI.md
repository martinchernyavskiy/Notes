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