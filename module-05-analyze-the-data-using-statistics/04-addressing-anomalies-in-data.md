# 5.4 Addressing Anomalies in Data

**Topic objective:** Interpret visualizations to identify anomalies in data.

---

## 5.4.1 Finding anomalies with visualizations

### What's an anomaly?

An **anomaly** (also called an **outlier**) is a data point that **sticks out**. It doesn't follow the normal pattern of the rest of the data.

It's actually pretty common for data sets to have them. They usually come from:

- **Corruption** of the data
- **Experiment errors**
- **Human error**

---

### Example: spotting a typo with a scatter plot

The course uses a piece of the **bike sales** data set.

**Step 1: Make a scatter plot of customer age**

- Highlight the **customer age** for the **first 10 entries**
- Go to the **Insert** tab and pick the **scatter plot** chart type
- Excel puts each of the 10 ages on the graph as a **dot**

Looking at it, all the ages are in a pretty tight range, from about **18 to 41**. Nothing weird.

**Step 2: Add a mistake on purpose**

To show how this works, they add a **human error**. On row 10, they put a **1 in front of 35**, which turns the age into **135**.

**Step 3: Make a new scatter plot**

Now the plot looks totally different. One dot is way above everything else, so the anomaly **jumps out right away**.

**Step 4: Find it and fix it**

- Hover your cursor over the outlier
- It shows that it's the **ninth entry** in the table, which is **row 10** (row 1 is the header row, so that's why the numbers are off by one)
- Now you can go **check what the real age should be** and fix the mistake

### The big idea

If you look at a table full of numbers, a 135 hiding in there is **hard to see**. In a scatter plot, it's impossible to miss. That's the power of visualizations for finding anomalies.

---

## 5.4.3 Outliers and anomalies

### Why we care

Before analysis can start, a lot of time goes into **cleaning the data**. While cleaning, you might find outliers. When you do, you need to **investigate** them, so you can either:

- **Correct** the data, or
- **Understand what the outlier actually means**

### What's an outlier?

An **outlier** is a value or data point that is **very different** from the others. It can be much **smaller** or much **greater**.

In the course figure, one point sits at the **extreme bottom right**, far from the others. Every other point **clusters along the trend line**, so that lonely point is the outlier.

### Mistake or real?

Here's the key thing I noticed: an outlier isn't automatically *bad*. It could go either way.

| Type of outlier | What it means | What it does to your analysis |
|---|---|---|
| **A mistake** | A typo, corruption, or error | Can cause **anomalies in your results** if you leave it in |
| **Not an error** | A real value that's just unusual | Can be a **very important** piece of information |

That's why investigating anomalies is such a big part of data cleaning. It makes sure the data can be analyzed properly and gives **accurate and valid results**.

### How to find outliers

| Data size | How to spot outliers |
|---|---|
| **Small data sets** | Fairly easy. Just **sort or filter** the data |
| **Large data sets and big data** | You need other tools. Two common visualizations are **scatter plots** and **box plots** |

---

## Quick takeaways

- **Anomalies (outliers)** are data points that don't fit the normal pattern.
- Common causes: **corruption, experiment errors, and human error**.
- **Scatter plots** make outliers easy to see, even when they're hard to spot in a table.
- Hovering over an outlier tells you **which entry** it is, so you can go check and fix it.
- Outliers can be **mistakes** (fix them) or **real and important** (understand them). Don't just delete everything that looks strange.
- For small data sets, **sort and filter**. For big data, use **scatter plots** and **box plots**.
