# 6.2 SQL

---

## 6.2.1 The SQL query language

Okay, so we designed our database with all its tables and columns. Now what? We need a way to:

- **Add** data
- **Read** data
- **Update** data when it changes
- **Delete** data we don't need

Most relational databases do all of this with a language called **SQL** (Structured Query Language). Every time we use SQL to do something in a database, that's called a **query**.

SQL queries are made of **statements**, and like any programming language they follow a defined **syntax**.

### A first query

Say we have a **Movie** table in a Movies database with three columns: `MovieId`, `Title`, and `Year`. To list the title and year of every movie:

```sql
SELECT title, year FROM Movie
```

`SELECT` is a keyword that means "I want to read and display some data." It's the first word, and it sets the goal of the whole query.

### DML vs. DDL

SQL has two main parts:

| Part | Full name | What it's for | Commands |
|---|---|---|---|
| **DML** | Data Manipulation Language | Working with the **data itself** | `SELECT`, `INSERT`, `UPDATE`, `DELETE` |
| **DDL** | Data Definition Language | Creating and maintaining the **schema** (create tables, define structure, set data types for columns) | `CREATE`, `DROP`, and more |

### Quick note

SQL is supported by almost every relational database system (RDBS), so relational databases are often called **"SQL databases."** SQL is a standard, but each RDBS supports its **own set of SQL keywords**. So always check the **documentation** for the one you're using.

---

## 6.2.2 What is SQL?

**SQL** is a programming language that uses **statements** to talk to relational databases. A statement tells the database what we want to do with the data.

With correct statements, you can:

- **Retrieve** data
- **Update** it
- **Delete** it
- **Create** tables
- **Set permissions** on tables

### The most used statement: SELECT

`SELECT` is the most common SQL statement. You need it any time you want to **retrieve data** from one or more tables.

### DDL statements

`CREATE DATABASE` / `CREATE TABLE` and `DROP DATABASE` / `DROP TABLE` are usually used by **database administrators**. They belong to **DDL**. For now, we focus on **DML**.

### Reading a whole table

Once you're connected to a database, you can see everything in a table like this:

```sql
SELECT * FROM patients;
```

- `SELECT` starts the query
- `*` (the asterisk) means **all**
- So it asks the database to return **all the fields (columns)** from the `patients` table

### Handy habits

- **Capitalize SQL keywords** to make queries easier to read. SQL isn't case-sensitive, so lowercase would still run
- **End a query with a semicolon** (`;`)
- Spaces are ignored in SQL, but you'll save yourself frustration if you **avoid spaces in column and table names**

---

## 6.2.4 Using SQL to query data

In real data analysis, we usually want a **specific subset** of a table, not everything.

**Goal:** Get the title and year of only the movies released **after 1976**, ordered **alphabetically by title**.

```sql
SELECT title, year
FROM Movie
WHERE year > 1976
ORDER BY Title ASC;
```

Let's break it down piece by piece.

### SELECT

- It's a "read statement," a command that asks to **read and display** stored data
- It's followed by the **list of columns** we want back. Here that's `title` and `year`

### Selecting all fields

The Movie table has three columns: `movieID`, `title`, and `year`. The query above **won't show `movieID`**.

To get every column, you could list them all, or just use `*`:

```sql
SELECT *
FROM Movie
```

This returns all attributes, including `movieID`.

### FROM

`FROM` says **which table** to get the data from. You can also get data from **more than one table** at a time. That comes later.

### WHERE

The **columns to select** and the **table to select from** are the only **mandatory** parts of a query.

But we usually want some **filtering**, and that's what `WHERE` does. Here we only want movies with a year **later than 1976**. Since year is a number, "later than" becomes "greater than":

```sql
SELECT *
FROM Movie
WHERE year > 1976;
```

You can also combine conditions. For movies released **after 1976 or before 1950**:

```sql
SELECT *
FROM Movie
WHERE year > 1976 OR year < 1950;
```

### ORDER BY

`ORDER BY` controls **how the results are displayed**.

```sql
SELECT *
FROM Movie
WHERE year > 1976
ORDER BY title ASC;
```

`ORDER BY title ASC` sorts by title in **ascending** (alphabetical) order, A to Z.

You can also **limit the number of rows** returned with `LIMIT`. For example, only the first 10 results.

> ⚠️ `LIMIT` works in **some** RDBSs (like **MySQL**) but not in others.

### Query parts at a glance

| Part | What it does | Required? |
|---|---|---|
| `SELECT` | Chooses the columns to show | Yes |
| `FROM` | Chooses the table | Yes |
| `WHERE` | Filters rows | No |
| `ORDER BY` | Sorts the results | No |
| `LIMIT` | Limits how many rows come back (not in every RDBS) | No |

### Operators for WHERE conditions

| Operator | Meaning |
|---|---|
| `=` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `>=` | Greater than or equal to |
| `<` | Less than |
| `<=` | Less than or equal to |
| `BETWEEN` | Within a range of values, from a low value to a high value |
| `LIKE` | Searches for a **pattern** |
| `IN` | Gives **multiple possible values** for a column |
| `AND` | Both conditions must be true |
| `OR` | At least one condition must be true |
| `NOT` | Flips a condition (true becomes false, false becomes true) |

Quick examples:

