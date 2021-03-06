# SQL vs NoSQL

Created By: Chris Trinh
Last Edited: Jan 17, 2020 4:14 PM

- What is the difference between relational and non-relational databases?
    - Relational have predefined schemas like phone books; store phone numbers and addresses
    - Non-relational are unstructured, distributed, and have dynamic schemas
        - like file folders holding every person's information
- What is SQL?
    - Store datas in rows and columns
    - MySQL, oracle, MS SQL, SQLLite, Postgres, MariaDB
- What are common types of noSQL and what do they do?
    - Key-Value Stores
        - Data is stored in key-value pairs
        - Redis, Voldemort, Dynamo
    - Document DB
        - Data is stored in documents and are grouped together called collections.
            - Each collection can have a different structure
        - CouchDB, MongoDB
    - Wide-Column DB
        - Instead of tables, we have column families (containers for rows)
            - We don't need to know the columns up front and no set number of columns.
        - Best suited for analyzes large datasets
        - Cassandra, HBase
    - Graph DB
        - Store data for relations used in a graph
        - Nodes(entities), properties(information on entities) and lines(connections of entities)
        - Neo4J and InfiniteGraph
- What are some high level differences between SQL and NoSQL?
    - Storage
        - SQL stores data in tables where each row is an entitiy and a column represents a data pint.
        - NoSQL databases have data storage models
    - Schema
        - SQL each record is conformed to a fixed schema
        - NoSQL, record is dynamic and doesn't have colmns
    - Querying
        - SQL uses SQL (structured query language)
        - NoSQL uses UNQL (unstructured query language)
    - Scalability
        - SQL are vertically scalable (higher power servers)
        - NoSQL are horizontal scalable (more servers)
    - Reliability
        - SQL are more reliable
        - NoSQL sacrifices reliability for performance and scalability
- What is ACID Compliancy?
    - Stands for Atomicity, Consistency, Isolation, and Durability
- When to use SQL DB?
    - Ensure ACID compliancy
    - Data is structured and unchanging
- when to use NoSQL DB?
    - Prevents data from being the bottleneck
    - Stores large colume of data with little to no structure
    - Making the most out of cloud computing and storage for savings cost
    - Rapid Development and huge scaling