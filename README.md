# fema-declarations

<h2> Motivation </h2>
To determine whether counties can better predict whether a weather event will be declared a disaster and request aid in advance and to help FEMA better plan for the instances in which they will need to provide aid.

<h2> Methodology and Results </h2>
Tools used: scikit-learn, pandas, seaborn    

The data used for this project can be categorized in two groups: exposure and susceptibility. Exposure considers weather-related factors, such as levels of precipitation and temperature. I pulled this information from CDIAC. I then used the National Oceanic and Atmospheric Administration (NOAA) to find all major weather events and merged this with FEMA's database of declarations to find those events that were declared disasters. The second category of data is susceptibility, which relates to socioeconomic factors and quality of infrastructure, with data being used from the Census and the American Community Survey.     

I ran several types of classification models, including logistic regression, random forest, and gradient boosting trees. Because FEMA-declared disasters make up only 3-4% of the dataset, I oversampled with a 1:1 ratio for both the training and final holdout datasets. Gradient boosting trees performed the best so I used gridsearch to finalize the parameters for the model. 

<h2> Results </h2>

On the holdout set, the model performed well with a recall score of 88%. In this case, recall is an important parameter because it is better to ensure that all disasters are captured. The important features were per capita income, average temperature during the event, percentage minority, and percentage rural.    

I created a d3 map showing the locations of the weather events and color-coding by whether the event was FEMA-declared.     


<h2> Next Steps </h2>

Unsurprisingly, demographics was the most important in predicting a FEMA declaration. However, it might be interesting to break down this analysis by region to hone in on other factors. It would also be interesting to see whether this could be used to forecast declarations given weather predictions for a county. Expanding the dataset to include historical data would also help to identify shifts in trends of weather events, but also to show whether counties that receive aid are able to rebound and better prepare for future storms. 
