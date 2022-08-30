# Amazon Vine Analysis

## Purpose

The purpose of this analysis is to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. In this analysis a dataset on Pet Products was used from a set of approximately 50 different datasets.

## Overview

•	Use PySpark methods and functions to get DataFrame information.

•	Use PySpark functions to transform and filter data.

•	Connect to an AWS RDS instance.

•	Load to transformed data in pgAdmin.

## Results

The dataset is first cleaned and transformed into sperate dataframes. 

##### Initial DataFrame
png

##### Transformed DataFrames
png
###### Customers DataFrame
png
###### Products DataFrame
png
###### Review DataFrame
png
###### Vine DataFrame
png

The data is connected using Google Colab notebooks through an AWS RDS instance. The transformed data is then imported to pgAdmin tables. 

##### pgAdmin Tables

###### Customers Table
png

###### Products Table
png

###### Review IDs Table
png

###### Vine Table
png


The dataset is of the big data size with a total review count of 2,642,619. Filtering and extracting the reviews that only have 20 or more votes left the analysis with 39,376 reviews. Helpful votes were defined as 50% or greater than the total votes bringing the count to 820,566 reviews.

#### With the analysis preformed the following questions can be answered:

•	How many Vine reviews and non-Vine reviews were there?

Reviews that were paid for by the Vine program came to a count of 4,103 reviews. Unpaid or non-Vine reviews came to a count of 816,463.


•	How many Vine reviews were 5 stars? 

Vine reviews with 5-star ratings have a count of 1,704.

•	How many non-Vine reviews were 5 stars?

Non-Vine reviews with 5-star ratings have a count of 458,620.

•	What percentage of Vine reviews were 5 stars? 

The percentage of Vine reviews with 5-stars can be rounded to 42%.

•	What percentage of non-Vine reviews were 5 stars?

The percentage of non-Vine reviews with 5-stars can be rounded to 57%.

## Summary

The number of Vine reviews count to non-Vine reviews count is 4,103 to 816,463. This shows that there is a large difference in the number of reviews. Looking at the number of reviews that received 5-star ratings it is 1,704 Vine reviews to 816,463. This shows that even though the reviews are unpaid there is more of the higher rated unpaid reviews. Broken down into percentages it’s comparable of 42% Vine 5-star rated reviews to 57% non-Vine 5-star rated reviews. 

This summary shows that the Vine program doesn’t seem to have a positive bias or an impact on reviews. 

Further analysis into other ratings such as 4-star, 3-star, 2-star, and 1-star can elaborate on the comparison of Vine to non-Vine reviews. It is possible that due to being paid more honest reviews from paid Vine reviewers leading to lower ratings.
