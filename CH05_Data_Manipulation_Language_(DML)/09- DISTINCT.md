# SQL - DISTINCT

- **DISTINCT Keyword:**
    - `DISTINCT` is used with `SELECT` to remove duplicate Rows from the Result Set.
    - It displays each unique Value or unique combination of Values only once.
    - `DISTINCT` is written immediately after `SELECT`.
    - The basic structure is:
        ```sql
            SELECT DISTINCT Column1, Column2, ...
            FROM Table_Name;
        ```
    - `DISTINCT` affects only the displayed query result.
        - It does not delete duplicate Data from the actual Table.

- **Departments and Assigned Employees:**
    - Selecting from the `Departments` Table displays all Departments.
        - This includes Departments that do not have assigned Employees.
    - To display only Department Numbers that are assigned to Employees, select `DepartmentNumber` from the `Employee` Table.
    - Example:
        ```sql
            SELECT DepartmentNumber
            FROM Employee;
        ```
    - In this statement:
        - Each Employee Record provides a `DepartmentNumber`.
        - When multiple Employees belong to the same Department, the same `DepartmentNumber` appears more than once.

- **Remove Duplicates from One Column:**
    - Use `DISTINCT` to display each Department Number only once.
    - Example:
        ```sql
            SELECT DISTINCT DepartmentNumber
            FROM Employee;
        ```
    - In this statement:
        - Duplicate `DepartmentNumber` Values are removed from the Result Set.
        - Each Department Number with assigned Employees appears once.

- **Remove Duplicates from Multiple Columns:**
    - `DISTINCT` can be used with more than one selected Column.
    - In this case, it removes duplicate combinations of the selected Column Values.
    - Example: display the Department Number and Supervisor without duplicate combinations.
        ```sql
            SELECT DISTINCT DepartmentNumber, Supervisor
            FROM Employee;
        ```
    - In this statement:
        - `DISTINCT` considers `DepartmentNumber` and `Supervisor` together.
        - A duplicate Row is removed only when both the `DepartmentNumber` and `Supervisor` Values are the same.
        - Each unique Department Number and Supervisor combination appears once.

- **DISTINCT with One Column vs Multiple Columns:**
    - **One Column:**
        - `DISTINCT` removes repeated Values in that Column.
        - Example:
            ```sql
                SELECT DISTINCT DepartmentNumber
                FROM Employee;
            ```
    - **Multiple Columns:**
        - `DISTINCT` removes repeated combinations of the selected Columns.
        - Example:
            ```sql
                SELECT DISTINCT DepartmentNumber, Supervisor
                FROM Employee;
            ```

- **Important Note:**
    - `DISTINCT` is useful when the query result contains repeated Values.
    - It helps make the Result Set clearer by displaying only unique Rows.
    - It does not change the Data stored in the Database.

- #### SUMMARY:
    - **DISTINCT:**
        - Is written after `SELECT`.
        - Removes duplicate Rows from the Result Set.
    - **One Column:**
        - Displays each unique Value once.
    - **Multiple Columns:**
        - Displays each unique combination of selected Values once.
    - **Database Data:**
        - Is not changed by `DISTINCT`.
