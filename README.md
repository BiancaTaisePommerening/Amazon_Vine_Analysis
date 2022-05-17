# Amazon_Vine_Analysis
Big Data


## **Project Overview**


Analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

Out of a list of 50 different datasets, the Outdoor Reviews was the one chosen for this analysis, where the goal is to determine if having a paid Vine review makes a difference in the percentage of 5-star reviews.



## **Solution Design**

### **Perform ETL on Amazon Product Reviews**

- Pick a dataset from the Amazon Review datasets;
- Create a new Google Colab Notebook;
- Using PySpark:
    - Read in a CSV file;
    - Extract the dataset into a DataFrame;
    - Use its methods and functions to perform ETL;
    - Transform the DataFrame into four separate DataFrames that match the table schema in pgAdmin;
- Create an AWS RDS database;
- Upload the transformed data into the appropriate pgAdmin tables; 
- Run queries using PostgreSQL in pgAdmin to confirm that the data has been uploaded.

### **Determine Bias of Vine Reviews**

- Create a new Google Colab Notebook as a Jupyter Notebook file;
- Read in a CSV file into a Jupyter Notebook through Googgle Colaboratory;
- Use the same dataset used for deliverable 1.
- Using PySpark:
    - Read in a CSV file into a Jupyter Notebook through Googgle Colaboratory;
    - Extract the dataset into a DataFrame;
    - Retrieve all the rows on the DataFrame where the total_votes count is equal to or greater than 20, which are the ones more likely to be helpful;
    - Create a new DataFrame out of the previous one to retrieve all the rows where the number of helpful_votes divided by total_votes is equal to or greater than 50%.
    - Create a new DataFrame out of the previous one that retrieves all the rows where a review was written as part of the Vine program (paid), vine == 'Y'.
    - Create a new DataFrame to retrieve all the rows where the review was not part of the Vine program (unpaid), vine == 'N'.
    - Determine the total number of reviews, the number of 5-star reviews, and the percentage of 5-star reviews for the two types of review (paid vs unpaid).
    - Export the ipynb file, and save it to the GitHub repository.

### **Written Analysis**

- Write a Report on the Analysis (README.md).


## **Results**

### **1. Total Amount of Reviews**

- 37544

![total_reviews](./resources/total_reviews.png)


### **2. Total Amount of Paid Reviews**

- 103

![total_paid_reviews](./resources/total_paid_reviews.png)


### **3. Total Amount of Unpaid Reviews**

- 37441

![total_unpaid_reviews](./resources/total_unpaid_reviews.png)


### **4. Total Amount of 5-Star Paid Reviews**

- 55

![paid_five_stars_reviews](./resources/paid_five_stars_reviews.png)

### **5. Total Amount of 5-Star Unpaid Reviews**

- 19737

![unpaid_five_stars_reviews](./resources/unpaid_five_star_reviews.png)

### **6. Percentage of 5-Star Paid Reviews**

- 53.4%

![percentage_five_stars_paid](./resources/percentage_five_stars_paid.png)

### **7. Percentage of 5-Star Unpaid Reviews**

- 52.71%

![percentage_five_stars_unpaid](./resources/percentage_five_stars_unpaid.png)


## **Summary**

### **DataFrame Displaying the Results**

- The following Dataframe displays:
    - Total Number of Reviews;
    - Total Number of 5-star reviews;
    - % of 5-star Unpaid Reviews (unpaid 5-star reviews divided by total amount of unpaid reviews);
    - % of 5-star Paid Reviews (cpaid 5-star reviews divided by total amount of paid reviews);



![results_df](./resources/results_df.png)


When looking at the results individually, 53.4% seems to be very high for only 5-star reviews which could lean into a bias conclusion. On the other hand this result is very similar to the 52.71% of 5-star reviews given by non-vine customers, which suggests that Vine members might be actually given honest results.


### **Additional Analysis**

Looking at the total amount of reviews 37544 and the amount of paid reviews 103, it indicates that the proportion of reviews is unbalanced, suggesting that a sampling analysis should be done and/or collecting more paid reviews to further analyze the matter.
