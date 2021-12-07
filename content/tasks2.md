---
layout: default
title: Tasks
parent: Part 2
nav_order: 2


---
# Tasks
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Introduction

## Data import

*How to import .csv or .txt files into Excel*

Make sure to extract both files from the downloaded archive prior to the data import!

Step 1
{: .label .label-step}

Open new workbook.  

{: .step}

Step 2
{: .label .label-step}

Choose File -> Import in the Excel menu

{: .step}

Step 3
{: .label .label-step}

Select type **CSV file** and select the *bc-popular-boys-names.csv*

{: .step}

Step 4
{: .label .label-step}

In the Text Wizard select Delimited and choose Semicolon as the delimiter. Make sure that the preview looks correct

  ![image-20211207000421068](images/image-20211207000421068.png)

{: .step}

Step 5
{: .label .label-step}

We are only planning to use the data from the last 10 years (2010-2019). Therefore, the columns for 1920-2009 can be skipped. 

Click on the 1920 column and select **Do not import column**. Press Shift and scroll down to the column for 2009, click on it and click on **Do not import column** again. Make sure that only columns 1920-2009 are labeled as Skip. Other columns (Name, 2010, 2011, ..., 2019, Total) should be labeled General.

  ![image-20211207001152333](images/image-20211207001152333.png)

  ![image-20211207001346050](images/image-20211207001346050.png)

{: .step}

Step 6
{: .label .label-step}

Rename the current sheet to "Boys" and follow the same procedure for the Girls data (file *bc-popular-girls-names.csv*) 

{: .step}

## Data Operations

### Combining sheets

*Working with two (or more) sheets simultaneously* 

We now have two sheets with the same structure (Name, years 2010-2019 and Total) for boys and girls. 

Suppose we want to add another column **Max Year** to store the maximum value in the period 2010-2019 for each name. If the sheets have the same structure, we can do it simultaneously: 

Step 1
{: .label .label-step}

With *Boys* sheet open, press Shift and click on the *Girls* sheet. Make sure both sheets are selected:

![image-20211207131253554](images/image-20211207131253554.png)

{: .step}

Step 2
{: .label .label-step}

Continue to work on the *Boys* sheet. Add a name for the new column, for example, **Max Year**. 

{: .step}

Step 3
{: .label .label-step}

Add formula to the second cell to select the maximum over the ten years period.

<details>
<summary>Formula (click to open)</summary>
<br>
`=MAX(B2:K2)`
</details>

{: .step}

Step 4
{: .label .label-step}

Drag the formula down until the last row. 

<details>
<summary>Easy way to drag formula down</summary>
<br>
Double-click the bottom right of the cell (little square thingy that you usually drag down)
</details>

{: .step}

Step 5
{: .label .label-step}

Now switch over to the *Girls* sheet. The new column should appear there as well.

*Note*: Due to the difference in the number of rows, for *Girls* sheet formula is filled until the 2000th row. You can drag it down further manually or use shortcut from the previous step. 

{: .step}

### Index-Match

For **Max Year** column, it can be interesting to see not the maximum value itself, but rather the year during which this maximum value was captured. This may be done using a combination of INDEX() and MATCH() formulas.

Step 1
{: .label .label-step}

Select both sheets using Shift, similar to how we did it in the last exercise. 

{: .step}

Step 2
{: .label .label-step}

First, we need to find what column <u>matches</u> with the maximum value. To do that, we can use `MATCH()` function that has a following syntax:

`=MATCH(lookup_value, lookup_array, [match_type])`

<details>
<summary>Answer (click to open): </summary>
<br>
`=MATCH(MAX(B2:K2),B2:K2,0)`
</details>

{: .step}

Step 3
{: .label .label-step}

After getting the index of a column that has a maximum value, we need to get the name of that column (or a year, corresponding to this column). Let's use `INDEX()` for that purpose:

`=INDEX(array, row_num, [column_num])`

<details>
<summary>Answer (click to open): </summary>
<br>
`=INDEX(B1:K1,1,MATCH(MAX(B2:K2),B2:K2,0))`
</details>

{: .step}

Step 4
{: .label .label-step}

The combination of INDEX and MATCH gives us the exact year in which the maximum was reached. However, if we drag the formula now, the `array` argument for `INDEX` will change, so we need to fix it using the absolute references:

<details>
<summary>Answer (click to open): </summary>
<br>
`=INDEX($B$1:$K$1,1,MATCH(MAX(B2:K2),B2:K2,0))`
</details>

{: .step}

Step 5
{: .label .label-step}

Drag the formula down to fill all the cells. 

{: .step}

### Named Range

In the formula for the **Max Year** we have an absolute reference to lookup the column names ($B$1:$K$1), and a relative reference to the number of uses corresponding to each individual row (B2:K2). 

For the usuability and overall clarity (for example, if you are sharing your workbook with someone else who may wonder what the formula means), we can fix the absolute reference and give it a name, similiar to creating variables when programming.

Step 1
{: .label .label-step}

On the Formulas tab select **Define Name**

![image-20211207141746576](images/image-20211207141746576.png)

{: .step}

Step 2
{: .label .label-step}

Enter a name for the data range, for example, *years*

{: .step}

Step 3
{: .label .label-step}

Since we are working simultaneously with two sheets it is better for the Named Range to be independent from the sheet name. Therefore, you can specify the following range:

`=$B$1:$K$1` (do not forget the equal sign in front)

Click OK.

{: .step}

Step 4
{: .label .label-step}

You can now rewrite the formula in the M2 using the *years* Named Range:

<details>
<summary>Answer (click to open): </summary>
<br>
`=INDEX(years,1,MATCH(MAX(B2:K2),B2:K2,0))`
</details>

{: .step}

