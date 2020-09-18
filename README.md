## Toronto Housing Price Analysis

### Results:
#### Top 5 Final Prices of Properties by Type in Toronto
![Top 5 Final Prices of Properties by Type in Toronto](../master/Results/final-prices-of-different-properties-by-type.png)

#### Toronto Neighbourhood Boundaries - Shapefile is from OpenDataToronto and visualization is plotted with Python's GeoPandas library
![](https://github.com/KevinRiady/Toronto-Housing-Prices-Analysis/blob/master/Results/Toronto-neighbourhood-boundaries.png)

#### Overall house price in the GTA is highly skewed - to be normalized
![](https://github.com/KevinRiady/Toronto-Housing-Prices-Analysis/blob/master/Results/final_price_highly_skewed.png)

#### Overall median household income in the GTA is highly skewed - to be normalized
![](https://github.com/KevinRiady/Toronto-Housing-Prices-Analysis/blob/master/Results/average_income_highly_skewed.png)

#### Distribution of house prices in the GTA
![](https://github.com/KevinRiady/Toronto-Housing-Prices-Analysis/blob/master/Results/distribution-of-housing-prices-in-GTA.png)

#### Distribution of house prices in the GTA post-normalization using BoxCox Technique
![](https://github.com/KevinRiady/Toronto-Housing-Prices-Analysis/blob/master/Results/distribution-of-transformed-housing-prices-in-GTA.png)

#### Distribution of household income in the GTA
![](https://github.com/KevinRiady/Toronto-Housing-Prices-Analysis/blob/master/Results/distribution-of-mean-income-in-GTA.png)

#### Distribution of household income in the GTA post-normalization using BoxCox Technique
![](https://github.com/KevinRiady/Toronto-Housing-Prices-Analysis/blob/master/Results/distribution-of-transformed-mean-income-in-GTA.png)

#### A visualization of household income within each district in the GTA post-normalization
![](https://github.com/KevinRiady/Toronto-Housing-Prices-Analysis/blob/master/Results/GTA-neighbourhood-income-color-coded.png)

#### Feature Importance Plot
![](https://github.com/KevinRiady/Toronto-Housing-Prices-Analysis/blob/master/Results/feature-importance-plot.png)

#### Feature Correlation Graph
![](https://github.com/KevinRiady/Toronto-Housing-Prices-Analysis/blob/master/Results/features-correlation-graph.png)

#### ML Algorithms Test Scores
![](../master/Results/ML-algo-test-scores.png)


### End to End Machine Learning Project


1. **End Goal**
     - A web application service for eager homebuyers/homesellers.
         1. By inputting address/No. of bedrooms or bathrooms/ square feet, you'd be able to predict the appropriate house price up to X% of accuracy. 
         2. By inputting your income, find which areas would be best suited for you. Find areas where you'd be below average & where you'd be above average in income. 
     
2. **Framing the Analysis**
   - It is a supervised learning and a univariate multiple regression problem.
   - Performance Measure: Root Mean Square Error (RMSE). 
     - Since the total number of outliers is quite low, this is more ideal than using Mean Absolute Error.
   
3. **Project Ideas**
   - Implement a recommender system for houses in the neighbourhood you're interested in.


**Making sense of the data:**
1. ✅ How many different types of properties are there?
2. ✅ For each property type, what prices do they typically command?
    - ✅ Calculate the median, and percentiles for each property type.
3. ✅ Typical number of bedrooms & bathrooms, sqft. and parking in each type of property
4. ✅ Which feature has the greatest contribution to the house price? 
5. ✅ How much negotiation takes place during housing deals? (The mean of the difference between Final Price and Listed Price)
6. ✅ Determining the spread of housing & the mean price of houses in each area (neighbourhood locations and shapes are from another dataset)
   - Calculate the median, and percentiles of prices for each neighbourhood.
7. ✅ Average income of the people who live in those areas (from title or full address)
8. ✅ How correlated is average income with final home price?

**Data Science and Machine Learning Techniques used in this project:**
- ✅ Stratified sampling to ensure sufficient number of instances within each income bracket.
- ✅ Identifying correlations
- Exploring attribute combinations
- ✅ Handling text and categorial attributes.
- ✅ Power Transformers using Bokeh/Seaborn - Log Transform: Purpose is to normalize a skewed dataset. The use of Yeo-Johnson Transformation
- ✅ Feature scaling and feature importance matrix (Tree Repressor)
- 🟧 Custom imputer for missing values: Base Estimator and TransformerMixin

**Machine Learning Steps:**

Introduction
1. ✅ Train and test set
   - Ensuring the use of stratified sampling vs. random sampling to ensure enough instances within each income bracket.
2. ✅ Exploring models and shortlisting the best ones
3. ✅ Creation of custom evaluation functions
4. ✅ Creating estimator space and preselecting models 
5. ✅ Cross-validation technique
Hyperparameter Tuning
6. ✅Intro to Bayesian Optimization
7. 🟧Using various techniques: LightGBM with Hyperopt, LightGBM with RandomSearchCV, Hyperopt vs RandomSearchCV, XGboost with Hyperopt, RandomForest with Hyperopt
8. 🟥Leverage encapsulation using StackingCVRegressor

**Key Learning Opportunities**
- sklearn API design principles of Consistency (Estimators, Transformers, Predictors) and Inspection (Non-profileration of classes, composition and sensible defaults).

**Performance enhancements to be implemented**
- Speed:
    - Modify import statements for quicker imports
    - Make read_excel faster
    - ❗ Modify slow *for* loops with their corresponding list comprehension version
- Memory:
    - Reduce the number of dataframe copies
    
**Enhancing Data Visualization Results**
- *Final price by property type* boxplot -> remove outliers from view for a more effective visualization.