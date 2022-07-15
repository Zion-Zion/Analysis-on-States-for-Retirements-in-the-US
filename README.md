# Analysis-on-States-for-Retirements-in-the-US


## Introduction
This is my first end-to-end project on Data Analysis. I used the data modelling and data loading skills I learned from #NG30daysofLearning with PowerBI.

## Problem Objective
After service years, civil servants, entrepreneurs, employers and employees usually retire. They do this for various reasons, for example, the freedom from onerous work, leisure to do the things one wants to do, e.t.c. The report looks into the states in the US to get the best and worst states to retire after service years.
## Tools
- Microsoft PowerBI for analysis and visualization.
- Brackets for Markdown

## Data Sourcing
The table containing the different states and their various ranking was obtained from [The best and worst states for retirement 2021](https://www.bankrate.com/retirement/best-and-worst-states-for-retirement/#3). While the information on the States like capital, abbreviation e.t.c, was obtained from [List of states and territories of the United States](https://en.wikipedia.org/wiki/List_of_states_and_territories_of_the_United_States)
## Data Transformation
> The tables have been renamed. The Table for ranks to **Table_Rank** while that of State information to **Table_Info**.

#### For Table_Rank;
- Duplicates were removed.
- Table was sorted in ascending order with the column 'Overall Score' as a reference point.
- A new index column was created with 1 as the starting point and an increment value of 1. This new column was renamed to replace the 'Overall Rank' column (since duplicates have been removed).
- The data type of each column was changed to the appropriate type with respect to the column content.

![Ranked States](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/Table_Rank.png)

#### For Table_Info;
- The first row, which contained some unnecessary information, was removed.
- The ' <sup>`[D]`</sup> ', which was found at the end of the names of some States, was removed using the Replace value function.
- Unimportant columns were removed.
- The columns left were renamed for improved readability.
![State Info](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/Table_Info.png)

### Merge
-  A new 'Complete Table' was created by merging Table_Rank and Table_Info on the States column using `Left Join`.



![Merged Table](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/Complete%20Table.png)

## Data Model

The data model for the analysis is pretty straightforward. The three tables are linked together in a one-to-one relationship by the State column. Also, a new measure, Population density, was created in the complete table using:

`Population density = 'Complete Table'[Population] / ('Complete Table'[Land area (Km²)])`


![Data Model](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/Data%20model.png)

## Findings and recommendations

Georgia, Florida, Tennessee, Missouri and Wyoming top the list of the best states when all categories are combined. However, each state has its peculiarity, pros and cons. For example, Tennesse boasts of the best affordability, but its crime rate is better than just 5 states.

![Report page 1](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/best%20and%20worst%20state%201.png)

Looking at specifics, here are some things to consider.
- For persons seeking a place with a pocket-friendly way of life, Tennessee and Oklahoma should be their dream States, while States like California, Connecticut and Hawaii should be avoided.
- States like New Hampshire, Maine and New Jersey can be called the Safe Haven of the country. They have a very low crime rate as compared to Louisiana, Alaska and New Mexico on the other end of the spectrum.
- For persons that enjoy arts, entertainment, culture and the likes, States like Maine, Montana and Vermont are the best for retirement. Utah, Mississippi and Texas do not possess such in the grand scheme of things.
- Many are fans of a warm climate; however, this temperature factor isn't enough to rank a State by weather. Other factors like the occurrence of tornadoes, landslides and so on affect its overall rating. A state like Florida would've taken a spot in the top 2 if not for frequencies of Acts of God. Arizona, Kentuck and West Virginia top the list for good weather, with Alaska, Wyoming and Maine sitting deep down the list.
- Another factor that can influence one's decision is access to amenities, health care, food, and economic security. Massachusetts, beautiful Hawaii and New Jersey are favourites in this regard, with New Mexico, Arkansas and Mississippi being the least ranked States

![Report page 2](https://github.com/Zion-Zion/Analysis-on-States-for-Retirements-in-the-US/blob/main/best%20and%20worst%20state%202.png)


