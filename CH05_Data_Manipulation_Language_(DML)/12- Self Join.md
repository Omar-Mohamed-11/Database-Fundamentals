# SQL - Self Join

- **Self Join:**
    - A Self Join is a Join in which a Table is joined with itself.
    - It is useful when a Table contains a Recursive Relationship.
    - A Recursive Relationship occurs when Records in the same Table are related to other Records in that Table.
        - For example:
            - Employees are stored in the `employee` Table.
            - A Supervisor is also an Employee.
            - Each Employee Record can store the SSN of its Supervisor.

- **Employee and Supervisor Relationship:**
    - The `employee` Table is used twice in the same query:
        - One copy represents the Employee.
        - The other copy represents the Supervisor.
    - Table Aliases are required to distinguish the two uses of the same Table.
        - `E` represents the Employee.
        - `S` represents the Supervisor.

- **Self Join Syntax:**
    - The basic structure is:
        ```sql
            SELECT E.Column_Name, S.Column_Name
            FROM employee E
            JOIN employee S
            ON E.Supervisor_Column = S.SSN_Column;
        ```
    - The Join Condition matches:
        - The Supervisor ID stored in the Employee Record.
        - With the Supervisor's SSN in the Supervisor Record.

- **Display Employee and Supervisor Names:**
    - Example:
        ```sql
            SELECT E.fname AS EmployeeName, S.fname AS SupervisorName
            FROM employee E
            JOIN employee S
            ON E.supervisor_ssn = S.ssn;
        ```
    - In this statement:
        - `employee E` represents the Employee copy of the `employee` Table.
        - `employee S` represents the Supervisor copy of the same `employee` Table.
        - `E.fname` selects the Employee's First Name.
        - `S.fname` selects the Supervisor's First Name.
        - `AS EmployeeName` gives the Employee Name Column a clear label.
        - `AS SupervisorName` gives the Supervisor Name Column a clear label.
        - `E.supervisor_ssn = S.ssn` is the Self Join Condition.

- **How the Join Condition Works:**
    - `E.supervisor_ssn` contains the SSN of the Supervisor for an Employee.
    - `S.ssn` identifies an Employee Record that represents the Supervisor.
    - The condition:
        ```sql
            E.supervisor_ssn = S.ssn
        ```
        - Matches each Employee with the Employee Record of that Employee's Supervisor.
        - Produces a Result Set where each Employee Name is paired with a Supervisor Name.

- **Important Notes:**
    - A Self Join does not create another physical copy of the Table.
        - The same Table is referenced twice in one query.
    - Table Aliases are important because both sides of the Join use the same Table Name.
    - Without Aliases, SQL cannot clearly distinguish the Employee Columns from the Supervisor Columns.

- #### SUMMARY:
    - **Self Join:**
        - Joins a Table with itself.
        - Is used for Recursive Relationships.
    - **Employee / Supervisor Example:**
        - The `employee` Table represents both Employees and Supervisors.
    - **Aliases:**
        - `E` represents the Employee.
        - `S` represents the Supervisor.
    - **Join Condition:**
        - `E.supervisor_ssn = S.ssn` matches an Employee with that Employee's Supervisor.
