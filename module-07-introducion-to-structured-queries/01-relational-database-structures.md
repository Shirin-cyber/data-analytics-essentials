# 7.1 Relational Database Structures

**Topic objective:** Explain the structure of relational databases.

---

## 7.1.1 The database schema

The superpower of relational databases is that they store data in **different but related tables**. That way we avoid a lot of **redundancy** and **mismatched data**.

### Back to the Movies database

Quick reminder of what's in it:

- A table for **movies**
- A table for **people** (who can be actors or directors)
- Tables that define the **relationship** between people and movies
- More tables for **gross income** and **reviews**

With basic SQL, it's easy to query one table. For example:

- The list of all the people from **Spain**
- All the movies from **1984**

But what about these?

- The **nationalities of the actors** in a specific movie
- The **directors of movies** whose reviews average **higher than 9**

Those need data from **several tables at once**. The data we need for analysis usually isn't all in one table. So we have to **combine related data from multiple tables**.

And to do that, we first have to understand the database's **schema**. It tells us what data exists and how it's organized.

### What's a schema?

A **database schema** is the definition of **how data is organized** inside the tables of a database.

A schema is built from these pieces:

| Piece | What it is |
|---|---|
| **Table** | Data in rows and columns, like a spreadsheet. Each **row** is a unique record, and each **column** is a field |
| **Field** | One attribute of a record. Field names are the **column headings** |
| **Record** | One row in a table. A collection of related attributes about one item |

But the schema does more than describe fields and records. It also defines:

- The **record keys** (next section)
- The **relationships between tables**
- The **data types** of the fields in each table

---

## 7.1.2 Keys

Since data is spread across tables, **relationships between tables** let us put it back together whenever we need it.

### Example: the Gross Income table

This table holds the **gross income for each movie, in each month, of each year**.

Here's the problem: we can't repeat all the movie info in every Gross Income row. But we still need to know **which movie** each row is about.

The solution: **MovieId**.

- In the **Movie** table, every movie has a **unique MovieId**. Two movies can't share one
- That makes MovieId the **primary key** of the Movie table
- In the **Gross Income** table, MovieId is used to **point to the movie** each row is about
- When a column in one table uses the **primary key of another table** to point to a specific record, it's called a **foreign key**

### Formal definitions

| Key | Definition |
|---|---|
| **Primary Key (PK)** | A field (column) in a table with a **unique identifier for each record**. It can also be a **combination of multiple columns** |
| **Foreign Key (FK)** | A column, or combination of columns, in a table that **matches the primary key of another table** |

### Keys can be a combination of columns

In the Gross Income table, there's a different row for each movie, for each month, of each year. So the **same MovieId shows up many times**.

Here's an illustration (my own sample data):

| MovieId | Month | Year | Amount |
|---|---|---|---|
| 101 | 1 | 2020 | 500000 |
| 101 | 2 | 2020 | 300000 |
| 101 | 1 | 2021 | 100000 |
| 102 | 1 | 2020 | 700000 |

MovieId alone repeats. But the **combination of `MovieId`, `Month`, and `Year`** is unique for every row. So that combination of three columns is the **primary key** of the Gross Income table. This kind of key is called a **composite key**.

### Building a new table on top of it

Now say we want gross income **by country**, for each movie, month, and year. We make a new table, `Gross_Income_Country`:

- The Gross Income primary key (the three columns) becomes a **foreign key** in this new table
- Add a column for **Country**
- Add a column for **Amount**

Does this new table need its own primary key? Yes. We ask: what combination of columns makes each row unique? Here it's:

**`MovieId`, `Month`, `Year`, and `Country`**

---

## 7.1.3 Database relationships

Tables can be related in three different ways.

### One-to-Many

- A single movie has **multiple Gross Income rows** (one for each month)
- A Gross Income row has **multiple Gross_Income_Country rows** (one per country in that month)
- But each Gross Income row points to **only one movie**

### Many-to-Many

- Look at the **Movie** and **Movie_Actor** tables
- A movie can have **many actors**
- An actor can be in **many movies**

### One-to-One

- Movies need money, usually from a **loan**. Say we add a table for **movie loans**
- For this example, a movie can have **only one loan**, and a loan can apply to **only one movie**

### Definitions

| Relationship | What it means |
|---|---|
| **One to Many** | A record in one table can relate to **multiple records** in the second table. But a record in the second table can only relate to **one** record in the first |
| **One to One** | A record in one table can relate to only **one record** in the second table, and the other way around |
| **Many to Many** | **Multiple records** in one table can relate to **multiple records** in the other |

---

## 7.1.4 Data types

A **data type** describes the **format of the data** in a column. Here are the most common ones. More might be available, depending on the database server.

| Data type | What it is |
|---|---|
| **CHAR(size)** | Short for "character size." A **fixed-length** string that can have numbers, letters, or special characters in any mix. The max length is usually **255** characters |
| **VARCHAR(size)** | Short for "variable character size." A **variable-length** string with numbers, letters, or special characters, up to a maximum length (for example, **65,535** characters) |
| **TEXT** | A string usually used for **long-form text** |
| **INT** | Short for "integer." A number field that can only hold **positive or negative whole numbers** |
| **DECIMAL** | A number field with an **exact, fixed-point** (decimal) number |
| **FLOAT** | A number field with a **floating-point** number |
| **DATETIME** | A **date and time** combined. It comes in many standard formats. Example: `YYYY-MM-DD hh:mm:ss` |

---

## Quick takeaways

- Relational databases store data in **related tables** to avoid redundancy and mismatched data.
- To combine data from multiple tables, you first need to understand the **schema**: tables, fields, records, keys, relationships, and data types.
- A **primary key** uniquely identifies each record. It can be a **combination of columns**.
- A **foreign key** points to the primary key of another table.
- Three relationship types: **one-to-many**, **many-to-many**, and **one-to-one**.
- Data types describe the format of a column: **CHAR, VARCHAR, TEXT, INT, DECIMAL, FLOAT, DATETIME**.
