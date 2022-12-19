---
title: Numbers
nav: true
---
# Examining Numbers & Dates in OpenRefine

When a table is imported into OpenRefine, all data is formatted as *strings*, basically a piece of text. We can sort column values as numbers, but this does not change the data type in a column from text to numbers. Rather, this interprets the values as numbers for the purposes of sorting but keeps the underlying data type as is.

We can, however, transform columns to other data types (e.g., number or date) using the  `Edit cells > Common transforms`  feature. Here we will experiment changing columns to numbers and see what additional capabilities that gives us.

Be sure to close any facets you have enabled from the left panel before this step, so that we can be sure we are working on the complete dataset. You can close an existing facet by clicking the  `x`  in the upper left of that facet window.


### Date formatting

So far we’ve been looking only at ‘String’ type data. It is possible to treat numbers and dates as strings. For example in the Date column the data of capture is represented as a String. However, some operations and transformations only work on ‘number’ or ‘date’ type data, such as sorting values in numeric or date order. To carry out these functions we need to convert the values to a date or number first.

{% capture text %}
To transform cells in the  `Date`  column to date format:
- Click the down arrow for the  `Date` column
- Select  `Edit cells > Transform`
- In the ‘Expression’ box type the GREL expression `value.toDate("dd/MM/yyyy")`
- OK
The values are now displayed in green and follow a standard convention for their display format (ISO 8601) - this indicates they are now stored as date data types in OpenRefine. We can now carry out functions that are specific to dates.

Let's create another column with a different date format.
- On the `Date` column dropdown select `Edit column->Add column based on this column`. Using this function you can create a new column, while preserving the old column
- In the  `New column name` type “Formatted-Date”
In the ‘Expression’ box type the GREL expression `value.toString("dd MMMM yyyy")`.{% endcapture %} {% include card.md header="Activity - tranforming text to date formats" text=text %}

Other common transformations include changing letter case, data formats and more. Take a look at the other options with `Edit cells>  Common transforms`.

### Numeric facets

Sometimes there are non-numeric values or blanks within a column which may represent errors in data entry. We can find these by using a  `Numeric`  facet.

{% capture text %}
- Click the down arrow for the  `Water Temp (C)` column
- Select  `Edit cells > Common Transforms > To number` (another easy method to transform data type)
- Edit a few cells, replacing the numbers with text, such as "abc", and make a few other cells blank. Change the `Data type` to `text` before applying.
- Click down arrow again and select `Facet > Numeric facet`.

A histogram (a representation of the distribution of numerical data) opens in the left hand menu. 
Notice that there are several checkboxes in this facet,  `Numeric`,  `Non-numeric`,  `Blank`,  `Error`.
Below these are counts of the number of cells in each category. You should see checks for  `Non-numeric`  and  `Blank`  if you changed or deleted some values.
- experiment with checking or unchecking these boxes to select subsets of your data.
- when finished exploring, close this facet by clicking the  `x`  in the upper left corner of its panel.

Note that closing a facet will not undo the edits you have made to the cells in this column.
- Use the  `Undo / Redo`  function to reverse these changes.{% endcapture %} {% include card.md header="Activity - numeric facet" text=text %}

##### Watch this video to find out how do perform the steps above.

<div style="padding:65.63% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/782406598?h=036f742c2e&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Dates an numbers in OpenRefine"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

-----

<p align="center">
  <a href="https://griffithunilibrary.github.io/data-cleaning-intro/content/6-lesson.html"><-- BACK</a> |
  <a href="https://griffithunilibrary.github.io/data-cleaning-intro/content/8-lesson.html">NEXT --></a>
</p>
