# SQL - Data Definition Language (DDL)

- **Data Definition Language (DDL):**
    - **DDL** is a part of **SQL** that is used to define and manage the structure of database objects.
    - It focuses on the database structure rather than manipulating the Records / Data stored inside tables.
        - DDL is used to create a new table or make changes to an existing table structure.
        - DDL can also remove a table structure when it is no longer needed.
    - The main DDL commands covered are:
        - `CREATE`
        - `ALTER`
        - `DROP`
        - `TRUNCATE`

- **CREATE Command:**
    - The `CREATE` command is used to create new database objects.
    - In this topic, the focus is on using `CREATE` to create a **Table**.
    - When creating a table, the database designer specifies:
        - The **Table Name:**
            - Identifies the new table in the database.
        - The **Columns:**
            - Define the Fields / Attributes that will be stored in the table.
        - The **Data Types:**
            - Define the kind of value that each column can store.
        - The **Constraints:**
            - Define rules that control the values stored in the table.
    - Example:
        ```sql
            CREATE TABLE Employee (
                Employee_ID INT PRIMARY KEY,
                Employee_Name VARCHAR(100) NOT NULL,
                Salary DECIMAL(10,2)
            );
        ```
    - The previous statement creates a table called `Employee`.
        - `Employee_ID`, `Employee_Name`, and `Salary` are the table columns.
        - `INT`, `VARCHAR(100)`, and `DECIMAL(10,2)` are Data Types.
        - `PRIMARY KEY` and `NOT NULL` are Constraints.

- **ALTER Command:**
    - The `ALTER` command is used to modify the structure of an existing table.
    - It is used when a structural change is needed after the table has already been created.
        - **Adding a new column:**
            - A new Field / Column can be added to an existing table.
            - Example:
                ```sql
                    ALTER TABLE Employee
                    ADD Hire_Date DATE;
                ```
            - The previous statement adds a new column called `Hire_Date` to the `Employee` table.
        - **Removing an existing column:**
            - An existing Field / Column can be removed from a table.
            - Example:
                ```sql
                    ALTER TABLE Employee
                    DROP COLUMN Hire_Date;
                ```
            - The previous statement removes the `Hire_Date` column from the `Employee` table.

- **DROP Command:**
    - The `DROP` command removes the database object itself.
    - When `DROP` is used with a table:
        - The Table structure is removed.
        - All Data stored inside the table is removed.
        - The table no longer exists in the database.
    - Example:
        ```sql
            DROP TABLE Employee;
        ```
    - After this statement is executed, `Employee` is no longer an available table.

- **TRUNCATE Command:**
    - The `TRUNCATE` command removes all Data from a table.
    - Unlike `DROP`, it does not remove the Table structure.
        - The table remains in the database.
        - The Columns, Data Types, and Constraints remain defined.
        - The table can still be used afterward to store new Records.
    - Example:
        ```sql
            TRUNCATE TABLE Employee;
        ```
    - The detailed behavior of `TRUNCATE` will be discussed later, as stated in the video.

- **Comparison of DDL Commands:**
    - The commands have different purposes when working with database objects and tables.
        - **CREATE:**
            - Creates a new database object or table structure.
            - Example result:
                - A new `Employee` table is created.
        - **ALTER:**
            - Modifies the structure of an existing table.
            - Example result:
                - A new `Hire_Date` column is added to the `Employee` table.
        - **DROP:**
            - Removes the table structure and all Data inside the table.
            - Example result:
                - The `Employee` table no longer exists.
        - **TRUNCATE:**
            - Removes all Data from a table while keeping the Table structure.
            - Example result:
                - The `Employee` table remains available, but it contains no Records.

- #### SUMMARY:
    - **DDL:**
        - A part of SQL that defines and manages the structure of database objects.
        - Focuses on the structure of a table, not on manipulating the Data / Records inside it.
    - **CREATE:**
        - Creates the structure of a new database object.
    - **ALTER:**
        - Modifies the structure of an existing table.
    - **DROP:**
        - Removes the structure / object and all its Data.
    - **TRUNCATE:**
        - Removes all Data while keeping the Table structure.
