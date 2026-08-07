- A **Distributed Database Environment** is a collection of databases that are physically stored at different locations but logically work together as one database.
- **Distributed Database** supports high availability of Database.

- There are two methods to create distributed database environment:
	
	1. **Replication:** 
		- Replication involves copying the database.
		- There are two types of Replication:
			1. **Full Replication:** an exact copy of the entire database on another server, providing high availability by switching to the secondary server if the primary fails.
			2.  **Partial Replication:** copying only part of the database relevant to a specific location, with periodic synchronization to the main database.
	
	2. **Fragmentation:**
		- Fragmentation means dividing the database into fragments:
			- **Horizontal Fragmentation:** dividing by rows (records).
			- **Vertical Fragmentation:** dividing by columns.
			- **Hybrid Fragmentation:** a combination of both, preserving database rules and constraints.
		- Each fragment is distributed to different servers connected via a network, which helps avoid a single point of failure.
		
- If one fragment or replica fails, the system continues to operate normally. 
- Setting up a distributed database requires installing and configuring DBMS software on each server, with licensing depending on the use case.
- Distributed databases can be categorized into those using Replication and those using Fragmentation.
- The choice between a distributed or centralized database depends on business needs, cost, availability, and data criticality. There is no absolute rule mandating one over the other.

- **Advantages:**
	- Database is not a single point of failure.
- **Disadvantages:**
	- High cost.