# Database Normalization

- **Normalization:**
    - **Normalization** is a process that uses a set of tests called **Normal Forms**.
    - It is used to organize Database Data and evaluate the quality of a Database Design.
    - Normalization has two main purposes:
        - **Test and improve an existing Database Design:**
            - Checks whether the design contains unnecessary Data Redundancy.
            - Helps avoid Insert, Update, and Delete Anomalies.
        - **Design a Database from scratch:**
            - Can be used as a method for creating a Database Design.
            - Helps organize the Data into suitable Tables.

- **Problems in a Poor Database Design:**
    - A Database Design may contain unnecessary repeated Data.
    - It may also create Anomalies when Data is inserted, updated, or deleted.
    - These problems can affect:
        - Data Storage requirements.
        - Data Consistency.
        - Data Integrity.

- **Normalization Example:**
    - Consider two Tables:
        - `Employee Department`
        - `Employee Project`
    - The Tables are linked by the Employee's `SSN`.
    - In this design, Department information may be repeated for multiple Employees.
        - For example, the Department Name may be repeated.
        - The Department Manager Number may also be repeated.
    - Repeating the same information in many Records causes Data Redundancy.

- **Data Redundancy:**
    - **Data Redundancy** means storing the same Data more than once.
    - In the Employee Department example:
        - The same Department Name can appear in many Employee Records.
        - The same Manager Number can appear in many Employee Records.
    - Data Redundancy can cause:
        - More Storage Space to be used.
        - A greater possibility of inconsistent Data.
        - Insert, Update, and Delete Anomalies.

- **Anomalies:**
    - An **Anomaly** is a problem that occurs when Data is inserted, updated, or deleted in a poor Database Design.
    - The main Anomalies are:
        - Insert Anomaly.
        - Delete Anomaly.
        - Update Anomaly.

- **Insert Anomaly:**
    - An **Insert Anomaly** occurs when required Data cannot be added without adding unrelated Data.
    - In the example:
        - A new Department may not be added unless an Employee is added with it.
        - A new Project may not be added unless an Employee is added with it.
    - This prevents Department or Project Data from being stored independently when needed.

- **Delete Anomaly:**
    - A **Delete Anomaly** occurs when deleting one Record unintentionally removes other important information.
    - In the example:
        - Deleting an Employee Record may remove the only stored information about a Department.
        - This may incorrectly imply that the Department no longer exists.

- **Update Anomaly:**
    - An **Update Anomaly** occurs when the same Data must be changed in multiple Records.
    - In the example:
        - Changing a Department Manager Number may require updating many Employee Records.
        - If some Records are not updated:
            - The same Department may have different Manager Numbers in different Records.
            - The Data becomes inconsistent.

- **Null Values and Data Integrity:**
    - A poor Database Design can also contain Null Values.
    - Null Values can affect Data Integrity.
    - Normalization helps handle design issues that can lead to unnecessary Null Values.

- **Benefits of Normalization:**
    - Normalization helps improve Database Design Quality.
    - It helps reduce Data Duplication.
        - This can reduce Storage requirements.
    - It helps avoid:
        - Insert Anomalies.
        - Delete Anomalies.
        - Update Anomalies.
    - It supports more consistent Data and improved Data Integrity.

- #### SUMMARY:
    - **Normalization:**
        - A process that uses tests called Normal Forms.
        - Is used to evaluate, improve, or create a Database Design.
    - **Main Goals:**
        - Reduce Data Redundancy.
        - Avoid Insert, Update, and Delete Anomalies.
        - Improve Data Integrity.
    - **Insert Anomaly:**
        - Occurs when Data cannot be added without adding unrelated Data.
    - **Delete Anomaly:**
        - Occurs when deleting a Record unintentionally removes important Data.
    - **Update Anomaly:**
        - Occurs when repeated Data must be updated in many Records, creating a risk of inconsistency.
