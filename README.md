# Analysis-on-States-for-Retirements-in-the-US


## Introduction
This is my first end-to-end project on Data Analysis. I used the data modelling and data loading skills I learnt from #NG30daysofLearning with PowerBI.

## Problem Objective
After service years, civil servants, entrepreneurs, employers and employees usually retire. They do this for various reasons for example, the freedom from the onerous work, leisure to do the things one actually want to do e.t.c. The report looks into the states in the US to get the best and worst state to retire after service years.
## Tools
- Microsoft PowerBI for analysis and visualization.
- Brackets for Markdown

## Data Sourcing
The table containing the different states and their various ranking was gotten from [The best and worst states for retirement 2021](https://www.bankrate.com/retirement/best-and-worst-states-for-retirement/#3). While information on the state like capital ,abbreviation e.t.c, was gotten from [List of states and territories of the United States](https://en.wikipedia.org/wiki/List_of_states_and_territories_of_the_United_States)
## Data Transformation
> The table for ranks will now be reffered to as Table_Rank while that of State information will be reffered to as Table_Info

#### For Table_Rank;
- Duplicates were removed.
- Table was sorted in ascending order with column 'Overall Score' as refrence point.
- A new index column was created with 1 as starting point and an increment value of 1. This new column was renamed to replace the 'Overall Rank' column (since duplicates have being removed).
- The data type of each column was changed to the appropriate type with respect to the column content.

![Ranked States](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/Table_rank%20(2).png)

#### For Table_Info;
- The first row which contained some unneccessary information was removed.
- The '`[D]`' which was found at the end of the names of some states was removed using the Replace value function.
- Unimportant columns were removed.
- The columns left were renamed for improved readability.
![State Info](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/Table_Info%20(2).png)

### Merge
-  A new 'Complete Table' was created by merging Table_Rank and Table_Info on the States column using `Left Join`
- A new column, Population density was created using:

`Population density = 'Complete Table'[Population] / ('Complete Table'[Land area (Km²)])`


![Merged Table](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/Complete%20Table.png)

## Data Model

The data model for the analysis is pretty straightforward. The three tables are linked together in a one-to-one relationship by the State column
![Data Model](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/Data%20model.png)

## Findings and recommendation

Georgia, Florida, Tennese, Missouri and Wyoming top the list  for the best states when all categories are combined. However, each state has its own peculiarity, pros and cons. For example, Tennesse boasts of the best affordability, but its crime rate is better than just 5 states.

- For

Other factors that can affect one's decision is closeness to family, access to medical care e.t.c

![Report page 1](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/best%20and%20worst%20state%201.png)

![Report page 2](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/best%20and%20worst%20state%202.png)
