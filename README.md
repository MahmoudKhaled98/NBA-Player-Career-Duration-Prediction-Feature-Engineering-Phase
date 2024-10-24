# NBA Player Career Duration Prediction - Feature Engineering Phase


## Overview
This project aims to provide insights to the National Basketball Association (NBA) by analyzing player performance data to predict career duration. In this phase, I focus on feature engineering to identify and create relevant features that enhance the predictive power of the model.
## Table of Contents
- [Project Description](#project-description)
- [Key Objectives](#key-objectives)
- [Feature Engineering Steps](#feature-engineering-steps)
- [Dataset](#dataset)
- [Feature Selection](#feature-selection)
- [Feature Transformation](#feature-transformation)
- [Feature Extraction](#feature-extraction)
- [Future Steps](#future-steps)
- [Conclusion](#conclusion)
- [How to Run](#how-to-run)
- [References](#references)

## Project Description
The goal of this project is to assist NBA managers and coaches in identifying players likely to succeed in the competitive environment of professional basketball. By analyzing a dataset of NBA player performance records, we aim to predict whether a player's career will last at least five years.

## Key Objectives
- Conduct feature engineering to identify the most effective predictors for career duration.
- Clean and prepare the data for the Naive Bayes model, ensuring it meets the model's assumptions.
- Create new features that reflect player performance and efficiency based on existing data.

## Feature Engineering Steps
1. **Data Exploration**: Review the dataset to understand its structure, dimensions, and features.
2. **Feature Selection**: Identify relevant features and discard those that do not contribute meaningfully to the model (e.g., player names).
3. **Feature Transformation**: Ensure that categorical features are encoded as numerical values `Feature encoding`.
4. **Feature Extraction**: 
   - Combine relevant features to create new metrics like `total_points` and `efficiency`.
   - Assess and extract features that will improve the predictive capability of the model.

## Dataset
The dataset consists of performance metrics for NBA players, including:

|Column Name|Column Description|
|:---|:-------|
|`name`|Name of NBA player|
|`gp`|Number of games played|
|`min`|Number of minutes played|
|`pts`|Average number of points per game|
|`fgm`|Average number of field goals made per game|
|`fga`|Average number of field goal attempts per game|
|`fg`|Average percent of field goals made per game|
|`3p_made`|Average number of three-point field goals made per game|
|`3pa`|Average number of three-point field goal attempts per game|
|`3p`|Average percent of three-point field goals made per game|
|`ftm`|Average number of free throws made per game|
|`fta`|Average number of free throw attempts per game|
|`ft`|Average percent of free throws made per game|
|`oreb`|Average number of offensive rebounds per game|
|`dreb`|Average number of defensive rebounds per game|
|`reb`|Average number of rebounds per game|
|`ast`|Average number of assists per game|
|`stl`|Average number of steals per game|
|`blk`|Average number of blocks per game|
|`tov`|Average number of turnovers per game|
|`target_5yrs`|1 if career duration >= 5 yrs, 0 otherwise|


## Feature Selection
The resulting features selected for the model include:
- Games played (`gp`)
- Average points (`pts`)
- Minutes played (`min`)
- Field goal percentage (`fg`)
- Three-point percentage (`3p`)
- Free throw percentage (`ft`)
- Total rebounds (`reb`)
- Assists, steals, blocks, and turnovers.
- Engineered Features: 
  - Total Points (`total_points`)
  - Efficiency (`efficiency`)

## Feature Transformation
A key part of feature transformation is 'feature encoding'. Categorical columns I plan to use as features must be converted into numerical formats.

- Many types of models are designed in a way that requires the data coming in to be numerical, normalized, standardized, or taking the log() if its distribution is skewed. So, transforming categorical features into numerical features is an important step. 
- In this particular dataset, `name` is the only categorical column, and the other columns are numerical. Given that `name` is not selected as a feature, all of the features that are selected at this point are already numerical and do not require transformation. 

## Feature Extraction
Through the feature engineering process, the following new features were created:
- **Total Points (`total_points`)**: Total points scored across all games, calculated by combining `gp` and `pts`.
- **Efficiency (`efficiency`)**: Points earned per minute, derived from the total points (`total_points`) divided by the total minutes played (`min * gp`).

## Future Steps
The next phase will involve building the Naive Bayes model using the cleaned and engineered dataset. Insights gained from the model will be shared with stakeholders, along with recommendations based on the analysis.

## Conclusion

In this project, I'm focused on feature engineering to help predict NBA player career longevity based on performance metrics. 

- **Data Overview**: The dataset consists of 1,340 observations with 21 features, primarily numerical, capturing player performance metrics.

- **Feature Selection**: I carefully selected relevant features such as games played, points scored, shooting percentages, and various performance statistics to create meaningful insights.

- **Engineered Features**:
Through the feature engineering process, the following new features were created:
  - **`total_points`**: Total points scored across all games, calculated by combining `gp` and `pts`.
  - **`efficiency`**: Points earned per minute, derived from the total points `total_points` divided by the total minutes played (`min * gp`).

- **Data Integrity**: I ensured that the data is clean and free of missing values, as this is crucial for building an effective predictive model.

- **Statistical Balance**: I evaluated the class distribution in the target variable, which indicates career duration, noting that while it is somewhat imbalanced, it is not severely skewed.

- **Next Steps**: Moving forward, I will prepare the data for a Naive Bayes model, keeping in mind the independence assumption of features. This will involve creating new features that reflect player efficiency and performance while dropping redundant original features.

- **Insights for Stakeholders**: Key attributes will be summarized for stakeholders, providing them with an understanding of how player performance metrics will inform the predictive model and assist in strategic decisions.
## How to Run

1. **Clone the repository**:

    ```bash
    git clone <https://github.com/MahmoudKhaled98/NBA-Player-Career-Duration-Prediction-Feature-Engineering-Phase.git>
    ```

2. **Install the required dependencies**:

    ```bash
    pip install -r requirements.txt
    ```

3. **Run the Jupyter notebook**:

    ```bash
    jupyter notebook
    
## References
- [Pandas Documentation](https://pandas.pydata.org/)
