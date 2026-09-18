# SQL - ORDER BY

- **ORDER BY Clause:**
    - The `ORDER BY` clause is used to sort the Data displayed by a `SELECT` statement.
    - It organizes the Result Set according to the Values in one or more Columns.
    - The basic structure is:
        ```sql
            SELECT Column1, Column2, ...
            FROM Table_Name
            ORDER BY Column_Name;
        ```
    - `ORDER BY` is written after the `FROM` clause.
        - When a `WHERE` clause is used, `ORDER BY` is written after `WHERE`.

- **Sort by One Column:**
    - A Result Set can be sorted according to one selected Column.
    - Example: display the First Name and SSN of Employees sorted by First Name.
        ```sql
            SELECT FirstName, SSN
            FROM Employee
            ORDER BY FirstName;
        ```
    - In this statement:
        - `FirstName` and `SSN` are the Columns displayed.
        - `ORDER BY FirstName` sorts the displayed Records using the `FirstName` Column.

- **Ascending Order:**
    - By default, `ORDER BY` sorts Data in Ascending Order.
    - Ascending Order can also be specified explicitly by using `ASC`.
    - Example:
        ```sql
            SELECT FirstName, SSN
            FROM Employee
            ORDER BY FirstName ASC;
        ```
    - `ORDER BY FirstName` and `ORDER BY FirstName ASC` both sort the Result Set in Ascending Order.

- **Descending Order:**
    - Use `DESC` to sort Data in Descending Order.
    - Example:
        ```sql
            SELECT FirstName, SSN
            FROM Employee
            ORDER BY FirstName DESC;
        ```
    - In this statement:
        - The Result Set is sorted by `FirstName` in Descending Order.
        - `DESC` changes the default Ascending Order to Descending Order.

- **Sort by Multiple Columns:**
    - More than one Column can be used in an `ORDER BY` clause.
    - Each sorting Column is separated by a comma.
    - The first Column is the primary sorting level.
    - The next Column is used to sort Records that have the same Value in the previous Column.
    - Example: sort Employees first by Department Number in Ascending Order, then by Salary in Descending Order.
        ```sql
            SELECT FirstName, DepartmentID, Salary
            FROM Employee
            ORDER BY DepartmentID ASC, Salary DESC;
        ```
    - In this statement:
        - `DepartmentID ASC` sorts Employees by Department Number in Ascending Order.
        - `Salary DESC` sorts Employees by Salary in Descending Order within each Department.

- **ORDER BY with WHERE:**
    - `WHERE` filters the Data, then `ORDER BY` sorts the displayed Results.
    - Example:
        ```sql
            SELECT FirstName, Salary
            FROM Employee
            WHERE Salary > 1500
            ORDER BY Salary DESC;
        ```
    - In this statement:
        - `WHERE Salary > 1500` displays only Employees earning more than `1500`.
        - `ORDER BY Salary DESC` sorts those Employees from the highest Salary to the lowest Salary.

- #### SUMMARY:
    - **ORDER BY:**
        - Sorts the Result Set returned by a `SELECT` statement.
    - **Ascending Order:**
        - Is the default sorting order.
        - Can be written explicitly using `ASC`.
    - **Descending Order:**
        - Is specified using `DESC`.
    - **Multiple Columns:**
        - Can be used to sort Data at more than one level.
        - Each Column can have its own sorting order.
