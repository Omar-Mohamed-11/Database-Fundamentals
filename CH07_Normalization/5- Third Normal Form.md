# Third Normal Form (3NF)

- **Third Normal Form (3NF):**
    - A Relation is in **Third Normal Form (3NF)** when it meets two conditions:
        - The Relation is already in Second Normal Form (2NF).
        - The Relation has no Transitive Dependencies.
    - 3NF focuses on removing Transitive Dependencies between Non-Key Attributes.

- **Transitive Dependency:**
    - A **Transitive Dependency** occurs when a Non-Key Attribute depends on another Non-Key Attribute.
        - The second Non-Key Attribute depends on the Key.
    - The dependency can be represented as:
        ```text
            Key -> Non-Key Attribute 1
            Non-Key Attribute 1 -> Non-Key Attribute 2
        ```
    - In this situation, `Non-Key Attribute 2` depends transitively on the Key.

- **3NF Example:**
    - Suppose a Table contains the following Attributes:
        - `Student ID`
        - `Name`
        - `Location`
        - `Level`
        - `Level Manager`
    - In this Table:
        - `Level` depends on `Student ID`.
        - `Level Manager` depends on `Level`.
    - The dependency can be represented as:
        ```text
            Student ID -> Level
            Level -> Level Manager
        ```
    - Therefore:
        - `Level Manager` depends transitively on `Student ID`.
        - The Table contains a Transitive Dependency.
        - The Table is not in 3NF.

- **Convert the Table to 3NF:**
    - To remove the Transitive Dependency, separate the dependent Attributes into a new Table.
    - Create a new `Level` Table that contains:
        - `Level`
            - Primary Key.
        - `Level Manager`
    - The `Level` Table stores the Manager for each Level.

- **Original Table After Decomposition:**
    - After creating the new `Level` Table, the original Table contains:
        - `Student ID`
        - `Name`
        - `Location`
        - `Level`
    - In the original Table:
        - `Level` is a Foreign Key.
        - `Level` references the `Level` Table.
    - The Transitive Dependency is removed.
        - `Level Manager` is stored in the Table where `Level` is the Primary Key.
    - The original Table is now in Third Normal Form.

- **Review of Normal Forms:**
    - **First Normal Form (1NF):**
        - Does not contain Multivalued Attributes, Repeating Groups, or Composite Attributes.
        - Contains Atomic Attributes.
    - **Second Normal Form (2NF):**
        - Is already in 1NF.
        - Does not contain Partial Dependencies.
    - **Third Normal Form (3NF):**
        - Is already in 2NF.
        - Does not contain Transitive Dependencies.
    
	- ![[norms_review.png|632]]

- **Normalization up to 3NF:**
    - Normalization up to 3NF is usually sufficient for a Database Design.
    - It helps:
        - Improve Data Integrity.
        - Reduce Data Redundancy.
        - Avoid unnecessary effects on Database Performance.
    - Further Normalization is possible:
        - Fourth Normal Form (4NF).
        - Fifth Normal Form (5NF).
    - Further Normalization is often unnecessary unless specific Business needs require it.

- #### SUMMARY:
    - **Third Normal Form (3NF):**
        - Requires the Relation to be in 2NF.
        - Does not allow Transitive Dependencies.
    - **Transitive Dependency:**
        - Occurs when a Non-Key Attribute depends on another Non-Key Attribute that depends on the Key.
    - **Convert to 3NF:**
        - Move the transitively dependent Attribute to a new Table.
        - Use the determining Non-Key Attribute as the new Table's Primary Key.
    - **Normalization up to 3NF:**
        - Is usually sufficient to improve Data Integrity and reduce Redundancy.
