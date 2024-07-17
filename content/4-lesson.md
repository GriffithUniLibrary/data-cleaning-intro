---
title: Facets
nav: true
---
# Facets & Clustering 

--------

### Facets
Faceting is a useful feature of OpenRefine and can help you:
- Get an overview of the data in a project
- Get counts of data in specific columns
- Help you identify missing, misspelled or inconsistent data.

A common use case for your data might be where you want to know how many times a particular value appears in a column in your data.

A 'Facet' groups all the like values that appear in a column, and then allows you to filter the data by these values 
and edit the values for a number of records in one go.


{% capture text %}
The first facet to explore is  `Text facet`. It groups all the identical text values in a column and lists each value and the number of records in which that value appears. Facet information always appears in the left-hand panel in the OpenRefine interface.

Here we will use faceting to look at the values represented in the  `Area` column.

- Scroll over to the  `Area` column.
- Click the down arrow and choose  `Facet > Text facet`.

In the left panel, you will now see a box containing every unique value in the `Area` column, along with a number representing how many times that value occurs in the column.  There are also some blank values to identify later.  At the top of the box you can sort the results by name and count. A great feature for exploring a large dataset.

- Try sorting this facet by name and by count. How are they sorted? (name is alphabetical and count is largest first).
- Which areas have the highest and lowest shark catches? (Townsville is the highest, Bribie Island the lowest).
- Close facet by clicking the  `x`  in top corner of the Facet panel.{% endcapture %} {% include card.md header="Activity – Looking at data through Facets" text=text %}


{% capture alert %}*Note:* Always close facets when you are finished with them, so as not to affect future facets or results.
{% endcapture %}
{% include alert.md text=alert color="warning" %}

You can also amend data with Facets.

In this next activity you want to limit to a sub-set of this data, with records from the south of the Cairns `Area` only. 
{% capture text %}
- Scroll to  `Area`  Column.
- Click the down arrow and choose  `Facet > Text facet`. Unique values will be displayed in left hand panel.
- Click on the choices in the facet, or hover over them,  `edit`  and  `include`  functions appear.
- Hover over *Cairns* and use `include`  function to narrow results just to those records.
- Check how many records display? (39).
- Now use  `Exclude`  to return to all records.
- Use  `include`  function again for values  `Cairns`.
- Remove all these records from the dataset.
- Select  `All column > Edit rows > Remove all matching rows`.
- This value is now displayed in red and missing counts. Click  `reset`.
- How many records are now available? (429)
- Close the facet.{% endcapture %} {% include card.md header="Activity - amending data through Facets" text=text %}

You can also edit values using the facets feature. 
{% capture text %}
- Use faceting to look at the  `Species Name`  Column.
- What are the results? 34 value choices. Do you see different representations of the same value?
- Hover over  *BULL WHALERS* and choose  `Edit` correct the spelling to *BULL WHALER* then select `Apply`. This changes all five incorrect records.
- Do this again for *COMMON BLACKTIP WHALERS* to correct the spelling for all records at once.
- Do you now have 32 value choies for the variable `Species Name`? 
- We will explore the other representations of values in another exercise.
- Close facet{% endcapture %} {% include card.md header="Activity – fixing errors with Facets" text=text %}

The *Species Name* values are represented in all capital letters. Let's change this using a `Common transforms` to titlecase. 
{% capture text %}
- Select `Species Name > Edit cells > Common transforms > To titlecase`.
Now the case format is consistent throught the dataset.{% endcapture %} {% include card.md header="Activity - fix font case with `Common transforms`" text=text %}

##### Watch these steps in the video below.

<div style="padding:65.63% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/781293593?h=9808616cb4&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Facets in OpenRefine"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

OpenRefine's many transformations functions will be explored further soon.

----

#### More on Facets

As well as  `Text facets`, OpenRefine supports other types of facets. These include:

