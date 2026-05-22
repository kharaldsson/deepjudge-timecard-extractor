# deepjudge-timecard-extractor

Fields to accommodate:

Original Index
Work Date
Timekeeper Name
Work Hours
Work Rate
Work Amount
WIP Hours
WIP Rate
WIP Amount
Task
Billed
Invoice Number
Matter Number
Matter Name
Narrative

## CSV TABLE NODE DOCUMENTATION
CSV Table
Create a CSV table.


Create and export tabular data as a CSV file based on your structured JSON input.

Notes
Input Validation: Fails if 'content' is not valid JSON or is missing the "rows" key. Every unique key in rows becomes a CSV column header.
Filename: Use a valid filename and extension.
Supports Unicode: Data is UTF-8 encoded and supports non-English characters.
Flexible Row Structure: Not all rows require the same columns.
Example Usage
Suppose you want to export survey results:

Filename: survey_results.csv Content: {"rows": [{"Name": "Dana", "Score": "8", "Comments": "Great!"}, {"Name": "Lee", "Score": "7"}]} CSV Data output:

Name,Score,Comments
Dana,8,Great!
Lee,7,
File output: A file named survey_results.csv containing the above data.
Inputs
Filename: String
The filename of the output file. For example, results.csv or table_export.csv. Must contain the .csv extension. Avoid special characters.
Content: String
The content to add to the table as a JSON string. Example: {"rows": [{"column1": "Value 1", "column2": "Value 2"}]}. The top-level object must contain a "rows" key; each row is a dict with columns as keys. If columns differ between rows, all unique columns become headers and missing cells are left empty.
Outputs
CSV Data: String
The content of the CSV file as a string. Useful for downstream processing or inspection.
File: GeneratedFile
The generated CSV file. Downloadable with the specified filename and contents.
