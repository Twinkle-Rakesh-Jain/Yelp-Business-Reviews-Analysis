# Yelp-Business-Reviews-Analysis

## Project Description
This project is an end-to-end data analytics pipeline leveraging Python, Snowflake, and SQL. The primary objective is to analyze Yelp business reviews and extract meaningful insights. The dataset used is the Yelp Open Dataset, which provides real-world business data, including reviews, photos, check-ins, and attributes such as hours, parking availability, and ambience.

<img width="1250" alt="Screen Shot 2025-03-23 at 3 08 39 PM" src="https://github.com/user-attachments/assets/d6caddf0-f58a-457d-a4fc-79e822d5777d" />


### Datasets Used
1. Yelp Reviews: ~5GB JSON file containing ~7 million records.

2. Yelp Businesses: ~100MB JSON file with business details.
3. Link to dataset: https://business.yelp.com/data/resources/open-dataset/

## Data Processing Steps 
### Step 1: Data Ingestion

1. The large Yelp Reviews JSON file was split into 10 smaller JSON files using Python for optimized data ingestion.

2. Both Yelp Reviews (split files) and Yelp Businesses files were uploaded to AWS S3.

3. Created a Snowflake database and two tables with VARIANT data type for JSON storage.

4. Loaded the data from AWS S3 into Snowflake using the COPY INTO command.

### Step 2: Sentiment Analysis Function
1. Developed a User-Defined Function (UDF) in Snowflake using Python.

2. Utilized the TextBlob library to analyze sentiment polarity.

3. Classified reviews into Positive, Neutral, or Negative sentiment categories.
   
### Step 3: Data Transformation
1. Extracted relevant fields from JSON format into structured tabular format.

2. Created tbl_yelp_reviews with columns: business_id, review_date, user_id, review_stars, review_text, and sentiment analysis results.

3. Created tbl_yelp_businesses with columns: business_id, name, city, state, review_count, stars, and categories.

## SQL Query Execution for Business Insights
After processing the data, we executed SQL queries in Snowflake to derive key business insights. These queries helped us analyze user behavior, review patterns, and business performance. Below are the top 10 insights we extracted:
1. Top business categories by count
2. Top 10 users reviewing the most restaurants
3. Most reviewed business categories
4. Top 3 recent reviews per business
5. Month with the highest reviews
6. Percentage of 5-star reviews per business
7. Top 5 most reviewed businesses per city
8. Businesses with 100+ reviews and their average rating
9. Top 10 users with the most reviews and businesses reviewed
10. Top 10 businesses with the highest positive sentiment
    
These insights provided valuable information for understanding customer preferences and business trends.

## Conclusion
This project successfully demonstrated the power of big data processing, sentiment analysis, and SQL-based insights using Snowflake, Python, and SQL. By leveraging cloud storage (Amazon S3), JSON data handling, and UDFs in Snowflake, we efficiently processed millions of records and derived actionable business insights.

### Key takeaways include:
1. Sentiment analysis provided valuable indicators of customer satisfaction.
2. Identified top-performing businesses and categories based on review trends.
3. Uncovered patterns in user engagement and business popularity.
   
These insights can help businesses enhance their customer experience, optimize marketing strategies, and improve service offerings based on data-driven decisions.


