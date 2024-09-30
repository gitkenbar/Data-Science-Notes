# Stats 101
## PL15 - V1 - The Basics
### RDS Data and Variable Naming
    Let's assume you own a small Regional Delivery Service (RDS) who offers same-day delivery for letters, packages, and other small cargo. You are able to use Google Maps to group individual deliveries into one trip to reduce time and fuel costs. Therefore some trips will have more than one delivery.

    As the owner you would like to be able to estimate how long a delivery will take based on two factors: 1. The total distance of the trip in miles and 2. The number of deliveries that must be made during the trip

    To conduct your analysis you take a random sample of 10 past trips and record three pieces of information for each trip: 1. Total miles, 2. Number of deliveries, and 3. total travel time in hours.

    Miles Traveled  | numDeliveries | Travel Time(hr)
        (x₁)        |       (x₂)    |       (y)
        89          |       4       |       7
        66          |       1       |       5.4
        78          |       3       |       6.6
        111         |       6       |       7.4
        44          |       1       |       4.8
        77          |       3       |       6.4
        80          |       3       |       7
        66          |       2       |       5.6
        109         |       5       |       7.3
        76          |       3       |       6.4

    Remember in this case, you would like to be able to predict the TOTAL travel time using both the miles traveled and nubmer of deliveries on each trip.

    In what way does travel time depend on the first two measures?

    Travel time is the dependent variable and miles traveled and number of deliveries are independent variables.

    Note: some prefer predictor variables(s) and response variable instead of independent variable and dependent variable.


### Multiple Regression
    Multiple Regression is an extension of simple linear regression.

    IV -> DV  Simple linear regression 1 to 1

    IV IV IV (one or more) -> Multiple regression Many-to-One

### New considerations

    Adding more independent variables to a multiple regression procedure does not mean the regression will be "better" or offer better predictions; in fact it can make things worse. This is called Overfitting

    The addition of more independent variables create more relationships among them. So not only are the independent variables potentially related to the dependent variable, the are also potentially related to each other. When this happens, it is called Multicollinearity.

    The ideal is for all the independent variables to be correlated with the dependent variable but not with each other.

    because multicollinearity and overfitting, there is a fair amount of prep-work to do BEFORE conducting multiple regression analysis if one is to do it properly:
        Correlations
        Scatter Plots
        Simple Regressions

    Some independent variables or sets of independent variables are better at predicting the DV than others. Some contribute nothing.

    The Ideal is for all the independent variables to be correlated with the dependent variable but NOT with each other.

### Interpreting Coefficients
    In multiple regression, each coefficient is interpreted as the estimated change in y corresponding to a one unit change in a variable, when all other variables are held constant.

    ȳ = 27 + 9x₁ + 12x₂

    So in this example, $9000 is an estimate of the expected increase in sales y, corresponding to a $1000 increase in capital investment (x₁) when marketing (x₂) are held constant

## PL15 - V2 - Data Preparation
    Pre-work steps
        1. Generate a list of potential variables: independent(s) and dependent
        2. Collect Data on the Variables
        3. Check the relationships between each independent variable and the dependent variable using scatterplots and correlations
        4. Check the relationships among the independent variables using scatterplots and correlations
        5. (Optional) Conduct simple linear regressions for each IV/DV pair
        6. Use the non-redundant independent variables in the analysis to find the best fitting model
        7. Use the best fitting model to make predictions about the dependent variable.
   

   Before we include any independent variables with multiple regression we must prove a correlation with the dependent variable. If there isn't one, we will NOT use it.

   Multicollinearity - Relationships between Independent variables, they can cause issues with multiple regression

   If two independent variables are correlated they are redundant and you would only use one.

## PL15 - V3 - Evaluating Basic Models

    Regression analysis

    Variable Regressions

    In this first step, we will perform a simple regression for each independent variable individually. The first will be conducted in Excel then the rest in Minitab (SPSS, SAS, JMP, R, etc are all fine)
    We will discuss interpretations of results
    We will note how our results change:
        Coefficients
            Values, t-statistic, p-value
        Analysis of Variance (ANOVA)
            F-value, p-value
        R-Squared, R-squared(adjusted), R-squared(predicted)
        VIF (Variance Inflation Factor)
        Mallows Cₚ

    The standard error of the regression is the average distance of the datapoints from the regression line, in dependent variable units.

    The smaller the error, the less variation around the regression line. The larger the area the more "padding" around the regression line.

    

