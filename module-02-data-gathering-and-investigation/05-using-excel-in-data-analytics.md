# Using Excel in Data Analytics

Excel is one of those tools that might look simple at first, but it can do quite a lot when you're working with data. You don't always need complicated software to get started with analysis. Sometimes, a spreadsheet is enough to help you understand what's happening in a dataset.

## What can Excel do?

Excel is useful for several tasks in data analytics, including:

- **Cleaning data:** Finding and fixing errors or inconsistencies in a dataset.
- **Sorting and filtering:** Arranging data in a particular order or displaying only the records you need.
- **Using formulas and functions:** Performing calculations without doing everything manually.
- **Conditional formatting:** Highlighting cells based on certain rules, making important values easier to spot.
- **Creating charts:** Turning numbers into visuals that are easier to understand.
- **Using PivotTables:** Summarizing and exploring larger datasets by grouping information and comparing values.
- **Aggregating data:** Combining values to calculate things like totals, averages, and counts.

## Understanding workbooks and worksheets

An Excel file is called a **workbook**. Inside a workbook, you can have one or more **worksheets**, which are the individual spreadsheet pages.

A worksheet is made up of rows and columns. Rows run horizontally and are numbered, while columns run vertically and are labelled with letters. The box where a row and column meet is called a **cell**.

An Excel worksheet supports up to:

- **1,048,576 rows**
- **16,384 columns** (up to column XFD)

Each cell can hold data such as text, numbers, dates, or formulas.

## A few Excel functions worth knowing

Functions make calculations much easier, especially when a dataset has lots of rows.

| Function | What it does |
|---|---|
| `SUM()` | Adds values together |
| `AVERAGE()` | Calculates the mean |
| `COUNT()` | Counts cells containing numbers |
| `MAX()` | Finds the largest value |
| `MIN()` | Finds the smallest value |

For example, if a column contains marks scored by students, `AVERAGE()` can calculate the average mark without you having to add everything up yourself.

## Importing data into Excel

Data doesn't always begin inside an Excel spreadsheet. You might receive it as a CSV file and need to import it before you can work with it.

When importing a CSV file, pay attention to the **delimiter**. A delimiter is the character used to separate values in the file. A comma is common, but other characters, such as semicolons or tabs, can also be used.

If Excel puts all the information into one column instead of separating it properly, the delimiter settings may need to be checked.

Regional settings can also affect how Excel interprets dates and numbers. For example, date formats and decimal separators can differ between regions. During the course lab, changing the Windows regional format to English (United States) was one suggested way to address these issues. However, depending on your Excel version and the file, using **Data → From Text/CSV** and checking the import settings may be enough without changing your computer's regional settings.

## My main takeaway

Excel isn't just for storing information. It can help you clean, organize, calculate, summarize, and visualize data. Learning these basics gives you a useful starting point before moving on to more advanced analysis tools.
