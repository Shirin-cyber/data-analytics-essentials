# 5.1 Using Statistics to Interpret Data

**Topic objective:** Describe different types of statistics.

---

## 5.1.1 What are statistics, populations, and samples?

### Statistics

The American Statistical Association says statistics is the science of **learning from data**, and of measuring, controlling, and sharing **uncertainty**.

Okay, in plain words: it's a part of math about pulling useful info out of **patterns**.

In analytics, we use it to:

- Find **relationships** between variables
- Measure how strong those relationships (correlations) are
- Figure out how likely something is to **happen again**

### Population

A **population** is a group of similar things (people, objects, or events) that share a set of traits.

Example: **all tweets**. Each single tweet is one **member** of that population.

The population can be defined in different ways, depending on what you care about:

- All living people
- All tweets since January 1st, 2020

It's basically the big group we want to learn about.

### Sample

Here's the problem. Studying *all* living people, or *all* tweets since 2020, is usually not realistic. That's way too much.

So we pick a smaller group that represents the whole population. That's a **sample**.

- Samples are **randomly selected**
- They need to be **representative** of the bigger population
- That way we can draw conclusions about the sample and **generalize** them to the whole population

Think of it like tasting a spoonful of soup to know how the whole pot tastes.

| Term | Meaning | Example |
|---|---|---|
| Population | The whole group you want to know about | All tweets since Jan 1, 2020 |
| Sample | A smaller, representative group from it | A random selection of those tweets |

---

## 5.1.2 Descriptive statistics

First, you decide on the **problem statement** (the question you're asking) and the **population**. Then you need some kind of statistical analysis.

There are two main branches we cover in this course:

1. **Descriptive statistics**
2. **Inferential statistics**

### What descriptive statistics do

They **describe or summarize** the values and observations in a data set.

**Example:** A fitness tracker logs someone's daily steps and heart rate for **10 days**.

- They hit their fitness goal on **6 of the 10 days**, so they were successful **60%** of the time
- Their heart rate peaked at **140 bpm** but averaged **72 bpm**

Those numbers (60%, max 140, average 72) are descriptive statistics. They take a pile of data and make it simple.

### What counts as basic descriptive statistics?

- The **total number** of data points
- The **range** of values (lowest to highest)
- How many times a certain value **shows up**
- Answers about whether there are **trends**

You can show the results as numbers or as visuals, like **pie charts, bar charts, or histograms**.

### The catch

Descriptive statistics only tell you about the **current or past** state of what you observed. They do **not** let you:

- **Compare** groups
- Draw **conclusions**
- Make **predictions** about data that isn't part of the population

Back to the fitness tracker: we can't say the person is unhealthy just because they hit their goal 60% of the time. And we can't use one person's data to predict how other people will do.

That's the gap. And it's exactly where inferential statistics comes in.

---

## 5.1.3 Inferential statistics

Descriptive statistics summarize data you **already have**. But sometimes collecting data on a huge population is too hard, or not even possible.

So what do you do? You study a smaller **representative sample**, and then use **inferential statistics** to test ideas (called **hypotheses**) and draw conclusions about the bigger population.

**Inferential statistics** = collecting, analyzing, and interpreting data from a sample so you can **generalize or predict** something about the whole population.

### Things to watch out for

When you use a sample, you have to ask:

- Do the groups I picked actually look like the bigger group?
- Does the **environment** of the study match the real world?

To handle this, analysts use different **sampling techniques** to cut down on **error** and make the findings more trustworthy. Which technique to use depends on the **type of data**.

### Descriptive vs. inferential

| | Descriptive | Inferential |
|---|---|---|
| Works with | Data you already have | A sample from a bigger population |
| What it does | Summarizes and describes | Tests hypotheses, generalizes, predicts |
| Can it compare or predict? | No | Yes |
| Example | "This person hit their goal 60% of the time" | "Based on this sample, here's what we expect for the whole population" |

---

## 5.1.7 Statistics and big data

Big data analytics uses different statistical approaches, and both kinds show up.

### Descriptive statistics for checking quality

Descriptive statistics describe a sample. That's helpful for understanding the sample, and also for checking how **good the data is**.

Big data comes from many different places, so some data points might be **corrupted, incomplete, or missing**. Descriptive statistics can help you:

- See how much of the sample is actually **good for the analysis**
- Figure out the **rules for removing** data that's bad or doesn't fit

Graphs of descriptive statistics let you quickly judge a sample's quality.

**Example:** You pick a sample of tweets. Some have **only text**. Others have **text and images**.

Whether you keep or drop the tweets with images depends on your **question**. If you include them, you have to account for the information in the images too. So the question decides what counts as valid data, even with a simple rule like "has an image or not."

### Common inferential analyses in big data

| Analysis | What it's used for |
|---|---|
| **Cluster analysis** | Finding groups of observations that are **similar to each other** |
| **Association analysis** | Finding **co-occurrences** of values for different variables (things that show up together) |
| **Regression analysis** | Measuring the **relationship**, if any, between changes in one or more variables |

---

## Quick takeaways

- **Statistics** = learning from data and dealing with uncertainty.
- A **population** is the whole group you care about. A **sample** is a smaller, random, representative piece of it.
- **Descriptive statistics** summarize what you already have (counts, ranges, averages, trends). They can't compare groups, draw conclusions, or predict.
- **Inferential statistics** use a sample to test hypotheses and make predictions about the whole population.
- Sampling techniques help reduce error and build confidence in the results.
- In big data, descriptive statistics help check **data quality**, and common inferential methods include **cluster, association, and regression analysis**.
