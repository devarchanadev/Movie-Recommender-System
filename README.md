# 🎬 Movie Recommender System

[![Jump to Project Overview](https://img.shields.io/badge/Project%20Overview-📋-blue?style=for-the-badge&logo=read-the-docs)](#project-overview) 
[![Jump to Analysis & Comparison](https://img.shields.io/badge/Analysis%20and%20Comparison-🔍-blue?style=for-the-badge&logo=search)](#analysis-comparison) 
[![Jump to Business Impact](https://img.shields.io/badge/Business%20Impact-💼-blue?style=for-the-badge&logo=business)](#business-impact) 
[![Jump to Tools & Technologies](https://img.shields.io/badge/Tools%20and%20Technologies-🔧-blue?style=for-the-badge&logo=tools)](#tools-technologies) 
[![Jump to Data Processing](https://img.shields.io/badge/Data%20Processing-📊-blue?style=for-the-badge&logo=analytics)](#data-processing) 
[![Jump to Insights & Recommendations](https://img.shields.io/badge/Insights%20and%20Recommendations-📝-blue?style=for-the-badge&logo=write)](#insights-recommendations) 
[![Jump to Key Takeaways](https://img.shields.io/badge/Key%20Takeaways-🏆-blue?style=for-the-badge&logo=trophy)](#key-takeaways) 
[![Jump to Installation Steps](https://img.shields.io/badge/Installation%20Steps-📥-blue?style=for-the-badge&logo=download)](#installation-steps) 
[![Jump to Conclusion](https://img.shields.io/badge/Conclusion-📉-blue?style=for-the-badge&logo=chart)](#conclusion)

[![GitHub Repo](https://img.shields.io/badge/Visit-GitHub_Repo-181717?style=for-the-badge&logo=github)](https://github.com/your-repo-link)  
[![Download Dataset](https://img.shields.io/badge/Download%20Dataset-green?style=for-the-badge)](https://grouplens.org/datasets/movielens/)

---

## Project Overview

In this project, I developed a movie recommender system similar to those used by popular streaming platforms like Netflix and Amazon Prime. Leveraging the MovieLens dataset, which consists of approximately 100,000 ratings from 943 users on 1,664 movies, the system aims to provide personalized movie recommendations.

## 🚀 Implementation

### User-Based Recommendation System

1. **Data Preparation**: Converted MovieLens data into a `realRatingMatrix` suitable for recommendation algorithms.
2. **Model Training**: Created a recommender model using the **UBCF (User-Based Collaborative Filtering)** method.
3. **Recommendation Generation**: Generated top 10 movie recommendations for a subset of 5 users.

```r
library(recommenderlab)
data(MovieLense)
R <- as(MovieLense, "realRatingMatrix")
recommender_userbased <- Recommender(R, method = "UBCF")
recom <- predict(recommender_userbased, R[1:5], n=10)
as(recom, "list")
```

## Item-Based Recommendation System
1. **Model Training**: Applied the IBCF (Item-Based Collaborative Filtering) method to the same realRatingMatrix.
2. **Recommendation Generation**: Generated top 10 recommendations for the same subset of 5 users.

---

## 🔍 Analysis & Comparison

### Recommendations Comparison

| **User** | **User-Based Recommendations**                      | **Item-Based Recommendations**                  |
|----------|-----------------------------------------------------|--------------------------------------------------|
| User 0   | Boot, Das, Matilda                                 | The Dorothy Day Story, Big Bang Theory          |
| User 1   | Con Air, Paradise Lost                             | They Made Me a Criminal, The Dorothy Day Story  |
| User 2   | Heavy Metal, MST3K                                 | The Dorothy Day Story, Legal Deceit             |
| User 3   | It Happened One Night, Jungle Book                 | Men of Means, The Dorothy Day Story             |
| User 4   | Paradise Lost, Leaving Las Vegas                   | They Made Me a Criminal, Coldblooded            |

### Observations

- **Relevance**: Recommendations align with user interests based on historical data.
- **Novelty**: Introduces new and lesser-known movies, enhancing content discovery.
- **Serendipity**: Provides unexpected and diverse choices, potentially surprising users.
- **Diversity**: Includes a mix of genres, catering to various user preferences.

## 💼 Business Impact

The recommender system can significantly enhance user engagement and satisfaction for streaming platforms by providing personalized and diverse movie recommendations. By utilizing collaborative filtering techniques, it addresses user preferences more accurately, thereby improving content discovery and retention.

## 🔧 Tools & Technologies

- **R Programming Language**
- **recommenderlab Library**
- **MovieLens Dataset**: [Download MovieLens Dataset](https://grouplens.org/datasets/movielens/)

## 📊 Data Processing

- **Data Cleaning**: Managed missing values and formatted the data for analysis.
- **Data Source**: MovieLens dataset provides user ratings and movie information.

## 📝 Insights & Recommendations

- **Relevance**: Align recommendations with user interests based on historical ratings.
- **Novelty**: Introduce lesser-known content to expand discovery.
- **Serendipity**: Provide unexpected choices to enhance user experience.
- **Diversity**: Include a variety of genres to cater to different interests.

## 🏆 Key Takeaways

- **Statistical Importance**: Analyzing user preferences and item similarities provides valuable insights into user behavior and content alignment.
- **Recommender Systems**: User-based methods focus on similar user preferences, while item-based methods emphasize item attributes.
- **Data Science Practice**: Effective collaborative filtering improves personalized recommendations.

## 📥 Installation Steps

1. Install R from [CRAN](https://cran.r-project.org/)
2. Install the `recommenderlab` package using: `install.packages("recommenderlab")`
3. Load the dataset and libraries as shown in the provided R scripts

## 📉 Conclusion

The recommender system successfully meets its goals of relevance, novelty, serendipity, and diversity. By understanding user preferences and item similarities, it provides a tailored and engaging user experience. Further analysis with user feedback and additional metrics will enhance the system's performance and alignment with user needs.
