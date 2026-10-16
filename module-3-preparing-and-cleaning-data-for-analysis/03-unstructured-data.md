# 3.3 Unstructured Data

---

## 3.3.1 Big data and decision making

Every single day, a crazy amount of data gets generated, and most companies are collecting, storing, and analyzing it. The goal is to turn all that data into **strategic information and discoveries**.

### The numbers (from the course)

| Stat | What it says |
|---|---|
| 4 out of 5 | IT managers say their companies are analyzing the data they collect |
| 2 out of 3 | IT managers say big data is a priority for 2022 and the next five years |
| 1 out of 4 | managers say their company is actually getting strategic value from the data today |
| 27 billion+ | IoT connected devices and sensors expected by 2025 |

So most companies are *trying*, but only a small group is really getting value out of it. That gap is the challenge. On top of that, there are worries about **data security** and **risk management**.

### Data in Motion

Big data is just the beginning. The most valuable data often comes from **devices, sensors, and monitors** when it's used **in real time**. Cisco calls this **Data in Motion**.

Why it matters: it lets people and machines make **actions and decisions instantly**. Think of machine-to-machine communication, with billions of connected devices talking to each other.

### The storage problem

A huge chunk of big data is **unstructured or semi-structured**. That means it doesn't fit into standard database layouts and storage systems. So we need new types of storage and new ways of organizing it.

One of the new options is the **data lake**:

- A place to store **both structured and unstructured data**
- Organizes large amounts of data from lots of different sources (documents, websites, images, and more)

And before this kind of data can be analyzed, it needs **new methods of processing** first.

---

## 3.3.3 Unstructured files

**Unstructured data** is raw data that isn't organized in any predefined way.

- It has **no fixed schema**, so nothing tells you what type of data it is or what format it's in
- There's **no set way** to enter it, group it, or analyze it

### Examples

- Photos, audio, and video (the actual content)
- Web pages, blogs, wikis
- Books, journals, white papers, articles
- PowerPoint presentations and word processing documents
- Email
- Text in general
- A **traffic camera feed** that keeps sending images non-stop

Even a PDF of a course chapter counts. You can search the text, but it's not organized in any predefined format.

### Why it matters

Both structured and unstructured data are valuable to individuals, organizations, industries, and governments. So organizations need to take **all forms of data** and find ways to format it so it can be managed and analyzed.

---

## 3.3.5 Sources of unstructured data

The internet is full of unstructured data:

- Text, images, videos, and audio
- Public web forums and blogs
- Social media like YouTube, Facebook, instant messaging, RSS, and Twitter

Most of it isn't easy to put into a database without some kind of **processing** first.

### Ways to extract and process it

#### 1. NoSQL databases and data lakes

- Unstructured data is often stored in **non-relational databases** or **data lakes**
- A data lake is a **centralized repository** for raw data from IoT devices, websites, mobile apps, social media, and other sources
- They store real-time data in its **original format**
- NoSQL gets covered later in the course

#### 2. Web scraping

- Web pages are made for **humans**, not machines
- Web scraping tools **automatically pull data out of HTML pages**
- Usually it's an automated process using a **bot or web crawler**
- It copies specific data from the web into a **database or spreadsheet**, where it's easy to analyze

#### 3. APIs (Application Program Interfaces)

- Big web service providers (like Facebook) offer **standardized interfaces** so you can collect their data automatically
- The most common type is the **RESTful API**
- RESTful APIs use **HTTP** to communicate and **JSON** files to store the data
- Sites like Google and Twitter gather huge amounts of **static and streaming data**, and their APIs let analysts and engineers access **subsets** of it

### Quick comparison

| Method | How it works | Good for |
|---|---|---|
| NoSQL / data lakes | Stores raw data in its original format | Holding lots of mixed, real-time data |
| Web scraping | Bot or crawler copies data from web pages | Getting data from sites that don't offer it directly |
| APIs | Standard interface, HTTP plus JSON | Pulling data straight from big web services |

---

## Quick takeaways for this part

- Most big data is **unstructured or semi-structured**, so it doesn't fit standard databases.
- **Data in Motion** (Cisco's term) means real-time data from devices and sensors that lets decisions happen instantly.
- A **data lake** stores structured and unstructured data from many sources.
- **Unstructured data** has no fixed schema and no predefined organization. Think photos, video, email, web pages, and text.
- Main ways to get at it: **NoSQL/data lakes, web scraping, and APIs**.
- **RESTful APIs** use HTTP and JSON.
