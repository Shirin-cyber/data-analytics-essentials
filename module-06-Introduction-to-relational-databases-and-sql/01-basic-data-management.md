# 6.1 Basic Data Management

**Topic objective:** Explain the basic concepts of databases and data management.

---

## 6.1.1 Introduction to databases

Until now we used spreadsheets to manage and analyze data. But a lot of the time, the data we need actually lives in a **database**, either on our own computer (local) or somewhere else (remote).

### What's a database?

A **database** is a place that stores data in a **defined structure**. They're usually built for a specific purpose. Examples:

- An **employee database** for an HR app
- An **inventory database** for a sales order system

### The building blocks

| Term | What it is | Employee database example |
|---|---|---|
| **Record** | One item, person, or transaction and its characteristics | One employee |
| **Field** | One characteristic stored in a record | First name, last name, address, birthdate, employee number |
| **Table** | A collection of records, like a spreadsheet table with rows and columns | The whole Employee table |

So a table is basically like a spreadsheet: records and fields arranged in rows and columns.

### Schema and metadata

- **Schema:** describes the **design and structure** of the database. That means table names, fields, data types, and how the tables relate to each other
- **Metadata:** data about data. It tells you what's inside the database, like the schema, indexes, views, how big the tables are (in KB or MB), and how many rows there are

### DBMS (Database Management System)

Databases are created and managed with a **DBMS**. In a client-server setup, the DBMS software is often called the **server**.

A DBMS is more than just an app running on a server. It's complex software that:

- Lets users and apps **interact with the data**
- Makes sure many **transactions can happen at the same time** without messing each other up
- Controls the **integrity and security** of the data

### Types of databases

| Type | Example | Notes |
|---|---|---|
| **Flat files** | Excel files | Simple, one file |
| **Relational databases** | SQL Server, MySQL | Connected tables. This is what we use in this module |
| **NoSQL databases** | | Relatively new. They have a **flexible schema** and can scale up the number of fields in a record and the number of records |

In this module we work with **relational databases** and the **SQL** query language. Both are used a lot by data analysts.

---

## 6.1.2 Flat file databases

### A little history

People have been storing data for thousands of years. The oldest cuneiform writing that archaeologists found was often about **accounting**, like how many cows were sold to a farmer or what an army's soldiers were paid.

Methods changed, but for a long time we kept doing the same thing with pen and paper, like a **ledger**.

When computers showed up, we basically copied that. The result: **flat file databases**.

### What's a flat file database?

It's like a ledger, but stored as text inside a table on a computer.

- Info is stored in **rows**, and every row has the same structure
- Each row is called a **record** or **instance**
- **Columns** run top to bottom and hold one type of info. They're called **fields** or **attributes**
- Rows run left to right

A **spreadsheet** is a flat file database. So is a **CSV file** (plain text, where a **delimiter** like a comma separates the values in each row).

### Good for simple data, but...

Flat files work fine for simple data. But with large amounts of **complex** data they get inefficient fast. They're also prone to errors, especially **data inconsistency**.

### The gold miner example

Imagine a general store in the gold rush keeping a flat file of what miners buy:

```
Customer, date, article, cost
Joe "Goldentooth" Smith, 12-23-1897, Cat gut banjo strings, $0.15
Joe "Goldentooth" Smith, 12-31-1897, Bottle of whiskey, $0.75
```

**Problem 1: Redundancy.** Joe's full name has to be written again every time he buys something. Lots of repeated info makes the file inefficient.

**Problem 2: Inconsistency after a change.** Joe loses his golden tooth in a fight, so now he's "Missingtooth":

```
Joe "Missingtooth" Smith, 01-02-1898, Can of soup, $0.05
```

Now the same customer has **two different names** in the file. To fix it, you'd have to find and correct **every old "Goldentooth" entry**.

**Problem 3: Typos.** If someone writes "Bottle of whisky" instead of "whiskey," a search for "whiskey" **misses that entry**.

**Problem 4: Changing the structure.** Say you want to add the customer's address:

```
Customer, address, date, article, cost
Joe "Goldentooth" Smith, Stinky Hut #23, 02-12-1898, Golden tooth, $20.99
```

Adding a column in the middle and filling in the missing values for all the old records would be really hard.

### Flat files: advantages and challenges

| Advantages | Challenges |
|---|---|
| All records are in **one file** | Hard to **change the record structure** |
| **Simple** to set up and use | **Inefficient** for large-scale record keeping |
| Efficient for **smaller businesses and datasets** | More **redundancy** from duplicate records |
| | **Data inconsistencies** are easy to create |

---

## 6.1.3 Limitations of flat files

Once the structure of data gets more complex, a flat file can't store it efficiently. That's where relational databases come in.

