---
title: Formatting data tables in Spreadsheets
teaching: 10
exercises: 20
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
- Sebastian Kupny
---

::::::::::::::::::::::::::::::::::::::: objectives

- Describe best practices for data entry and formatting in spreadsheets.
- Apply best practices to arrange variables and observations in a spreadsheet.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How should data be formatted in spreadsheets?

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: instructor

### Narrative Guidance

- Go through the point about keeping track of your steps and keeping raw data raw
- Go through the cardinal rule of spreadsheets about columns, rows and cells
- Hand them a messy data file and have them pair up and work together to clean up the data.
  *Give them 15 minutes to do this.*
- Ask for what people did to clean the data. As they bring up different points you can
  refer to them in the 02-common-mistakes.md file, or expand a bit on the point they brought up.
  If you are just teaching the lesson, it would be good to familiarize yourself with
  the set of mistakes in 02-common-mistakes. All these mistakes are present in the messy
  dataset.
- If you get a response where they've fixed the date, you can pause and go to the
  03-dates-as-data.md lesson. Or you can say you'll come back to dates at the end.
  There's an exercise in that file about how to change the
  date into three columns using Excel's built in MONTH, DAY, YEAR functions. Have them
  run through that exercise.

:::::::::::::::::::::::::::::::::::::::::::::::::::

The most common mistake made is treating the program like it is a notebook by relying on context, notes in the margin, spatial layout of data and fields to convey information.
As humans,
we can (usually) interpret these things,
but computers are unintelligent,
and unless we explain to the computer what every single thing means
(and that can be hard!)
it will not be able to see how our data fit together.

Using the power of computers,
we can manage and analyze data in much more effective and faster ways,
but to use that power,
we have to set up our data for the computer to be able to understand it
(and computers are very literal).

This is why it's extremely important to set up well-formatted tables from the outset **before** you even start collecting data to analyse.
**Data organization is the foundation of your data-related work.**
Unorganized data can make it harder to work with your data,
so you should be mindful of your data organization when doing your data entry.
You'll want to organize your data in a way that allows other programs and people to easily understand and use the data.

:::::::::::::::::::::::::::::::::::::::::  callout

## Callout

**Note:** the best layouts/formats (as well as software and
interfaces) for **data entry** and **data analysis** might be
different. It is important to take this into account, and ideally
automate the conversion from one to another.


::::::::::::::::::::::::::::::::::::::::::::::::::

### Keeping track of your analyses

When working with spreadsheets during data clean up or analyses, it's
very easy to end up with a spreadsheet that looks very different from the one
you started with. In order to be able to reproduce your analyses or figure out
what you did when your leadership team ask for a different analysis,
you **must:**

- **create a new file or tab with your cleaned or analyzed data.** Do
  not modify that original dataset, or you will never know where you
  started!
- **keep track of the steps you took in your clean up or analysis.**
  You should track these steps as a scientist would each step in an
  experiment. You can do this in another text file, or a good option
  is to create a new tab in your spreadsheet with your notes. This way
  the notes and data stay together. Be sure you're saving your spreadsheet
  with a file format compatible with multiple tabs, if you do this!

This might be an example of a spreadsheet setup:

![](fig/spreadsheet-setup.png){alt='spreadsheet setup'}

We will put these principles into practice today during your exercises.

### Structuring data in spreadsheets

The cardinal rules of using spreadsheet programs for data:

1. Put all your **variables in columns** - the thing you're measuring,
  like 'length' or 'attendance'.
2. Put each **observation in its own row**.
3. **Don't combine multiple pieces of information in one
  cell**. Sometimes it just seems like one thing, but think if that's
  the only way you'll want to be able to use or sort that data.
4. **Leave the raw data raw** - don't mess with it!
5. Export the cleaned data to a **text based format** like CSV. This
  ensures that anyone can use the data, and is the format required by
  most data repositories.

For instance, we have data from attendance and instruction for previous
research data management workshops. Different people have entered data into a
single spreadsheet. They keep track of things like date, number of attendees, and
who delivered the workshop.

If they were to keep track of the data like this:

![](fig/multiple-info.png){alt='multiple-info example'}

the problem is that the number of attendees of different types (post-graduate
researcher (PGR), post-doctoral research associate (PDRA), and other) are in
the same field. So if they wanted to look at attendance by post-graduate
researchers, it would be hard to set up the data to do this. If instead we
put attendee categories in different columns, you can see that it would be much
easier.

### Columns for variables and rows for observations

The rule of thumb, when setting up a datasheet, is **columns =
variables**, **rows = observations**, **cells = data** (values).

So, instead we should have:

![](fig/single-info.png){alt='single-info example'}

:::::::::::::::::::::::::::::::::::::::  challenge

## Exercise

We're going to take a messy version of some library training data and clean it up.

1. First [download the data](data/training_attendance.xlsx)
2. Open up the data in a spreadsheet program.
3. You can see that there are three tabs. Various people have recorded
  training attendance statistics over 2016 and 2017, and they have
  kept track of the data in their own way. Now you're being asked to
  evaluate the training programme and you want to be able to start
  doing statistics with the data.
4. With the person next to you, work on the messy data so that a
  computer will be able to understand it. Clean up the 2016 and 2017
  tabs, and put them all together in one spreadsheet.
5. After you go through this exercise, we'll discuss as a group what you think was wrong
  with this data and how you fixed it.
  

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::  callout

## Important

Do not forget of our first piece of advice:
**create a new file** for the cleaned data, and **never
modify the original (raw) data**.


::::::::::::::::::::::::::::::::::::::::::::::::::

An excellent reference, in particular with regard to R scripting is

:::::::::::::::::::::::::::::::::::::::::  callout

## Resource

Hadley Wickham, *Tidy Data*, Vol. 59, Issue 10, Sep 2014, Journal of
Statistical Software. [http://www.jstatsoft.org/v59/i10](https://www.jstatsoft.org/v59/i10).


::::::::::::::::::::::::::::::::::::::::::::::::::

<!-- *Instructors see notes in 'instructors_notes.md' on this exercise.* -->

:::::::::::::::::::::::::::::::::::::::: keypoints

- Use one column for one variable
- Use one row for one observation
- Use one cell for one value
- Never modify your raw data. Always make a copy before making any changes.
- Keep all of the steps you take to clean your data in a plain text file.

::::::::::::::::::::::::::::::::::::::::::::::::::


