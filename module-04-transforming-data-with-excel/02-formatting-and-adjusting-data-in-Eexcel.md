# 4.2 Formatting and Adjusting Data

**Topic objective:** Use data analysis tools and techniques to format and adjust data with Excel.

---

## 4.2.1 Converting data in Excel

Sometimes raw data isn't in the right format for what you need. That's a real problem when you want to import it into other tools for more analysis.

### The situation

We're using the **clothing** subset of the bike sales data. The **product** column lists each item by **name and size** together, separated by a comma.

But the marketing analysis and ordering systems need:

1. The **description** and the **size** in **separate columns**
2. The item names in **all lowercase**

So there are two jobs: split the column, then fix the case.

---

### Job 1: Split one column into two (Text to Columns)

**1. Prep the sheet**

- Hide the columns you won't use (highlight them and choose **Hide**)
- Insert two new columns, **M** and **N**, to hold the results. What you name them doesn't matter yet, since you'll rename them later

**2. Select the product column** you want to split

**3. Open the wizard**

On the **Data** menu, choose **Text to Columns**.

| Wizard step | What to do |
|---|---|
| Step 1 | Excel already picks **Delimited** and shows a preview |
| Step 2 | Choose the delimiter, which is a **comma** here. The preview shows where the columns will break |
| Step 3 | Leave the format on **General**, and set the **Destination** |

The destination is the most important part of step 3. We want the split data to land in the **two new columns**, not on top of the original. Click the **arrow icon** at the end of the destination box to jump back to the sheet, then select the destination columns.

**4. Click Finish**

You'll get a **warning that there's already data** in the destination. That's only because the table headings are sitting there already, so it's fine.

**5. Rename the columns** to **description** and **size**.

---

### Job 2: Change the case

Excel has three case options for text:

| Function | Result |
|---|---|
| **PROPER** | First Letter Of Each Word Capitalized (this is what the descriptions are now) |
| **LOWER** | all lowercase |
| **UPPER** | ALL UPPERCASE |

We want lowercase, so we use the **LOWER** function.

**1.** In the old product column (column **L** in the example), enter `=LOWER(` then click the description cell **M2**, then close the parenthesis. The text shows up in lowercase.

**2.** Apply it to the whole column. Select from **L2 to the end of the data** with `Ctrl+Shift+Down Arrow`, then paste the formula.

**3. Not done yet!** Column L now holds *formulas*, not actual text. We need real lowercase text, so:

- **Copy** the contents of column L
- Use **Paste Special → Values** to paste into column **M**

**4.** Delete column L. We don't need it for analysis anymore.

> 💡 Formula results are tied to the formula. **Paste Special → Values** turns them into plain text you can keep.

---

## 4.2.2 Conditional formatting

**Conditional formatting** automatically changes how cells look (colors, bars, fonts) based on their values. It's a quick way to see **patterns and trends** before doing any bigger analysis.

### The scenario

The bicycle store wants to know which **accessories** are bought more often by buyers **under 35**. The owner wants to focus purchasing and marketing on a younger market.

Before any visualizations or predictions, we take a quick look to make sure the data is **relevant** to what the store needs. This time we're using an **aggregate view** of the bike sales data, already arranged by **country** and **product subcategory**.

### Tool 1: Top/Bottom rules

Question: *What are the top 10 accessories by items sold in France?*

1. Highlight the column
2. On the **Home** menu, click **Conditional Formatting**
3. Choose **Top/Bottom Rules → Top 10 Items**

With a short list you could probably figure out the top 10 by eye. With **hundreds of items**, that's not realistic, and this does it instantly.

### Tool 2: Above or below average

To compare a particular item **across countries**:

1. Clear the earlier formatting
2. Highlight the **row** you want to analyze
3. Choose to highlight cells **above or below the average**

### Tool 3: Data bars

Data bars show values as a **graphic** right inside the cells.

1. Highlight the data
2. Apply **Data Bars** and pick a color

Now it's easy to see which items in each column are bought most often.

