# Module 6 Wrap-Up: Introduction to Relational Databases and SQL

We use databases all the time, even without noticing. This module covered how relational databases are built, and how to ask them questions using SQL.

---

## The big picture

Here's how the two topics connect:

1. **Basic data management (6.1):** Understand where the data lives. Flat files are simple but get messy. Relational databases split data into linked tables, so each piece of info is stored once.
2. **SQL (6.2):** Learn the language to get data out of those tables. Pick the columns, choose the table, filter, sort, and calculate.

The common thread: the database's structure (tables, keys, relationships) is what makes SQL queries possible. Good structure means clean data, and SQL lets you pull exactly what you need.

---

## Key terms

| Term | Quick meaning |
|---|---|
| Database | A place that stores data in a defined structure |
| Record | One item, person, or transaction and its characteristics (a row) |
| Field | One characteristic stored in a record (a column value) |
| Table | A collection of records arranged in rows and columns |
| Schema | The design and structure of a database |
| Metadata | Data about data (schema, indexes, views, table sizes, row counts) |
| DBMS | Software that creates and manages databases |
| Flat file database | Data in one file, in rows with the same structure (like a spreadsheet or CSV) |
| Data inconsistency | The same info stored in different ways in different places |
| Relational database | Data kept in separate, linked tables |
| RDBS | Software for creating and using relational databases (MySQL, PostgreSQL, Oracle Rdb, SQL Server) |
| NoSQL database | Newer type of database with a flexible schema |
| ERD | Entity relationship diagram, showing how tables relate |
| Primary key | Uniquely identifies each row in a table. No duplicates or nulls |
| Foreign key | Points to a primary key in another table. Can have duplicates |
| SQL | Structured Query Language, used to talk to relational databases |
| Query | Any time we use SQL to do something in a database |
| DML | Data Manipulation Language: `SELECT`, `INSERT`, `UPDATE`, `DELETE` |
| DDL | Data Definition Language: creates and maintains the schema (`CREATE`, `DROP`) |
| `SELECT` / `FROM` | Choose the columns to read and the table to read them from |
| `WHERE` | Filters rows |
| `ORDER BY` | Sorts the results (`ASC` or `DESC`) |
| `LIMIT` | Caps how many rows come back (not in every RDBS) |
| Alias | A temporary name for a column or table, made with `AS` |
| Aggregate operators | `SUM`, `AVG`, `COUNT`, `MIN`, `MAX` |
| `GROUP BY` / `HAVING` | Group results, and filter those groups |

---

## Summary

### Basic data management (6.1)

- A **database** holds data in a defined structure: **tables** made of **records** and **fields**.
- The **schema** describes the structure, **metadata** is data about data, and a **DBMS** manages it all.
- **Flat files** are simple but cause **redundancy, inconsistency**, and trouble when the structure changes.
- **Relational databases** store data in **linked tables**, so each piece of info lives in one place.
- **Entity tables** hold things (Movie, Person). **Relationship tables** link them (Movie_Actor).
- Relational databases are popular, but they can be **expensive, need special skills**, and slow down with big complex tables.
- **ERDs** show how tables relate. **Primary keys** are unique per row. **Foreign keys** point to other tables' primary keys.

### SQL (6.2)

- **DML** works with the data. **DDL** works with the schema.
- The only required parts of a query are **`SELECT`** and **`FROM`**.
- **`WHERE`** filters, **`ORDER BY`** sorts, and operators like `=`, `>`, `LIKE`, `IN`, `AND`, `OR`, `NOT` build conditions.
- **Best practices:** uppercase keywords, spaces between keywords, single quotes for text, aliases with `AS`, indentation, and `--` comments.
- **Aggregate operators** do calculations right in the query. **`WHERE`** filters rows, **`HAVING`** filters groups, and **`GROUP BY`** creates the groups.
- Each RDBS has its own SQL keywords, so check the documentation.
