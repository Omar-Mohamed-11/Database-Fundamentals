# SQL - Aggregate Functions

- **Aggregate Functions:**
    - Aggregate Functions perform a calculation on a group of Values and return one result.
    - They are used with `SELECT` to summarize Data in a Table.
    - Common Aggregate Functions include:
        - `MAX()`
        - `MIN()`
        - `COUNT()`
        - `AVG()`

- **MAX Function:**
    - `MAX()` returns the highest Value in a Column.
    - Example: find the highest Salary in the company.
        ```sql
            SELECT MAX(Salary) AS max_salary
            FROM Employee;
        ```
    - In this statement:
        - `MAX(Salary)` finds the highest Value in the `Salary` Column.
        - `AS max_salary` gives the result a clear output label.

- **MIN Function:**
    - `MIN()` returns the lowest Value in a Column.
    - Example: find the lowest Salary in the company.
        ```sql
            SELECT MIN(Salary) AS min_salary
            FROM Employee;
        ```
    - In this statement:
        - `MIN(Salary)` finds the lowest Value in the `Salary` Column.
        - `AS min_salary` gives the result a clear output label.

- **Find the Maximum and Minimum Salary Together:**
    - `MAX()` and `MIN()` can be used together in one query.
    - Example:
        ```sql
            SELECT MAX(Salary) AS max_salary,
                   MIN(Salary) AS min_salary
            FROM Employee;
        ```
    - In this statement:
        - `MAX(Salary)` returns the highest Salary.
        - `MIN(Salary)` returns the lowest Salary.
        - `max_salary` and `min_salary` make the query output easier to understand.

- **COUNT Function:**
    - `COUNT()` counts Values in a Column.
    - Example: count the Employees that have a Salary Value.
        ```sql
            SELECT COUNT(Salary) AS salary_count
            FROM Employee;
        ```
    - In this statement:
        - `COUNT(Salary)` counts only non-`NULL` Values in the `Salary` Column.
        - `AS salary_count` gives the result a clear output label.

- **AVG Function:**
    - `AVG()` calculates the average of the Values in a Column.
    - Example: calculate the average Salary.
        ```sql
            SELECT AVG(Salary) AS average_salary
            FROM Employee;
        ```
    - In this statement:
        - `AVG(Salary)` calculates the average using the non-`NULL` Values in the `Salary` Column.
        - `AS average_salary` gives the result a clear output label.

- **Aggregate Functions and NULL Values:**
    - Aggregate Functions applied to a Column ignore `NULL` Values.
    - For example:
        - `COUNT(Salary)` counts only Employees whose `Salary` is not `NULL`.
        - `AVG(Salary)` calculates the average from only non-`NULL` Salary Values.
        - `MAX(Salary)` and `MIN(Salary)` use the available non-`NULL` Salary Values.
    - Therefore, `NULL` Salary Values do not affect the Count, Average, Maximum, or Minimum calculation.

- **Aliases with Aggregate Functions:**
    - An Alias gives the result of an Aggregate Function a meaningful name.
    - Example:
        ```sql
            SELECT MAX(Salary) AS max_salary,
                   MIN(Salary) AS min_salary
            FROM Employee;
        ```
    - Without Aliases, the output labels would be the function expressions.
    - Using `max_salary` and `min_salary` makes the output clearer.

- #### SUMMARY:
    - **MAX():**
        - Returns the highest Value in a Column.
    - **MIN():**
        - Returns the lowest Value in a Column.
    - **COUNT():**
        - Counts non-`NULL` Values in a specified Column.
    - **AVG():**
        - Calculates the average of non-`NULL` Values in a specified Column.
    - **Aliases:**
        - Give Aggregate Function results clear output labels.
