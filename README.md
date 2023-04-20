# ETL-pipeline-predict-customer-Behavioral-Interaction

## Introduction
This project builds an ETL pipeline to process 8GB of the search and content data of the FPT company, along with applying the Customer360 model to predict the behavior and interaction of customers to make reasonable decisionsThis project builds an ETL pipeline to process 8GB of the search and content data of the FPT company, along with applying the Customer360 model to predict the behavior and interaction of customers to make reasonable decisions.
<br>
![customer_360_data-2-1024x981 (3)](https://user-images.githubusercontent.com/101572443/233166379-ed883b3d-ff6d-4e8e-b9b6-722e7a663d5b.png)

## Dataset
The dataset used for processing is the content data of April and the lookup data of June and July generated when customers use FPT telecom services:
- [log content](#)
- [log search](#bỏlinkgithubvao)

## ETL process description
- log content <br>
The 'log content' has the schema as below: <br>
![screenshot_1681929647 (1)](https://user-images.githubusercontent.com/101572443/233170588-95393779-53ec-494f-b1da-b92b7b139e95.png)
  - Clean & Change table format: Dive into the '_source' data to clean them up by pivoting the 'Type' and sum the 'TotalDuration' to figure out exactly how many hours each 'Contract' spends on each category, then expand on the ideas below.
  - Most Watch: Based on the data table calculated above find out which 'Type' has the 'Most Watch' for each 'Contract' by applying the Window ranking function to find where the 'rank == 1' and pick it outputting a new column named 'Most_Watch'.
  - Taste: This column contains all 'Types' whose watch time is not NULL of each 'Contact'.
  - IQR(InterQuartile Range) type: applying this type to exclude outliers or abnormal values in the data as well as give decide the usage frequency of the user, and assign a value to each interval as follows:
    -  Divide total duration to 3 parts:
      - duration < 25%(q1): lower
      - 25%(q1) =< duration =< 75%(q3): middle
      - duration < 75%(q3): upper
<br>

- log search <br>
## Results

## Requirements
- [Python 3.10.9](#)
- [Java 19.0.2](#)
- [Hadoop winunit.exe-2.7.1](#)
- [Spark 3.3.1-bin-hadoop2](https://www.youtube.com/watch?v=OmcSTQVkrvo)
- [Install Apache PySpark](https://www.youtube.com/watch?v=OmcSTQVkrvo)
