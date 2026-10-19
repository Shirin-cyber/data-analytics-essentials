# Module 4 Wrap-Up: Analyzing Data with Excel

Step 4 of the Data Analytics Process is **preparing data for analysis**. In this module we used Excel to do it: sort, filter, clean, reformat, calculate, and summarize.

---

## The big picture

Here's how the three topics connect:

1. **Sort and filter (4.1):** Get the data in order and use filters to spot problems like blanks, duplicate spellings, and shifted rows.
2. **Format and adjust (4.2):** Fix how the data looks and is structured: split columns, change text case, highlight patterns, and combine tables from different sheets.
3. **Calculate (4.3):** Use functions and formulas to work with the data, then summarize it with charts and pivot tables.

The common thread: raw data almost never comes ready to use. Excel gives you the tools to clean it and shape it so the analysis and visualizations you build later are actually correct.

---

## Key terms

| Term | Quick meaning |
|---|---|
| Sort | Put data in order (ascending or descending) by one or more columns |
| Multi-level sort | Sort by one column first, then break ties with another column |
| Custom List | A custom sort order, like January to December instead of alphabetical |
| Filter | Show only the data that meets requirements you set |
| Table (Format as Table) | An Excel table with a name and filter dropdowns on each column header |
| Auto-fill | Drag the small square in a cell's corner to copy its value down a column |
| Text to Columns | Wizard that splits one column into several using a delimiter |
| PROPER / LOWER / UPPER | Functions that change the case of text |
| Paste Special → Values | Pastes the result of a formula as plain values instead of the formula |
| Conditional formatting | Rules that change how cells look based on their values |
| Data bars | Conditional formatting that shows values as bars inside the cells |
| INDEX/MATCH | A way to look up and combine data from tables that aren't arranged the same way |
| CONCATENATE | Joins data from multiple columns into one |
| LEN / LEFT / RIGHT | Count characters, or grab the first or last characters of text |
| COUNT / COUNTBLANK / COUNTA / COUNTIF | Counting functions for checking data quality |
| SUMIF(S) / AVERAGEIFS / MINIFS / MAXIFS | Calculations that only include cells meeting your criteria |
| Function vs. formula | A function is predefined by Excel. A formula is one you build yourself |
| Relative reference | Cell reference that shifts when a formula is copied |
| Absolute reference | Cell reference locked with `$` (like `$L$1`) so it never shifts |
| Chart Elements / Styles / Filters | The three buttons for customizing a chart |
| Pivot table | Tool that automatically summarizes, analyzes, explores, and presents data |
| Pivot chart | A visualization built from the data in a pivot table |
| Refresh | Updating a pivot table after the original data changes |

---

## Summary

### Sorting and filtering (4.1)

- Sorting works on one or more columns. Select all the data first and check **"My data has headers."**
- Use a **Custom List** to sort months in calendar order.
- Convert data to a **table** before filtering. Table names can't have spaces.
- Filter dropdowns reveal anomalies like **blanks, inconsistent names, and wrong values**.
- Fix problems with deleting filtered blank rows, **auto-fill**, **Find & Replace**, or moving shifted cells.

### Formatting and adjusting (4.2)

- **Text to Columns** splits a column. Set the destination carefully.
- **LOWER, UPPER, and PROPER** change text case. Use **Paste Special → Values** to keep results as plain text.
- **Conditional formatting** helps you see patterns fast: top/bottom rules, above/below average, data bars, and custom rules.
- **INDEX/MATCH** combines tables that aren't arranged the same way. Match on every column needed to uniquely identify a row.

### Data calculations (4.3)

- Handy functions: **CONCATENATE, LEN, LEFT, RIGHT**, plus counting and criteria functions.
- Every formula starts with **`=`**. Use **absolute references** (`$`) when a reference shouldn't shift.
- Know the common errors: `#DIV/0!`, `#N/A`, `#REF`, `#NAME`, `#VALUE`, `#NUM`, `#NULL`.
- Build charts from the **Insert** tab and customize them with the three chart buttons.
- **Pivot tables** summarize data quickly. Remember to **refresh** them after the source data changes.
