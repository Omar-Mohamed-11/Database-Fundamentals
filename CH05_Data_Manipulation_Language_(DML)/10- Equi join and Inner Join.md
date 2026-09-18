# SQL - EQUI JOIN and INNER JOIN

- **Join:**
    - A Join is used to retrieve related Data from more than one Table.
    - Tables are connected by a Join Condition based on related Keys.
    - The Join Condition identifies which Rows in one Table are related to Rows in another Table.
    - Joins are used when the required Data is stored across multiple Tables.
        - For example:
            - Employee Data is stored in the `Employee` Table.
            - Department Data is stored in the `Departments` Table.
            - A query can display related Employee and Department Data together.

- **EQUI  JOIN:**
    - `EQUI JOIN` is a type of Join that displays Rows with matching Values in both Tables.
    - The basic structure is:
        ```sql
            SELECT Table1.Column_Name, Table2.Column_Name
            FROM Table1, Table2
            WHERE Table1.Related_Column = Table2.Related_Column;
        ```
    - The statement contains:
        - `EQUI JOIN`:
            - Connects the second Table to the first Table.
        - `WHERE`:
            - Specifies the Join Condition.
        - `Table1.Related_Column = Table2.Related_Column`:
            - Matches related Rows from the two Tables.

- **INNER JOIN:**
    - `INNER JOIN` is a type of Join that displays Rows with matching Values in both Tables.
    - The basic structure is:
        ```sql
            SELECT Table1.Column_Name, Table2.Column_Name
            FROM Table1
            INNER JOIN Table2
            ON Table1.Related_Column = Table2.Related_Column;
        ```
    - The statement contains:
        - `INNER JOIN`:
            - Connects the second Table to the first Table.
        - `ON`:
            - Specifies the Join Condition.
        - `Table1.Related_Column = Table2.Related_Column`:
            - Matches related Rows from the two Tables.

- **Employee and Department:**
    - An Employee can be connected to the Department in which the Employee works.
    - Example:
        ```sql
            SELECT Employee.FirstName, Departments.DepartmentName
            FROM Employee
            INNER JOIN Departments
            ON Employee.DepartmentNumber = Departments.DepartmentNumber;
        ```
    - In this statement:
        - `Employee.FirstName` displays the Employee's First Name.
        - `Departments.DepartmentName` displays the related Department Name.
        - `Employee.DepartmentNumber = Departments.DepartmentNumber` is the Join Condition.
        - The query displays Employees with their related Departments.

- **Employee and Managed Department:**
    - An Employee can also be connected to the Department that the Employee manages.
    - Example:
        ```sql
            SELECT Employee.FirstName, Departments.DepartmentName
            FROM Employee
            INNER JOIN Departments
            ON Employee.SSN = Departments.ManagerSSN;
        ```
    - In this statement:
        - `Employee.SSN` is matched with `Departments.ManagerSSN`.
        - The query displays the Employee Name and the Department managed by that Employee.

- **Column Name Ambiguity:**
    - Column Name Ambiguity occurs when two Tables have Columns with the same Name.
    - In this case, the Column Name should be qualified with its Table Name.
    - Example:
        ```sql
            SELECT Employee.DepartmentNumber, Departments.DepartmentNumber
            FROM Employee
            INNER JOIN Departments
            ON Employee.DepartmentNumber = Departments.DepartmentNumber;
        ```
    - In this statement:
        - `Employee.DepartmentNumber` identifies the Column from the `Employee` Table.
        - `Departments.DepartmentNumber` identifies the Column from the `Departments` Table.
        - Writing the Table Name before the Column Name removes ambiguity.

- **Table Aliases:**
    - A Table Alias is a short name used to represent a Table inside a query.
    - It makes a query shorter and clearer, especially when multiple Tables are used.
    - Example:
        ```sql
            SELECT E.FirstName, D.DepartmentName
            FROM Employee AS E
            INNER JOIN Departments AS D
            ON E.DepartmentNumber = D.DepartmentNumber;
        ```
    - In this statement:
        - `E` is the Alias for the `Employee` Table.
        - `D` is the Alias for the `Departments` Table.
        - `E.FirstName` and `D.DepartmentName` identify Columns using the Table Aliases.

- **Join Three Tables:**
    - A query can join more than two Tables when related Data is stored in several Tables.
    - For example, the `Employee`, `Project`, and `Works_For` Tables can be joined to display Employees, their Projects, and the Hours worked.
    - Example:
        ```sql
            SELECT E.FirstName, P.ProjectName, W.Hours
            FROM Employee AS E
            INNER JOIN Works_For AS W
            ON E.EmployeeID = W.EmployeeID
            INNER JOIN Project AS P
            ON W.ProjectID = P.ProjectID;
        ```
    - In this statement:
        - `Employee` is joined with `Works_For` using the Employee Key.
        - `Works_For` is joined with `Project` using the Project Key.
        - The Result Set displays the Employee Name, Project Name, and Hours worked.

- **Important Notes:**
    - A correct Join Condition is necessary to retrieve related Data correctly.
    - Qualifying Column Names with Table Names or Table Aliases avoids ambiguity.
    - `INNER JOIN` displays only Rows that have matching related Values in the joined Tables.

- #### SUMMARY:
    - **Join:**
        - Retrieves related Data from multiple Tables.
        - Uses a Join Condition based on related Keys.
    - **INNER JOIN and EQUI JOIN:**
        - Displays Rows with matching Values (`Primamry Key`, `Foreign Key`) in both Tables.
    - **ON:**
        - Specifies the Join Condition.
    - **Table Alias:**
        - Is a short name that makes multi-table queries clearer.
    - **Multiple Tables:**
        - Can be joined to display interconnected Data such as Employees, Projects, and Hours worked.
