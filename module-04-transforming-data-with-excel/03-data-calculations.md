# 4.3 Data Calculations

**Topic objective:** Use Excel techniques to perform data calculations.

---

## 4.3.1 Handy functions for data work

So far we've used Excel's built-in tools to clean and organize data. But there are also a bunch of functions you can type into the **formula bar** that data professionals use all the time. Here are the main ones.

### Text functions

**CONCATENATE** combines data from one or more columns into a single column. It's basically the **opposite of Text to Columns**, which split one column into two.

Example: you have a **Category** column and a **Product** column and want one column with both. Put a dash in quotes between them to separate the two:

```
=CONCATENATE(A2," - ",B2)
```

**LEN** returns the **number of characters** in a cell. It's useful when the data has to go into another application that limits field sizes.

**LEFT** and **RIGHT** grab the **first or last X characters** of a cell. They're handy for pulling out:

- An area code from a list of phone numbers
- A month abbreviation
- A two-letter state code from an address

### Counting functions (great for cleaning data)

| Function | What it returns |
|---|---|
| **COUNT** | Number of **numeric** cells in a range. Useful if you're not sure everything in a column is formatted as a number |
| **COUNTBLANK** | Number of **blank** cells in a range |
| **COUNTA** | Number of **non-blank** cells in a range |
| **COUNTIF** | Number of cells that meet a **specific criteria** |

### Functions with criteria

Many basic functions get more powerful when you add criteria.

| Function | What it does |
|---|---|
| **SUMIF** | Sums values based on one criteria (for example, customer age) |
| **SUMIFS** | Sums values based on **multiple** criteria |
| **AVERAGEIFS** | Averages values only if the cells meet the criteria in the formula |
| **MINIFS / MAXIFS** | Finds the minimum or maximum value that meets the criteria |

A nice thing to know: as Microsoft updates Excel, a lot of the new features are about automating, formatting, and doing things that used to need **complex manual formulas**. So keep exploring the functions and try them on real data. There's a complete list of Excel functions on the Microsoft support page.

---

## 4.3.2 Formulas and functions

### What's the difference?

| | Function | Formula |
|---|---|---|
| What is it | Predefined by Excel, uses a **keyword** | Built by **you** using operators |
| Example | `=AVERAGE(L2:L37)` | `=L1/L7` |

Both follow **strict rules**, so it's a good idea to **plan out your calculation** before typing it into the spreadsheet.

### The basics

**Every Excel formula starts with an equals sign (`=`).**

The `=` tells Excel the cell holds a **calculation**, not text or a plain number. That way you see the **result** instead of the formula itself.

Example: type `=1+2` and the cell shows **3**. Without the equals sign, it would just show the text `1+2`.

---

### Relative vs. absolute references

You can do calculations on a **constant** (like the number 5) or on data in a **specific location** (a cell or a range of cells). For example, `=L1/L7` divides the value in L1 by the value in L7.

References come in two types:

| Type | How it behaves |
|---|---|
| **Relative** | Changes depending on **where the formula is** |
| **Absolute** | Always points to the **same cell or range**, no matter where it's pasted |

**Relative is the default.** If you copy a formula down to the rows below it, it automatically uses the values from those lower rows. That's what happened when you copied and pasted formulas down in the Manipulate Data lab.

**To make a reference absolute**, add a dollar sign (`$`) before the column and/or row indicator.

| Written as | Meaning |
|---|---|
| `=L1/L7` | Both references are **relative** |
| `=$L$1/$L$7` | Both references are **absolute**. Always uses L1 and L7 |

The column and row parts work **independently**, so you can put the `$` on **only the column** or **only the row** too.

---

### Using built-in functions

Built-in functions start with a **keyword** that names the calculation. Most keywords describe what the function does, and the syntax is usually similar.

Example with AVERAGE, which accepts a range or a list of cells:

```
=AVERAGE(L2:L37)
=AVERAGE(L2, L5, L6)
```

> ⚠️ **Close all your parentheses and brackets.** If you don't, Excel gives you an error when you press Enter. In long functions this is easy to mess up.

**Finding a function:**

- Start a cell with `=` and begin typing the function name. A menu of matching functions usually appears, with a short description of each
- If it doesn't show up automatically, **right-click a cell** and type `=` in the text box that says **"Search the menus"**
- Picking a function puts its name and an open parenthesis in the formula bar and the cell

