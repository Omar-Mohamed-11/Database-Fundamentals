- **DBMS Architecture (Three Schema Architecture):**

	- **External Schema:**
		- The External Schema represents different views of the data tailored for various users or applications, ensuring data security and customized access.
		- *"What the user sees"*, they are concerned with what data the user will see and how the data will be presented to the user.

	- **Conceptual Schema:**
		-  The Conceptual Schema is the overall logical design of the database, including tables, relationships, and constraints, independent of physical storage.
		- *"The logical model"*, they are concerned with what is presented.
		  (define database structures such as tables and constraints).

	- **Physical Schema:**
		- The Physical Schema details how data is physically stored on devices like hard disks, including file allocation, access paths, and storage management. These schemas are kept separate to achieve data independence, meaning changes in one schema do not necessarily affect the others.
		- *"The physical model"*, how the data are represented in the database?
		  how the data structures are implemented?

- These schemas are kept separate to achieve data independence, meaning changes in one schema do not necessarily affect the others.

- **Data Models:** we have two types of data model

	- **The logical model / conceptual model:**
		- Provide concepts that are close to the way many users perceive data, entities, attributes and relationships.   *Ex: **ERD*** 

	- **The physical model:**
		- Describes how data is sorted in the computer and the access path needed to access and search for data.     *Ex: **Physical Schema*** 