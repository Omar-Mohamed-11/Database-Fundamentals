# Second Normal Form (2NF)

- **Second Normal Form (2NF):**
    - A Table is in **Second Normal Form (2NF)** when it meets two conditions:
        - The Table is already in First Normal Form (1NF).
        - The Table has no Partial Dependencies.
    - 2NF focuses on removing Partial Dependencies from a Table with a Composite Primary Key.

- **Partial Dependency:**
    - A **Partial Dependency** occurs when a Non-Key Attribute depends on only part of a Composite Primary Key.
    - A Composite Primary Key contains more than one Attribute.
    - To check for a Partial Dependency:
        - Identify the Composite Primary Key.
        - Check each Non-Key Attribute.
        - Determine whether the Non-Key Attribute depends on the entire Key or only part of it.

- **2NF Example:**
    - Suppose a Table contains the following Attributes:
        - `Student ID`
        - `Subject`
        - `Subject Description`
        - `Grade`
    - The Composite Primary Key is:
        ```text
            Student ID, Subject
        ```
    - The Non-Key Attributes are:
        - `Subject Description`
        - `Grade`

- **Identify the Partial Dependency:**
    - In the example:
        - `Subject Description` depends only on `Subject`.
        - `Subject Description` does not depend on `Student ID`.
        - Therefore, `Subject Description` depends on only part of the Composite Primary Key.
    - This is a Partial Dependency.
        ```text
            Subject -> Subject Description
        ```
    - Because the Table contains a Partial Dependency, it is not in 2NF.

- **Convert the Table to 2NF:**
    - To remove the Partial Dependency, separate `Subject Description` into a new Table.
    - Create a new `Subject` Table that contains:
        - `Subject`
            - Primary Key.
        - `Subject Description`
    - The new Table stores each Subject and its Description only once.

- **Original Table After Decomposition:**
    - After creating the new `Subject` Table, the original Table contains:
        - `Student ID`
        - `Subject`
        - `Grade`
    - In the original Table:
        - `Student ID` and `Subject` remain the Composite Primary Key.
        - `Subject` is also a Foreign Key.
            - It references the `Subject` Table.
    - The Partial Dependency is removed.
        - `Subject Description` is now stored in the Table where `Subject` is the Primary Key.
    - The Table is now in Second Normal Form.

- **Benefits of Second Normal Form:**
    - 2NF removes Partial Dependencies.
    - It separates Data that depends on only part of a Composite Primary Key.
    - It improves the organization of the Database Design.

- #### SUMMARY:
    - **Second Normal Form (2NF):**
        - Requires the Table to be in 1NF.
        - Does not allow Partial Dependencies.
    - **Partial Dependency:**
        - Occurs when a Non-Key Attribute depends on only part of a Composite Primary Key.
    - **Convert to 2NF:**
        - Move the partially dependent Attribute to a new Table.
        - Use the part of the Key that determines the Attribute as the new Table's Primary Key.
    - **Example:**
        - `Subject Description` depends only on `Subject`.
        - It is moved to a separate `Subject` Table.
