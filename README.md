# King's County Housing Data Linear Regression Analysis 

![Kings County Map](Pictures/kc_map.png)

This experiment in linear regression aims to assess the fluctuation of prices of homes in Kings County, Seattle, for a private equity firm focusing on real estate acquisitions. The manipulation of the homes' variables such as square feet, waterfronts, and other architectural features affect the total worth of the house, and it is the intention of these linear models to explain the home's value. 

The data collected for the experiment range from 2014 to 2015, and it is essential to acknowledge the limitations of that specific factor as home prices were in a steep heel which marked the 2010's housing market from its recovery from the previous decade.



# Business Problem

The project was financed by a private equity firm looking to invest in the private home sector across the King's County area.

This linear regression analysis explains the relationship between an investment's price and the features of the underlying assets. 

The data used to project this model was limited to homes under six bedrooms and below the price of two million dollars. After analyzing the data, it was determined that these are the most popular household dimensions.

While this leads to a more robust and accurate inferring model, it does not shed enough light on homes considered the top tier of Seattle real estate.

# Data

The data used in this linear regression is housing data from Kings' County, Seattle, Washington. The data included the following columns; these are their names and descriptions:

* **id** - unique identified for a house
* **dateDate** - house was sold
* **pricePrice** -  is prediction target
* **bedroomsNumber** -  of Bedrooms/House
* **bathroomsNumber** -  of bathrooms/bedrooms
* **sqft_livingsquare** -  footage of the home
* **sqft_lotsquare** -  footage of the lot
* **floorsTotal** -  floors (levels) in house
* **waterfront** - House which has a view to a waterfront
* **view** - Has been viewed
* **condition** - How good the condition is ( Overall )
* **grade** - overall grade given to the housing unit, based on King County grading system
* **sqft_above** - square footage of house apart from basement
* **sqft_basement** - square footage of the basement
* **yr_built** - Built Year
* **yr_renovated** - Year when house was renovated
* **zipcode** - zip
* **lat** - Latitude coordinate
* **long** - Longitude coordinate
* **sqft_living15** - The square footage of interior housing living space for the nearest 15 neighbors
* **sqft_lot15** - The square footage of the land lots of the nearest 15 neighbors


Of the columns provided, the following were used for all three models:

Continious Variables: sqft_living, sqft_lot, sqft_basement, lat,long
Categorical Variables: bedroom, bathroom, floor,waterfront, view,condition, grade, yr_built,renovated


The baseline model was carried out using raw data. 

The subsequent model used a logarithmic transformation of the price of the homes to make statistical predictions more valid.

The third and final model focused on homes with a price under two-million dollars and six bedrooms, honing in on the niche market targeted by the private equity firm.


# Results

## Model 1

The baseline model included data from all homes sold across Kings County, Seattle. 

The following graphic depicts the early correlation between price and square feet.

![M1sq](Pictures/modelprice.png)

When we look at the linearity of the model, we appreciate the shortcomings of its predictive power.

![model1_lin](Pictures/model1.png)

## Model 2

The second model was carried out using data after a logarithmic or Log-Level regression on the price value as it is the dependent variable or determining outcome we are after.  

![Model_r](Pictures/model2_r.png)

The 'R-squared' value depicts the percentage of uncertainty the data used reflects on the outcome of this model.

The error below depicts the mistakes made while calculating the values from the same data set split into 80/20 percent between the "train" data and the "test" data.


Train: 173545.43\
Test: 184910.27


This number reflects the possible error from the actual home price of the underlying asset. 

The Price to variable relationship did, however, considerably increase.

![model2_lin](Pictures/model2.png)

## Model 3

The third model was performed under the same circumstances as the second model, except that home prices were kept under two-million dollars, and the number of bedrooms per home was six or less.

![model3_r](Pictures/model3_r.png)
![model3_var](Pictures/model3_var.png)
![model3_price](Pictures/model3_price.png)



**Train: 157,669.94\
Test: 153,145.46**

![bedrooms](Pictures/finalmodelpng.png)

The final model depicts a complex relationship between price and the underlying features of the home. The most correlated asset was square foot per home, with a positive correlation between price and area increase. 



This is a model where the dependent variable is logged, but the independent variable is not:


ln(Y) = a + bX + e


This is known as a log-level model, and the interpretation is that a unit increase in X results in a 100*b% rise in Y (we multiply by 100 because b is a percentage).



This would mean that a year increase in bedrooms is associated with a roughly 100*b% rise in price (log_price).

