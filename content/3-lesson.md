---
title: Layout
nav: true
---
# The Layout of OpenRefine

-----

### Display 

OpenRefine displays data in a tabular format, similar to how you might view data in a spreadsheet or database. 
- Each row will usually represent a 'record' or 'observation' in the data
- Each column represents a type of information or 'variable'
- Individual bits of data or 'values' live in 'cells' at the intersection of a row and a column

- A limited number of rows of data are displayed to save on memory, however the program is working on ALL rows.
- Adjust the number of rows displayed by selecting 5, 10, 25, 50 etc. at the top left of the table of data. It isn't necessary to show large amounts on the screen as OpenRefine has better ways of exploring the data.

### Working with data in OpenRefine

- Navigate through records using *first/previous/next/last* navigation options at the top right of the table of data or select a specific page 
- Use the drop-down menus at the top of each column to work with data
- Selecting an option in a particular column (e.g., to make a change to the data), affects all the cells in that column 
- Perform changes one column at a time, even when making changes across several columns
- Use the `All` column to reoder and remove columns on mass


###  Rows and Records

OpenRefine has two modes of viewing data: 'Rows' and 'Records'. 
- Rows mode: each row represents a single record in the data set
- Records mode: OpenRefine can link together multiple rows as belonging to the same record 

This is useful when working with `xml` files, MARC records, as well as `csv` files. We will see an example of this later.

{% include figure.html img="ORLayout.png" alt="OpenRefine layout" caption="OpenRefine layout" width="75%" %}

### Undo / Redo

OpenRefine provides Undo and Redo operations to make changes to your data work, going back to your very first action. Find out how this works in the [GREL](https://griffithunilibrary.github.io/data-cleaning-intro/content/6-lesson.html) activities. 

### Saving projects

Projects are saved automatically as you work on them,  so there is no need to save copies as you go along. 

### Opening existing projects

To open an existing project in OpenRefine, click  `Open Project`  from the main OpenRefine screen (in the left-hand menu). 
When you click this, you will see a list of the existing projects and can click on a project's name to open it.

##### Watch this video to see OpenRefine's layout.
<div style="padding:62.66% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/780981536?h=95c2cf6f1c&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Layout of OpenRefine"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

-----

<p align="center">
  <a href="https://griffithunilibrary.github.io/data-cleaning-intro/content/2-lesson.html"><-- BACK</a> |
  <a href="https://griffithunilibrary.github.io/data-cleaning-intro/content/4-lesson.html">NEXT --></a>
</p>
