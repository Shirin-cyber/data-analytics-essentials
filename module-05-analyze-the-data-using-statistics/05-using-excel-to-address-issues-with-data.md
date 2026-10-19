# 5.5 Using Excel to Address Issues with Data

**Topic objective:** Use VLOOKUP or XLOOKUP in Excel to identify and fix issues.

---

## 5.5.1 Meet VLOOKUP

**VLOOKUP** is one of Excel's most useful functions for data analysis.

What does it do? It looks for a value in **one column** of a table, and then gives you back a matching value from **another column** in the same row.

Why it's handy:

- It can grab matching values from a **big dataset** on the fly, for many values
- It can pull from **different spreadsheets or even different workbooks**
- It makes analysis **quicker and easier**

---

### Example 1: Find a movie's budget

The course uses a piece of the **movie dataset**. Here it's cut down to **11 rows** for the demo, but the full dataset has **more than 45,000 rows**.

**Goal:** Get the budget for the movie **2 Guns**.

In cell **G3**, type:

```
=VLOOKUP("2 Guns", A1:D11, 3, FALSE)
```

Here's how to read it:

| Part | Meaning |
|---|---|
| `"2 Guns"` | The value we're looking for |
| `A1:D11` | The table range to search in |
| `3` | Return the value from the **third column** of that range (this is the budget) |
| `FALSE` | Only accept an **exact match**, not an approximate one |

In plain words: *"Find 2 Guns in the first column of the table, and if you find it, give me what's in the third column."*

The result is **$61 million**.

This was way faster than searching or filtering for it by hand.

---

### Example 2: Look up whatever is typed in a cell

Typing the movie name inside the formula is kind of limiting. Better idea: let the formula look at a **cell**, so you can change the movie any time.

In **G3**, type:

```
=VLOOKUP(F3, $A$1:$D$11, 3, FALSE)
```

What changed:

- Instead of `"2 Guns"`, it looks at whatever title is typed into **F3**
- The table range uses **absolute references** (`$A$1:$D$11`), so it stays locked when you copy the formula

At first, G3 shows **`#N/A`**. That's because nothing's typed in F3 yet, so there's nothing to look up.

Type **2 Guns** into F3 and it returns **$61 million**.

You can also copy the formula down into **G4 and G5**. Then type a movie name in F4 and F5, and you get each movie's budget.

---

## 5.5.3 What you can do with VLOOKUP

VLOOKUP is great when:

- You need to find info in a **large spreadsheet**
- You keep looking up the **same type of information**

### What the name means

VLOOKUP = **"vertical lookup."** It searches down a **vertical column** of a table for a value you give it.

That means your data has to be in a **table** where each row holds different but related pieces of data in each column.

It always searches the **leftmost column** of the table. When it finds the value, it returns info from the **same row**, but from a different column.

> ⚠️ If you use an **approximate match**, the first column (the lookup column) must be **sorted** in numeric or alphabetical order.

### The 4 parts of a VLOOKUP

| # | Part | What it is |
|---|---|---|
| 1 | **Lookup value** | What you're searching for |
| 2 | **Range** | The table to search in |
| 3 | **Column number** | Which column in the range has the value you want back |
| 4 | **Match type** | `TRUE` = approximate match, `FALSE` = exact match only |

> 💡 If you leave out `FALSE`, VLOOKUP **defaults to an approximate match**. That's a sneaky way to get wrong results, so for lookups like names and titles, use `FALSE`.

---

## XLOOKUP: the newer alternative

**XLOOKUP** is a newer lookup function that works a lot like VLOOKUP.

| | VLOOKUP | XLOOKUP |
|---|---|---|
| Where it searches | Only the **leftmost** column of the table | **Any** column |
| Default match | **Closest match**, unless you use `FALSE` | **Exact match** |
| Availability | Works in all versions | Not in every Excel version |
| Backward compatible? | Yes | **No**. Worksheets with XLOOKUP may not work in older Excel |

In this course, you can use **either one**, as long as it's available in the spreadsheet tool you're using.

A quick example of XLOOKUP (my addition, not from the course):

```
=XLOOKUP(G2, A2:A11, C2:C11)
```

This reads: look for G2 in column A, and return the matching value from column C.

---

## Example 3: Typed value lookup

Here the title is typed into **G2**, and the formula in **G3** returns the budget:

```
=VLOOKUP(G2, A1:D11, 3, FALSE)
```

- It searches **A1 through D11** for the row matching what's in G2
- If found, it returns the value in **column 3** of that row
- `FALSE` means an **exact match**
- Until something is typed in G2, G3 shows **`#N/A`**

After typing in a movie title, the formula returns that movie's budget.

---

## Example 4: Using VLOOKUP for data cleaning

VLOOKUP can also clean data. For example, you can **compare two columns** and find the values that show up in **both**.

### The setup

- Column **A**: "Good" superheroes
- Column **B**: "Evil" villains

Nobody can be both good and evil, so **no name should appear in both columns**. VLOOKUP can catch any that do.

For each villain, the cell to the right (column C) checks if that name also shows up in the Good column.

### The formula

For the villain **Abomination** (in B2), cell **C2** has:

```
=VLOOKUP(B2, $A$2:$A$10, 1, FALSE)
```

| Part | Meaning |
|---|---|
| `B2` | The villain's name to look for |
| `$A$2:$A$10` | Search the Good list. The `$` signs lock the range so it stays put when copied |
| `1` | Return the value from column 1 (the name itself) |
| `FALSE` | Exact match only |

**What you get:**

- Abomination isn't in the Good list → **`#N/A`** (no duplicate)
- Change the name in the Evil list to **Agent 13**, who's also in the Good list at A7 → the name **shows up in C2**, so you've found a duplicate

Copy the formula down column C to check every entry. Thanks to the `$` signs, it still searches **A2 through A10** each time.

---

## Customizing the results

Seeing `#N/A` or a name is kind of confusing. You can make it say something clear, like **Unique** or **Duplicate**:

```
=IF(ISNA(VLOOKUP(B2,$A$2:$A$10,1,FALSE)),"Unique","Duplicate")
```

Two new functions are doing the work:

| Function | What it does |
|---|---|
| **IF** | Makes a logical comparison (if this, then that, otherwise this) |
| **ISNA** | Checks if a cell has the `#N/A` error |

Together: if VLOOKUP finds nothing (so it gives `#N/A`), the cell says **"Unique"**. Otherwise it says **"Duplicate"**.

Copy the formula down to get a clean label for every row.

---

## Quick takeaways

- **VLOOKUP** searches the leftmost column of a table and returns a value from another column in the same row.
- Four parts: **lookup value, range, column number, match type**.
- Use **`FALSE`** for an exact match. Leaving it out gives an approximate match by default.
- Use **absolute references** (`$A$1:$D$11`) so the range doesn't shift when you copy the formula.
- `#N/A` means nothing was found, or nothing was typed in the lookup cell yet.
- **XLOOKUP** can search any column and defaults to exact match, but it isn't backward compatible.
- VLOOKUP helps with **data cleaning** too, like finding duplicates between two lists.
- Wrap it in **IF and ISNA** to show clear labels like "Unique" and "Duplicate."
