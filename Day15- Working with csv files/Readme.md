📅 Day 15 — Working with CSV Files in Pandas

This folder contains my Day 15 learning work from the 100 Days of Machine Learning challenge.

The focus of this day was on reading, exploring, and efficiently handling CSV/TSV files using pandas, including real-world scenarios such as large datasets, encoding issues, and memory optimization.

📘 What I Learned

The notebook covers practical usage of pandas.read_csv() and related techniques:

🔹 Basic CSV Loading

Reading local CSV files

Understanding default pandas behavior

🔹 Reading Data from External Sources

Loading CSV data from a URL using requests and StringIO

🔹 Handling Different File Formats

Reading TSV (tab-separated) files using sep="\t"

Assigning column names manually

🔹 Column & Index Control

Selecting specific columns using usecols

Setting an index column with index_col

Adjusting headers using header

🔹 Series Extraction

Converting a single-column DataFrame to a Series using .squeeze()

🔹 Limiting Data for Inspection

Loading a subset of rows using nrows

🔹 Encoding Handling

Reading files with specific encodings to avoid decoding errors

🔹 Data Type Optimization

Explicitly specifying column data types using dtype

Reducing memory usage for large datasets

🔹 Date Parsing

Automatically parsing date columns using parse_dates

🔹 Custom Value Conversion

Applying user-defined functions with converters

🔹 Missing Value Handling

Defining custom missing values using na_values

🔹 Working with Large CSV Files

Reading large datasets in chunks using chunksize

Understanding iterator behavior (TextFileReader)

Iterative processing of data chunks
