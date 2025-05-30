---
title: Formatting problems
teaching: 20
exercises: 0
authors:
- Jez Cope
- Christie Bahlai
- Aleksandra Pawlik
- Sherry Lake
contributors:
- Jennifer Bryan
- Alexander Duryee
- Jeffrey Hollister
- Daisie Huang
- Owen Jones
- Ben Marwick
- Jesse Johnston
---

::::::::::::::::::::::::::::::::::::::: objectives

- Recognize and resolve common spreadsheet formatting problems.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- What common mistakes are made when formatting spreadsheets?

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: instructor

### This lesson is for reference

- **Don't go through this chapter** except to refer to as responses to the exercise in
  the previous chapter.

:::::::::::::::::::::::::::::::::::::::::::::::::::

## Common Spreadsheet Errors

- [Multiple tables](#tables)
- [Multiple tabs](#tabs)
- [Not filling in zeros](#zeros)
- [Using bad null values](#null)
- [Using formatting to convey information](#formatting)
- [Using formatting to make the data sheet look pretty](#formatting-pretty)
- [Placing comments or units in cells](#units)
- [More than one piece of information in a cell](#info)
- [Field name problems](#field-name)
- [Special characters in data](#special)
- [Inclusion of metadata in data table](#metadata)
- [Date formatting](03-dates-as-data.md)

***

## Multiple tables {#tables}

A common strategy is creating multiple data tables within one
spreadsheet. **This confuses the computer, so don't do this!** When
you create multiple tables within one spreadsheet, you're drawing
false associations between things for the computer, which sees each
row as an observation. You're also potentially using the same field
name in multiple places, which will make it harder to clean your data
up into a usable form. The example below depicts the problem:

![](fig/2_Multiple_Tables.png){alt='Screengrab of spreadsheet showing formatting errors - multiple tables in one sheet'}

## Multiple tabs {#tabs}

But what about worksheet tabs? That seems like an easy way to organise data, right? Well, yes and no. When you create extra tabs, you fail to allow the computer to see connections in the data that are there (you have to introduce spreadsheet application-specific functions or scripting to ensure this connection). Say, for instance, you make a separate tab for each year.

This is bad practice for two reasons:
**1\)** you are more likely to accidentally add inconsistencies to your data if each time you take a measurement, you start recording data in a new tab, and
**2\)** even if you manage to prevent all inconsistencies from creeping in, you will add an extra step for yourself before you analyze the data because you will have to combine these data into a single datatable. You will have to explicitly tell the computer how to combine tabs - and if the tabs are inconsistently formatted, you might even have to do it by hand!

The next time you're entering data, and you go to create another tab or table, I want you to ask yourself "Self, could I avoid adding this tab by adding another column to my original spreadsheet?"

Your data sheet might get very long over the course of recording data. This makes it harder to enter data if you can't see your headers at the top of the spreadsheet. But do NOT repeat headers. These can easily get mixed into the data, leading to problems down the road.

Instead you can Freeze the column headers.

[Documentation on how to freeze column headers in Microsoft Excel](https://support.microsoft.com/en-us/office/freeze-panes-to-lock-rows-and-columns-dab2ffc9-020d-4026-8121-67dd25f2508f)

[Documentation on how to freeze column headers in LibreOffice Calc](https://help.libreoffice.org/latest/en-US/text/scalc/guide/line_fix.html)

[Documentation on how to freeze column headers in Google Sheets](https://support.google.com/docs/answer/9060449?co=GENIE.Platform%3DDesktop&hl=en)

## Not filling in zeroes {#zeros}

It might be that when you're measuring something, it's
usually a zero, say the number of participants at a training event. Why bother
writing in the number zero in that column, when it's mostly zeros?

However, there's a difference between a zero and a blank cell in a spreadsheet. To the computer, a zero is actually data. You measured or counted it. A blank cell means that it wasn't measured and the computer will interpret it as a null value.

The spreadsheets or statistical programs will likely mis-interpret blank cells that are meant to be zero. This is equivalent to leaving out data. Zero observations are real data! Leaving zero data blank is not good in a written format, but NEVER okay when you move your data into a digital format.

## Using bad null values {#null}

**Example**: using -999, other numerical values, zero, or text to represent missing values.
Whatever the reason, it's a problem if unknown or missing data is recorded as -999, 999, or 0.
Many statistical programs will not recognize that these are intended to represent missing (null) values.
How these values are interpreted will depend on the software you use to analyze your data.

**Solution**: A solution will depend on the final application of your data and how you intend to analyse it,
but it is essential to use a clearly defined and CONSISTENT null indicator. Blank cells are the best choices for most applications;
when working in R, `NA` may be an acceptable null value choice.

There are many reasons that null values may be represented differently within a dataset. Sometimes confusing null values are automatically recorded from the measuring device.
In that case, there's not much you can do, but such inconsistencies can often be addressed in data cleaning
with a tool like [OpenRefine](https://librarycarpentry.org/lc-open-refine/) before using or sharing the data.
In other cases, null values may convey different reasons why the data is missing.
It may be useful to capture these reasons, but if you use the same column it is effectively storing two pieces of information in one column.
In such a case, it would be good to create a new column like `data_missing`, then to use that column to capture the reasons for missing data.

| Null Values | Problems                                                                                                                                                                   | Compatibility         | Recommendation | 
| ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- | -------------- |
| 0           | Indistinguishable from a true zero                                                                                                                                         |                       | NEVER use      | 
| Blank       | Hard to distinguish values that are missing from those overlooked on entry. Hard to distinguish blanks from spaces, which behave differently.                              | R, Python, SQL, Excel | Best option    | 
| \-999, 999   | Not recognized as null by many programs without user input. Can be inadvertently entered into calculations.                                                                |                       | Avoid          | 
| NA, na      | Can also be an abbreviation (e.g., North America), can cause problems with data type (turn a numerical column into a text column). NA is more commonly recognized than na. | R                     | Good option    | 
| N/A         | An alternate form of NA, but often not compatible with software.                                                                                                           |                       | Avoid          | 
| NULL        | Can cause problems with data type.                                                                                                                                         | SQL                   | Good option    | 
| None        | Uncommon. Can cause problems with data type.                                                                                                                               | Python                | Avoid          | 
| No data     | Uncommon. Can cause problems with data type, contains a space.                                                                                                             |                       | Avoid          | 
| Missing     | Uncommon. Can cause problems with data type.                                                                                                                               |                       | Avoid          | 
| \-, +, .     | Uncommon. Can cause problems with data type.                                                                                                                               |                       | Avoid          | 

Choices for representing null values, as illustrated in the table above, are proposed and explained further by White and others in their article: [Nine simple ways to make it easier to (re)use your data.](https://ojs.library.queensu.ca/index.php/IEE/article/view/4608) _Ideas in Ecology and Evolution_ 6 (2013): 1-10. DOI: [10\.4033/iee.2013.6b.6.f](https://10.4033/iee.2013.6b.6.f)

## Using formatting to convey information  {#formatting}

**Example**: highlighting cells, rows or columns that should be excluded from an analysis, leaving blank rows to indicate separations in data.

![](fig/formatting.png){alt='formatting'}

**Solution**: create a new field to encode which data should be excluded.

![](fig/good_formatting.png){alt='good formatting'}

## Using formatting to make the data sheet look pretty {#formatting-pretty}

**Example**: merging cells.

**Solution**: If you're not careful, formatting a worksheet to be more aesthetically pleasing can compromise your computer's ability to see associations in the data. Merged cells are an absolute formatting NO-NO if you want to make your data readable by statistics software. Consider restructuring your data in such a way that you will not need to merge cells to organise your data.

## Placing comments or units in cells {#units}

**Example**: Your data was collected, in part, by a summer student who you later found out was mis-recording the duration of training sessions, some of the time. You want a way to note these data are suspect.

**Solution**: Most statistical programs can't see Excel's comments, and would be confused by comments placed within your data cells. As described above for formatting, create another field if you need to add notes to cells. Similarly, don't include units in cells (such as "hours","min"): ideally, all the units or measurements you place in one column should be of the same standard, but if for some reason they aren't, insert another column and specify the units.

## More than one piece of information in a cell {#info}

**Example**:
One table recorded attendance by the different types of attendees. This table recorded number of attendees of different types: post-graduate researcher (PGR), post-doctoral research associate (PDRA), and other.

**Solution**:
Never include more than one piece of information in a cell. Design your data sheet to include a column for each type of attendee, if this information is important to collect, rather than just a total number.

## Field name problems {#field-name}

Choose descriptive field names, but be careful not to include: spaces, numbers, or special characters of any kind. Spaces can be misinterpreted by parsers that use whitespace as delimiters and some programs don't like field names that are text strings that start with numbers.
Underscores (`_`) are a good alternative to spaces and consider writing names in camel-case to improve readability. Remember that abbreviations that make sense at the moment may not be so obvious in 6 months but don't overdo it with names that are excessively long. Including the units in the field names avoids confusion and enables others to readily interpret your fields.

**Examples**

| Good Name          | Good Alternative   | Avoid                |
|--------------------+--------------------+----------------------|
| Max\_temp\_C       | MaxTemp            | Maximum Temp (°C)    |
| Precipitation\_mm  | Precipitation      | precmm               |
| Mean\_year\_growth | MeanYearGrowth     | Mean growth/year	 |
| sex                | sex                | M/F                  |
| length             | length             | l                   |
| cell\_type         | CellType           | Cell Type            |
| Observation\_01    | first\_observation | 1st Obs              |

## Special characters in data {#special}

**Example**: You treat Excel as a word processor when writing notes, even copying data directly from Word or other applications.

**Solution**: This is a common strategy. For example, when writing longer text in a cell, people often include line breaks, em-dashes, et al in their spreadsheet.  Worse yet, when copying data in from applications such as Word, formatting and fancy non-standard characters (such as left- and right-aligned quotation marks) are included.  When exporting this data into a coding/statistical environment or into a relational database, dangerous things may occur, such as lines being cut in half and encoding errors being thrown.

General best practice is to avoid adding characters such as newlines, tabs, and vertical tabs.  In other words, treat a text cell as if it were a simple web form that can only contain text and spaces.

## Inclusion of metadata in data table {#metadata}

**Example**: You add a legend at the top or bottom of your data table explaining column meaning, units, exceptions, etc.

**Solution**: While recording data about your data ("metadata") is essential, this information should not be contained in the data file itself. Unlike a table in a paper or a supplemental file, metadata (in the form of legends) should not be included in a data file since this information is not data, and including it can disrupt how computer programs interpret your data file. Rather, metadata should be stored as a separate file in the same directory as your data file, preferably in plain text format with a name that clearly associates it with your data file. Because metadata files are free text format, they also allow you to encode comments, units, information about how null values are encoded, etc. that are important to document but can disrupt the formatting of your data file.

:::::::::::::::::::::::::::::::::::::::: keypoints

- Don't use multiple tables in one sheet
- Don't use multiple tabs in a file
- Fill in zero when you mean zero
- Use an appropriate null value to record missing data
- Don't use formatting to convey information or make the spreadsheet look pretty
- Don't put units or comments in cells
- Don't combine several values in one cell
- Take care over column names
- Avoid including special characters in your data file
- Put metadata (units, legends etc.) in a separate file

::::::::::::::::::::::::::::::::::::::::::::::::::


