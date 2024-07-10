FLOOD PREDICTION IN LAGOS USING RANDOM FOREST ANALYSIS

INTRODUCTION
Flooding is the most frequent and natural catastrophe that may happen anyway within the globe. Lagos, Nigeria faces recurrent challenges with flooding due to its coastal location, rapid urbanization, and inadequate infrastructure. The city is ranked as the number seven in the fastest growing cities. This report aims to explore the methodologies and strategies for predicting flood events in Lagos, crucial for enhancing preparedness and mitigating risks.
Map of Lagos State
 
DATA COLLECTION
To predict the next flood event in Lagos, the following data sources and methodologies were utilized:
1.	Historical Flood Data: I gathered historical rainfall data for Lagos from 2002-2024 to identify patterns and trends in precipitation.
2.	Meteorological Data: I gathered meteorological data and flood data to know the potential flow of flood in Lagos. These includes Rainfall patterns, sea levels.
3.	Predictive Modelling: I made use of statistical model like the Linear Regression model to predict the next flood event.
The collected dataset from 2002-2024 were merged based on common columns (Date and Location) to create a comprehensive dataset. Missing values were filled with zeros to handle the gaps found in the data. Some unnecessary columns were deleted to ensure a clean analysis.  
 
EXPLORATORY DATA ANALYSIS

1.	YEARLY RAINFALL

This graph shows the average amount of rainfall in Lagos over the past 10 years, from 2005-2025. The average rainfall has fluctuated over the past 10 years. There has been an increase in rainfall in the past from (2005-2010) and lower rainfall in the lesser years (2015-2024).

2.	DISTRIBUTION OF PRECIPICATION

This graph shows the frequency of precipitation in Lagos, and it is measured in millimetres(mm). We can see that the frequency of precipitation is highest at lower amounts of precipitation, and it decreases as the amount of precipitation increases. This means that there is a higher frequency of lower precipitation events in Lagos.
FEATURE ENGINEERING
Feature engineering is the process of creating new features or modifying existing ones to improve the performance of machine learning models. In the context of flood prediction, the features were carefully engineered to capture the relevant patterns and relationships within the data that could help in predicting flood events.
1. Date: Extracting this component from the date time column helps the model understand seasonal patterns, trends, and variations over time.
2. Weather-related Features: Knowing the Cumulative Rainfall that is summing up rainfall over the past few days can provide a more comprehensive view of the water saturation in the area, which is critical for flood prediction.
3. Lag Features: Including the rainfall from the previous day or previous days can help capture the short-term dependencies and trends.
Feature engineering directly impacts the model's ability to learn and make accurate predictions. By including relevant and well-constructed features, we provide the model with the necessary information to identify patterns and relationships that are indicative of flood events. For example, cumulative rainfall can help the model understand the conditions that lead to floods, which might not be apparent if the features were used in isolation.
The features are listed at the left hand side of the graph, with ‘precip’(precipitation) at the top and ‘cumulative rainfall’ at the bottom. The importance of each feature is represented by the height of the bar on the right hand side of the graph. This shows that precip, humidity, temp are the most important features for the model.
DATA ANALYSIS/ MODEL SELECTION
Random Forest Classifier is a learning method that is capable of handling complex relationships between variables. It is trained on features including temperature, humidity, cumulative rainfall, and precipitation. The Random Forest model predicts flood probability using a combination of decision trees, aggregating predictions to assess flood risk based on weather conditions. Here's a detailed explanation of how the Random Forest formula and model were applied in the flood prediction task.
1.  	Decision Trees: A decision tree splits the data at various points based on features to create nodes and branches, eventually leading to a prediction at the leaf nodes.The splits in the tree are determined based on measures like information gain, which quantifies the reduction in uncertainty (entropy) after a split.
2. Random Forest Construction:
Bootstrap Sampling: Multiple subsets of the original dataset are created by sampling with replacement.
Feature Selection: For each tree, a random subset of features is selected at each split, ensuring diverse and uncorrelated trees.
Building Trees: Each tree is built independently using the bootstrapped datasets and selected features.
Aggregation: The final prediction is obtained by aggregating the predictions from all trees. For classification, this is typically the mode of the predictions, and for regression, it is the average.
APPLICATION IN FLOOD PREDICTION
The data was split into training and testing sets to evaluate the model's performance on unseen data. A Random Forest classifier was trained on the training data using the engineered features. The model learns to identify patterns and relationships in the data that are indicative of flood events. The trained model was used to make predictions on the test set. The performance of the model was evaluated using metrics such as accuracy, precision, recall, and F1 score, derived from the confusion matrix. The model was then applied to future dates to predict the likelihood of flood events. The date with the highest predicted probability of flooding was identified as the next likely flood date.
 
 
 

RESULTS/FINDINGS
The chart above displays observed and forecasted flood data for Lagos from 2015 to 2025. The blue bars represent observed data, while the red line and shaded pink area represent the forecasted flood data with confidence intervals.
1.    Observed Data (2015-2023)
The blue bars indicate the
frequency and intensity of observed flood events in Lagos over the period from
2015 to 2023. There are significant variations in flood events, with
some peaks reaching high values, indicating severe flooding events. The density and height of the bars suggest periods of frequent flooding, particularly around the years 2017, 2018, and 2020.
2.    Forecasted Data (2024-2025)
The red line represents the
forecasted mean flood severity from mid-2023 to 2025. The shaded pink
area around the red line indicates the confidence interval, suggesting the
range within which future flood events are expected to occur. The forecast shows a steady trend, indicating expected flood activity in the coming years, though the precise intensity and frequency can vary within the shaded confidence interval.
 
PREDICTION
The forecasted data suggests continued flood risk in the near future, with the confidence interval widening as it extends further into the future, indicating increasing uncertainty. Based on the forecast, significant flood events are likely around mid-2024, aligning with historical patterns of flooding typically occurring during the rainy season which is usually from April- October. The exact date of the next flood is [Timestamp('2024-07-08 00:00:00'), Timestamp('2024-07-09 00:00:00'), Timestamp('2024-07-12 00:00:00')
 


CONCLUSION
Through comprehensive feature engineering, we enhanced the model's ability to capture relevant patterns and relationships within the data. The Random Forest model, with its ensemble learning approach, provided robust predictions by combining multiple decision trees. This approach enabled us to accurately predict the next likely flood date in Lagos, aiding in proactive flood management and disaster preparedness.
RECOMMENDATIONS
Urban Planning: Implement strict zoning laws to restrict development in high-risk flood areas.
Infrastructure Improvement: Upgrade drainage systems and construct barriers to manage floodwaters.
Wetland Restoration: Rehabilitate natural wetlands to enhance drainage and reduce flood risk.
FURTHER ANALYSIS
Further analysis and continuous monitoring of flood data are recommended to refine the predictions and update flood management plans accordingly. Regular updates to the forecast model with new data will enhance the accuracy and reliability of flood predictions.

DATA SOURCE
Nigerian Meteorological Agency (NIMET) 

