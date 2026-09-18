# First Normal Form (1NF)

- **Normalization:**
    - **Normalization** is the process of organizing Data in a Database.
    - It improves a poor Database Design by decomposing poorly structured Tables into smaller, more manageable Tables.
    - Normalization is based on:
        - Keys.
        - Functional Dependencies.
    - The Database Design is tested against conditions called **Normal Forms**.

- **First Normal Form (1NF):**
    - A Table is in **First Normal Form (1NF)** when it meets the following conditions:
        - It does not contain Multivalued Attributes.
        - It does not contain Repeating Groups.
        - It does not contain Composite Attributes.
    - The Attributes in the Table should be Atomic.
        - Each Attribute contains one Value for each Record.

- **Multivalued Attributes:**
    - A **Multivalued Attribute** contains more than one Value for the same Record.
    - Example:
        - A Student has multiple Telephone Numbers stored in one Cell.
    - This does not meet the requirements of 1NF because one Attribute contains multiple Values.

- **Repeating Groups:**
    - A **Repeating Group** occurs when the same type of information is repeated for one Record.
    - Example:
        - A Student has multiple Subjects.
        - Each Subject may include:
            - Subject Name.
            - Subject Description.
            - Grade.
    - Storing multiple Subjects, Descriptions, and Grades in the same Student Record creates a Repeating Group.

- **Composite Attributes:**
    - A **Composite Attribute** contains more than one related part.
    - A Table in 1NF should not contain Composite Attributes.
    - The Attributes should be organized as Atomic Attributes.

- **Convert a Student Table to 1NF:**
    - Suppose a `Student` Table contains:
        - Student information.
        - Multiple Telephone Numbers for the same Student.
        - Multiple Subjects with their Descriptions and Grades.
    - The Telephone Numbers and Subjects should be separated into new Tables.

- **Telephone Table:**
    - A separate `Telephone` Table can be created for the Student Telephone Numbers.
    - It contains:
        - `Student ID`
        - `Telephone Number`
    - Each Telephone Number is stored in a separate Record.
        - A Student with multiple Telephone Numbers can have multiple Records in the `Telephone` Table.

- **Subjects Table:**
    - A separate `Subjects` Table can be created for Student Subjects.
    - It contains:
        - `Student ID`
        - `Subject`
        - `Subject Description`
        - `Grade`
    - Each Subject for a Student is stored in a separate Record.
        - This removes the Repeating Group from the `Student` Table.

- **Student Table After Decomposition:**
    - After creating the `Telephone` and `Subjects` Tables:
        - The original `Student` Table contains only its Atomic Attributes.
        - It does not contain Multivalued Attributes.
        - It does not contain Repeating Groups.
        - It does not contain Composite Attributes.
    - The Table Design is now in First Normal Form.

- **Benefits of First Normal Form:**
    - 1NF improves Data Organization.
    - It separates repeated and multivalued Data into suitable Tables.
    - It makes the Database Design more manageable and efficient.

- #### SUMMARY:
    - **First Normal Form (1NF):**
        - Requires Atomic Attributes.
        - Does not allow Multivalued Attributes, Repeating Groups, or Composite Attributes.
    - **Multivalued Attribute:**
        - Contains more than one Value in the same Attribute for a Record.
    - **Repeating Group:**
        - Repeats the same type of information for one Record.
    - **Decomposition to 1NF:**
        - Separates multivalued Attributes and Repeating Groups into new Tables.
        - Leaves the original Table with Atomic Attributes.
