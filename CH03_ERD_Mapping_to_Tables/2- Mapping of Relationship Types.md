# Mapping of Relationship Types

- **Mapping Relationship Types:**
    - The process of transforming relationships in the Conceptual Design into a Relational Schema.
    - The mapping rule depends on the type of relationship between the Entities.

- **One-to-Many (1 : M) Relationship:**
    - Take the **Primary Key** from the **one side**.
    - Place it as a **Foreign Key** in the table on the **many side**.
    - For example, the relationship between **Department** and **Employee**:
        - `Department`
            - Primary Key: `Department_ID`
        - `Employee`
            - Foreign Key: `Department_ID`
        - `Department_ID` from the Department table becomes a Foreign Key in the Employee table.

- **Unary / Recursive One-to-Many Relationship:**
    - The same One-to-Many mapping rule is used.
        - Take the Primary Key from the **one side**.
        - Place it as a Foreign Key on the **many side**.
    - Both sides belong to the **same table**.
    - The Foreign Key may be renamed to avoid confusion between it and the Primary Key.

- **Relationships involving Weak Entities:**
    - The mapping should preserve the relationship between the **Weak Entity** and its owner Entity.
    - The identifying relationship is represented without unnecessarily duplicating information.
    - Redundant data should be avoided.

- **Many-to-Many (M : N) Relationship:**
    - Create a new **Junction Table**.
        - It contains the Primary Key of the first Entity as a Foreign Key.
        - It contains the Primary Key of the second Entity as a Foreign Key.
        - The two Foreign Keys together form the **Primary Key** of the Junction Table.
    - If the relationship has Attributes:
        - Store them in the Junction Table because they belong to the relationship itself.

- **One-to-One (1 : 1) Relationship:**
    - The mapping depends on the **Participation Constraint** of each Entity.
    - **May / Must:**
        - Take the Primary Key from the **may side**.
        - Place it as a Foreign Key on the **must side**.
    - **Must / Must:**
        - There are two possible approaches:
            - Merge the two tables into one table.
            - Create a new table:
                - Store the Primary Key of the first Entity as a Foreign Key.
                - Store the Primary Key of the second Entity as a Foreign Key.

- **Ternary Relationship:**
    - A relationship that involves **three Entities**.
    - Create a new table for the relationship.
        - Put the Primary Key of each of the three Entities in the new table.
        - These Primary Keys become Foreign Keys.
        - The three Foreign Keys together form the **Primary Key** of the new table.

- The main goal of these mapping rules is to:
    - Correctly represent relationships in the Relational Schema.
    - Minimize data **Redundancy**.
    - Preserve the relationships between Entities.
    - Maintain an efficient and consistent database design.

### Ex:
![Mapping Relationship Types to Relational Schema](mapping_relationships.png)
