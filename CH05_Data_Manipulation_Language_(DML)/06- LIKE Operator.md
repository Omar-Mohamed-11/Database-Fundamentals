# SQL - "LIKE" Operator

- **LIKE Operator:**
    - `LIKE` is used in a `WHERE` clause to compare a Value with a Pattern.
    - It is useful when the exact Value is not known.
    - Instead of searching for an exact Value, `LIKE` searches for Values that match the specified Pattern.
    - The basic structure is:
        ```sql
            SELECT Column1, Column2, ...
            FROM Table_Name
            WHERE Column_Name LIKE 'Pattern';
        ```

- **Wildcards Used with LIKE:**
    - Wildcards are special characters used to represent unknown characters in a Pattern.

    - **Question Mark `?`:**
        - Replaces exactly one Character.
        - It is used when one Character is unknown or may vary.
        - Example Pattern:
            ```sql
                'Ahm?d'
            ```
        - This Pattern can match:
            - `Ahmed`
            - `Ahmad`
        - In this Pattern:
            - `?` replaces the Character between `m` and `d`.
            - It can represent `e` in `Ahmed` or `a` in `Ahmad`.

    - **Asterisk `*`:**
        - Replaces zero or more Characters.
        - It is used when any number of Characters may appear in a part of the Value.
        - It can also represent no additional Characters.

- **Example: Second Letter Is "o":**
    - To find Employees whose second letter in `FirstName` is `o`, create a Pattern that represents:
        - Any first Character.
        - The letter `o` as the second Character.
        - Zero or more Characters after it.
    - Example:
        ```sql
            SELECT *
            FROM Employee
            WHERE FirstName LIKE '?o*';
        ```
    - In this statement:
        - The first `?` represents any single first Character.
        - `o` must be the second Character.
        - `*` represents zero or more Characters after `o`.
        - Only Employees whose `FirstName` matches this Pattern are displayed.

- **Example: Match Name Variations:**
    - The `LIKE` operator can handle slight variations in Data.
    - Example:
        ```sql
            SELECT *
            FROM Employee
            WHERE FirstName LIKE 'Ahm?d';
        ```
    - This statement displays Employees whose `FirstName` matches the Pattern `Ahm?d`.
        - It can match `Ahmed`.
        - It can match `Ahmad`.
    - The Pattern is enclosed in single quotes because it is a Character Value.

- **LIKE vs Exact Comparison:**
    - An exact comparison searches for one exact Value.
    - `LIKE` searches for Values that match a Pattern.
    - Use `LIKE` when:
        - The exact Value is unknown.
        - Part of a Value is known.
        - Variations in a Value must be included in the search.

- #### SUMMARY:
    - **LIKE:**
        - Compares a Column Value with a Pattern.
        - Is useful when the exact Value is not known.
    - **`?`:**
        - Replaces one Character.
    - **`*`:**
        - Replaces zero or more Characters.
    - **Example Pattern `?o*`:**
        - Finds Values whose second Character is `o`.
    - **Example Pattern `Ahm?d`:**
        - Can match both `Ahmed` and `Ahmad`.
