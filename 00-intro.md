---
title: Using spreadsheet programs for data organization
teaching: 10
exercises: 5
authors:
- Jez Cope
- Christie Bahlai
- Aleksandra Pawlik
contributors:
- Jennifer Bryan
- Alexander Duryee
- Jeffrey Hollister
- Daisie Huang
- Owen Jones
- Clare Sloggett
- Harriet Dashnow
- Ben Marwick
- Sherry Lake
---

::::::::::::::::::::::::::::::::::::::: objectives

- Understanding some drawbacks and advantages of using spreadsheet programs
- Distinguish machine readable tidy data from data that is easy to read for humans

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- What are good data practices for using spreadsheets for organizing data?

::::::::::::::::::::::::::::::::::::::::::::::::::

Good **data organization** is the foundation of much of our day-to-day
work in libraries. Most **librarians** have data or do data entry in
spreadsheets. Spreadsheet programs are very **useful graphical
interfaces** for designing data tables and handling very basic data
quality control functions.

Spreadsheets encompass a lot of the things we need
to be able to do as librarians. We can use them for:

- Data entry
- Organizing data
- Subsetting and sorting data
- Statistics
- Plotting

***

### Spreadsheet outline

In this lesson, we will look at:

- Good data entry practices - formatting data tables in spreadsheets
- How to avoid common formatting mistakes
- Dates as data - beware!
- Basic quality control and data manipulation in spreadsheets
- Exporting data from spreadsheets

**Much of your time when you're producing a report will be spent in
this 'data wrangling' stage.** It's not the most fun, but it's
necessary. We'll teach you how to think about data organization and
some practices for more effective data wrangling.

***

### What this lesson will not teach you

- How to do *statistics* in a spreadsheet
- How to do *plotting* in a spreadsheet
- How to *write code* in spreadsheet programs

If you're looking to do this, a good reference is
[Head First Excel by O'Reilly Media](https://www.amazon.com/Head-First-Excel-learners-spreadsheets/dp/0596807694).

***

### Why aren't we teaching data analysis in spreadsheets

- Data analysis in spreadsheets usually requires **a lot of manual
  work**. If you want to change a parameter or run an analysis with a
  new dataset, you usually have to redo everything by hand. (We do
  know that you can create macros, but see the next point.)

- It is also difficult to **track or reproduce statistical or plotting
  analyses** done in spreadsheet programs when you want to go back to
  your work or someone asks for details of your analysis.

### Spreadsheet programs

There are a number of spreadsheet programs available for use on a desktop or web browser:

- LibreOffice Calc
- Microsoft Excel
- Apple Numbers
- Google Sheets
- Gnumeric
- Apache OpenOffice Calc

Commands may differ a bit between programs, but the general idea
is the same. In this lesson, we will assume that you are most likely using Excel as
your primary spreadsheet program. There are others with similar functionality, including Gnumeric, OpenOffice Calc, and Google Sheets, but Excel is the package you're most likely to have available on your work computer.

***

:::::::::::::::::::::::::::::::::::::::  challenge

## Questions:

- How many people have used spreadsheets in their work?
- What kind of operations do you do in spreadsheets?
- Which ones do you think spreadsheets are good for?
  

::::::::::::::::::::::::::::::::::::::::::::::::::

***

:::::::::::::::::::::::::::::::::::::::  challenge

## Question

- Spreadsheets can be very useful, but they can also be frustrating and even sometimes give us incorrect results. What are some things that you've accidentally done in a spreadsheet, or have been frustrated that you can't do easily?
  

::::::::::::::::::::::::::::::::::::::::::::::::::

***

## Problems with Spreadsheets

Spreadsheets are **good for data entry**, but in reality we **tend to
use spreadsheet programs for much more** than data entry. We use them
to create data tables for publications, to generate summary
statistics, and make figures.

Generating **tables for reports** in a spreadsheet is not optimal -
often, when formatting a data table for publication, we're reporting
key summary statistics in a way that is **not really meant to be read
as data**, and often involves **special formatting** (merging cells,
creating borders, making it pretty). We advise you to do this sort of
operation within your document editing software.

The latter two applications, **generating statistics and figures**, should
be used with caution: because of the graphical, drag and drop nature of
spreadsheet programs, it can be very difficult, if not impossible, to
replicate your steps (much less retrace anyone else's), particularly if your
stats or figures require you to do more complex calculations. Furthermore,
in doing calculations in a spreadsheet, it's easy to accidentally apply a
slightly different formula to multiple adjacent cells. When using a
command-line based statistics program like R or SAS, it's practically
impossible to accidentally apply a calculation to one observation in your
dataset but not another unless you're doing it on purpose.

### Using Spreadsheets for Data Entry and Cleaning

**HOWEVER**, there are circumstances where you might want to use a
spreadsheet program to produce "quick and dirty" calculations or
figures, and some of these features can be used in **data cleaning**,
prior to importation into a statistical analysis program. We will show
you how to use some features of spreadsheet programs to check your
data quality along the way and produce preliminary summary statistics.

In this lesson, we're going to talk about:

1. [Formatting data tables in spreadsheets](01-format-data.md)
2. [Formatting problems](02-common-mistakes.md)
3. [Dates as data](03-dates-as-data.md)
4. [Basic quality control and data manipulation in spreadsheets](04-quality-control.md)
5. [Exporting data from spreadsheets](05-exporting-data.md)
6. [Data export formats caveats](06-data-formats-caveats.md)

:::::::::::::::::::::::::::::::::::::::: keypoints

- We will discuss good practices for data entry and formatting
- We will not discuss analysis or visualisation

::::::::::::::::::::::::::::::::::::::::::::::::::