```sql
-- Movies with titles that start with "Jaws"
SELECT * FROM Movie WHERE title LIKE 'Jaws%';

-- Movies released in one of these years
SELECT * FROM Movie WHERE year IN (1975, 1977, 1980);

-- Movies from 1970 through 1980
SELECT * FROM Movie WHERE year BETWEEN 1970 AND 1980;
```

(The `%` in `LIKE` means "anything can come after." These three examples are mine, to show how each operator looks.)

---

## 6.2.6 Best practices in SQL queries

The labs have you write queries a certain way. There's a reason: these habits make queries easy to read for **people and for systems**. The examples use a hospital's **patients** dataset.

### 1. Pay attention to case

Write SQL **keywords in uppercase** (`SELECT`, `FROM`, `WHERE`) so they stand out from table and column names.

### 2. Use spaces to separate keywords and parameters

```sql
SELECT *     -- good
SELECT*      -- avoid
```

### 3. Use single quotes for text

Text values like `'this is text'` or `'(555) 123-4567'` go in **single quotes**.

Why? Some databases save **double quotes** for identifiers, like table and column names.

### 4. Use aliases to make queries more readable

An **alias** is a **temporary, alternative name** for a column or table. You make one with the **`AS`** keyword.

Say a column is called `ploc`, which means patient location. That's not very clear, so:

```sql
SELECT ploc AS patient_location
FROM patients
ORDER BY patient_location
```

Aliases can also **shorten long names**. Just use them **consistently** so nothing gets confusing.

### 5. Use indentation and new lines

This query is valid:

```sql
select * from Movie where year > 1976 order by title asc limit 10;
```

But this one is easier to read and looks more professional:

```sql
SELECT *
FROM   movie
WHERE year > 1976
ORDER BY title ASC
LIMIT  10;
```

Some organizations have their own formatting standards, so follow those if they exist.

### 6. Add comments where they'll help later

Comments help others (and future you) understand complex queries. Use a **double dash** (`--`) before the comment:

```sql
SELECT *
FROM   movie
WHERE year > 1976
ORDER BY title ASC  -- We want alphabetical order
LIMIT  10;          -- We only need the top 10 for a "Top Ten" list
```

---

## 6.2.9 Using operators in SQL queries

To analyze data, we often need to calculate things from the results. We could dump the data into a spreadsheet and find averages or counts there. But it's **faster to do it in the query** using **operators** that aggregate values.

**Syntax:** the keyword, then the field to work on **inside parentheses**. You can add conditions with `WHERE`.

### Aggregate operators

| Operator | What it outputs |
|---|---|
| `SUM()` | The **sum** of the values in the field |
| `AVG()` | The **average** of the values in the field |
| `COUNT()` | The **number of records** containing the field |
| `MIN()` | The **minimum** value in the field |
| `MAX()` | The **maximum** value in the field |

### Combining operators

You can use several in one statement. Say we want to know how many reviews the movie with ID 123 has, plus its highest and lowest score:

```sql
SELECT COUNT(*),
       MAX(Score),
       MIN(Score)
FROM Review
WHERE MovieId = 123;
```

The `*` inside `COUNT` counts **every row** returned.

### HAVING vs. WHERE

Now say we only want movies with an **average score above 7.0**. For that we use a new keyword, **`HAVING`**.

| | WHERE | HAVING |
|---|---|---|
| Sets conditions on | A **field** (individual rows) | **Groupings** |
| Works with aggregation? | No | **Yes** |

Here we group the data by `MovieId` with `GROUP BY`:

```sql
SELECT MovieId,
       COUNT(*),
       AVG(Score),
       MAX(Score),
       MIN(Score)
FROM Review
GROUP BY MovieId
HAVING AVG(Score) > 7.0
ORDER BY AVG(Score) DESC;
```

### Aliases to clean up the output

Column titles like `AVG(Score)` aren't very friendly. Use `AS` to rename them:

```sql
SELECT MovieId,
       COUNT(*)   AS Number_of_reviews,
       AVG(Score) AS Average_score,
       MAX(Score) AS Max_score,
       MIN(Score) AS Min_score
FROM Review
GROUP BY MovieId
HAVING AVG(Score) < 8.0
ORDER BY Average_score DESC;
```

Now the output makes sense even to someone who doesn't know the data.

---

## Quick takeaways

- **SQL** lets us add, read, update, and delete data. Each time we use it, that's a **query**.
- **DML** (`SELECT`, `INSERT`, `UPDATE`, `DELETE`) works with the **data**. **DDL** (`CREATE`, `DROP`) works with the **schema**.
- `SELECT` and `FROM` are the only required parts. `WHERE` filters, `ORDER BY` sorts, and `LIMIT` caps the rows (not in every RDBS).
- `SELECT *` means all columns.
- Operators like `=`, `>`, `LIKE`, `IN`, `AND`, `OR`, and `NOT` build conditions.
- Best practices: uppercase keywords, spaces between keywords, single quotes for text, aliases with `AS`, indentation, and `--` comments.
- Aggregate operators: `SUM`, `AVG`, `COUNT`, `MIN`, `MAX`.
- `WHERE` filters rows. `HAVING` filters groups. Use `GROUP BY` for grouping.
- Check your RDBS documentation, since each one supports its own SQL keywords.
