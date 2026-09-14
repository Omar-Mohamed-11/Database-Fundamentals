# SQL - Data Control Language (DCL)

- **Data Control Language (DCL):**
    - **DCL** is a part of **SQL** that controls access to database objects.
    - Its purpose is to manage which users are allowed to perform specific operations.
        - It manages user access.
        - It controls **Privileges / Permissions**.
        - It controls access to database objects such as Tables.
    - The two main DCL commands are:
        - **GRANT:**
            - Gives a user a Privilege.
        - **REVOKE:**
            - Removes a previously granted Privilege from a user.

- **GRANT Command:**
    - The `GRANT` command is used to give users specific Privileges on database objects.
    - Common Privileges include:
        - **SELECT:**
            - Allows a user to retrieve / view Data from a Table.
        - **INSERT:**
            - Allows a user to add new Records to a Table.
        - **UPDATE:**
            - Allows a user to modify existing Data in a Table.
        - **DELETE:**
            - Allows a user to remove Records from a Table.

    - **Grant SELECT to one user:**
        - Example:
            ```sql
                GRANT SELECT ON Employees TO Ahmed;
            ```
        - Explanation of the statement:
            - `GRANT`:
                - Gives a Privilege to a user.
            - `SELECT`:
                - Is the Privilege being granted.
                - It allows the user to view / retrieve Data.
            - `ON Employees`:
                - Specifies the database object.
                - The Privilege applies to the `Employees` Table.
            - `TO Ahmed`:
                - Specifies the user who receives the Privilege.
        - Therefore:
            - Ahmed is allowed to use `SELECT` on the `Employees` Table.
            - Ahmed can view the Data in `Employees`.

    - **Grant all DML Privileges:**
        - Example:
            ```sql
                GRANT ALL ON Departments TO Mary;
            ```
        - `ALL` can be used to grant all relevant DML Privileges at once.
            - Instead of granting Privileges one by one, the statement grants them together on the specified Table.
            - In this example:
                - The database object is the `Departments` Table.
                - The user receiving the Privileges is Mary.

    - **Grant a Privilege to multiple users:**
        - Example:
            ```sql
                GRANT SELECT ON Employees TO Ahmed, Mary;
            ```
        - More than one user can be specified in the same `GRANT` statement.
            - Ahmed receives the `SELECT` Privilege on `Employees`.
            - Mary also receives the `SELECT` Privilege on `Employees`.

- **WITH GRANT OPTION:**
    - **WITH GRANT OPTION** gives a user the ability to grant the same Privilege to other users.
    - Example:
        ```sql
            GRANT SELECT ON Employees TO Ahmed WITH GRANT OPTION;
        ```
    - Difference between the two statements:
        - Without `WITH GRANT OPTION`:
            ```sql
                GRANT SELECT ON Employees TO Ahmed;
            ```
            - Ahmed receives the `SELECT` Privilege on `Employees`.
            - Ahmed can use `SELECT` on the Table.
        - With `WITH GRANT OPTION`:
            ```sql
                GRANT SELECT ON Employees TO Ahmed WITH GRANT OPTION;
            ```
            - Ahmed receives the `SELECT` Privilege on `Employees`.
            - Ahmed can use `SELECT` on the Table.
            - Ahmed can also grant the same `SELECT` Privilege to another user.
    - Example of the permission flow:
        - Database Owner → Ahmed
            - Ahmed receives `SELECT` on `Employees`.
            - Because the Privilege was given with `WITH GRANT OPTION`:
                - Ahmed can grant `SELECT` on `Employees` to another user.

- **REVOKE Command:**
    - The `REVOKE` command is used to remove Privileges that were previously granted to users.
    - Example:
        ```sql
            REVOKE UPDATE ON Departments FROM Mary;
        ```
    - Explanation of the statement:
        - `REVOKE`:
            - Removes a previously granted Privilege.
        - `UPDATE`:
            - Is the Privilege being removed.
        - `ON Departments`:
            - Specifies that the Privilege applies to the `Departments` Table.
        - `FROM Mary`:
            - Specifies the user from whom the Privilege is removed.
    - Therefore:
        - Mary's `UPDATE` Privilege on the `Departments` Table is removed.
        - Mary is no longer allowed to update Data in `Departments`.

- **REVOKE ALL:**
    - `REVOKE ALL` is used to remove all granted Privileges from one or more users on a specified database object.
    - Example:
        ```sql
            REVOKE ALL ON Departments FROM Mary, Ahmed;
        ```
    - Explanation of the statement:
        - `ALL`:
            - Removes all granted Privileges on the specified object.
        - `ON Departments`:
            - Specifies the `Departments` Table.
        - `FROM Mary, Ahmed`:
            - Specifies multiple users.
            - The Privileges are removed from both Mary and Ahmed.
    - Therefore:
        - The statement removes all granted Privileges from Mary and Ahmed on the `Departments` Table.

- **GRANT vs REVOKE:**
    - **GRANT:**
        - Gives / adds Privileges to users.
        - Example:
            ```sql
                GRANT SELECT ON Employees TO Ahmed;
            ```
    - **REVOKE:**
        - Removes Privileges from users.
        - Example:
            ```sql
                REVOKE SELECT ON Employees FROM Ahmed;
            ```
    - The difference is:
        - `GRANT` determines that a user is allowed to perform an operation.
        - `REVOKE` removes the user's permission to perform that operation.

- **DCL vs DML vs DDL:**
    - **DCL:**
        - Controls access and Permissions on database objects.
        - Determines **who is allowed** to perform operations.
        - Main commands:
            - `GRANT`
            - `REVOKE`
    - **DML:**
        - Works with the Data stored inside Tables.
        - Examples:
            - `SELECT`
            - `INSERT`
            - `UPDATE`
            - `DELETE`
    - **DDL:**
        - Defines and manages the structure of database objects.
        - Examples:
            - `CREATE`
            - `ALTER`
            - `DROP`
            - `TRUNCATE`
    - Important distinction:
        - DCL does not describe how to manipulate Table Data or how to create a Table structure.
        - DCL controls which users are allowed to perform operations on database objects.

- **Main Idea:**
    - **DCL** controls access to database objects.
        - `GRANT` gives Privileges.
        - `REVOKE` removes Privileges.
        - `WITH GRANT OPTION` allows a user to pass / grant the same Privilege to other users.
