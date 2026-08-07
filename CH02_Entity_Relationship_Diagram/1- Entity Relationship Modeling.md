- Entity Relationship Modeling, or Entity Relationship Diagram (ERD), is a method used to create the Conceptual Design of a database.
- This **ERD** identifies information required by the business by displaying the relevant entities and relationships between them.

- **Entity:** 
	- An Entity is a thing in the real world with an independent existence, Physical existence or conceptual existence.
	- Each entity has a group of characteristics or attributes, which help me to identify or define this entity. 
	- For example, in a banking system, Clients are Entities with attributes like account number, name, ID card details, address, and phone number. These attributes help identify and describe each Client.
	  In other systems, such as an educational institute, Students are Entities with attributes like name, graduation year, college, and GPA. Courses or Subjects can also be Entities, described by attributes such as course code, credit hours, and prerequisites.

- **Attribute:**
	- An Attribute is a property or characteristic of an entity.
	- For example, Entity: (Student), Attributes: (Student ID, Name, Age, Address).

- **Relationship:**
	- A Relationship describes how two or more entities are associated with each other.
	- For example, Entities: (Student, Course), Relationship: (Student -- enrolls  in --> Course).

- In building a data model a number of questions must be addressed:
	1. What entities need to be described in the model?
	2. What characteristics or attributes of those entities need to be recorded?
	3. Can an attribute or a set of attributes be identified that will uniquely identify one specific occurrence of an entity?
	4. What associations or relationships exist between entities?
