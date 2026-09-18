# SQL - Outer Join and Full Join

- **Inner Join vs Outer Join:**
    - **INNER JOIN / EQUI JOIN:**
        - Returns only Rows that have matching related Values in both Tables.
        - An Employee Name appears only when the Employee has a matching Department.
        - A Department Name appears only when the Department has a matching Employee.
    - **OUTER JOIN:**
        - Returns matching Rows and also includes Rows that do not have a match.
        - When a matching Row does not exist, the Columns from the unmatched Table display `NULL`.
        - Types of Outer Join include:
            - `LEFT OUTER JOIN`
            - `RIGHT OUTER JOIN`
            - `FULL OUTER JOIN`

- **LEFT OUTER JOIN:**
    - `LEFT OUTER JOIN` returns all Rows from the left Table.
    - It also returns matching Rows from the right Table.
    - If a Row in the left Table has no match in the right Table:
        - The left Table Row is still displayed.
        - The right Table Columns display `NULL`.
    - Basic structure:
        ```sql
            SELECT Table1.Column_Name, Table2.Column_Name
            FROM Table1
            LEFT OUTER JOIN Table2
            ON Table1.Related_Column = Table2.Related_Column;
        ```
    - Example: display all Employees and their Departments.
        ```sql
            SELECT E.FirstName, D.DepartmentName
            FROM Employee AS E
            LEFT OUTER JOIN Departments AS D
            ON E.DepartmentNumber = D.DepartmentNumber;
        ```
    - In this statement:
        - `Employee` is the left Table.
        - All Employees are displayed.
        - If an Employee has no assigned Department, `D.DepartmentName` displays `NULL`.

- **RIGHT OUTER JOIN:**
    - `RIGHT OUTER JOIN` returns all Rows from the right Table.
    - It also returns matching Rows from the left Table.
    - If a Row in the right Table has no match in the left Table:
        - The right Table Row is still displayed.
        - The left Table Columns display `NULL`.
    - Basic structure:
        ```sql
            SELECT Table1.Column_Name, Table2.Column_Name
            FROM Table1
            RIGHT OUTER JOIN Table2
            ON Table1.Related_Column = Table2.Related_Column;
        ```
    - Example: display all Departments and their Employees.
        ```sql
            SELECT E.FirstName, D.DepartmentName
            FROM Employee AS E
            RIGHT OUTER JOIN Departments AS D
            ON E.DepartmentNumber = D.DepartmentNumber;
        ```
    - In this statement:
        - `Departments` is the right Table.
        - All Departments are displayed.
        - If a Department has no assigned Employee, `E.FirstName` displays `NULL`.

- **FULL OUTER JOIN:**
    - `FULL OUTER JOIN` returns all Rows from both Tables.
    - Matching Rows are combined according to the Join Condition.
    - Rows without a match are also displayed.
        - The Columns from the unmatched Table display `NULL`.
    - Basic structure:
        ```sql
            SELECT Table1.Column_Name, Table2.Column_Name
            FROM Table1
            FULL OUTER JOIN Table2
            ON Table1.Related_Column = Table2.Related_Column;
        ```
    - Example: display all Employees and all Departments.
        ```sql
            SELECT E.FirstName, D.DepartmentName
            FROM Employee AS E
            FULL OUTER JOIN Departments AS D
            ON E.DepartmentNumber = D.DepartmentNumber;
        ```
    - In this statement:
        - Matched Employee-Department pairs are displayed together.
        - Employees without Departments are displayed with `NULL` for Department Data.
        - Departments without Employees are displayed with `NULL` for Employee Data.

- **Join Result Summary:**
    - **INNER JOIN:**
        - Displays only matched Employee-Department pairs.
    - **LEFT OUTER JOIN:**
        - Displays all Employees.
        - Also displays their matching Departments when available.
    - **RIGHT OUTER JOIN:**
        - Displays all Departments.
        - Also displays their matching Employees when available.
    - **FULL OUTER JOIN:**
        - Displays all Employees and all Departments.
        - Matches related Rows where possible.
        - Displays `NULL` when no matching Row exists.

- **Important Notes:**
    - The position of the Tables is important for `LEFT OUTER JOIN` and `RIGHT OUTER JOIN`.
        - The first Table is the left Table.
        - The second Table is the right Table.
    - The `ON` clause specifies the Department ID Join Condition.
    - Outer Joins are useful when unmatched Data must be included in the Result Set.

- #### SUMMARY:
    - **INNER JOIN:**
        - Returns only matching Rows from both Tables.
    - **LEFT OUTER JOIN:**
        - Returns all Rows from the left Table.
        - Shows `NULL` for unmatched right Table Data.
    - **RIGHT OUTER JOIN:**
        - Returns all Rows from the right Table.
        - Shows `NULL` for unmatched left Table Data.
    - **FULL OUTER JOIN:**
        - Returns all Rows from both Tables.
        - Shows `NULL` where no match exists.
