# Module 3: Preparing and Cleaning Data for Analysis

## Part 1: Sources of Data (3.1)

**Module objective:** Explain how to obtain appropriate data for analysis.

---

## 3.0 So... what's this module even about?

Before you can analyze anything, the data has to be ready. This is the step in the data analytics process where you check three things:

| Check | What it really means |
|---|---|
| Relevant | Does this data actually help answer my question? |
| Right format | Can my tools read and work with it? |
| Clean | Is it free from invalid or corrupted stuff? |

Think of it like cooking. You don't throw random ingredients in a pot. You pick the right ones, prep them, and toss out the rotten ones first.

---

## 3.1 Where does data come from?

Turns out, data is *everywhere*. Basically any file or system that holds information is a possible source.

### Data hiding in files

A huge amount of historical data sits in everyday file types:

- Word documents
- Emails
- Spreadsheets
- PowerPoints
- PDFs
- HTML pages
- Plain text files

And what's inside those files? Stuff like medical insurance forms, invoices, business statements, customer interactions, and tax documents.

### Data inside organizations

Companies create raw data all the time through their own systems:

- Customer relationship management (CRM) systems
- Learning management systems (LMS)
- Human resource systems and records

This data usually lives in **private databases**, and only authorized people can get to it. So you can't just grab it. You need permission.

### Open data (the free stuff)

**Open data** is data that people or organizations collected and then shared publicly, so anyone can use it.

Where to find it:

- Big companies like Amazon, Google, and Microsoft
- Government agencies
- Sites like **GitHub** and **Kaggle**, which have datasets for analysis, research, and machine learning

> ⚠️ **Heads up:** Always check the **license** before using internet data. Most open data is free, but some is only allowed for **non-commercial** use.

### Quick comparison

| Source type | Examples | Who can access it |
|---|---|---|
| Files | Word, PDF, spreadsheets, emails | Depends on where the files are stored |
| Internal systems | CRM, LMS, HR records | Authorized people only |
| Open data | Kaggle, GitHub, government sites | Public (check the license) |

---

## 3.1.2 Picking the *right* data

Having lots of data isn't the goal. Having **relevant** data is.

Picking data means two things:

1. Figuring out what type of data you need
2. Finding a source for it

Always go back to your **original business question**.

**Example:** Say you want to know the demographics of people who bought product X in the past year. Then you should only use data connected to product X. Throwing in data about product Y just adds noise.

This is what keeps your analysis **valid** (it measures what it's supposed to) and **reliable** (you can trust it).

### What if the data isn't there?

Sometimes the data you need just doesn't exist yet. Then you might have to:

- Set up new ways to **collect** the data, or
- **Combine data from multiple sources** into one format you can analyze

### Questions to ask yourself before choosing a data source

- What data points do I need for this analysis?
- Do I already have access, or do I need to find a dataset somewhere else?
- Where can I find reliable sources I can verify?
- How often is the data collected and updated?
- How is it licensed, and does it cost money?
- Is it in a format I can use, or convert to use, with my tools?

---

## 3.1.5 Static vs. streaming data

Analysts deal with two kinds of data, and the difference is all about **timing**.

| | Static data | Streaming data |
|---|---|---|
| When is it analyzed? | After it's received **and stored** | **As it comes in**, event by event |
| Analysis style | Batch, later | Real-time |
| Typical output | Report after the fact | Live dashboard or input to an automated function |

### Example: movie review site

Imagine an analyst sorting viewer comments into **positive** or **negative** during the week a new movie preview comes out.

- **As static data:** Save all the comments in a database, then analyze them at the end of the week.
- **As streaming data:** Analyze every comment the moment it shows up.

Streaming results often show up on a **dashboard that keeps updating**, or get fed into something automatic.

So the same data can be treated either way. It depends on how fast you need the answers.

---

## 3.1.7 Data types and formats

Once you've got the data, it needs prep work. This part is a big deal:

> Experts estimate data preparation can take **50 to 80 percent** of the time of a whole analysis.

Yep, most of the job is getting the data ready, not the fancy analysis part.

Why so much work? Because datasets from different sources often **don't match each other**. Sometimes you also have to convert data to a different type. For example, dates stored as text need to be turned into numbers before you can do statistics with them.

### Common data types

Data types matter because they decide what calculations and comparisons you can do.

| Type | What it is | Quick notes |
|---|---|---|
| **String** | Text: letters, symbols, punctuation, and numbers you won't calculate with | Also includes white space (the spaces that separate and format text) |
| **Integer** | Whole numbers with no decimals | Whether negatives count depends on the programming language. Often used to order or rank things |
| **Floating point** | Numbers with decimal places | Used a lot in statistical analysis |
| **Date and time** | When an observation was recorded | Formats vary a lot between sources |
| **Boolean** | `TRUE` or `FALSE` | Written as TRUE/FALSE, not as a text string |

### Same data, different formats

Even when the data type is the same, the **format** can change depending on the source.

**Spelling and language**

Different languages use different symbols for the same word, and British and American English spell some words differently. If you're searching text for ways people travel, you need to look for both:

- `airplane` (American)
- `aeroplane` (British)

Otherwise you'd miss results and your analysis wouldn't be accurate.

**Dates**

Some countries put the day first, others put the month first:

```
03/04/2026
```

- Day first → **3 April 2026**
- Month first → **March 4, 2026**

Same text, two different dates. This is why everything has to be converted into **one single format** before analysis.

**Time**

- 12-hour format: `3:30 PM`
- 24-hour format: `15:30`

Same idea. Pick one format and convert everything to it.

---

## Quick takeaways for this part

- Data comes from files, internal systems, and open data sources.
- Always check **licenses** on open data.
- Choose data that's **relevant to your business question**. More data isn't always better.
- **Static** data is analyzed later. **Streaming** data is analyzed as it arrives.
- Data prep can eat up **50 to 80 percent** of an analysis.
- Know your **data types** (string, integer, floating point, date/time, boolean).
- Watch out for **format differences** like spelling, dates, and time, and convert to one standard format.

*Next up: 3.2*
