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

## Intro

*Importing csv files*

Step 1
{: .label .label-step}

Make sure to extract both files from the downloaded archive prior to the data import!

1. Open new workbook.  

2. Choose File -> Import in the Excel menu

3. Select type **CSV file** and select the *bc-popular-boys-names.csv*

4. In the Text Wizard select Delimited and choose Semicolon as the delimiter. Make sure that the preview looks correct

  ![image-20211207000421068](images/image-20211207000421068.png)

5. We are only planning to use the data from the last 10 years (2010-2019). Therefore, the columns for 1920-2009 can be skipped. 

  Click on the 1920 column and select **Do not import column**. Press Shift and scroll down to the column for 2009, click on it and click on **Do not import column** again. Make sure that only columns 1920-2009 are labeled as Skip. Other columns (Name, 2010, 2011, ..., 2019, Total) should be labeled General.

  ![image-20211207001152333](images/image-20211207001152333.png)

  ![image-20211207001346050](images/image-20211207001346050.png)

6. Rename the current sheet to "Boys" and follow the same procedure for the Girls data (file *bc-popular-girls-names.csv*) {: .step}

