# SQL - Indexes

- **Index:**
    - An **Index** is a Database Object used to improve Data Retrieval Performance.
    - It helps the Database find required Records more quickly.
    - An Index can be understood as an organized Phone Book.
        - A Phone Book keeps Names in an organized order.
        - Each Name is linked to its related phone number.
        - This allows a required phone number to be found without searching every entry.
    - In the same way, an Index:
        - Organizes Key Values.
        - Links each Key Value to its related Record.
        - Allows the Database to locate Data more quickly.

- **Problems Addressed by an Index:**
    - An Index helps when Data has the following characteristics:
        - **Data is not sorted:**
            - The required Value may not be stored in an organized order inside the Table.
            - Searching for a Value can require checking many Records.
        - **Data is not stored contiguously in Physical Memory:**
            - Related Records may not be stored beside each other in Physical Memory.
            - Finding the required Record can take more time.
    - The Index provides an organized path to the required Record.

- **Index and Data Retrieval:**
    - An Index speeds up Data Retrieval Operations.
    - When the Database searches for a Record:
        - It can use the organized Index Values.
        - The Index directs the Database to the related Record.
        - The Database does not need to search the entire Table in the same way.

- **Index and Data Modification:**
    - Although an Index improves Data Retrieval, it can slow down Data Modification Operations.
    - This includes:
        - `INSERT`
        - `UPDATE`
        - `DELETE`
    - When Data is modified:
        - The Table must be updated.
        - The Index must also be updated to reflect the change.
    - Therefore, an Index should be created when its faster Data Retrieval benefit is needed.

- **When to Create an Index:**
    - An Index is useful for Columns that are searched frequently.
    - Before creating an Index, consider the balance between:
        - Faster Data Retrieval.
        - Slower `INSERT`, `UPDATE`, and `DELETE` operations.

- **CREATE INDEX Statement:**
    - The `CREATE INDEX` statement is used to create an Index.
    - The basic structure is:
        ```sql
            CREATE INDEX Index_Name
            ON Table_Name (Column_Name);
        ```
    - In this statement:
        - `Index_Name` identifies the new Index.
        - `Table_Name` specifies the Table that contains the Data.
        - `Column_Name` specifies the Column that will be indexed.

- **DROP INDEX Statement:**
    - The `DROP INDEX` statement is used to remove an Index.
    - The basic structure is:
        ```sql
            DROP INDEX Index_Name;
        ```
    - Removing an Index removes the organized search structure.
        - It does not remove the Data stored in the Table.

- #### SUMMARY:
    - **Index:**
        - A Database Object used to improve Data Retrieval Performance.
        - Organizes Key Values and links them to their related Records.
    - **Main Purpose:**
        - Helps find Data faster when Table Data is not sorted or stored contiguously in Physical Memory.
    - **Advantage:**
        - Speeds up searching and retrieving Data.
    - **Disadvantage:**
        - Can slow down `INSERT`, `UPDATE`, and `DELETE` operations because the Index must also be updated.
    - **CREATE INDEX:**
        - Creates an Index on a Table Column.
    - **DROP INDEX:**
        - Removes an Index without removing the Table Data.