---

## 6.1.4 Relational databases

### The movie example

Say we want to store data about movies. A relational database could do it like this:

- A **Movie table** holds the title, year of release, and an **ID number** for each movie
- Other tables hold the other info: one for **actors**, one for **monthly income**, one for **reviews**
- Each of those tables **references the Movie table**

As long as the system can read the references between tables, we can search and find what we need.

That's the whole idea: a **relational database** keeps related types of data in **separate tables**, and the tables can have **relationships** with each other that link everything together.

### What a table looks like

Each table has a **name, columns, and rows**:

- Each **column heading** identifies what's in that column
- Each **row** is a **record**, with the values (attributes) for that record
- The spot where a column and row meet is a **field**
- All fields in a column hold the **same type of data in the same format** (number, text, or date)

**Example: a Person table**

| Column (attribute) | Data type |
|---|---|
| Person_ID | Number |
| Name | Text |
| Last_Name | Text |
| Date_Birth | Date |
| Nationality | Text |

### Two kinds of tables

- **Entity tables** hold things, like **Movie** or **Person**
- **Relationship tables** define connections, like **Movie_Actor** or **Movie_Director**

(We learn how these work later in the course.)

### Schema

Everything about the tables, attributes, relationships, and other parts of the database is written down in the **schema**, a formal description of the database's structure.

The schema is easy to change. With a simple command, you can add a column, add new tables, or delete old ones.

### Why it fixes the flat file problems

A person's info is stored **only once**, then **linked** to the movies they act in or direct. Some people do both, which is why it's smart to have one **People** table instead of separate Actors and Directors tables.

So if something about a person changes, you update it **in one place**. That avoids the **redundancy and inconsistency** problems from flat files.

### Popular, but not perfect

Relational databases are simple, easy to use, and accurate, which makes them the **most popular** database model today. But the **cost, maintenance, and lack of scalability** mean they're not right for every situation.

### RDBS tools

A **Relational Database System (RDBS)** is software for creating relational databases and using them to store and get data. The best-known ones:

- **MySQL**
- **PostgreSQL**
- **Oracle Rdb**
- **Microsoft SQL Server**

### Relational databases: advantages and challenges

| Advantages | Challenges |
|---|---|
| Data is in **interrelated tables**, so complex data is stored efficiently | RDBS software can be **expensive** to set up and maintain |
| More **security** and **accuracy** | You need a **specific skillset** to use it |
| Great for **large data storage** | Can be **slow** with multiple large, complex tables |

---

## 6.1.5 Entity Relationship Diagrams (ERDs)

Flat files like spreadsheets are simple but limited. Relational databases fix some of those problems, mostly by letting tables have **relationships** with each other. The tradeoff is that the structure gets more **complex**.

To understand that complexity, we use an **ERD (entity relationship diagram)**. It shows **how the tables are related** to each other. It's the key to understanding a database.

### The example ERD

The course shows an ERD with three tables: **Content, User, and Rating**. In the diagram, keys are shown as little **key symbols** next to the fields.

### Primary keys

The fields marked with **orange keys** are the **primary keys**.

- A **primary key** uniquely identifies each row in a table
- Every value in it must be **unique**
- It **can't have duplicates or null (empty) values**

### Foreign keys

Fields with **white keys** are **foreign keys**.

- A **foreign key** points to the **primary key of another table**
- Example: `content_id` in the **User** table points to the primary key `content_id` in the **Content** table
- Unlike primary keys, foreign keys **can have duplicates** (and usually do)

### Why keys matter

Both are essential for keeping the database **accurate and consistent** (called **integrity**), and you need them when **joining** fields from different tables into one.

| | Primary key | Foreign key |
|---|---|---|
| What it does | Uniquely identifies each row in its own table | Links to the primary key in another table |
| Duplicates? | **No** | **Yes**, usually |
| Empty values? | **No** | Depends on the design |

---

## Quick takeaways

- A **database** stores data in a defined structure. It's made of **tables, records, and fields**.
- The **schema** describes the structure. **Metadata** is data about data. A **DBMS** manages the database.
- Three database types: **flat file**, **relational**, and **NoSQL**.
- **Flat files** are simple but get redundant, inconsistent, and hard to change as data gets bigger.
- **Relational databases** split data into linked tables, so each piece of info is stored **once**.
- Entity tables hold things (Movie, Person). Relationship tables link them (Movie_Actor).
- Common RDBS tools: **MySQL, PostgreSQL, Oracle Rdb, SQL Server**.
- **ERDs** show how tables relate.
- A **primary key** is unique per row, no duplicates, no nulls. A **foreign key** points to another table's primary key and can repeat.
