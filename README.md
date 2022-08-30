# Amazon Vine Analysis

## Purpose

The purpose of this analysis is to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. In this analysis a dataset on Pet Products was used from a set of approximately 50 different datasets.

## Overview

•	Use PySpark methods and functions to get DataFrame information.

•	Use PySpark functions to transform and filter data.

•	Connect to an AWS RDS instance.

•	Load to transformed data in pgAdmin.

## Results

### Amazon Reviews ETL

The dataset is first cleaned and transformed into sperate dataframes. 

##### Initial DataFrame

![df](https://user-images.githubusercontent.com/103263248/187537510-c69f9a50-e557-4d49-89dd-24ddb7f0ec65.png)

##### Transformed DataFrames

###### Customers DataFrame

![customer_df](https://user-images.githubusercontent.com/103263248/187537572-0dc86401-0ff1-458f-9dec-1c59c8b22762.png)

###### Products DataFrame

![products_df](https://user-images.githubusercontent.com/103263248/187537605-62d48d97-f1c0-49cf-92a8-7bffecf79587.png)

###### Review DataFrame

![review_df](https://user-images.githubusercontent.com/103263248/187537664-c57aad43-daa4-4f2e-b514-4ca62d0093f0.png)

###### Vine DataFrame

![vine_df](https://user-images.githubusercontent.com/103263248/187537698-9a23c7b4-c4b5-4f57-be0b-8a56f02725ad.png)


The data is connected using Google Colab notebooks through an AWS RDS instance. The transformed data is then imported to pgAdmin tables. 

##### pgAdmin Tables

###### Customers Table

![customers_table](https://user-images.githubusercontent.com/103263248/187537774-8a78f7ae-f6bb-431e-9ac8-ba0089c00c4d.png)

###### Products Table

![products_table](https://user-images.githubusercontent.com/103263248/187537811-012d97fc-f8c2-4fd4-acf3-e7144394f8d3.png)

###### Review IDs Table

![review_id_table](https://user-images.githubusercontent.com/103263248/187537832-6bb8a48f-2a52-49d9-b3b6-c4bc3b25f2ec.png)

###### Vine Table

![vine_table](https://user-images.githubusercontent.com/103263248/187537854-6449339f-7793-4531-97f6-cd6c2e9ddfbe.png)

### Vine Reviews

This is a big data size with a total review count of 2,642,619. 
To preform an analysis on the Vine program, the reviews are broken down with further filtering and transforming into dataframes.

##### Total Votes of 20 or more DataFrame
![total_votes_20plus_df](https://user-images.githubusercontent.com/103263248/187544804-f3158f27-b5bb-4e24-9e23-57cd49fb8dc3.png)

Reviews that have only 20 or more votes. The dataframe gives us a count of 39,376 reviews that meet the 20 or more votes criteria. 

![votes_count](https://user-images.githubusercontent.com/103263248/187538464-192105a2-2765-4f6c-9a13-a429ac64f460.png)

##### Helpful Vote DataFrame
![helpful_vote_50plus](https://user-images.githubusercontent.com/103263248/187544831-c682384d-5880-4c3d-9c1c-0c2af87f2834.png)

Helpful votes were defined as 50% or greater than the total votes.
820,566 reviews that meet the helpful votes of 50% or greater criteria.

![helpful_count](https://user-images.githubusercontent.com/103263248/187538509-6b4cc450-9495-4dcd-b28c-861c99080b5c.png)

##### Paid Vine DataFrame
![paid_vine_df](https://user-images.githubusercontent.com/103263248/187544858-50c8846f-5c98-41eb-b142-4f37d7e5a3ff.png)

All of the reviews that where written as part of the vine program are put into one dataframe
The reviews that meet this criteria gives us a count of 4,103 reviews.

![paid_count](https://user-images.githubusercontent.com/103263248/187545214-345e78f8-ef09-42be-b688-73dc88f029a1.png)

##### Unpaid Non-Vine Reviews DataFrame
![unpaid_vine_df](https://user-images.githubusercontent.com/103263248/187544882-1c5a05a4-2108-47a1-820f-2926df906e96.png)

This dataframe is made up of reviews that were not part of the Vine program. 
The reviews that meet this criteria gives us a count of 816,463 reviews.

![unpaid_count](https://user-images.githubusercontent.com/103263248/187545235-4ed1e4fa-aff3-4c3a-8ebd-7446f1a96caf.png)

##### Vine reviews with 5-star rating DataFrame
![paid_star_rating_df](https://user-images.githubusercontent.com/103263248/187544905-857b6681-19d0-4fdd-9640-50c742fbb8a4.png)

All of the reviews that are part of the Vine program that give a rating of 5-stars are listed in this dataframe. These reviews give us a count of 1,704 reviews.

![paid_star_count](https://user-images.githubusercontent.com/103263248/187545269-a713c074-25ab-4980-a958-f44e9aa28feb.png)

##### Non-Vine Unpaid reviews with 5-star rating DataFrame
![unpaid_star_rating_df](https://user-images.githubusercontent.com/103263248/187544922-56b5bc2c-76f3-49d9-a474-be4033a600c1.png)

These are the reviews that received 5-start rating reviews but were not part of the Vine programm. This dataframe gives us a count of 816,463 reviews that meet this criteria. 

![unpaid_star_count](https://user-images.githubusercontent.com/103263248/187545283-8318ed5d-d2d8-4428-960a-fce6d9b3d48c.png)

### With the analysis preformed the following questions can be answered:

•	How many Vine reviews and non-Vine reviews were there?

Reviews that were paid for by the Vine program came to a count of 4,103 reviews. 

![paid_count](https://user-images.githubusercontent.com/103263248/187538277-807dc895-50e9-443f-aadc-54f66c59d1d8.png)

Unpaid or non-Vine reviews came to a count of 816,463.

![unpaid_count](https://user-images.githubusercontent.com/103263248/187538301-67f94911-665b-4c0d-beed-c7c026b12e45.png)

•	How many Vine reviews were 5 stars? 

Vine reviews with 5-star ratings have a count of 1,704.

![paid_star_count](https://user-images.githubusercontent.com/103263248/187537956-cb5a8682-65a7-4ff3-9533-642172a42059.png)

•	How many non-Vine reviews were 5 stars?

Non-Vine reviews with 5-star ratings have a count of 458,620.

![unpaid_star_count](https://user-images.githubusercontent.com/103263248/187538077-7b1b488d-9ffa-4fe6-aee7-17b720bb46eb.png)

•	What percentage of Vine reviews were 5 stars? 

The percentage of Vine reviews with 5-stars can be rounded to 42%.

![percent_paid](https://user-images.githubusercontent.com/103263248/187538163-82db2077-51fc-4b35-a90b-4f451cb1f159.png)

•	What percentage of non-Vine reviews were 5 stars?

The percentage of non-Vine reviews with 5-stars can be rounded to 57%.

![percent_unpaid](https://user-images.githubusercontent.com/103263248/187538137-885a099d-68a2-4abd-a8cd-4bf2729e4661.png)

## Summary

The number of Vine reviews count to non-Vine reviews count is 4,103 to 816,463. This shows that there is a large difference in the number of reviews. Looking at the number of reviews that received 5-star ratings it is 1,704 Vine reviews to 816,463. This shows that even though the reviews are unpaid there is more of the higher rated unpaid reviews. Broken down into percentages it’s comparable of 42% Vine 5-star rated reviews to 57% non-Vine 5-star rated reviews. 

This summary shows that the Vine program doesn’t seem to have a positive bias or an impact on reviews. 

Further analysis into other ratings such as 4-star, 3-star, 2-star, and 1-star can elaborate on the comparison of Vine to non-Vine reviews. It is possible that due to being paid more honest reviews from paid Vine reviewers leading to lower ratings.
