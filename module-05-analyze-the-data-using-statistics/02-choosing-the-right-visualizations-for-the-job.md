# 5.2 Choosing the Right Visualization for the Job

**Topic objective:** Select data visualizations to best explain analysis results.

---

## 5.2.1 Why visualizations matter

**Data visualization** means showing information and data in a visual way, using things like charts, graphs, and maps.

Why bother? Because it's an easy way to see **trends, outliers, and patterns** in data.

Think about where we are in the process:

1. Collect the data
2. Process it
3. Analyze it
4. **Visualize it** so you can draw conclusions

### A good visualization tells a story

A good one does two things:

- Removes the **noise** (stuff that doesn't matter)
- Highlights the **useful info**

So you can think of it as **visual storytelling**. It helps answer *who, what, when, where,* and *how*.

Making good visualizations is a big skill for a data analyst. Your **stakeholders** (the people who need the results) need to look at the data and focus on the parts that need their attention.

Why it works: humans process **images faster than tables of numbers**. So good visuals help people make **faster, better decisions** and understand complicated data.

---

## 5.2.3 Common types of visualizations

There are tons of chart types. How do you pick? Ask yourself:

- **How many variables** do I want to show?
- **How many data points** are in each variable?
- Is the data **over time**, or am I comparing data points at **one moment**?

Here are the main chart types.

---

### Line charts

A very common comparison chart.

**Use it when:**

- Your data is **continuous**
- You have **lots of data points**
- You want to show a **trend over time**

**Examples:**

- Quarterly sales for the past five years
- Number of customers per week in a new shop's first year
- A stock's price over one day, from opening to closing bell

**Best practices:**

- **Label the axes**
- Put **time on the x-axis** (horizontal) and **values on the y-axis** (vertical)
- Use a **solid line**, not a broken one, to show the data is continuous
- Keep the number of lines **low**. You need a really good reason to plot more than four. If you do, add a **legend**
- **Minimize gridlines** so they don't distract. Only use them to point out certain values or time periods
- Adjust where the **y-axis starts** so a line has roughly a **45-degree slope**. This shows the change clearly without making it look more dramatic than it is

---

### Column charts

Vertical bars. Probably the most common chart for showing the values of **one variable across similar categories**.

**Examples:**

- Populations of the BRICS nations (Brazil, Russia, India, China, South Africa)
- Last year's sales for the top four car companies
- Average test scores for six math classes

**Best practices:**

- **Label the axes**
- If showing change over time, put **time on the x-axis**
- If time isn't involved, **order the columns** from tallest to shortest (or the reverse)
- Use a **solid color**. To highlight one column, give it an **accent color** and keep the rest the same color
- Best with **no more than seven categories** on the horizontal axis, so each column is easy to read
- **Start the y-axis at zero** so the columns show their true values
- Spacing between columns should be about **half a column's width**

---

### Bar charts

Like column charts, but **horizontal**. Longer bar = bigger value. They usually don't show change over time.

**When they shine:** when the **names are long**, because there's room to write them next to each bar.

**Examples:**

- GDP of the 25 highest-producing nations in a given year
- Number of cars sold by each sales rep in a group
- Exam scores for each student in a math class

**Best practices:**

- **Label the axes**
- Consider ordering bars from **longest to shortest**. Whether the longest goes on the top or bottom depends on what the data means and what's easiest to understand
- Use a **solid color**, with an **accent color** to highlight one bar
- **Start the x-axis at zero**
- Spacing between bars should be about **half a bar's width**

---

### Pie charts

Used to show how a **total is split up**. Each slice is a percentage, and all slices together must add up to **100%**.

**Examples:**

- A company's yearly expenses (rent, admin, utilities, production)
- A country's energy sources (oil, coal, gas, solar, wind)
- Survey results for favorite movie type (action, romance, comedy, drama, sci-fi)

**Best practices:**

- **Limit the categories** so people can tell slices apart. After about **ten segments**, the slices stop meaning much
- If needed, combine small slices into one called **"Other"** or **"Miscellaneous"**
- Give each segment a **different color** or shade of gray
- Order the segments **clockwise by size**
- Make sure everything adds up to **100%**

---

### Scatter plots

Super popular for showing **correlations** or how **many data points are spread out**. They're also good for spotting **clusters** and **outliers**.

**Examples:**

- Life expectancy vs. GDP for each country in a group
- Daily ice cream sales vs. average outside temperature
- Weight vs. height for each person in a group

**Best practices:**

- **Label the axes**
- Use a **big enough data set** so clusters or outliers actually show up
- **Start the y-axis at zero** to show the full values. The x-axis depends on the data. For example, if the x-axis is customer age, you don't need to start at zero years old
- If there's a clear correlation, consider adding a **trend line**
- Don't use more than **two trend lines**

---

## Quick guide: which chart should I use?

| I want to show... | Use a... |
|---|---|
| A trend over time with lots of data points | **Line chart** |
| One variable across a few categories | **Column chart** |
| Categories with long names, or ranking many items | **Bar chart** |
| How a total is split into parts | **Pie chart** |
| A relationship between two variables, clusters, or outliers | **Scatter plot** |

---

## Quick takeaways

- A good visualization **tells a story** by cutting noise and highlighting what matters.
- Humans understand visuals **faster** than tables of numbers.
- Before choosing a chart, ask: how many variables, how many data points, and is it over time?
- **Line** = trends over time. **Column** = compare categories (up to about seven). **Bar** = long labels or rankings. **Pie** = parts of a whole (must total 100%). **Scatter** = correlations and outliers.
- Always **label your axes**.
- Use **solid colors** with one **accent color** to highlight what matters.
- Start bar and column axes at **zero** so the sizes aren't misleading.
