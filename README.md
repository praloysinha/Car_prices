# Predicting Car_prices 
Link to the Jupiter Notebook https://github.com/praloysinha/Car_prices/blob/main/Praloy_Practical_Application_II.ipynb

Important - The csv datafile was not uploaded due to its size as it Git Hub did not accept a 50 MB file

**Objective: ** - The car dealership would like to know the important features in an used car which would increase the price of a car. It would help him to maintain the inventory based on those features and hence get a better return on his investment

**Approach and Assumption:** In order to know what features are potentially important, we would need to conduct a data analyses of the available data and build a logical model which would predict the prices of the used car and show the important features which maximise it.
The assumption is that sufficient data is available to analyze which is reflective of the current reality and modelling them would give way to predict prices with reasonable accuracy.

**Data** - A dataset of 426,880 entries comprising of the price of the used car and its 17 different features were used for this analyses

**Exploration and Preparation** - The dataset was explored to gauge its quality for missing values, data types, zero values, columns which can be dropped without any impact, and categorical data. A few data preparation operations were conducted to get it ready for modelling.
The following were used - dropping of a few unnecessary columns and rows, conversion to usable data types,  simple imputation of null and zero values, encoding of categorical values with _James Stein_ encoder. Iterative imputation was evaluated but dropped due to high number of categorical values which werent imputed by this method. 

**Modelling:** A regression model with Price as the dependant variable and the other features were built. A few key steps in it were the following:-
1. Variance inflation Factor check for Multicollinearity
2. Scaled the data for comparable model coefficients
3. Created the train - test split for the Hold Out Cross validation
4. Built the Pipeline with Polynomial features, sequential feature selection to get the top 5 features since there were 14 of them, and a Ridge regression to model the coefficients
 ![image](https://github.com/praloysinha/Car_prices/assets/153297109/baaeb1d9-1824-4dfb-b8c7-4b2923325992)
5. The training MSE was quite low at 0.97 which meant a good fit
6. **Important** - GridSearchCv was not used due to 2 reasons
a. The MSEs were quite low and optimization may not yield signifcantly better results
b. It is taking VERY LONG TIME to process this data and I did not get any results after running for hours
The coefficients were extracted for the 5 features

**Results and Interpretaion** - The top features in descending order of importance are **Model, Region, condition, manufacturer**. All of them are positively related to price except for the 5th one model^2 which is negatively related. So higher the model, regiom,condition, manufacturer score, higher the price.
The top ones in each of these features are which would drive higher price: 
**Models:**
mazda3 i touring hatchback
leaf s hatchback 4d
gladiator overland
silverado 1500
tahoe
sorento
xf 20d premium sedan 4d
pt cruiser limited edit
romeo stelvio ti sport suv
traverse premier

 The car dealership should focus on the **above top 10 models** above in the **3 cities (Bellingham, Birmingham and Auburn)** in **good condition** manufactured by **Ford and Chevrolet** in order to maximise the price of the car that they sell. 
 
 **Conclusion:** The inventory of the dealership with the above features would help get a better price. 
