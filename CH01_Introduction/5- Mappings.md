- **Mappings** are the process that transforms requests and results between different schema levels in a database system.

![[Pasted image 20260806060032.png|688]]

- There are three schemas: External, Conceptual, and Physical. When a user requests data through the External schema, the request is sent to the Conceptual schema, which maps it to the appropriate tables containing the data. Then, the request moves to the Physical schema, which knows the exact data locations on disk, retrieves the data, and sends it back through the Conceptual schema to the External schema, which delivers the results to the user. Mappings are the core process that converts requests and results between these different levels.