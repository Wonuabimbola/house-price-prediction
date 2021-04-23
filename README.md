# King's County Housing Project

### Authors: [Wonuola Abimbola](https://github.com/Wonuabimbola), [Kibae Kim](https://github.com/jayce7376)


## Overview

We have been provided with a large dataset containing information about houses sold in the DC area between 2014 and 2015. We will be using regression modeling to analyze and predict house sales price in the King County area.

### Questions we would like to answer

* Do the prices of the houses sold differ depending on the city they're located in?
* Does renovation have an effect on house price?
* Do waterfront houses have higher prices than other houses?

## Exploratory Data analysis

Using the "Geopandas" package and matplotlib, we plotted a map showing the houses in King County Area.
![Dataset kingcountymap](https://github.com/Wonuabimbola/phase_2_project/blob/master/images/kingcountyMap.png)

We also created some visualization showing some of the variables and their relationships with the house prices in our dataset.
![Dataset Regplots](https://github.com/Wonuabimbola/phase_2_project/blob/master/images/regression_plots.png)

The plots above show that some of the variables like sqft_living, number of bathrooms, number of bedrooms and grade have a clear positive relationship with price. We also saw that there is a high chance that the price of a house with a waterfront is higher than the price of a house without a waterfront.

Also, during the exploration, we discovered quite a few things:
* There are 267 duplicated houses
* 744 of the houses were renovated
* 97.55% of the houses in the dataset have between 2 and 5 bedrooms
* 98.42% of the houses have between 1 and 4 bathrooms

#### We then decided to visualize a barplot showing these findings
![findings visualization](https://github.com/Wonuabimbola/phase_2_project/blob/master/images/data_cleaning.png)

## Data Cleaning

We cleaned the data up a bit by dropping the duplicated house entries. We also dropped the rows that had NAN values as well.


## Feature Engineering

### Cities

We used city names instead of the zipcodes because we thought the city names would also be able to explain the price differences between the areas. We were able to get the city names that correspond to the zipcodes in the data by using [this website](https://www.zipcodestogo.com/Washington/) and we added it as a new column to our existing dataframe.

We created dummy variables by categorizing
* the cities into high, low priced cities using the average price per city. 
* the houses into those that were sold less than 20 years after they were renovated, those that were sold more than 20 years after they were sold and those that were not renovated.

We found we did not need to create dummy columns for waterfront as it was already in that format.

We then plotted the different categories above against their average prices as shown below.
![Dummy variables of cities,waterfront,and renovation against their average prices](https://github.com/Wonuabimbola/phase_2_project/blob/master/images/Price&dummy_variables.png)

## Model Testing

After testing several models with different variables and squared variables, we removed some multicollinearity and found the model with the best R-squared score (0.695). 

Using the coefficient of the predictors from our linear regression model, we predicted the house prices. This figure below shows the comparison between the prices we predicted and the actual prices of the houses in order for us to see how close our predictions are.
![predicted versus actual house prices](https://github.com/Wonuabimbola/phase_2_project/blob/master/images/Real_predicted_price.png)

## Conclusion

We were able to achieve a test RMSE of approximately 189,719 which we know is quite high. However, our R-squared score of 0.695 is pretty good as it explains 69.5% of the variance in the house price that is predictable from our independent variables.

* Cities
  
  * The house prices in higher priced cities are $128k higher while the house prices in lower priced cities are $185k lower than middle priced cities’.

* Renovation
  
  * The houses with less than 20 years between date sold and date renovated are $82k higher than houses that were not renovated.

* Waterfront
  
  * The prices of waterfront houses are $650k higher than other houses.

## Next Steps

We also think that there may be other external factors like quality of schools, crime rate, proximity to transport or malls; that may also affect the pricing of houses. So, obtaining data on these factors in relation to the location of the houses would greatly help our model in being more accurate.

# Navigation


```
├── README.md                              <- This README file
├── data
│   ├── mapping                            <- contains files for mapping with geopandas
│   ├── column_names.md                    <- description of columns
│   ├── kc_house_data.csv                  <- data provided by flatiron school
├── gitignore                              <- files to ignore
├── King_County_Project.ipynb              <- final notebook
├── king_county_housing_presentation.pdf   <- presentation
└── images                                 <- Visualizations used in README and pdf file
