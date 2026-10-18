# 3.4 Data Preparation

---

## 3.4.1 Why data needs prep

Data is easier to get than ever. It sits in databases, websites, cloud storage, and analytic tools, and it can even stream straight from devices to the analysis processor.

The catch: all that data isn't collected the same way or in the same format. That makes it hard to combine and trust, especially when you need answers fast to make better decisions.

Also, data usually can't be used as-is. Sometimes extra stuff gets collected that you don't need. So it has to be **cleaned**.

### What does cleaning actually involve?

- Removing **unwanted** data
- Fixing **incorrect** data
- Filling in **missing** data

You do this by searching for certain criteria (or the lack of it) and working on the data until no more anomalies are left. After that, it can be analyzed and visualized.

### Transforming data

When data gets pulled out of its original source, it usually has to be **transformed** too. Common transformations:

- Putting date and time fields into the **same format**
- **Summing** numerical data and finding the max and min values
- Removing **empty or error** records
- Identifying **location data** and turning it into coordinates, countries, zip codes, or other identifiers

Once it's cleaned and transformed, it's ready for analysis.

---

## 3.4.3 ETL and ELT

**ETL** and **ELT** are two versions of the same process for moving data through a pipeline. The steps are the same, just in a different order for different situations.

| | ETL | ELT |
|---|---|---|
| Order | Extract → **Transform** → Load | Extract → Load → **Transform** |
| When does transformation happen? | Before loading into the database | After loading, as the data gets used |
| Where does the data go? | A database, already cleaned up | Straight to storage in raw, unstructured form |
| Best for | Mixed sources that need to be combined | Large amounts of unstructured data |

### Why ETL exists

One company's data might be spread across Word docs, spreadsheets, plain text, PowerPoints, emails, and PDFs. Another company might keep everything in relational databases. All those formats make it hard to combine and analyze, so ETL transforms the data **before** loading.

### Why ELT exists

With ELT, raw data skips the transformation step and goes straight into storage. The transformation happens later on the stored data when it's needed.

---

### Step 1: Extract

Find and gather data from different sources so it can be converted into **one single format** for analysis.

Sources might include:

- Relational databases
- NoSQL
- Flat files
- XML files
- Other formats

### Step 2: Transform

Data usually has to be transformed before it goes into a **data warehouse**. This step uses **rules** to convert the source data into the type the target database needs.

Tasks in this step:

- Converting measurements to the same dimension (for example, **Imperial to Metric**)
- **Joining** data from several sources
- **Aggregating** and **sorting**
- Calculating **new values** from aggregated data
- Applying **validation rules**

**Cleaning (scrubbing) is part of this step.** Data that might contain empty or error records goes through cleaning, and validation tells you whether it needs cleaning. Examples:

- Removing blank records
- Standardizing formats like date, time, and location

This makes the source data **consistent**.

### Step 3: Load

The transformed data goes into the database so it can be queried.

- How the load works varies a lot, depending on the source data, the target database, and the kind of querying you'll do
- Some organizations **overwrite** existing data with newer cumulative data
- During loading, rules in the **database schema** get applied. They check things like:
  - **Uniqueness** of data
  - **Consistency** of data
  - That **mandatory fields** aren't empty

These rules help make sure the load, and any querying afterward, actually works.

---

## 3.4.5 Cleaning data (with Excel)

Before analysis, data has to be cleaned. That means removing or updating information that is:

- Incomplete
- Incorrect
- Improperly formatted
- Duplicated
- Irrelevant

Cleaning data in **Excel** is a key skill for data analysts, and Excel has built-in functions for it.

### Walkthrough

For this walkthrough, imagine a sales dataset saved as a **CSV file** (columns like product, quantity, and cost).

**1. Load the CSV into Excel**

- A CSV is just a text file with a delimiter between fields and each row on its own line
- Excel usually detects the delimiter and puts each field in its own column
- It **doesn't** auto-adjust column widths, so highlight the columns and expand them to see everything
- The first row usually holds the **column headings**

**2. Remove duplicate rows**

- Use Excel's remove duplicates function (on the **Data** tab)
- Select all columns, since we want to compare entire rows
- Check the box **"My data has headers"** so the header row isn't treated as data
- In the course example, Excel found and removed **518 duplicate rows**

**3. Delete blank rows**

- Use **Find & Select → Go To Special**
- Choose **Blanks** from the list
- Excel highlights all the blank cells, and then you can delete those rows

**4. Remove rows with obvious errors**

Rows with clearly wrong values can skew your analysis or mess up your visualization.

Example: in a sales dataset, no sold item should have a **cost of zero**. To find them:

- Select the **cost column**
- Open **Find & Select** and enter `0` in the **Find what** field
- Turn on **Match entire cell contents** so you only get cells that are exactly zero
- Click **Find All** to see every match
- Press `Ctrl+A` to select all the found cells
- Right-click a selected cell and choose **Delete**
- In the delete box, choose **Entire row** and click **OK**

All the zero-cost rows are gone.

> 💡 If you know the correct cost for a product, you can use **Find and Replace** to fix the value instead of deleting the row.

The course's advice: practice with Excel and different datasets to get better at cleaning data.

---

## Quick takeaways for this part

- Data from different sources comes in different formats, so it has to be **cleaned and transformed** before analysis.
- Cleaning = remove unwanted data, fix incorrect data, fill in missing data.
- **ETL**: Extract → Transform → Load. **ELT**: Extract → Load → Transform.
- ELT is mostly used for **large amounts of unstructured data**.
- The **Transform** step includes joining, aggregating, sorting, validating, and cleaning.
- The **Load** step applies schema rules (uniqueness, consistency, mandatory fields).
- In Excel: remove duplicates (with "My data has headers" checked), delete blanks with Go To Special, and find and delete obvious errors like zero costs.
