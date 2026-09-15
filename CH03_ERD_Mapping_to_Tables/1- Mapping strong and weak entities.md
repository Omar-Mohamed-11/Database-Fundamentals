# ERD Mapping to Tables

- **ERD Mapping to Tables:**
    - The process of transforming the **Conceptual Design** of a database, represented by an **Entity Relationship Diagram (ERD)**, into a **Logical Design** for a relational database.
    - The result is a set of tables (relations), columns, and keys that represent the Entities and Attributes in the ERD.
    - The main goal is to create an efficient and consistent database design by following the mapping rules.

- **Mapping an Entity to a Table:**
    - Each **Entity** in the ERD is mapped to a separate table (relation).
    - The Attributes of the Entity become columns in the table.
    - A **Primary Key** is selected to uniquely identify each record (row) in the table.
    - For example:
        - An **Employee** Entity has the Attributes `EmployeeID`, `Name`, and `Salary`.
        - It can be mapped to: `Employee(EmployeeID, Name, Salary)`
        - `EmployeeID` is the **Primary Key** because it uniquely identifies each Employee record.

- **Mapping Attributes:**
    - **Simple Attribute:**
        - Mapped directly to one column in the table.
        - For example, `Salary` in the Employee Entity becomes a `Salary` column in the Employee table.

    - **Composite Attribute:**
        - Must be divided into its smaller components before mapping it to a table.
        - Each component becomes a separate column.
        - For example, `FullName` can be divided into:
            - `FirstName`
            - `LastName`
        - The table contains `FirstName` and `LastName` columns instead of one `FullName` column.

    - **Multi-valued Attribute:**
        - Requires a separate table that contains the Multi-valued Attribute and the Primary Key of its owner Entity.
        - The owner Primary Key becomes a **Foreign Key** in the new table to maintain **Referential Integrity**.
        - For example, if an Employee can have multiple phone numbers:
            - `Employee(EmployeeID, Name, Salary)`
            - `EmployeePhone(EmployeeID, PhoneNumber)`
            - `EmployeeID` in `EmployeePhone` is a Foreign Key that refers to `EmployeeID` in the Employee table, and we take two columns together as a primary key of the new table.

    - **Derived Attribute:**
        - Usually calculated dynamically instead of being stored in the table.
        - For example, `Age` can be calculated from `BirthDate` when it is needed.

- **Mapping a Weak Entity:**
    - A **Weak Entity** depends on its owner Entity for identification.
    - When mapping a Weak Entity to a table:
        - The Primary Key of the owner Entity must be included in the Weak Entity table.
        - The owner Primary Key becomes a **Foreign Key**.
        - It is also part of the Weak Entity's **Composite Primary Key**.
    - For example, if `Dependent` is a Weak Entity owned by `Employee`:
        - `Employee(EmployeeID, Name)`
        - `Dependent(EmployeeID, Name, Relation)`
        - The Composite Primary Key of `Dependent` can be `(EmployeeID, Name)`.

- The main mapping rules are:
    1. Convert each Entity into a table.
    2. Convert each Attribute into a column.
    3. Select a Primary Key to uniquely identify each record.
    4. Split Composite Attributes into separate columns.
    5. Create a separate table for each Multi-valued Attribute and include the owner Primary Key as a Foreign Key.
    6. Calculate Derived Attributes when needed instead of storing them.
    7. Include the owner Primary Key in the Composite Primary Key of a Weak Entity.

- These rules transform the ERD into a relational database design while preserving the information and identification requirements of the original Conceptual Design.
