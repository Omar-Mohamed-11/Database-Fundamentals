# SQL - SELECT Command

- **Data Manipulation Language (DML):**
    - **DML** is a part of **SQL** that is used to work with the Data stored inside Tables.
    - The `SELECT` command is a DML command.
        - It is used to display / retrieve Data from a Database Table.

- **SELECT Command:**
    - The `SELECT` statement displays the Values stored in selected Columns.
    - The basic structure is:
        ```sql
            SELECT Column1, Column2, ...
            FROM Table_Name;
        ```
    - The statement contains:
        - `SELECT`:
            - Specifies the Column or Columns that should be displayed.
        - `FROM`:
            - Specifies the Table from which Data will be retrieved.

- **Select Specific Columns:**
    - Write the required Column Names after `SELECT`.
    - Separate multiple Column Names with commas.
    - Example:
        ```sql
            SELECT DepartmentID, DepartmentName
            FROM Departments;
        ```
    - In this statement:
        - Only `DepartmentID` and `DepartmentName` are displayed.
        - The Data is retrieved from the `Departments` Table.

- **Column Names That Contain Spaces:**
    - If a Column Name contains spaces, enclose the Column Name in square brackets `[ ]`.
    - Example:
        ```sql
            SELECT [Department Name], [Manager Name]
            FROM Departments;
        ```
    - In this example:
        - `[Department Name]` is a Column Name that contains a space.
        - `[Manager Name]` is a Column Name that contains a space.
        - The square brackets allow SQL to identify the complete Column Name.

- **Select All Columns:**
    - Use the asterisk `*` after `SELECT` to display all Columns in a Table.
    - Example:
        ```sql
            SELECT *
            FROM Departments;
        ```
    - In this example:
        - `*` represents all Columns in the `Departments` Table.
        - The statement displays every Column and its Data.

- **Filter Data Using WHERE:**
    - Use the `WHERE` clause to display only Records that meet a Condition.
    - The basic structure is:
        ```sql
            SELECT Column1, Column2, ...
            FROM Table_Name
            WHERE Condition;
        ```
    - Example:
        ```sql
            SELECT DepartmentID, DepartmentName
            FROM Departments
            WHERE DepartmentID = 10;
        ```
    - In this statement:
        - The `WHERE` clause filters the Data.
        - Only the Department Record with `DepartmentID` equal to `10` is displayed.
    - A Condition can also be used to display Data for a specific Manager.

- **Writing Commands in a Script:**
    - A SQL command can be written on more than one line.
    - Pressing `Enter` moves to the next line / command in the script.
    - The SQL keywords and clauses should be organized clearly, for example:
        ```sql
            SELECT *
            FROM Departments
            WHERE DepartmentID = 10;
        ```

- #### SUMMARY:
    - **SELECT:**
        - A DML command used to display / retrieve Data from a Table.
    - **Specific Columns:**
        - Write the required Column Names after `SELECT`.
    - **All Columns:**
        - Use `*` to select all Columns from a Table.
    - **FROM:**
        - Specifies the Table that contains the required Data.
    - **WHERE:**
        - Filters the displayed Data according to a Condition.
    - **Column Names with Spaces:**
        - Enclose them in square brackets `[ ]`.
