---
title: GREL
nav: true
---

# Transforming data using GREL 

(General Refine Expression Language)

-----

Transformations in OpenRefine enable manipulations of data in columns. These include:

- Splitting data from a single column into multiple columns (e.g., splitting an address into multiple parts) to enable tidy data – one variable per column.

- Standardising the format of data in a column without changing the values (e.g., removing punctuation, extraneous characters or standardising a date format)

- Extracting data from a longer text string (e.g., finding DOIs within a bibliographic citation)

It can be difficult to read, ingest and process data which has multiple values within the one cell.  OpenRefine has methods to split those values into multiple cells or columns. OpenRefine has several ways to do this. 

First we will clean data using the in-built programming capabilities of General Refine Expression Language (GREL) within OpenRefine. Many GREL expressions are a little like Excel formulae, although they tend to focus on text manipulations rather than numeric functions.


{% capture text %}
- Go to `Species Name` column then `Edit > Text Facet`
A number of species names have an addtional `*` asterix symbol and this was to indicate that the shark was caught in the afternoon.  This is actually an additional variable, AM/PM and not tidy, but we don't need the variable so will remove the `*` from the cells.
- Select `Text filter` and in the left hand search box add `*` and press `return`
- Result - 18 matching rows

Let's remove all the unnecessary `*` by using the GREL command  `value.replace`.
`Value.replace`  is the *command*. What needs to be added to make the *command* work are what are called *arguments* in programming speak. In this case, the arguments are the values of *what needs to be replaced*, and then *what it needs to be replaced with*. The argument is written inside brackets like this  `("value to replace","new value")`.
- Click the down arrow at the top of the  `Species Name`  column.
- Select  `Edit Cells > Transform ...` . 

This will open a window in which you can enter a *GREL expression*. An expression is a combination of the *command* you will be using, plus the *arguments* you will be using to modify the command, i.e. the values that will be changed.
- In the Expression box, type  `value.replace(" *", "")`  to remove all the instances of the *whitespace* followed an `*`  replacing them with nothing `""`.

In this case, the second value is empty since we want to remove ` *` , i.e. replace the *whitespace* and `*` with nothing. You only need to add spaces within the expression if they appear inside the quotation marks. If you do they will be added or removed, depending on within which set of values they appear.

The *Preview* screen will display on the left the cell value as it is before transformation, and on the right, what the value will be after the expression has run. This allows you to correct any errors in writing the expression, e.g., adding spaces where they are not needed, using unmatching quote marks. 
- Click  `OK`.

The  `Species Name`  column should now contain no `*`.{% endcapture %} {% include card.md header="Activity - transforming data using GREL" text=text %}

It is easy to re-use GREL expressions, as OpenRefine provides a history of commands. You can select them and reuse as is or make changes. Let's try this with the uneccesary and untidy addition of `, QLD` on the end of some values in the  `Area`  column.

{% capture text %}
- at  `Area` column, select  `Edit cells > Transform ...`
- click the  `History`  tab
- click on the first  `Reuse`  option
- click inside the expression box, change character  `" *",""` to `", QLD ",""`  (i.e. space & asterix character to comma, space character and QLD)
- preview to check correctness
- click  `OK`.{% endcapture %} {% include card.md header="Activity - repeat transformation steps by using History" text=text %}

##### See the steps taken in this video. 
<div style="padding:75% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/782366289?h=369fe1bb1e&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;" title="GREL_Shark.mp4"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

-----

### Undo and Redo

It is common while exploring and cleaning a dataset to discover after you've made a change that you really should have done something else first. OpenRefine provides *Undo* and *Redo* operations to make this easy, no matter how far along you have gone.

{% capture text %}
- Click where it says  `Undo / Redo`  on the top left side of the screen. All the changes you have made so far are listed here.
- Click on the previous step, before *Text transform on 17 cells in column Area.....* to remove that step.
- Visually confirm that the `, QLD` data has been re added to the cells.
- Click on the final step to do the text transformation to the 17 cells again.
- Click on the `Facet/Filter` tab to exit the `Undo/Redo` feature.{% endcapture %} {% include card.md header="Activity - Undo" text=text %}

-----

<p align="center">
  <a href="https://griffithunilibrary.github.io/data-cleaning-intro/content/5-lesson.html"><-- BACK</a> |
  <a href="https://griffithunilibrary.github.io/data-cleaning-intro/content/7-lesson.html">NEXT --></a>
</p>
