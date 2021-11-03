---
layout: default
title: Tasks
parent: Content
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

## Intro


*Getting familiar with basic objects in Excel* 

Step 1
{: .label .label-step}
1. Open new workbook.  
2. Choose File -> New in the Excel menu or press Ctrl+N (Cmd+N on Mac)  
![](images/image-20210926205209032.png)
{: .step}

Step 2
{: .label .label-step}
1. Create new worksheet.  
2. In the opened workbook click on a plus in the bottom panel on the left ![image-20210926205404343](images/image-20210926205404343.png)
{: .step}

Step 3
{: .label .label-step}
Read more about difference between Workbook and Worksheet objects   [SOURCE]
{: .step}

## Data Types


*Switching between data types*

Most of the data is defined as a General type, unless specified otherwise. To learn what type a specific column is, select the range of values and check the dropdown list value in the Home tab. 


**Hint**: the default alignment used by Excel suggests the data type too: numbers are aligned to the right, while text is aligned to the left.


Step 1
{: .label .label-step}
What type is `Group` column?  
{: .step}

Step 2
{: .label .label-step}
What type is `District Code` column?
{: .step}

Step 3
{: .label .label-step}
Change `District Code` column to be Text.  
Select values in `District Code` column (or select all the values in the column by clicking on the `A` in the column names pane) and then select **Text** instead of General  
![](images/image-20210926211001795.png)
{: .step}

## Number as Dates

*How to avoid having numbers stored as dates*

Step 1
{: .label .label-step}
Try to put `1-20` in the first row of the `Group-District Code` column  
{: .step}

Step 2
{: .label .label-step}
1. Select filled cell (`D5`) and change type to be Text. Did it work?  
2. Unfortunately, Excel does not allow to switch between dates and text after the transformation has been done. However, we may prevent the automatic switch to the date format by choosing the format of column.
{: .step}

Step 3
{: .label .label-step}
Delete the value in the cell. Change the `Group-District Code`  column to be Text. Now. fill the first 5 values manually following the pattern (`1-20`, `2-20`,`3-20`, `4-20`,`TOTAL-20` ).  
{: .step}