You can also **combine** formats. For example, use data bars together with a rule highlighting the **bottom 10 performers**.

### Tool 4: Custom rules and formulas

Next scenario: look at **cost and profit** data for accessory sales. The goal is to highlight the **top 10%** of items by **profitability percentage**.

**Rule 1: Values greater than 1**

1. Highlight the column and click **Conditional Formatting**
2. Choose **Highlight Cells Rules → More Rules**
3. Pick **Format only cells that contain**
4. Set the condition to values **greater than 1**. In this example that means the **cost is less than half the sales price**
5. Set the format to a **blue** cell color

**Rule 2: Top 10 percent**

1. Open **Manage Rules** and click **New Rule**
2. Choose the **Top 10** rule and select the **percentage** option
3. Format cells meeting this rule with a **red font color**

The new rule joins the rule set for that range. Now it's easy to spot items with **more than 100% markup**, which generate the most profit.

> 💡 Conditional formatting is great for **highlighting data points worth investigating further**.

---

## 4.2.3 Combining datasets

Often you need data from **multiple worksheets** to do your analysis. Here we have two worksheets with tables from the bike sales dataset:

| Table | What's in it | How it's arranged |
|---|---|---|
| **Product sales** | Country, product description, quantity sold | Sorted by product. Has **accessories and clothing** |
| **Product profit** | Country, product description, total cost, total profit | Sorted and totaled by **country**. **Accessories only** |

### The goal

Combine them so we can calculate the **profit from the sale of an individual item**. For that, we need the **number of items sold** inside the product profit table. So we add a new column there to receive it.

### Why INDEX/MATCH?

Excel has several ways to combine data, but the two tables aren't arranged in the same format. So we use **INDEX/MATCH**.

The key insight: to combine the data logically, we need to match **both country and product**, because that *combination* uniquely identifies each row. Both sheets are formatted as **tables**, which makes the formula easier to enter.

### Breaking down the formula

The formula looks like this (table and column names here are illustrative):

```
=INDEX(ProductSales, MATCH(1, (ProductSales[Country]=$A3)*(ProductSales[Product]=$B3), 0), 3)
```

| Part | What it does |
|---|---|
| `INDEX(...)` | Returns the value at a given location in a range or array. The range is the **product sales** table, which is where we're pulling info from |
| `MATCH(...)` | Finds *where* in the product sales table the right row is, using the product profit table's values |
| `1` | The lookup value. It just identifies this lookup (a row where both conditions are true) |
| `$A3` | Holds the **country name**, which is matched against the product sales **country** column |
| `*` | Joins the two lookups together, so **both** must match |
| `$B3` | Holds the **product description**, matched against the product sales **product** column |
| `0` | Match type: **exact match** |
| `3` | The **column** in the product sales table that holds the value we want (quantity sold) |

### Match type cheat sheet

| Value | Meaning |
|---|---|
| `0` | Exact match |
| `1` | Largest value that's less than or equal to the lookup value |
| `-1` | Smallest value that's greater than or equal to the lookup value |

### One more thing: Ctrl+Shift+Enter

Because this formula works on a **table array** (a group of related values), the course says to finish it with **`Ctrl+Shift+Enter`** instead of just Enter.

After that, the number of items sold fills in the new column.

> 💡 Other methods, like **lookup functions**, can do the same thing if your data is formatted a certain way. **VLOOKUP** is covered in detail later in the course.

---

## Quick takeaways

- **Text to Columns** (Data menu) splits one column into several. Pick the delimiter, and set the **destination** carefully.
- Excel has three case functions: **PROPER**, **LOWER**, **UPPER**.
- Formulas leave you with formulas, not text. Use **Paste Special → Values** to keep just the results.
- **Conditional formatting** helps you see patterns fast: top/bottom rules, above/below average, data bars, and custom rules.
- Formatting rules can be **combined and managed** in Manage Rules.
- To combine tables that aren't arranged the same way, use **INDEX/MATCH**, and match on every column needed to uniquely identify a row.
- Array formulas are finished with **Ctrl+Shift+Enter**.
