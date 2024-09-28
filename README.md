# 📝⭐  Yelp_Star_Rating_Initiative
![](https://img.shields.io/badge/python-3.10%2B-blue?logo=Python)

⚡ Data Preprocessing, Clustering, Hypothesis Testing, and Logistic Regression Modelling ⚡

> [!NOTE]
> This project was conducted by Ruo-Ying Qi, Yudi Su, Keane Dylan Yennoto, Claire Zhao, and Kaibo Zhang, students from the Desautels Faculty of Management at McGill University. The study utilized publicly available data from the > Yelp platform and was supervised as part of the course INSY-446-001 Data Mining for Business Analytics. The Yelp dataset can be found [here](https://www.yelp.com/dataset). 

## Overview
Yelp, a leading online platform, connects consumers with local businesses through reviews, ratings, and photos. This study focuses on understanding the factors influencing Yelp's star ratings, and offering strategic recommendations to affiliated businesses. The project examines the impact of various business attributes and customer reviews on star ratings, providing insights to enhance Yelp's business performance. The study employed logistic regression analysis due to its interpretability and ease of coefficient examination, which is essential for generating actionable insights for business owners. 

## Repo Structure
```
Yelp_Star_Rating_Analysis/
├── README.md
├── INSY446 – W24 – Group 1 – Python – Process_script.ipynb               # data preprocessing and variable transformation
├── INSY446 – W24 – Group 1 – Python – Model_script.ipynb                 # clustering analysis and hypothesis testing
├── INSY446 – W24 – Group 1 – Python – Text_analysis_script.ipynb         # test cloud analysis for comments
├── INSY446 – W24 – Group 1 – Slides.pdf                                  # presentation slide
├── INSY446 – W24 – Group 1 – Summary.pdf                                 # final model report
```
### Step-by-step Breakdown

1. <details>
    <summary>Data Collection and Preprocessing.</summary>

    - The data utilized for this analysis comes from Yelp's public dataset, consisting of five distinct files capturing business information, reviews, and geographical data. Key preprocessing steps included:
        - Grouping businesses by continent using longitude and latitude coordinates to simplify the analysis.
        - Dropping rows with missing values in crucial columns, such as coordinates.
        - Transforming textual data from reviews into numerical metrics using the `TextBlob` package, focusing on sentiment polarity and subjectivity scores.

    **NOTE:** Data cleaning steps ensured the integrity and reliability of the dataset used for further analysis.

   </details>

2. <details>
    <summary>Exploratory Data Analysis and Clustering.</summary>

    - Initial exploratory data analysis helped to understand the distribution and characteristics of the dataset. The project employed k-means clustering with k=2 to identify potential regional differences across continents, resulting in no significant disparities between clusters.
    
    - The clustering analysis supported dividing star ratings into binary categories, setting a threshold at 4 to classify businesses as "positive."

   </details>

3. <details>
    <summary>Hypothesis Testing.</summary>

    - To validate our clustering results and other initial findings, several hypothesis tests were performed, including:
      - A chi-squared test was used to assess the distribution of businesses across continents, concluding that there was no significant regional impact.
      
    Detailed testing rationales and outcomes are documented in the report.
   </details>

4. <details>
    <summary>Logistic Regression Modelling.</summary>

    - A logistic regression model was selected for its interpretability, focusing on predicting whether a business would achieve a rating of 4 or above. Key steps included:
      - Data scaling and standardization to prepare the inputs for modeling.
      - Addressing convergence issues by removing nearly unitary variables and refining predictor selections.

      **Final Model Equation:**
      ```
      logit(Probability of Positive Rating) = −0.2014+2.5612×sentiment_comment−0.4024×subjectivity_comment+0.0415×sentiment_tip+0.0189×subjectivity_tip−0.0258×checkins+0.1546×BusinessAcceptsCreditCards_True+0.1280×BusinessParking_garage_True−0.1104×BusinessParking_valet_True+0.0340×BikeParking_True
      ```
      - The model's results underscored sentiment scores as a primary driver of positive ratings, while features like valet parking had unexpected negative influences.

   </details>
