# Module 3 Wrap-Up: Preparing and Cleaning Data for Analysis

**Module objective:** Explain how to obtain appropriate data for analysis.

---

## The big picture

Here's how it all fits together:

1. **Find data** from files, internal systems, or open data sources, and pick data that's actually relevant to your question.
2. **Know what kind of data you have.** Is it structured (neat tables), unstructured (photos, emails, web pages), or somewhere in between?
3. **Get it into a usable form.** Different sources mean different formats, so you extract it, transform it, and load it (ETL or ELT).
4. **Clean it.** Remove duplicates, blanks, and obvious errors so they don't mess up your results.

Only after all that does the real analysis start. And that prep work can take **50 to 80 percent** of the total time.

---

## Key terms

| Term | Quick meaning |
|---|---|
| Open data | Data shared publicly for anyone to use (check the license) |
| Static data | Data that's stored first and analyzed later |
| Streaming data | Data analyzed as it arrives, in real time |
| String | Text data |
| Integer | Whole number |
| Floating point | Number with decimals |
| Boolean | `TRUE` or `FALSE` |
| Structured data | Data in defined fields, like tables in a database or spreadsheet |
| CSV | Plain text file where commas separate columns and new lines separate rows |
| JSON / XML | Standard plain text formats for data records |
| Relational database | Tables connected by pre-defined relationships |
| Flat file database | Records stored in a single file with no hierarchy (like a spreadsheet) |
| Unstructured data | Raw data with no fixed schema (photos, video, email, text) |
| Data in Motion | Cisco's term for real-time data from devices and sensors |
| Data lake | Storage for structured and unstructured data from many sources |
| NoSQL database | Non-relational database, often used for unstructured data |
| Web scraping | Using a bot or crawler to pull data out of web pages |
| API / RESTful API | Standard interface for collecting data from a service, using HTTP and JSON |
| ETL | Extract → Transform → Load |
| ELT | Extract → Load → Transform |
| Data cleaning | Removing or fixing incomplete, incorrect, badly formatted, duplicated, or irrelevant data |

---

## Summary

- **Where data comes from:** files, internal systems (CRM, LMS, HR), and open data. Always pick data that matches your business question, and check licenses.
- **Static vs. streaming:** static data is analyzed after storage, streaming data is analyzed as it arrives.
- **Data types and formats:** know your strings, integers, floating point numbers, dates, and booleans. Convert differences in spelling, dates, and times into one standard format.
- **Structured data:** lives in defined fields, usually tables. Examples include relational databases, logs, spreadsheets, sensor readings, and transaction records.
- **CSV, JSON, and XML:** common plain text formats that make it easier to combine data from different sources.
- **Unstructured data:** has no fixed schema, and most big data is unstructured or semi-structured. You can get at it through NoSQL databases and data lakes, web scraping, and APIs.
- **Data prep:** ETL transforms before loading, ELT transforms after loading. The transform step covers joining, aggregating, sorting, validating, and cleaning.
- **Cleaning in Excel:** remove duplicates, delete blank rows, and find and remove obvious errors like zero costs.
