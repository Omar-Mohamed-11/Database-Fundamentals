# SQL - Sub-Queries

- **Sub-Query:**
    - A Sub-Query is a query written inside another SQL query.
    - It is also called a Nested Query.
    - The inner query returns a Value or Values that are used by the outer query.
    - A Sub-Query is enclosed in parentheses.
    - The basic structure is:
        ```sql
            SELECT Column_Name
            FROM Table_Name
            WHERE Column_Name Operator (
                SELECT Column_Name
                FROM Table_Name
                WHERE Condition
            );
        ```

- **Find the Salary of a Specific Employee:**
    - A Sub-Query can retrieve the Salary of a specific Employee, such as Ahmed Ali.
    - Example:
        ```sql
            SELECT Salary
            FROM Employee
            WHERE FirstName = 'Ahmed' AND LastName = 'Ali';
        ```
    - This query returns Ahmed Ali's Salary.
    - The returned Salary can then be used in another query for comparison.

- **Compare with One Value Returned by a Sub-Query:**
    - A standard Comparison Operator such as `>` or `<` can compare a Value with one Value returned by a Sub-Query.
    - Example: display Employees whose Salary is higher than Ahmed Ali's Salary.
        ```sql
            SELECT FirstName, LastName, Salary
            FROM Employee
            WHERE Salary > (
                SELECT Salary
                FROM Employee
                WHERE FirstName = 'Ahmed' AND LastName = 'Ali'
            );
        ```
    - In this statement:
        - The inner query retrieves Ahmed Ali's Salary.
        - The outer query compares each Employee's Salary with that returned Salary.
        - Only Employees earning more than Ahmed Ali are displayed.
    - The Comparison Operator works when the Sub-Query returns one Value.

- **Sub-Query That Returns Multiple Values:**
    - A Sub-Query can return more than one Value.
    - For example, a query that retrieves Salaries for all Employees in Department `10` can return multiple Salary Values.
        ```sql
            SELECT Salary
            FROM Employee
            WHERE DepartmentNumber = 10;
        ```
    - A standard Comparison Operator such as `>` or `<` cannot directly compare one Value with multiple Values returned by a Sub-Query.
    - Multi-row Operators such as `ALL` and `ANY` are used in this situation.

- **ALL Operator:**
    - `ALL` compares a Value with every Value returned by a Sub-Query.
    - Example: display Employees whose Salary is greater than all Salaries in Department `10`.
        ```sql
            SELECT FirstName, LastName, Salary
            FROM Employee
            WHERE Salary > ALL (
                SELECT Salary
                FROM Employee
                WHERE DepartmentNumber = 10
            );
        ```
    - In this statement:
        - The Sub-Query returns the Salaries of Employees in Department `10`.
        - `Salary > ALL` requires an Employee's Salary to be greater than every returned Salary.
        - The displayed Employee has a Salary higher than all Employees in Department `10`.

- **ANY Operator:**
    - `ANY` compares a Value with at least one Value returned by a Sub-Query.
    - Example: display Employees whose Salary is greater than at least one Salary in Department `10`.
        ```sql
            SELECT FirstName, LastName, Salary
            FROM Employee
            WHERE Salary > ANY (
                SELECT Salary
                FROM Employee
                WHERE DepartmentNumber = 10
            );
        ```
    - In this statement:
        - The Sub-Query returns the Salaries of Employees in Department `10`.
        - `Salary > ANY` requires an Employee's Salary to be greater than at least one returned Salary.
        - The Employee does not need to earn more than every Employee in Department `10`.

- **ALL vs ANY:**
    - **ALL:**
        - Compares a Value with every Value returned by the Sub-Query.
        - `Salary > ALL` means the Salary must be greater than all returned Salaries.
    - **ANY:**
        - Compares a Value with at least one Value returned by the Sub-Query.
        - `Salary > ANY` means the Salary must be greater than at least one returned Salary.

- **Important Notes:**
    - The inner query is executed to provide the Value or Values needed by the outer query.
    - Use standard Comparison Operators when the Sub-Query returns one Value.
    - Use `ALL` or `ANY` when the Sub-Query returns multiple Values.

- #### SUMMARY:
    - **Sub-Query:**
        - A query inside another SQL query.
        - Is enclosed in parentheses.
    - **One Returned Value:**
        - Can be compared using Operators such as `>` or `<`.
    - **ALL:**
        - Compares with every Value returned by a Sub-Query.
    - **ANY:**
        - Compares with at least one Value returned by a Sub-Query.
