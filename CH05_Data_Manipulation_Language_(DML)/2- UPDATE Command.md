# SQL - UPDATE Command

- **Data Manipulation Language (DML):**
    - **DML** is a part of **SQL** that is used to work with the Data stored inside Tables.
    - The `UPDATE` command is a DML command.
        - It is used to modify existing Data in a Table.

- **UPDATE Command:**
    - The `UPDATE` statement changes the Value of one or more Columns in existing Records.
    - The basic structure is:
        ```sql
            UPDATE Table_Name
            SET Column_Name = New_Value
            WHERE Condition;
        ```
    - The statement contains:
        - `UPDATE`:
            - Specifies that existing Data will be modified.
        - `Table_Name`:
            - Specifies the Table that contains the Data to be updated.
        - `SET`:
            - Assigns a new Value to a Column.
        - `WHERE`:
            - Specifies the Record / Records that should be updated.

- **Update One Column for a Specific Record:**
    - The following example changes an Employee's Salary to `1200` based on the Employee's `SSN`:
        ```sql
            UPDATE Employee
            SET Salary = 1200
            WHERE SSN = 123456789;
        ```
    - In this statement:
        - `Employee` is the Table being updated.
        - `Salary = 1200` changes the `Salary` Column to `1200`.
        - `WHERE SSN = 123456789` identifies the Employee Record that should be changed.
    - The `UPDATE` statement modifies Data at the Column level for the specified Record.

- **Update Multiple Columns:**
    - More than one Column can be updated in the same `UPDATE` statement.
    - Each Column assignment is written after `SET` and separated by a comma.
    - Example:
        ```sql
            UPDATE Employee
            SET Salary = 1200,
                DepartmentID = 10
            WHERE SSN = 123456789;
        ```
    - In this example:
        - The Employee's `Salary` is changed to `1200`.
        - The Employee's `DepartmentID` is changed to `10`.
        - Both changes are made for the Record identified by the `SSN` condition.

- **Importance of the WHERE Clause:**
    - The `WHERE` clause determines which Record or Records are updated.
    - When `WHERE` is included:
        - Only Records that meet the specified Condition are updated.
    - When `WHERE` is omitted:
        - All Records in the Table are updated.
        - The new Value is applied to the specified Column or Columns for every Record.
    - Example without `WHERE`:
        ```sql
            UPDATE Employee
            SET Salary = 1200;
        ```
    - In this example:
        - Every Record in the `Employee` Table has its `Salary` changed to `1200`.

- **UPDATE vs INSERT:**
    - **UPDATE:**
        - Modifies existing Data.
        - Changes one or more Columns in existing Records.
        - Uses `WHERE` to identify which Records should be modified.
    - **INSERT:**
        - Adds new Records to a Table.
        - Does not modify an existing Record.

- #### SUMMARY:
    - **UPDATE:**
        - A DML command used to modify existing Data in a Table.
    - **SET:**
        - Assigns new Values to one or more Columns.
    - **WHERE:**
        - Identifies the Record or Records to update.
        - If it is omitted, all Records in the Table are updated.
    - **Multiple Columns:**
        - Can be updated in one statement by separating their assignments with commas.