- `Numeric facets`  : displays a graph and includes 'drag and drop' controls to set a start and end range to filter the data displayed. Explore these later in the lesson on [Examining Numbers in OpenRefine](https://griffithunilibrary.github.io/data-cleaning-intro/content/7-lesson.html).
- `Timeline facets` : displays a histogram with values sorted chronologically.  This only works on cells formatted as 'date' data type.
- ` Customized facets`  provide a range of different facets including:
  - `Word facet`  - to break down text into words and count the number of records each word appears in
  - `Duplicates facet`  - this results in a binary facet of 'true' or 'false'. Rows appear in the 'true' facet if the value in the selected column is an exact match for a value in the same column in another row.
  - `Text length facet`  - creates a numeric facet based on the length (number of characters) of the text in each row for the selected column. This can be useful for spotting incorrect or unusual data in a field where specific lengths are expected (e.g., if the values are expected to be years, any row with a text length of more than 4 for that column is likely to be incorrect.)
  - `Facet by blank (null or empty)`  - a binary facet of 'true' or 'false'. Rows appear in the 'true' facet if they have no data present in that column. This is useful when looking for missing data.


{% capture text %}
Use a  `Customized facet`  to find out how many records are missing *Water Temp (C)* values. This facet shows *true* or *false* results.
- Select  `Facet > Customized facets > Facet by blank (null or empty)`.
- Hover over the *false* results and select `include`.

This result is a totals line which we don't need, let's remove it.
- Select  `All column > Edit rows > Remove all matching rows`.
- This value is now displayed in red and missing counts. Click  `reset`.
- How many records are now available? (428){% endcapture %} {% include card.md header="What data is missing in  `Water Temp (C)`  column?" text=text %}

--------

### Clustering

Another very useful feature of OpenRefine is Clustering.  In OpenRefine, clustering means 'finding groups of different values that might be alternative representations of the same thing'. For example, the text strings 'New York', 'new york'  or 'New Yrok' very likely refer to the same concept.

Clustering is a very powerful tool for identifying and fixing datasets which contain misspelled or mistyped entries.

OpenRefine has several clustering algorithms built in. Let's experiment with them.
{% capture text %}
- Create a Text Facet for  `Location` column, scroll through the list.  You will notice a number of values that are likely mis-typed entries.
- Click the  `Cluster`  button, on the top right of the facet. In the resulting pop-up window, different cluster methods and algorithms are available via drop down boxes.
- the  `key collision`  method and  `fingerprint`  keying function is the first displayed. 
- Try selecting different Methods and Keying Functions combinations, to see if merges are suggested. 
- When a merge is suggested the value with the most rows is suggest as the new cell value, you can change that by clicking on one of the other options or typing a new value name.
- Select the new value names by ticking the boxes.
- Click the  `Merge?`  box beside the cluster, then click  `Merge Selected and Re-cluster`  to apply the corrections to the dataset.
- There may be a few more clusters, to fix misspellings, typos, capitalisation, hyphens, etc.
- How many choices are now shown in the facet? Depending on your merges, there may be 63 choices remaining.
- Close the facet.{% endcapture %} {% include card.md header="Activity – fixing errors via Clustering" text=text %}
{% capture alert %}*Note:* Some merges are not necessary. The function `cologne-phonetic` will find *Miami Beach* and *Main Beach* as potential variants.  These are valid values, there is no need to merge these.
{% endcapture %}
{% include alert.md text=alert color="warning" %}

##### Watch this video to learn the Clustering function.

<div style="padding:75% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/781332471?h=61722a29b0&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;" title="ClustersInOpenRefine.mp4"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

----

### Different clustering algorithms

Detailed information on the different clustering algorithms and combinations is available here: [https://docs.openrefine.org/manual/cellediting#clustering-methods](https://docs.openrefine.org/manual/cellediting#clustering-methods).

-----

<p align="center">
  <a href="https://griffithunilibrary.github.io/data-cleaning-intro/content/3-lesson.html"><-- BACK</a> |
  <a href="https://griffithunilibrary.github.io/data-cleaning-intro//content/5-lesson.html">NEXT --></a>
</p>
