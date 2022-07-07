# Analysis-on-States-for-Retirements-in-the-US

## Problem Objective
To get the best and worst state in the US to retire after service years.
## Data Sourcing
The table containing the different states and their various ranking was gotten from [The best and worst states for retirement 2021](https://www.bankrate.com/retirement/best-and-worst-states-for-retirement/#3). While information on the state like capital ,abbreviation e.t.c, was gotten from [List of states and territories of the United States](https://en.wikipedia.org/wiki/List_of_states_and_territories_of_the_United_States)
## Data Transformation
> The table for ranks will now be reffered to as Table_Rank while that of State information will be reffered to as Table_Info

#### For Table_Rank;
- Duplicates were removed.
- Table was sorted in ascending order with column 'Overall Score' as refrence point.
- A new index column was created with 1 as starting point and an increment value of 1. This new column was renamed to replace the 'Overall Rank' column (since duplicates have being removed).
- The data type of each column was changed to the appropriate type with respect to the column content.

#### For Table_Info;
- The first row which contained some unneccessary information was removed.
- `[D]` which was found at the end of the names of some states was removed using the Replace value function.
- Unimportant columns were removed.
- The columns left were renamed for improved readability.

###Merge
-  A new 'Complete Table' was created by merging Table_Rank and Table_Info on the States column using `Left Join`
- A new column, Population density was created using:

`Population density = 'Complete Table'[Population] / ('Complete Table'[Land area (Km²)])`

## Findings and recommendation

Georgia, Florida, Tennese, Missouri and Wyoming top the list  for the best states when all categories are combined.

Each state has its own peculiarity, pros and cons. For example, Tennesse boasts of the best affordability, but its crime rate is better than just 5 states.

Other factors that can affect one's decision is closeness to family, access to medical care e.t.c

![best and worst state 1](https://user-images.githubuserc![best and worst state 2](https://user-images.githubusercontent.com/90080523/177680761-f131ab5e-858b-4d26-b465-ebd748652424.png)
ontent.com/90080523/177680743-8ceffb36-5f6f-4ce8-b08a-6a6ea00ddf42.png)