### Link: Prevent Excel from changing numbers into dates 
[Datawrapper Academy](https://academy.datawrapper.de/article/89-prevent-excel-from-changing-numbers-into-dates)

## Autofill


*How to fill values based on the pattern*

We now can fill the rest of the patern using Autofill option.

**Hint**: you can also use `CONCAT` formula to fill the pattern using values from `Group` and `District Name` columns. Please note, that in this case you need to change column type to be General for the formula to work.

Step 1
{: .label .label-step}
Select first 5 rows of `Group-District Code` column and drag the fill handle down  
![](images/image-20210926212807828.png)
{: .step}

### Link: Microsoft guide on using autofill 
[Microsoft Support](https://support.microsoft.com/en-us/office/copy-a-formula-by-dragging-the-fill-handle-in-excel-for-mac-dd928259-622b-473f-9a33-83aa1a63e218)

## Sorting


*Explore existing sorting options*

Step 1
{: .label .label-step}
1. Sort data by the total number of students (ascending order).  
2. Select the `Number of Students` column header (cell `E4`) and click Sort A to Z in the Data menu tab.  

**Hint**: Applying Filter allows to use different sorting options as well  
![](images/image-20210926213258804.png)
{: .step}

Step 2
{: .label .label-step}
1. Add another level of sorting, `District Code`.  
2. Follow the previous step now for `District Code` column, or use Sort option in the Data menu to add several rules and change their hierarchies.  
![](images/image-20210926213913533.png)
{: .step}

## Filter 


*Removing errors using Filter*


Step 1
{: .label .label-step}
Apply Filter (located in the Data menu) to the `District Code` column.   
![](images/image-20210926214341684.png)
{: .step}

Step 2
{: .label .label-step}
Select rows with blank District Code  
![](images/image-20210926214441951.png)
{: .step}

Step 3
{: .label .label-step}
Right click on selected rows and select option "Delete Rows"  
![](images/image-20210926214539172.png)
{: .step}

Step 4
{: .label .label-step}
Make sure you do not have any blanks left  
![](images/image-20210926214706616.png)
{: .step}

### Link: 3 ways to remove empty rows 
[Ablebits blog](https://www.ablebits.com/office-addins-blog/2013/10/01/remove-blank-rows-in-excel/)

## Find and Replace 


*Working with missing or masked values*


Step 1
{: .label .label-step}
1. Use Replace to find all "Msk" entries  
2. In the Find&Select option of main menu select Replace option or click Ctrl+H (both for PC and Mac);
![](images/image-20210926214917173.png)
{: .step}

Step 2
{: .label .label-step}
1. Replace "Msk" with blank.  
2. Do not put anything in the Replace field, not even a space
![](images/image-20210926215139163.png)
{: .step}

Step 3
{: .label .label-step}
1. Use Go-To-Special to highlight blank cells  
2. Select the table area (not including headers) and select Go To Special from the Find&Select options. Click Fill Color to highlight selected cells 
![](images/image-20210926215537641.png)
![](images/image-20210926215656596.png)
{: .step}

### Link: Filling empty cells using Go To Special 
[Spreadsheet Planet's tutorial](https://spreadsheetplanet.com/fill-blank-cells-with-value-above-in-excel/)

# Formulas


## Intro to Formulas


*Using SUM, AVG, COUNT*


**Hint**: instead of using the formulas directly, you can also see these metrics (count, avg, sum) in the bottom right corner of  the working area when selecting any range.


Step 1
{: .label .label-step}
Count how many observations contain number of test takers  
<details>
<summary>Answer (click to open)</summary>
<br>
`COUNT(F5:F49)`
</details>

{: .step}

Step 2
{: .label .label-step}
Calculate total sum of the `Number of Student` column  
<details>
<summary>Answer (click to open)</summary>
<br>
`SUM(E5:E49)`
</details>

{: .step}

Step 3
{: .label .label-step}
Find the average value of the `Score` column  
<details>
<summary>Answer (click to open)</summary>
<br>
`AVG(G5:G49)`
</details>

{: .step}

### Link: Basic Excel Formulas 
[Corporate Finance Institute](https://corporatefinanceinstitute.com/resources/excel/study/basic-excel-formulas-beginners/)

### Link: When to use absolute and relative references 
[Microsoft Support](https://support.microsoft.com/en-us/office/switch-between-relative-absolute-and-mixed-references-dfec08cd-ae65-4f56-839e-5f0d8d0baca9)

## Logical Functions


*Calculate some metric if condition is true*


Step 1
{: .label .label-step}
Create a new column `Percent of Test Takers`  
{: .step}

Step 2
{: .label .label-step}
Use IF to get the percent of test takers for the Total values only:  


<details>
<summary>Answer (click to open)</summary>
<br>
`IF(C5="TOTAL",F5/E5,"")`
</details>
{: .step}

## Conditional Summary


*Using SUMIF and SUBTOTAL*


SUMIF is a conditional summary, which works identical to the SUM function when a certain condition is true. SUBTOTAL is used to calculate different aggregate functions (sum, avg, etc.). Use 1 as the first parameter to calculate average.

Step 1
{: .label .label-step}
Open `Summary` sheet  
{: .step}

Step 2
{: .label .label-step}
Get the total number of test takers using `SUMIF()`;  

**Hint**:  Use "Data!" in front of the cell name (e.g. Data!C2) to reference a cell from the sheet named Data.  

<details>
<summary>Answer (click to open)</summary>
<br>
`SUMIF(Data!C5:C49,"TOTAL",Data!F5:F49)`
</details>
{: .step}

Step 3
{: .label .label-step}
Get the total number of test takers in Burnaby and Coquitlam using `SUBTOTAL()` .  

**Hint:** Filter the table to select only rows related to these two districts.

<details>
<summary>Answer (click to open)</summary>
<br>
`SUBTOTAL(9,Data!F5:F49)`
</details>

{: .step}

## VLOOKUP

Step 1
{: .label .label-step}
Return to the `Summary` sheet  
{: .step}

Step 2
{: .label .label-step}
Use `VLOOKUP` to fill the rest of the summaries. 

**Hint**: If VLOOKUP does not provide the right numbers, make sure to set the last parameter to be FALSE to get the exact match. 

<details>
<summary>Answer (click to open)</summary>
<br>
`VLOOKUP(A9,Data!D5:E49,2,FALSE)`
</details>
{: .step}

## Smart Paste


Step 1
{: .label .label-step}
Copy the `Percent of test takers` values from the `Data` sheet into the `Summary` sheet. 

To avoid messing up formula, use Smart Paste -> Values Only. 

**Hint**: You can also subselect the TOTAL values only using Filter and then copy and paste a set of values as a range rigght into the `Summary` sheet.  
![](images/image-20210927030923992.png)
{: .step}

# Summaries and Visuals


## Quick Analysis


*Using Analyze Data Tool*


NOTE: This option may not be avaliable in the older Excel versions or in the Office 365.

Step 1
{: .label .label-step}
Return to the `Data` sheet  
{: .step}

Step 2
{: .label .label-step}
Select all your data and choose "Analyze Data" on the right  
{: .step}

Step 3
{: .label .label-step}
Explore various options and choose what you think is appropriate!  
{: .step}

### Link: More on the Analyze Data tool and how to make most out of it 
[Microsoft Support](https://support.microsoft.com/en-us/office/analyze-data-in-excel-3223aab8-f543-4fda-85ed-76bb0295ffc4)

## Pivot Table


*Creating a simple Pivot Table* 


Step 1
{: .label .label-step}
Select `Pivot Table` from the Insert menu  
{: .step}

Step 2
{: .label .label-step}
Select all columns in the table and choose to place the pivot table in the new worksheet  
{: .step}

Step 3
{: .label .label-step}
In the opened worksheet, in the pane on the right select fields `District Name`, `Test Takers` and `Total Score` . Do you think this numbers are correct?  
![](images/image-20210927031947053.png)
{: .step}

Step 4
{: .label .label-step}
1. Select `Group` field name and move it to the Filter area. In the filter above, unselect the "TOTAL" option.  
2. Where to find a filter:
![](images/image-20210927032100033.png)
{: .step}

Step 5
{: .label .label-step}
In the Values area, change the `Total Score` from Sum to the Average. 

**Hint**: Click on the info symbol to change the aggregation function: 

![](images/viz-1.png)

{: .step}

## Visualizations


*How to make a simple visualization*


Step 1
{: .label .label-step}
Return to the `Data` sheet   
{: .step}

Step 2
{: .label .label-step}
Select only TOTAL rows using filters for `Group`  
{: .step}

Step 3
{: .label .label-step}
Select columns `District Name` and `Percent of Test Takers`. 

**Hint**: Hold CTRL or CMD to select both columns;
{: .step}

Step 4
{: .label .label-step}
In the Insert menu select 2D horizontal bar chart (Clustered Bar).  

*Advice*: Horizontal bar chart is a preferred when having categories with long names  
![](images/image-20210927032731844.png)
{: .step}

Step 5
{: .label .label-step}
Sort bins by sorting the `Percent of Test Takers` column.  

*Advice*: Sorting/filtering  the original data has a direct impact on the visualization.  
{: .step}

### Link: How-tos on plotting different graph types in Excel 
[EvergreenData's tutorials](https://stephanieevergreen.com/how-to/)

## Data Series in Visualizatons


*Adding average line*  

Step 1
{: .label .label-step}
Create new column named `Average`. Use previously learned *SUBTOTAL* to get the average Percent of Test Takers and fill the whole column with this value

<details>
<summary>Answer (click to open)</summary>
<br>
`SUBTOTAL(1,H$9:H$49)`
</details>
{: .step}

Step 2
{: .label .label-step}
Right click on the existing visualization, choose Select Data and add another series (in the Legend Series click on the plus button); 

{: .step}

Step 3
{: .label .label-step}
Select Average as `Y-values`, Average column name as `Name`, and District Name column as `X-values`. You should have another set of bins added to your visualization;

![](images/viz-2.png)

{: .step}

Step 4
{: .label .label-step}
Select series corresponding to average (click on the orange bins). You can Change Series Chart Type by clicking right button and selecting Combo. However, this option only supports vertical bar chart.  

![](images/viz-3.png)

![](images/viz-4.png)

There are some workarounds available. For example, you can *add linear trend line* (select series, go to Chart Design) and click Add Chart Element -> Trend Line -> Linear (or right click and select Add Trendline)

![](images/viz-5.png)

It will create vertical line for the average, just like we wanted. Now, you can *make your bins invisible*. Either in the Format menu or Format pane, select Fill -> No Fill and Border (or Shape Outline) -> No line.

![](images/viz-6.png)

{: .step}



## Saving your chart  

*Save Visualization*  

Step 1
{: .label .label-step}
Select Chart Area (be careful not to select the Plot Area instead), right click and select Save as Picture to save your visualization
{: .step}

