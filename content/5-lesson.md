---
title: Filter
nav: true
---

# Filter and Sort

------

### Filtering

There are many records in this dataset and you can filter them to work on a subset. Let's explore filtering by a word within the text values of a column.

{% capture text %}
- Click the down arrow next to  `Location > Text filter`.  A filter box will appear in the left margin
- Type *'bay'* and press return. There are 99 matching rows of the original 428 rows (and these rows are selected for the subsequent steps).
- Limit the results to one of the locations with *'Bay'* in the name. There are a couple of possibilities.
- Do  `Facet > Text facet`  on the  `Location`  column after filtering. This will show 8 locations with names that match your filter.
- To restrict to only one of these locations, select one to include.
- Close the facet and filter.{% endcapture %} {% include card.md header="Activity - filter to work on a subset of data" text=text %}

Faceting and filtering look very similar. A good distinction is that faceting gives you an overview, description and count of all of the data that is currently selected, while filtering allows you to select a subset of your data by a string - of text in this case - for analysis or cleaning.

##### Watch this video on filtering

<div style="padding:75% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/781345919?h=ac3a2cea9a&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;" title="FilterInOpenRefine.mp4"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

---

### Working with columns 

*Removing columns*

You can reorder the columns by clicking the drop-down menu at the top of the first column labelled `All`.
{% capture text %}
The `Number Caught` column shows that each observation is about one shark, so this variable is reduntant and needs to be removed. 

To do this:
- `Edit columns > Re-order / remove columns …`
- Drag `Number Caught` to the right hand side of the menu
- `Ok`{% endcapture %} {% include card.md header="Activity - remove columns" text=text %}

*Reordering columns*

You can also drag and drop column names to reorder the columns.

*Renaming columns*

You can rename a column by opening the drop-down menu at the top of the column that you would like to rename, and choosing `Edit column > Rename this column'. You will then be prompted to enter the new column name.

------

### Sorting data
Using `Area` variable, let's explore data using sorting.

{% capture text %}
- In  `Area`  column select drop-down menu and  `Sort`.   Options include:
  - Sort by text
  - Sort by numbers
  - Sort by dates
  - Sort by booleans (TRUE or FALSE values). 
- Select  `text`
- Additional options will then appear for you to fine-tune your sorting, select  `a-z`
- You can also specify what order to put `blanks` and `errors` in the sorted results
- Drag and move `blanks` and `errors` boxes to the top of the list. 
- `Ok`
- The dataset is now sorted in alphabetical order by Area.

When performing the first sort, you will notice the drop-down menu for the selected column shows  `Sort ...` 

If you try to re-sort a column that you have already used, the drop-down menu changes slightly, to  `> Sort`  without the  `...`, to remind you that you have already used this column. Additional options include:

  - `Sort > Sort ...` - This option enables you to modify your original sort.
  - `Sort > Reverse` - This option allows you to reverse the order of the sort.
  - `Sort > Remove sort` - This option allows you to undo your sort.
- Remove this sort.{% endcapture %} {% include card.md header="Activity - sort by text" text=text %}

------

### Sort by multiple columns

You can also sort by multiple columns and this makes it easier to explore data easily before analysis and processing. Do this by performing a sort on additional columns.

The sort results will depend on the order in which you select columns to sort.

To restart the sorting process with a specific column, check the  `sort by this column alone`  box in the  *Sort pop-up menu*.

If you go back to one of the already sorted columns and select `Sort > Remove sort` , that column is removed from your multiple sort. If it is the only column sorted, then data reverts to its original order.

{% capture text %}
- Sort  `Area` again, select  `Sort... > text and a-z`
- Add an additional sort by  `Location`, select  `Sort... > text and a-z`
- It is now easy to see an alphabetically list of all the locations in Bundaberg.
- Remove sort{% endcapture %} {% include card.md header="Activity - sort by multiple columns" text=text %}

Sorts in OpenRefine are temporary. If you remove the Sort, the data will go back to its original unordered state.

The Sort drop-down menu at the top of the screen also lets you amend the existing sort to:
- Reverse the sort order
- Remove existing sorts
- Reorder rows permanently.

### Find and fix missing values by sorting

Let’s try to find if there are missing values for the `Species Code` variable.

{% capture text %}
- In  `Species Code` column, select  `Sort... > numbers` 
- in pop up box select `smallest first` and reposition `Errors & Blanks` to the top of the column.
- `Ok`

Notice the first three values are missing. They are all associate witht the species name `Tiger Shark`. You may be able to identify the missing value by other variable attributes.

When you know your data or look at the variable in context with other similar observations you can identify what type of data problem might be occurring and possible solutions.

In this case, you could search other variables such as `Species Name` to identify correct Species Code details.
- Keep the current sort on `Species Code` then
- Go to `Species Name`, `Edit > Text Facet`
- Scroll down to and hover over `Tiger Shark` then click `include`

It is now possible to see the missing code `37018022` which matches the species name `Tiger Shark`
- Highlight and copy `Cntr C` the Species Code
- Hover over empty cell `Edit`
- Paste Species code in popup box
- Select `Apply to All Identical cells` button. This will fill all the empty cells with the same value.

Notice the yellow Mass Edit notice listing how many records were changed.{% endcapture %} {% include card.md header="Activity - find & fix missing values by sorting" text=text %}

##### Watch the steps to sort data in this video.

<div style="padding:75% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/781366985?h=1a484c9e0f&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;" title="SortingInOpenRefine.mp4"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

-----

<p align="center">
  <a href="https://griffithunilibrary.github.io/data-cleaning-intro/content/4-lesson.html"><-- BACK</a> |
  <a href="https://griffithunilibrary.github.io/data-cleaning-intro/content/6-lesson.html">NEXT --></a>
</p>

