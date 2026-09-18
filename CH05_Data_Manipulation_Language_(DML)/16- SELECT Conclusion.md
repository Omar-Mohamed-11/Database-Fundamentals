# SQL - SELECT Conclusion

- **Comprehensive SELECT Statement:**
    - A `SELECT` statement can combine multiple clauses to retrieve, join, group, filter, calculate, and sort Data.
    - The following example displays the Department Name, Maximum Salary, and Average Salary for each Department.
        - Only Departments whose Average Salary is greater than `1200` are displayed.
        - The Result Set is ordered by Department Name.
    - Example:
        ```sql
            SELECT D.DepartmentName,
                   MAX(E.Salary) AS max_salary,
                   AVG(E.Salary) AS average_salary
            FROM Employee E, Departments D
            WHERE E.DepartmentNumber = D.DepartmentNumber
            GROUP BY D.DepartmentName
            HAVING AVG(E.Salary) > 1200
            ORDER BY D.DepartmentName;
        ```

- **SELECT Clause:**
    - The `SELECT` clause specifies the Columns and calculated Values that should be displayed.
    - In this query:
        - `D.DepartmentName` displays the Department Name.
        - `MAX(E.Salary) AS max_salary` displays the Maximum Salary for each Department.
        - `AVG(E.Salary) AS average_salary` displays the Average Salary for each Department.
    - The Aliases `max_salary` and `average_salary` make the Result Set clearer.

- **FROM Clause:**
    - The `FROM` clause specifies the source Tables.
    - In this query:
        ```sql
            FROM Employee E, Departments D
        ```
        - `Employee` is represented by the Alias `E`.
        - `Departments` is represented by the Alias `D`.
        - Data from both Tables is required to display Department Names and Employee Salaries.

- **WHERE Clause:**
    - The `WHERE` clause filters Data and specifies the Join Condition between the Tables.
    - In this query:
        ```sql
            WHERE E.DepartmentNumber = D.DepartmentNumber
        ```
        - The Department Number in the `Employee` Table is matched with the Department Number in the `Departments` Table.
        - This connects each Employee with the Department in which the Employee works.

- **GROUP BY Clause:**
    - The `GROUP BY` clause groups Employees according to their Department Name.
    - In this query:
        ```sql
            GROUP BY D.DepartmentName
        ```
        - All Employees in the same Department form one group.
        - `MAX(E.Salary)` and `AVG(E.Salary)` are calculated separately for each Department group.

- **Aggregate Functions:**
    - Aggregate Functions calculate one result for each Department group.
    - In this query:
        - `MAX(E.Salary)` finds the highest Salary in each Department.
        - `AVG(E.Salary)` calculates the average Salary in each Department.

- **HAVING Clause:**
    - The `HAVING` clause filters groups after aggregation.
    - In this query:
        ```sql
            HAVING AVG(E.Salary) > 1200
        ```
        - The Average Salary is calculated for each Department group.
        - Only Departments whose Average Salary is greater than `1200` are included in the Result Set.

- **ORDER BY Clause:**
    - The `ORDER BY` clause sorts the final Result Set.
    - In this query:
        ```sql
            ORDER BY D.DepartmentName;
        ```
        - The Result Set is sorted by Department Name.
        - The default sorting order is Ascending Order.

- **Logical Execution Sequence:**
    - SQL clauses are written in one order but are logically processed by the DBMS in the following order:
        - **1. `FROM`:**
            - Loads the source Tables.
        - **2. `WHERE`:**
            - Filters Rows and applies the Join Condition.
        - **3. `GROUP BY`:**
            - Groups the remaining Rows by Department Name.
        - **4. Aggregate Functions and `HAVING`:**
            - Calculates the Maximum and Average Salary for each group.
            - Filters the groups using `HAVING AVG(E.Salary) > 1200`.
        - **5. `SELECT`:**
            - Prepares the Department Name, Maximum Salary, and Average Salary for display.
        - **6. `ORDER BY`:**
            - Sorts the final Result Set by Department Name.

- **Grouped Query Rules:**
    - When `GROUP BY` is used:
        - A selected Column must be included in the `GROUP BY` clause or be used inside an Aggregate Function.
        - In this query:
            - `D.DepartmentName` is selected and included in `GROUP BY`.
            - `MAX(E.Salary)` and `AVG(E.Salary)` are Aggregate Function results.
    - `ORDER BY` can reference selected Columns or grouped Columns.
        - `D.DepartmentName` is selected and grouped, so it can be used in `ORDER BY`.

- #### SUMMARY:
    - **SELECT:**
        - Specifies the Data and calculated Values to display.
    - **FROM and WHERE:**
        - Load and join the source Tables.
    - **GROUP BY:**
        - Groups Employees by Department Name.
    - **MAX() and AVG():**
        - Calculate the Maximum and Average Salary for each Department.
    - **HAVING:**
        - Filters Departments whose Average Salary is greater than `1200`.
    - **ORDER BY:**
        - Sorts the final Result Set by Department Name.
