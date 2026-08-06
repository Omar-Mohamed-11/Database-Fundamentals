

![Description](../IMAGES/Pasted%20image%2020260715232358.png)

- The main components of a Database System are the Database, DBMS (Database Management System), and the Application Program.
- The end user accesses the database through a user interface (UI) that is part of the Application Program, but the user does not see the backend database directly.
- The DBMS is divided into two parts:
	1. First part process the queries that came from the application program.
	2. Second part accessed the database itself and return, add, edit the data.
- The database itself is divided into two parts:
	1. Stored **database Definition** (Metadata).
		- Metadata: is the set of information about my data, and the database definition stored all information.
		  Ex: (Table name, Column name, Column data types, Constraints, Access Privileges,             Usernames, Passwords, User's Privileges, DB Objects structure, Log files)
	2. **Stored Database**: it is the data itself.

- Database systems **advantages**:
	- Controlling redundancy.
	- Restricting unauthorized access.
	- Sharing data.
	- Enforcing integrity Constraints.
	- Inconsistency can be avoided.
	- Providing backup and recovery.

- Database systems **disadvantages**:
	- Needs expertise to use.
	- DBMS is expensive.
	- May be incompatible with any other available DBMS,
	  but this problem can be fixed by using a third-party tool that can facilitate the transfer process.