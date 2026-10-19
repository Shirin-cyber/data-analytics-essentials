# Module 5 Wrap-Up: Analyze the Data Using Statistics

Data analytics leans on statistics. In this module we learned the basic ideas, then used Excel to build visuals, spot problems, and fix them.

---

## The big picture

Here's how the five topics connect:

1. **Statistics (5.1):** Understand the basics first. What a population and sample are, and how descriptive and inferential statistics are different.
2. **Choosing a visualization (5.2):** Once you have results, pick the chart that tells the story best.
3. **Creating visuals in Excel (5.3):** Actually build the chart: select data, Insert tab, customize.
4. **Anomalies (5.4):** Visuals, like scatter plots, make weird data points easy to see. Then you check if they're mistakes or real.
5. **VLOOKUP and XLOOKUP (5.5):** Tools to look things up, compare lists, and catch problems like duplicates.

The common thread: statistics tell you what the data means, visuals show it, and lookups and checks make sure the data is trustworthy.

---

## Key terms

| Term | Quick meaning |
|---|---|
| Statistics | The science of learning from data and dealing with uncertainty |
| Population | The whole group of similar things you want to know about |
| Sample | A smaller, random, representative piece of a population |
| Descriptive statistics | Summarize data you already have (counts, ranges, averages, trends) |
| Inferential statistics | Use a sample to test hypotheses and make predictions about a population |
| Hypothesis | An idea you test with data |
| Cluster analysis | Finds groups of observations that are similar to each other |
| Association analysis | Finds values that show up together |
| Regression analysis | Measures the relationship between changes in variables |
| Data visualization | Showing data with charts, graphs, and maps |
| Stakeholder | A person who needs the results of your analysis |
| Line chart | Shows trends over time |
| Column chart | Compares one variable across categories (vertical bars) |
| Bar chart | Same idea, horizontal bars, good for long labels |
| Pie chart | Shows parts of a whole that add up to 100% |
| Scatter plot | Shows relationships between two variables, clusters, and outliers |
| Trend line | A line on a scatter plot showing the correlation |
| Chart Elements / Chart Style | Excel buttons to add chart parts and change the look |
| Anomaly / outlier | A data point that doesn't fit the normal pattern |
| Box plot | A visualization used to find outliers in large data sets |
| VLOOKUP | Searches the leftmost column of a table and returns a value from the same row |
| XLOOKUP | Newer lookup that searches any column and defaults to exact match |
| `#N/A` | Error meaning nothing was found or nothing was entered |
| IF / ISNA | Functions used to give clear labels like "Unique" or "Duplicate" |

---

## Summary

### Using statistics (5.1)

- A **population** is the whole group. A **sample** is a smaller, representative piece.
- **Descriptive** statistics summarize what you have but can't compare groups, draw conclusions, or predict.
- **Inferential** statistics use a sample to test hypotheses and generalize to the population.
- In big data, descriptive statistics help check **data quality**. Common inferential methods are **cluster, association, and regression analysis**.

### Choosing a visualization (5.2)

- A good visual **tells a story** and cuts the noise. People understand visuals faster than tables.
- Pick a chart by asking how many variables, how many data points, and whether it's over time.
- **Line** for trends, **column** for categories, **bar** for long labels, **pie** for parts of a whole, **scatter** for relationships and outliers.
- Always label axes, use solid colors with an accent color, and start bar and column axes at zero.

### Creating visuals in Excel (5.3)

- Select data, go to the **Insert** tab, and pick a chart type.
- Customize with **Chart Elements** and **Chart Style**. Add a title and axis titles.

### Anomalies (5.4)

- Outliers come from corruption, experiment errors, or human error.
- **Scatter plots** make outliers jump out, even when they're hidden in a table.
- Outliers can be **mistakes** (fix them) or **real and important** (understand them).
- Small data sets: sort and filter. Big data: scatter plots and box plots.

### VLOOKUP and XLOOKUP (5.5)

- VLOOKUP has four parts: **lookup value, range, column number, match type**.
- Use **`FALSE`** for an exact match, and **absolute references** so the range stays put.
- XLOOKUP is newer, searches any column, and defaults to exact match, but it isn't backward compatible.
- Lookups help with **data cleaning**, like finding duplicates between two lists. Add **IF and ISNA** for clear labels.
