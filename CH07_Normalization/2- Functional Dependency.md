# Functional Dependency

- **Functional Dependency:**
    - A **Functional Dependency** is a Constraint between two Attributes / Columns or sets of Columns in a Database.
    - It describes a dependency relationship between Attributes.
    - If Attribute `A` functionally determines Attribute `B`:
        - Every valid Value of `A` uniquely determines the Value of `B`.
        - Each Value of `A` is associated with exactly one Value of `B`.
    - This relationship can be represented as:
        ```text
            A -> B
        ```
        - `A` functionally determines `B`.

- **Functional Dependency Example:**
    - Suppose that `SSN` functionally determines `ENAME`.
        ```text
            SSN -> ENAME
        ```
    - In this relationship:
        - Each `SSN` corresponds to exactly one `ENAME`.
        - The `SSN` Value uniquely determines the Employee Name.

- **Types of Functional Dependencies:**
    - The main types of Functional Dependencies are:
        - Full Functional Dependency.
        - Partial Functional Dependency.
        - Transitive Functional Dependency.

- **Full Functional Dependency:**
    - A **Full Functional Dependency** occurs when a Non-Key Attribute depends fully on the entire Key.
    - The Non-Key Attribute needs the complete Key to be determined.
    - Example:
        ```text
            SSN -> ENAME
        ```
    - In this example:
        - `ENAME` is determined by the entire `SSN`.
        - `ENAME` fully depends on `SSN`.

- **Partial Functional Dependency:**
    - A **Partial Functional Dependency** occurs when a Non-Key Attribute depends on only part of a Composite Key.
    - The Non-Key Attribute does not depend on the complete Composite Key.
    - Example:
        ```text
            P-NUMBER -> P-NAME, P-LOCATION
        ```
    - In this example:
        - `P-NAME` depends only on `P-NUMBER`.
        - `P-LOCATION` depends only on `P-NUMBER`.
        - `P-NAME` and `P-LOCATION` do not depend on the full Composite Key.

- **Transitive Functional Dependency:**
    - A **Transitive Functional Dependency** occurs when a Non-Key Attribute depends on another Non-Key Attribute.
        - The second Non-Key Attribute depends on the Key.
    - Example:
        ```text
            SSN -> D-NUMBER
            D-NUMBER -> D-NAME
        ```
    - In this example:
        - `D-NUMBER` depends on `SSN`.
        - `D-NAME` depends on `D-NUMBER`.
        - Therefore, `D-NAME` depends transitively on `SSN`.

- **Functional Dependencies in Database Design:**
    - Functional Dependencies describe how Attributes relate to each other.
    - They show which Attribute Values uniquely determine other Attribute Values.
    - They are used when analyzing Database Design and Normalization.

- #### SUMMARY:
    - **Functional Dependency:**
        - A Constraint between Attributes / Columns or sets of Columns.
        - Describes how one Attribute uniquely determines another Attribute.
    - **Full Functional Dependency:**
        - A Non-Key Attribute depends on the entire Key.
    - **Partial Functional Dependency:**
        - A Non-Key Attribute depends on only part of a Composite Key.
    - **Transitive Functional Dependency:**
        - A Non-Key Attribute depends on another Non-Key Attribute that depends on the Key.
