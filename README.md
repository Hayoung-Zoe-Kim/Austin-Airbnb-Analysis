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
#### Data Cleaning  [[code]](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/Data%20Cleaning_.ipynb)
- Drop the columns that are slightly off-topic from our analysis focus
  
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/drop_columns.png)

- Ensure that each column has the appropriate data type
  
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/convert_data_type.png)

- Dealing with missing values
  - Fill out as "No information entered" : description, neighborhood_overview, host_name, host_since, host_location, host_about, host_neighbourhood, host_has_profile_pic, host_identity_verified  
  - Fill with the median : bathrooms_text, bedrooms, beds, host_total_listings_count
  - Replace with the overall rating (review_scores_rating) : review_scores_accuracy, review_scores_cleanliness, review_scores_checkin,review_scores_communication, review_scores_location, review_scores_value

![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/dealing_with_missingvalues.png)


  
#### EDA [[code]](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/EDA.ipynb)
- “ Zip Code ” plays a significant role in our dataset. The exploratory data analysis (EDA) has revealed variations in the distribution of various features across different zip codes.
- Utilized 'Zip Code' as the main filter for constructing queries and driving visualizations
  
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/eda_zipcode.png)

#### Data Structuring and Managing in SQL and MongoDB(noSQL) 
- SQL querying
  
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/sql_query.png)

- MongoDB
  
![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/mongoDB_collection.png)


#### Visualization
- Tableau [Dashboard](https://public.tableau.com/app/profile/hayoung7844/viz/AustinAirbnbMarketOverview/Dashboard1) |  [Dashboard2](https://public.tableau.com/app/profile/hayoung7844/viz/AustinAirbnbChoroplethMaps/Dashboard2)

![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/Tableau_dashboard_.png)


![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/Tableau_choropleth.png)

- MongoDB Charts [Dashboard](https://charts.mongodb.com/charts-project-0-ylnjm/public/dashboards/9576c28a-2cf3-4cef-abbd-2658a5eae146)

![image](https://github.com/Hayoung-Zoe-Kim/Austin-Airbnb-Analysis/blob/main/MongoDBCharts.png)


## Conclusion
- By strategically deploying SQL for structured, quantitative data and NoSQL for the unstructured, qualitative parts of our dataset, we achieved a more nuanced and comprehensive analysis. This hybrid approach allowed us to maximize the strengths of both relational and non-relational databases, ensuring high efficiency and deeper insights.

- In Southwest Austin, Superhosts typically charge more for their Airbnb listings than their non-Superhost counterparts. This indicates that possessing Superhost status may enable hosts to warrant and demand somewhat higher prices.

- Superhosts show a smaller range in their listings' average ratings, from 4.32 to 4.98, compared to non-Superhosts, who range from 3.38 to 4.96. However, in neighborhoods like 78726 and 78746, non-Superhosts sometimes have higher average ratings than Superhosts, suggesting that while Superhosts are generally expected to offer higher quality, non-Superhosts can also achieve excellent ratings with outstanding services.

  
## ⭐️ Applicable Business Use Cases:

#### Sustained Dynamic Pricing Strategies:
- Assuming the project evolves beyond the prototype phase with sustained automatic data pipelines and lakes, hosts can utilize ongoing trends analysis in zip code-specific data, such as average prices and ratings. This enables the implementation of dynamic pricing models that accurately reflect the desirability and competition within different areas. Superhosts, in particular, could leverage their status to adjust prices competitively in regions where they typically command a premium, while non-Superhosts might concentrate on price optimization in neighborhoods where their ratings outperform the average.

#### Competitive Analysis and Market Positioning:
- The methodology used to differentiate between Superhosts and non-Superhosts in terms of pricing and ratings can be employed in a broader business context for competitive analysis. Companies can assess their position in the market compared to competitors, adjust their strategies to highlight their strengths, and address areas of weakness, enhancing their overall market positioning.

#### Value Proposition Enhancement:
- Insights into what drives higher ratings and customer satisfaction can inform businesses on how to enhance their value propositions. In industries like tourism, real estate, or any service-based sector, understanding the attributes that correlate with higher customer approval can guide improvements in service delivery and customer experience, akin to enhancing an Airbnb listing to achieve Superhost status.
