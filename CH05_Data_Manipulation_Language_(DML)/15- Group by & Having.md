# SQL - GROUP BY and HAVING

- **GROUP BY Clause:**
    - The `GROUP BY` clause groups Rows that have the same Value in a specified Column.
    - It is used with Aggregate Functions to calculate a result for each group.
    - The basic structure is:
        ```sql
            SELECT Group_Column, Aggregate_Function(Column_Name)
            FROM Table_Name
            GROUP BY Group_Column;
        ```
    - For example, Employees can be grouped according to their Department Number.
        - All Employees in the same Department form one group.
        - An Aggregate Function can then calculate a result for each Department group.

- **Average Salary for Each Department:**
    - `AVG()` can be used with `GROUP BY` to calculate the average Salary for each Department.
    - Example:
        ```sql
            SELECT DepartmentNumber, AVG(Salary) AS average_salary
            FROM Employees
            GROUP BY DepartmentNumber;
        ```
    - In this statement:
        - `GROUP BY DepartmentNumber` groups Employees by Department Number.
        - `AVG(Salary)` calculates the average Salary within each Department group.
        - `AS average_salary` gives the calculated result a clear output label.

- **HAVING Clause:**
    - The `HAVING` clause filters groups after the Aggregate Function calculation.
    - It is used when the filtering condition contains an Aggregate Function.
    - The basic structure is:
        ```sql
            SELECT Group_Column, Aggregate_Function(Column_Name)
            FROM Table_Name
            GROUP BY Group_Column
            HAVING Aggregate_Function(Column_Name) Condition;
        ```
    - `HAVING` is used after `GROUP BY`.

- **Filter Departments Using Maximum Salary:**
    - The following query displays the average Salary for each Department, but only for Departments whose maximum Salary is greater than `1800`.
        ```sql
            SELECT DepartmentNumber, AVG(Salary) AS average_salary
            FROM Employees
            GROUP BY DepartmentNumber
            HAVING MAX(Salary) > 1800;
        ```
    - In this statement:
        - `GROUP BY DepartmentNumber` creates a group for each Department.
        - `AVG(Salary)` calculates the average Salary for each Department group.
        - `HAVING MAX(Salary) > 1800` checks the highest Salary in each Department group.
        - Only Departments with a maximum Salary greater than `1800` are displayed.
        - The result shows each qualifying Department Number and its average Salary.

- **WHERE vs HAVING:**
    - **WHERE:**
        - Filters individual Rows before grouping and aggregation.
    - **HAVING:**
        - Filters groups after grouping and aggregation.
        - Is used for Conditions that contain Aggregate Functions such as `MAX()`, `MIN()`, `AVG()`, or `COUNT()`.
    - In this topic:
        - `HAVING MAX(Salary) > 1800` is used because the condition checks an Aggregate Function result for each Department group.

- **Order of the Query Clauses:**
    - The query is organized as follows:
        - `SELECT`:
            - Specifies the Department Number and calculated average Salary to display.
        - `FROM`:
            - Specifies the `Employees` Table.
        - `GROUP BY`:
            - Groups Employees by `DepartmentNumber`.
        - `HAVING`:
            - Keeps only Department groups whose maximum Salary is greater than `1800`.

- #### SUMMARY:
    - **GROUP BY:**
        - Groups Rows with the same Value.
        - Allows Aggregate Functions to calculate a result for each group.
    - **HAVING:**
        - Filters groups after aggregation.
        - Is used with Aggregate Function Conditions.
    - **Example Condition:**
        - `HAVING MAX(Salary) > 1800` displays only Departments whose highest Salary is greater than `1800`.
