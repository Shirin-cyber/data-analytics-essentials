# Module 3: Preparing and Cleaning Data for Analysis

> **Course:** Data Analytics Essentials · Cisco Networking Academy
> **TL;DR:** You've got the data. Now let's make it *usable*.

---

## So… what's this module actually about?

You've finished your first two modules, you've got a business question, and maybe even some raw data sitting in a spreadsheet that looks like it was thrown together by three different interns on three different Tuesdays.

That's exactly where this module picks up.

We're going to talk about **where data comes from**, how to tell the difference between a tidy CSV and a chaotic pile of social media posts, and — the big one — how to run the **ETL pipeline** (Extract → Transform → Load) to turn that mess into something you can actually analyze.

By the end, you'll be comfortable:

- Picking the right data source for the question you're trying to answer
- Knowing when something is "structured" vs. "unstructured" (and why that matters)
- Walking through an ETL process without freezing up
- Spotting duplicates, missing values, and other data gremlins
- Merging data from multiple sources in Excel

---

## What's in the box?

| Section | What you'll learn |
|---|---|
| **3.1** | Where does data actually come from? (Internal vs. external, and how to pick) |
| **3.2** | Structured data — CSVs, spreadsheets, databases. The "nice" stuff. |
| **3.3** | Unstructured data — NoSQL, data lakes, web scraping, APIs. The "messy" stuff. |
| **3.4** | Why data is dirty, and the ETL process that fixes it |
| **3.5** | Lab time: you'll actually do it in Excel |
| **3.5.2** | Quiz. Yeah, that part. |

---

## The stuff you'll keep coming back to

### Data sources (3.1)

Two buckets:

- **Internal** – your own databases, transaction logs, spreadsheets that someone exported "just in case"
- **External** – open-data portals, third-party APIs, web scraping

The rule of thumb: it has to be **relevant to your question** and **reasonably current**. A 2019 sales dataset won't help you answer a 2026 question.

### Structured data (3.2)

Rows. Columns. A schema. You know what each field means before you even open the file.

- CSV (comma-separated values)
- Excel workbooks
- Relational databases

This is the stuff that plays nicely with most tools.

### Unstructured data (3.3)

Everything else. Text, images, video, audio, tweets, Slack messages, PDFs that someone scanned.

It lives in:
- **NoSQL databases** (document stores, key-value pairs)
- **Data lakes** (big, flat, unorganized storage)
- **Web scraping** (automated extraction from HTML)
- **APIs** (programmatic access to external data)

It's harder to wrangle, but it's where a lot of the interesting signals hide.

### ETL — the heart of this module (3.4)

| Step | What's actually happening |
|---|---|
| **Extract** | Pull the raw data out of wherever it's sitting |
| **Transform** | The real work: deduplicate, fill gaps, fix typos, filter junk, standardize formats |
| **Load** | Drop the cleaned data into a database or a file that's ready for analysis |

**Quick checklist when you're cleaning:**

1. Is this data even relevant? If not, cut it.
2. Any duplicates? Kill them.
3. Typos, inconsistent naming, mixed formats? Fix them.
4. Missing values? Decide: drop, fill, or flag.
5. Outliers that look like data entry errors? Investigate.
6. Final sanity check. Does this actually make sense?

---

## 🛠️ What you'll be using

- **Microsoft Excel** – yes, Excel. It's not glamorous, but it's where the hands-on work happens
- **CSV files** – the universal "I don't care about formatting" format
- **Web-scraping concepts** – you'll see the idea, not build a scraper from scratch

---

## 📝 The Lab

**File:** `3.4.6 Lab - Preparing Data.xlsx`

You'll take a raw dataset and:
- Import it
- Find and remove duplicates
- Deal with missing/erroneous values
- Combine data from multiple sources using workbook links
- Export something clean

It's not hard, but it's the kind of thing you'll do *a lot* in a real analytics role.

---

## ✅ The Quiz

Covers everything above. The questions that trip people up:
- ETL definitions (know which task goes in which step)
- Structured vs. unstructured (know the difference cold)
- Characteristics of open data
- How unstructured data gets collected
- What makes a data source "relevant"

---

## Where you're coming from / going to

- **Before this:** Module 1 (Data Analytics Projects) → Module 2 (Getting Started with Data Gathering)
- **After this:** Module 4 – *Transforming Data with Excel* (where things get more fun)

---

## 🔗 Links

- [Course page on NetAcad](https://www.netacad.com/courses/data-analytics-essentials)
- [Credly badge (when you finish the whole course)](https://www.credly.com/org/cisco/badge/data-analytics-essentials)   
