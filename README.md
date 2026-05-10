# adwm-adb-rep

Adventure Works medallion project organized under `/Users/sharif.sk@zohomail.in/adwm-adb-rep`.

The project root now contains:

* `setup`
* `metadata`
* `bronze`
* `silver`
* `gold`
* `README.md`

Project hierarchy:

* `setup`
  * `catalog_objects`
  * `import_libraries`
* `metadata`
  * `control_table`
  * `schema_registry`
* `bronze`
  * `bronze_data_process`
* `silver`
  * `silver_data_process`
* `gold/dimensions`
  * `dimensions_ddl`
  * `DimCustomer`
  * `DimEmployee`
  * `DimProduct`
* `gold/facts`
  * `facts_ddl`
  * `FactSales`

Recommended execution order:

1. `setup/catalog_objects`
2. `setup/import_libraries`
3. `metadata/schema_registry`
4. `metadata/control_table`
5. `bronze/bronze_data_process`
6. `silver/silver_data_process`
7. `gold/dimensions/dimensions_ddl`
8. `gold/dimensions/DimCustomer`
9. `gold/dimensions/DimEmployee`
10. `gold/dimensions/DimProduct`
11. `gold/facts/facts_ddl`
12. `gold/facts/FactSales`

Execution notes:

* Run `catalog_objects` first to create or validate the required catalog and schema objects.
* Run `import_libraries`, `schema_registry`, and `control_table` before starting any data processing notebooks.
* Run the medallion layers in order: bronze first, then silver, then gold.
* Run `dimensions_ddl` before loading any dimension tables.
* Complete all dimension loads before running `facts_ddl` and `FactSales`.

Notes:

* Root-level duplicate notebooks were removed after the folder hierarchy was created.
* Project notebooks have been cleaned and standardized to keep only operational SQL, Python, DDL, `%run` logic, schema definitions, and concise durable markdown.
* Notebooks are organized by setup, metadata, bronze, silver, and gold responsibilities to keep the project easier to navigate and maintain.
