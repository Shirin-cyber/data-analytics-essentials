# 4.1 Sorting and Filtering Data with Excel

**Topic objective:** Use data analysis tools and techniques to sort and filter data with Excel.

---

## 4.1.1 Organizing data with sorting and filtering

Before analysis, you often need to **sort** and/or **filter** your data. Sometimes it's to prepare it, and sometimes it's to show specific important data. Excel has simple built-in options for both.

| Feature | What it does |
|---|---|
| **Sort** | Puts data in order within columns, either ascending or descending. Can work on one column or several |
| **Filter** | Shows only the data that meets requirements you define |

Using both together is a quick way to organize data and spot **anomalies** (weird stuff that doesn't look right).

---

## The example dataset

The walkthrough uses a **bicycle sales** dataset (the course data, which I'm describing from the walkthrough):

- Columns **A through R**
- Has a **header row**
- Already sorted by the **category** column

Goal: see the data sorted by **country** and then by **month of the year**.

---

## Part 1: Multi-level sort

**1. Select all the data**

Use the select all shortcut (`Ctrl+A`). We want *every* column sorted together, so rows don't get scrambled.

**2. Open the Sort function**

- Go to the **Sort** function
- Check **"My data has headers"** if Excel doesn't detect it automatically

**3. First level: country**

- Pick the **country** column
- Choose the standard **alphabetical** order (A to Z)

**4. Second level: month**

- Click **Add** to add another level
- Pick the **month** column

Here's the catch: if you sort months alphabetically, **April** shows up first, and that's not how a calendar works. So instead:

- Under Order, select **Custom List**
- The data uses full month names (not abbreviations), so pick the **January, February, March...** list from the dropdown

Now the data is sorted by country first, then in real calendar order by month. In the example, the top rows are **Australia**, starting with **February**.

> 💡 Multi-level sort = sort by one column, then break ties with a second column.

---

## Part 2: Filtering to find problems

Now that the data is sorted, we use filters to check whether it needs more cleanup before saving.

### Convert the data to a table first

Usually you convert the data to a **table** before filtering.

1. Select all the data (`Ctrl+A`)
2. On the **Home** menu bar, choose **Format as Table**
3. Pick a simple style
4. Name the table **BikeSales**

> ⚠️ Table names **can't contain spaces**.

After this, every column header gets a **dropdown arrow** for filtering.

### Looking at the country column

Country is the key column for this analysis, so we open its filter dropdown. It lists every value in the column. Three problems pop out right away:

| Problem | Details |
|---|---|
| Two names for the US | The United States appears under two different designations |
| Blank values | Some rows have no country |
| **Saarland** | It's not a country, so something's off |

---

## Fixing each problem

### 1. Blank rows

1. Open the filter dropdown and click **Select All** to *deselect* everything
2. Check **Blanks** and click **OK**
3. Now only the blank rows are showing, so select them and **delete** them
4. Open the dropdown again and click **Select All** to show all the values again

### 2. Two names for the United States

Filter the column to isolate the US entries, then fix them in one of two ways.

**Option A: Auto-fill (for a small number of rows)**

1. Type **United States** in the first cell of the column
2. Click the **small square** in the lower right corner of the cell (the cursor turns into a plus sign)
3. Drag the plus sign down to the bottom of the column
4. Auto-fill changes the value in every row

**Option B: Find & Replace (for lots of rows)**

- Use **Replace** from the **Find & Select** option on the Home menu bar

### 3. Saarland

Filter by **Saarland** and look closer. The whole row in the original `.CSV` file got **shifted over one column**.

Possible causes:

- **Data corruption**
- A **missing delimiter** in the file

Since only a few rows are affected, the fix is simple: **highlight the cells and move them over** to the right columns.

---

## Quick takeaways

- **Sorting** puts data in order (ascending or descending). **Filtering** shows only the data that meets your criteria.
- Select **all** the data before sorting so rows stay together, and check **"My data has headers"**.
- For a multi-level sort, use **Add** to add more levels.
- Use a **Custom List** to sort months in calendar order instead of alphabetical.
- Convert data to a **table** (Format as Table) before filtering. Table names can't have spaces.
- Filter dropdowns are a quick way to spot **blanks, duplicate spellings, and wrong values**.
- Fix small problems with **auto-fill** or by moving cells. Fix big ones with **Find & Replace**.
- A row shifted by one column usually means **corrupted data or a missing delimiter**.
