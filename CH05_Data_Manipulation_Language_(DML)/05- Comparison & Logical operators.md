# SQL - Comparison and Logical Operators

- **Filtering Data Using WHERE:**
    - The `WHERE` clause is used with `SELECT` to display only Records that meet a Condition.
    - Conditions can compare a Column Value with a specified Value.
    - Logical Operators and multi-row Operators can be used to combine or simplify Conditions.

- **Comparison Operator:**
    - A Comparison Operator compares Values in a `WHERE` Condition.
    - **Greater Than `>`:**
        - Selects Values that are greater than a specified Value.
        - Example: select Employees whose Salary is greater than `1500`.
            ```sql
                SELECT *
                FROM Employee
                WHERE Salary > 1500;
            ```
        - In this statement:
            - `Salary > 1500` is the Condition.
            - Only Employees earning more than `1500` are displayed.

- **Logical Operators:**
    - Logical Operators are used to combine more than one Condition in a `WHERE` clause.

    - **AND Operator:**
        - `AND` requires both Conditions to be true.
        - Example: select the First Names of Employees whose Salary is between `1500` and `2500`.
            ```sql
                SELECT FName
                FROM Employee
                WHERE Salary >= 1500 AND Salary <= 2500;
            ```
        - In this statement:
            - `Salary >= 1500` checks that the Salary is at least `1500`.
            - `Salary <= 2500` checks that the Salary is no more than `2500`.
            - An Employee is displayed only when both Conditions are true.

    - **OR Operator:**
        - `OR` requires at least one of the Conditions to be true.
        - Example: select Employees supervised by either of two Supervisors.
            ```sql
                SELECT *
                FROM Employee
                WHERE SuperSSN = 123456789 OR SuperSSN = 987654321;
            ```
        - In this statement:
            - Employees supervised by `123456789` are displayed.
            - Employees supervised by `987654321` are also displayed.
            - An Employee only needs to meet one of the two Conditions.

- **Multi-Row Operators:**
    - Multi-row Operators make it easier to test a Column against multiple Values or a range of Values.

    - **BETWEEN Operator:**
        - `BETWEEN` tests whether a Value is within a specified range.
        - It can be used instead of writing two Conditions with `AND`.
        - Example:
            ```sql
                SELECT FName
                FROM Employee
                WHERE Salary BETWEEN 1500 AND 2500;
            ```
        - This statement displays the First Names of Employees whose Salary is between `1500` and `2500`.
        - `BETWEEN 1500 AND 2500` includes the boundary Values `1500` and `2500`.

    - **IN Operator:**
        - `IN` tests whether a Column Value matches one of several listed Values.
        - It can be used instead of repeating the same Column with `OR`.
        - Example:
            ```sql
                SELECT *
                FROM Employee
                WHERE SuperSSN IN (123456789, 987654321);
            ```
        - This statement has the same purpose as:
            ```sql
                SELECT *
                FROM Employee
                WHERE SuperSSN = 123456789 OR SuperSSN = 987654321;
            ```
        - `IN` makes the Condition shorter when multiple Values are checked in the same Column.

- **AND / BETWEEN and OR / IN:**
    - **AND and BETWEEN:**
        - Both can be used to select Values within a range.
        - `BETWEEN` is a shorter form when checking one Column against a lower and upper Value.
    - **OR and IN:**
        - Both can be used to select Records that match one of multiple Values in the same Column.
        - `IN` is a shorter form when the same Column is tested against several Values.

- #### SUMMARY:
    - **Comparison Operator `>`:**
        - Selects Values greater than a specified Value.
    - **AND:**
        - Requires all combined Conditions to be true.
    - **OR:**
        - Requires at least one combined Condition to be true.
    - **BETWEEN:**
        - Selects Values within a specified range.
    - **IN:**
        - Selects Records that match one of multiple Values in the same Column.
