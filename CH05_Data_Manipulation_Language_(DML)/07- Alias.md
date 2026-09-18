# SQL - Alias

- **Alias:**
    - An Alias is a temporary name given to a Column in the query result.
    - It is commonly used to give a clear label to:
        - A Calculated Column.
        - Combined Data.
        - A Column with a long or unclear name.
    - The `AS` keyword is used to assign an Alias.
    - The basic structure is:
        ```sql
            SELECT Expression AS Alias_Name
            FROM Table_Name;
        ```
    - An Alias affects only the displayed query result.
        - It does not change the actual Column Name in the Table.
        - It does not change the Data stored in the Database.

- **Calculated Columns:**
    - A Calculated Column is created by performing an arithmetic operation on existing Data in a query.
    - The calculation is displayed as part of the query result.
    - **Example: Calculate a Bonus:**
        - A Bonus can be calculated as `10%` of an Employee's Salary.
            ```sql
                SELECT Salary * 0.1 AS Bonus
                FROM Employee;
            ```
        - In this statement:
            - `Salary * 0.1` calculates `10%` of the Salary.
            - `AS Bonus` gives the calculated result the Column label `Bonus`.
            - The original `Salary` Data is not changed.

- **Concatenate Columns:**
    - Concatenation combines the Values of two or more Columns into one displayed Value.
    - For example, `FirstName` and `LastName` can be combined to create a Full Name.
    - The concatenation operator can be `+` or `||`.

    - **Using `+`:**
        ```sql
            SELECT FirstName + ' ' + LastName AS Full_Name
            FROM Employee;
        ```

    - **Using `||`:**
        ```sql
            SELECT FirstName || ' ' || LastName AS Full_Name
            FROM Employee;
        ```

    - In these statements:
        - `FirstName` and `LastName` are combined into one Value.
        - `' '` adds a space between the First Name and Last Name.
        - `AS Full_Name` gives the combined result a clear label.
        - The concatenation operator used depends on the SQL environment.
        - If the alias name has a space we should put it in [ ],  Ex: 
           ```sql
              SELECT FirstName + ' ' + LastName AS [Full Name]
              FROM Employee;
           ```

- **Calculated Condition in WHERE:**
    - A calculation can also be used in a `WHERE` clause to filter Data.
    - Example: select Employees whose Annual Salary is greater than `10000`.
        ```sql
            SELECT *
            FROM Employee
            WHERE Salary * 12 > 10000;
        ```
    - In this statement:
        - `Salary * 12` calculates the Annual Salary from the Monthly Salary.
        - `> 10000` checks whether the calculated Annual Salary is greater than `10000`.
        - Only Employees who meet this Condition are displayed.

- **Alias and Database Content:**
    - An Alias is used for display in the query output.
    - It does not:
        - Rename a Column in the actual Table.
        - Modify existing Data.
        - Add a new stored Column to the Table.
    - It makes calculated or combined Data easier to understand when viewing the query result.

- #### SUMMARY:
    - **Alias:**
        - A temporary label for a Column in the query result.
        - Is assigned using `AS`.
        - Does not change the Database content.
    - **Calculated Column:**
        - Uses an arithmetic operation on existing Data.
        - Example: `Salary * 0.1 AS Bonus`.
    - **Concatenation:**
        - Combines Values from multiple Columns.
        - Can use `+` or `||`.
    - **Calculated WHERE Condition:**
        - Uses a calculation to filter Records.
        - Example: `Salary * 12 > 10000`.
