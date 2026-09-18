# SQL - INSERT Command

- **Data Manipulation Language (DML):**
    - **DML** is a part of **SQL** that is used to work with the Data stored inside Tables.
    - The `INSERT` command is a DML command.
        - It is used to add a new Record / Row to a Table.

- **INSERT Command:**
    - The `INSERT` command adds Data to an existing Table.
    - The basic structure is:
        ```sql
            INSERT INTO Table_Name (Column1, Column2, ...)
            VALUES (Value1, Value2, ...);
        ```
    - When inserting Data:
        - Each Value must match its corresponding Column.
        - Character values must be enclosed in single quotes.
        - Date values must be enclosed in single quotes.

- **Employee Table Example:**
    - The examples use an `Employee` Table with Columns such as:
        - `EmployeeID`
        - `Name`
        - `Address`
        - `DateOfBirth`
        - `Salary`
        - `DepartmentID`
        - `SuperSSN`

- **Methods of Using INSERT:**
    - **1. Specify all Columns and their Values:**
        - Write all Column Names after the Table Name.
        - Write the corresponding Values in the same order.
        - Example:
            ```sql
                INSERT INTO Employee
                (EmployeeID, Name, Address, DateOfBirth, Salary, DepartmentID, SuperSSN)
                VALUES
                (1, 'Ahmed', 'Cairo', '2000-01-01', 5000, 10, 123456789);
            ```
        - In this method:
            - Every Column being inserted into is written explicitly.
            - Every Value is matched with its Column by position.
            - `Ahmed`, `Cairo`, and `2000-01-01` are enclosed in single quotes because they are Character or Date values.

    - **2. Provide Values without Column Names:**
        - The Column Names are omitted.
        - The Values must follow the exact order of the Columns in the Table.
        - Example:
            ```sql
                INSERT INTO Employee
                VALUES
                (1, 'Ahmed', 'Cairo', '2000-01-01', 5000, 10, 123456789);
            ```
        - Important Note:
            - This method assumes that the listed Values follow the Table's Column order.
            - A Value in the wrong position will be matched with the wrong Column.

    - **3. Insert Data into Specific Columns Only:**
        - Write only the Column Names that will receive Values.
        - Write only the Values for those Columns.
        - Columns not included in the statement are left to their Default Value or `NULL`.
        - Example:
            ```sql
                INSERT INTO Employee
                (EmployeeID, Name, Salary, DepartmentID)
                VALUES
                (1, 'Ahmed', 5000, 10);
            ```
        - In this method:
            - Only `EmployeeID`, `Name`, `Salary`, and `DepartmentID` receive Values.
            - The remaining Columns are left to their Default Value or `NULL`.

- **Important Notes:**
    - The order of Values is important in every `INSERT` statement.
        - When Column Names are specified:
            - Values must match the written Column order.
        - When Column Names are omitted:
            - Values must match the original Column order in the Table.
    - Single quotes are required for Character and Date values.
    - The `INSERT` command manipulates the Data inside the Table.
        - It does not create or modify the Table structure.

- #### SUMMARY:
    - **INSERT:**
        - A DML command used to add a new Record / Row to a Table.
    - **Three INSERT Methods:**
        - Specify all Column Names and Values.
        - Provide only Values in the Table's Column order.
        - Specify only the Columns that should receive Values.
    - **Important Rule:**
        - Character and Date values are enclosed in single quotes.
