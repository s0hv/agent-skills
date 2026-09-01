# Database-Specific Tools
Database tools to interact with a database. You should always check what database
to use unless the user already provided the information.

## cancel_sql_query
Terminates an active query using its session identifier.

Parameters:
- `sessionId` (string, required): Query session ID.

## create_database_connection
Creates a new database connection (data source) by name, DBMS, JDBC URL, and a flag to check
connection. Establishes new data source configurations with optional validation.

Parameters:
- `name` (string, required): Unique database connection name.
- `dbms` (string, required): Database management system name.
- `url` (string, required): Fully formed JDBC URL of the database connection.
- `needToCheckDs` (boolean, required): Whether to test connection after creation.
- `projectPath`

## edit_database_connection
Edits an existing database connection (data source) identified by connectionId. Modifies DBMS
driver and connection URL while maintaining the name.

Parameters:
- `connectionId` (string, required): Unique connection ID.
- `dbms` (string, required): Database management system name.
- `url` (string, required): Fully formed JDBC URL of the database connection.
- `needToCheckDs` (boolean, required): Whether to test connection after edit.
- `projectPath`

## execute_sql_query
Execute a SQL query against the given database connection. Provides execution status and returns
data in CSV format when applicable.

Parameters:
- `connectionId` (string, required): Unique connection ID.
- `queryText` (string, required): SQL query to execute.

## fetch_query_result
Fetches rows from an already executed query by its ID, starting at the given row offset. Enables
pagination across previously executed query results.

Parameters:
- `resultSetId` (string, required): Opaque result-set ID from previous call.
- `offset` (integer, required): Row offset to start fetching from; defaults to 0.
- `projectPath`

## get_database_object_description
Retrieves the structure of a database object (columns, types, keys, indexes) within a particular
schema. Returns hierarchical text representation of database object metadata.

Parameters:
- `connectionId` (string, required): Unique connection ID.
- `databaseName` (string, required): Database name (empty if not applicable).
- `schemaName` (string, required): Schema name.
- `kind` (string, optional): Object kind code to filter by type.
- `objectName` (string, required): Name of the specific object.
- `projectPath`

## introspect_schema
Introspects a database schema, loading its metadata (tables, columns, and indexes) into the local
model. Refreshes or initially loads schema structure information.

Parameters:
- `connectionId` (string, required): Unique connection ID.
- `databaseName` (string, required): Database name (empty if not applicable).
- `schemaName` (string, required): Schema name.
- `projectPath`

## list_database_connections
Retrieves a list of configured database connections or data sources in the project. Returns
unique identifiers, names, DBMS types, and driver information.

Parameters: none.

## list_database_schemas
Retrieves a list of database schemas in the specified database connection. Provides schema names
and associated database identifiers.

Parameters:
- `connectionId` (string, required): Unique connection ID.
- `selectedOnly` (boolean, required): List only selected or all schemas.

## list_recent_sql_queries
Retrieves a list of recent, including currently running, queries for the given database
connection. Returns session IDs, execution times, states, and query text.

Parameters:
- `connectionId` (string, required): Unique connection ID.

## list_schema_object_kinds
Retrieves a list of supported schema object kinds for the given database connection. Supplies
object kind codes and human-readable names.

Parameters:
- `connectionId` (string, required): Unique connection ID.

## list_schema_objects
Retrieves a list of database objects within the given schema. Returns object names and their
classifications by kind.

Parameters:
- `connectionId` (string, required): Unique connection ID.
- `schemaName` (string, required): Schema name.
- `databaseName` (string, required): Database name (empty if not applicable).
- `kind` (string, optional): Object kind code to filter by type.

## preview_table_data
Returns preview data of the table, view, materialized view, or other table-like object using a
given database connection. Displays table content in CSV format with configurable row limits.

Parameters:
- `connectionId` (string, required): Unique connection ID.
- `schemaName` (string, required): Schema name.
- `databaseName` (string, required): Database name (empty if not applicable).
- `tableName` (string, required): Name of table/view.
- `maxRowCount` (integer, optional): Maximum rows to return; default is 100.

## test_database_connection
Returns connection diagnostic info: flag indicating if the connection is problematic, detailed
database information, and connection attempt summary.

Parameters:
- `id` (string, required): Unique connection ID.
