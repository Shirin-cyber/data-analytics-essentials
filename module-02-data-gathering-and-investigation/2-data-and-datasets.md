# 2. Data and Datasets

Before analyzing data, we need to understand what we're actually working with. Data can come from different sources, contain different types of information, and be stored in different file formats.

This section covers the basics of datasets, metadata, and CSV files, which are commonly encountered when working with data.

## 2.1 What Is Data?

Data consists of recorded facts, measurements, observations, or other information that can be collected and analyzed.

For example, a store might collect information about product prices, sales, and customer purchases. A hospital might record patient test results and appointment schedules.

Organizations collect and share data in different formats depending on their needs.

A **dataset** is a collection of related data that can be examined and analyzed together.

## 2.2 Private Datasets vs. Public Datasets

Not every dataset is available for everyone to use. Some datasets have restricted access, while others are made available to the public.

### Private Datasets

A private dataset can only be accessed by people who have the appropriate permission.

For example, a physician's patient dataset might contain:

- Patient demographics
- Medical test results
- Diagnoses
- Appointment schedules

This information may contain sensitive personal details, so access must be restricted and the data handled appropriately.

### Public Datasets

A public dataset is made available for broader use and can generally be accessed by anyone, subject to its applicable terms and conditions.

For example, the World Health Organization (WHO) provides health-related statistics for its member countries.

Public datasets are useful for learning, research, and data analytics projects because they allow people to investigate information without necessarily having to collect all the data themselves.

### Key Difference

- **Private dataset:** Access is restricted to authorized people.
- **Public dataset:** Data is made available for broader access and use.

Always check the access conditions and any restrictions before using a dataset.

## 2.3 Can a Dataset Contain Multiple Files?

Yes! A dataset doesn't always come as one single file.

Sometimes, related information is divided into several files, with each file containing a different part of the overall dataset.

For example, a movie dataset might include separate files for:

- Movie metadata
- Ratings
- Credits
- Keywords
- Other movie-related information

An analyst may need to examine multiple files to understand the complete picture.

Suppose we want to investigate whether movie budgets are related to audience ratings. We might need one file containing movie budgets and another containing ratings. Before combining them, we would need to identify how the records in those files relate to each other.

**Important:** Multiple files belonging to the same dataset may contain different information and serve different purposes.

## 2.4 What Is Metadata?

Metadata means **data about data**.

It describes a dataset or the information contained within it, helping analysts understand what they're looking at before beginning their analysis.

For example, metadata for a movie dataset might describe fields such as:

- Movie title
- Runtime
- Production company
- Popularity
- Budget

Metadata helps answer questions such as:

- What does this dataset contain?
- What does each file represent?
- What information is recorded in each column?
- What format is the data stored in?

Understanding metadata makes it easier to decide whether a dataset is relevant to the question we're trying to answer.

### Dataset vs. Metadata

Think of a dataset as the actual collection of information and metadata as the description that helps you understand that information.

For example, a spreadsheet might contain thousands of movie records. Information describing the meaning of its columns, the file format, and the contents of the dataset is metadata.

## 2.5 What Is CSV?

CSV stands for **Comma-Separated Values**.

It is a common text-based file format used to store and exchange tabular data.

Consider this example:

```csv
Movie,Year,Rating
Film A,2022,8.1
Film B,2023,7.5
Film C,2024,8.7
```

Here's how to read it:

- Each line represents a record.
- Commas separate the individual fields.
- The first line contains the column headings.
- The remaining lines contain the values for each movie.

The information can be imported into a spreadsheet application such as Excel for investigation and analysis.

### CSV vs. Excel Workbook

Although CSV files can be opened in Excel, a CSV file is not the same as an Excel workbook.

A CSV file stores tabular data as text. An Excel workbook can contain multiple worksheets, formulas, charts, formatting, and other spreadsheet features.

| Feature | CSV file | Excel workbook |
|---|---|---|
| File format | Text-based | Spreadsheet format |
| Multiple worksheets | No | Yes |
| Formulas and charts | Not preserved as spreadsheet features | Supported |
| Common use | Storing and exchanging tabular data | Organizing and analyzing data |

A CSV file can contain the results of calculations, but it does not preserve Excel formulas as working spreadsheet formulas.

## Key Takeaways

- **Data** consists of recorded facts, measurements, observations, or other information.
- **Dataset** means a collection of related data.
- **Private datasets** have restricted access, while public datasets are available for broader use.
- A dataset can contain multiple related files.
- **Metadata** describes a dataset and helps explain its contents and structure.
- **CSV** stands for Comma-Separated Values and is a common format for tabular data.
- CSV files and Excel workbooks are different, even though Excel can open CSV files.

Before starting an analysis, make sure you understand what the dataset contains, how it is organized, and whether it is suitable for your investigation.
