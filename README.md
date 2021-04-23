# King's County Housing Project

## Overview

We have been provided with a large dataset containing information about houses sold in the DC area between 2014 and 2015. We will be using regression modeling to analyze and predict house sales price in the King County area.

### Questions we would like to answer

* Do the prices of the houses sold differ depending on the city they're located in?
* Does renovation have an effect on house price?
* Do waterfront houses have higher prices than other houses?

## Exploratory Data analysis

Using the "Geopandas" package and matplotlib, we plotted a map showing the houses in King County Area.
![Dataset kingcountymap](https://github.com/Wonuabimbola/phase_2_project/blob/beta/images/kingcountyMap.png)

We also created some visualization showing some of the variables and their relationships with the house prices in our dataset.
![Dataset Regplots](https://github.com/Wonuabimbola/phase_2_project/blob/beta/images/regression_plots.png)

The plots above show that some of the variables like sqft_living, number of bathrooms, number of bedrooms and grade have a clear positive relationship with price. We also saw that there is a high chance that the price of a house with a waterfront is higher than the price of a house without a waterfront.

Also, during the exploration, we discovered quite a few things:
* There are 267 duplicated houses
* 744 of the houses were renovated
* 97.55% of the houses in the dataset have between 2 and 5 bedrooms
* 98.42% of the houses have between 1 and 4 bathrooms

#### We then decided to visualize a barplot showing these findings
