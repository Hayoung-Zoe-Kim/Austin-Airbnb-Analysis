# Austin-Airbnb-Analysis

## Project Overview

#### Purpose
The aim of the project is to leverage SQL, noSQL database as well as Visualization Tools like Tableau to provide a holistic view of Austin Airbnb market to the potential hosts. 

#### Problem Statement
- Context : In the competitive Austin Airbnb market, new hosts face uncertainty in starting out, needing guidance on area-specific trends and opportunities.
- Empowers new hosts with data-driven insights to make informed decisions on property listings and pricing strategies.
- Identifies market gaps and opportunities, helping hosts to optimize their offerings for better revenue potential.

## Methodology
Initially, we extracted perfume reviews through web scraping. We then selected long-tail perfumes with proven quality, indicated by overall ratings exceeding 4.5 out of 5. Based on the scent descriptions and the review texts, we calculated a comprehensive evaluation score for each review. This was achieved by multiplying the similarity and sentiment scores derived from the reviews against a simulated user profile detailing scent preferences, usage occasions, and price range. Finally, employing a Word2Vec model, our recommendation system generated a list of high-scoring long-tail perfumes.

#### Data Source & Preprocessing
- source: https://www.fragrancex.com/shopping/type/perfume](http://insideairbnb.com/get-the-data/
- Data: about 13,500 listings information +  655,000 review data
- Key Columns: Zip codes, room types, price, availability, superhost status, reviews

## Highlights of Analysis
#### Data Cleaning
- Drop the columns that are slightly off-topic from our analysis focus 
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/drop_columns.png)

- Ensure that each column has the appropriate data type
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/convert_data_type.png)

- Dealing with missing values
  - Fill out as "No information entered" : description, neighborhood_overview, host_name, host_since, host_location, host_about, host_neighbourhood, host_has_profile_pic, host_identity_verified  
  - Fill with the median : bathrooms_text, bedrooms, beds, host_total_listings_count
  - Replace with the overall rating (review_scores_rating) : review_scores_accuracy, review_scores_cleanliness, review_scores_checkin,review_scores_communication, review_scores_location, review_scores_value
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/dealing_with_missingvalues.png)

[code]
  
#### EDA
- “ Zip Code ” plays a significant role in our dataset. The exploratory data analysis (EDA) has revealed variations in the distribution of various features across different zip codes.
- Utilized 'Zip Code' as the main filter for constructing queries and driving visualizations
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/eda_zipcode.png)

#### Data Structuring and Managing in SQL and MongoDB(noSQL) 
- SQL querying
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/sql_query.png)

- MongoDB 
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/mongoDB_collection.png)

#### Visualization
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/Tableau_dashboard.png)

[Dashboard]

![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/MongoDB Charts_dashboard.png)

[Dashboard]



## Conclusion
- The Word2Vec model facilitated a nuanced understanding of user preferences, connecting scent descriptions and review texts with user sentiments to create a personalized recommendation experience.
  
- The dual-phase approach of the project shed light on a compelling aspect of the fragrance market: While the allure of obscure brands is undeniable for certain attributes, it is remarkable to observe that many affordable yet desirable perfumes originate from well-known houses. This suggests a complex interplay between brand perception and product quality, highlighting an opportunity for small to medium fragrance businesses to capitalize on their unique offerings.

- The value of our Long-Tail Perfume Recommendation System is that by bridging the gap between accessibility and exploration, it stands as a beacon for discovery in the vast ocean of fragrances, guiding consumers to their perfect scent match while supporting the growth of diverse perfume brands.

## ⭐️ Applicable Business Use Cases:

#### Niche Market Targeting:
- Boutique Retailers can use the system to stock inventory that aligns with the unique preferences of their customer base, helping them to differentiate from larger competitors.

#### Brand Development: 
- Emerging and indie fragrance brands can use insights from the system to position their products in the market effectively, focusing on untapped customer segments. Also, the system can help identify scent preferences and trends, which can be used to inform marketing campaigns and product development strategies.

#### Inventory Management:
- Retailers can use the system's insights to optimize their inventory, reducing stock of less popular items and focusing on what their customers are most likely to purchase. Moreover, insights from the recommendation system can assist in predicting future trends and demand for certain fragrances, aiding in production planning and inventory forecasting.

## More
Full Code : https://github.com/Hayoung-Zoe-Kim/Perfume-Recommendation-System/blob/main/0_Final_Long%20Tail%20Perfume%20Recommendation%20System.ipynb
