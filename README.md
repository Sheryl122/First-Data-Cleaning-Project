This is  the explanation for my data cleaning project, I was given data that displayed the amount of mass layoffs all over the world.

In this data cleaning assignment I followed these 4 steps
1. Remove Duplicates
2. Standardized the Data
3. Null Values or Blank values
4. Remove Any Columns

In order to start cleaning the data given, I first created a staging table and populated with the exact same data that was given in the raw dataset table that was provided. This new table was named layoffs_staging. This table is made just in case of mistakes, we want to have the raw dataset available. It is also not advised to manipulate raw data.

I identified duplicates by partitoning by all the colmuns and calling for  the ROW_NUMBER() so that if any  duplicates are present the ROW_NUMBER() will return an amount greater than 1 to represent that there are more than one row with all the same information in the columns I partioned by. This was done by creating a cte, which is a temporary table that can be referenced other times.
Once the duplicates are identified, another table is created (because you cannot delete rows through a cte) and rows where the row_num > 1, are deleted.
