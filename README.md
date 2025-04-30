Generic JSON Normalizer for Microsoft Fabric

This notebook is designed to parse and normalize any generic, nested JSON file. 
It performs the following key operations:

1. Normalization of Nested Structures: Each array or struct within the JSON is extracted into its own table. An artificial hash key is generated to serve as the primary key for each table.
2. Parent-Child Key Propagation: The primary key of the parent structure is passed down to its corresponding child tables to maintain relational integrity.
3. Table Creation: Separate tables are created for each nested array or struct encountered in the JSON file.
   
Prerequisites:
1. A JSON file to parse.
2. Access to a Fabric Lakehouse environment.
   
Important Considerations:
1. Performance: This is a generic parser and schema normalizer. When used with large or deeply nested JSON files, performance may be impacted due to runtime schema inference. Use with caution in such scenarios.
2. Flexibility of JSON: Given the highly flexible nature of JSON, there may be edge cases that this notebook does not fully support. It is recommended to thoroughly test the notebook with your specific JSON formats.

Limitations:
1. Currently, the code does not support json files which have '.' in the column/field names.