---

### Common errors

| Error | What caused it |
|---|---|
| `#NULL!` | The cell range in the formula was entered incorrectly (for example, two ranges that don't actually overlap) |
| `#DIV/0!` | The formula is trying to **divide by zero** |
| `#VALUE!` | The formula uses the wrong type of data, like text where a number is needed |
| `#REF!` | The formula refers to a cell that's **no longer valid** (for example, it was deleted) |
| `#NAME?` | Excel doesn't recognize something in the formula, like a **misspelled function name** |
| `#NUM!` | A problem with a **number** in the formula, such as one that's invalid or too big |
| `#N/A` | The value being looked up **can't be found** |
| `#####` | The column is **too narrow** to show the value |

---

## 4.3.5 Creating charts in Excel

Making a chart in Excel is pretty straightforward: pick your data, go to the **Insert** tab, and choose a chart type.

### Example: top 10 movies by budget

1. **Sort** the budget field in **descending** order
2. Select the **top 10 budgets** and their **10 movie titles**
3. Click the **Insert** tab
4. Look at the options in the **Charts** toolbar. Hovering over a chart type shows info about it
5. Click the **dropdown arrow** next to a chart type to see its subcategories
6. Choose a **2-D column chart**

Now you have a basic column chart. Time to customize it.

### The three chart buttons

Click inside the chart area and three buttons show up on the right:

| Button | Icon | What it does |
|---|---|---|
| **Chart Elements** | Plus sign (+) | Add or edit elements like the title, legend, grid lines, and data labels |
| **Chart Styles** | Paintbrush | Set a style and color scheme |
| **Chart Filters** | Funnel | Choose which data points are visible |

### Customizing the example

- **Title:** Click the chart title and change it to **"Top 10 Movies by Budget"**
- **Axis titles:** Click the chart, click **Chart Elements (+)**, and check **Axis Titles**. Then set the vertical axis title to **movie budget** and the horizontal axis title to **movie title**
- **Size:** Resize the chart so it's easier to read

---

## 4.3.6 Pivot tables

**Pivot tables** are one of the most useful tools for data analysts. They let you automatically **summarize, analyze, explore, and present** data. **Pivot charts** add visualizations to the data in a pivot table.

With them you can:

- Spot trends
- Compare data items
- Create charts in different styles

### Steps to create a pivot table

1. **Start with a worksheet** organized in columns and rows, with **column headers**.
2. **Select the table or range** you want to include. Make sure the **column headers** are included.
3. Go to the **Insert** menu. In the **Tables** section, try **Recommended PivotTables** to see different formats for your data. If none fit, choose **PivotTable → From Table or Range**.
4. In the **Create PivotTable** dialog box, your range shows in the **Table/Range** box and **New Worksheet** should be selected. For your first pivot tables, it's best to put them on a new worksheet tab.
5. A **blank PivotTable worksheet** appears with the **PivotTable Fields** list (your column headings). Click the fields you want to add.
6. Your fields land in one of four boxes at the bottom: **Filters, Columns, Rows, and Values**. **Drag and drop** fields between them to change how the pivot table summarizes your data.
7. The pivot table appears with your selections. Most things you can do in a normal spreadsheet work here too, like **sorting, filtering, and cell formatting**.

> ⚠️ **Updating the original data does NOT update the pivot table automatically.** You have to **refresh** the pivot table to see the new data.

---

## Quick takeaways

- **CONCATENATE** joins columns together. It's the opposite of Text to Columns.
- **LEN** counts characters. **LEFT** and **RIGHT** pull out the first or last characters.
- **COUNT, COUNTBLANK, COUNTA, and COUNTIF** are great for checking data while cleaning it.
- Add criteria with **SUMIF(S), AVERAGEIFS, MINIFS, and MAXIFS**.
- Functions are **predefined** by Excel. Formulas are **custom** built with operators.
- Every formula starts with **`=`**.
- **Relative** references change when you copy a formula. **Absolute** references (`$L$1`) don't.
- Always **close your parentheses**, and learn to read the common errors.
- Charts: select data, go to the **Insert** tab, pick a type, then customize with the three chart buttons.
- **Pivot tables** summarize and explore data, and you have to **refresh** them after the source data changes.
