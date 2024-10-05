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

    

## PL15 - V10 - Forward Selection
    Feature variables are examined one at a time.
    The analyst sets a stopping rule (there are several such as p-value) that acts as a hurdle that must be overcome to be allowed into the model.
    The added variable must reduce error significantly.
    The feature variable that reduces model error (SSE) the most is chosen so long as it passes the stopping rule.

### Flaws in Forward Selection
    The ability of variables to reduce error can change as other variables enter the model.
    As feature variables are added they begin to overlap and interact in how they explain variance (reduce error).
    Since a feature variable stays in the model once it enters forward selection is not flexible.

    Example: V1 enters first. Then V2. Then V3. Let's say V2 and V3 combined reduce error better than V1 alone. This may lead to V1 failing hte stopping rule, but it is stuck in the model!

    Squared semipartial correlations can tease out the relationships.
    It can also miss suppressor and/or complimentary relationships:
        Suppressor variables (also called enhancer variables) are strange. They correlate with parts of other variable(s) but not the target. They eat up (suppress) some of the non-relevant error in those variables making the model stronger.
        Complimentary variables are negatively correlated with each other but together explain the target variable very well; tradeoff.
    
    Step 1: Evaluate single features
        Ex: Housing data
        X1, X2, X3, X4

        Evaluate, find large F values, is p<0.05?, if yes. keep and compare.

        the p-value requirement to keep in model is up to the analyst, larger p values will allow more variables in the model, smaller will allow less. There is no 'right' answer.
        NOTE: SSE df p-value

    With no feature variables entered:
        SST = SSE

    RMSE = Root of mean square error

    Enter sqft. Largest SS(sum of squares) and overcomes stopping rule

    Enter bath. Largest SS and overcomes stopping rule

    Enter exemptHS. Largest SS and overcomes stopping rule.

    Reject beds. Fails to overcome stopping rule.

    Notice that the F-ratio (and sum of squares) for sqft keeps going down. Some of that error overlaps with other variables.

    F-Ratio Decline:
    152.18 to 91.47 to 76.14

    While it does not happen in this example, this is where forward selection can get us into trouble.

    It is possible that earlier variables stuck in the model violate the stopping rule as new variables are added and sum of squares is reallocated.

    price1000s = -63.67 + .00732(sqft) + 28.93(exempHS) + 35.47(baths)

    Each sqft adds $73.20
    Being in an exemplary school district adds 28,930 to the value of the home because it's an indicator variable
    Each bathroom adds $35,470 to the value of the home

    V1 - 40% of the variance (.4 R²)
    V2 - 30% of the variance (.3 R²)
    V3 - 20% of the variance (.2 R²)

    By forward selection, V1 would go first.
    But what if V2 and V3 added up to 45% and when they are added, and in the final model V1 only explains 10% of the variance and falls below the stopping rule.

    While this is exaggerated for educational purposes, it is important to know that this is possible. Forward selection can leave us with a variable that loses explained variance over time as the model grows and SS is shifted.

    SSR is the amount of SS our model eats up.

    Squared semi-partial correlations. Unique contributions of IVs to DV.

## PL 15 - V11 - Backward Elimination
    The process and logic for forward selection and backward elimination are mirror opposites of each other.
    If you understand forward selection, understanding backward elimination will be very easy
    Backward elimination does have the trait of showing the individual contribution to reduction in SSE by each feature variable at the start
    It is important to point out that forward, backward, stepwise and best subsets may not generate the same "Best Model"

    Feature variables are examined one at a time.
    The analyst sets a stopping rule (there are several such as p-value), that acts as a hurdle the variable must overcome to avoid being rejected from the model
    The added variable must not reduce error significantly
    The feature variable that reduces model error (SSE) the least is chosen so long as it passes the stopping rule
    Once a variable is out of the model, it stays out. It is never allowed back.
    Then the process repeats until all variables are out of the model OR no variable clears the stopping rule.
### Flaws in Backward Elimination
    The ability of variables to reduce error can change as other variables exit the model.
    As feature variables are removed others can overlap and interact in how they explain variance (reduce error).
    Since a feature variable is permanently removed from the model once it exits, backward elimination is not flexible.
    It is possible for a variable that exited early to overcome the stopping rule later as other variable are removed; but it's out of the model permanently.
    Temptation factor: R² will always decrease (or stay the same)

#### Example: 
    V1, V2, V3 and V4 start in the model. V4 is removed, then V3, then V2. But now V4 passes the stopping rule. However since it's eliminated, it cannot return.
    Squared semipartial correlation can tease out hte relationships.
    It can also miss suppressor and or complimentary relationships:
        Suppressor variables(also called enhancer variables) are strange. They correlate with parts of other variable(s) but not the target. They eat up (suppress) some of the non-relevant error in those variables making the model stronger
        Complimentary variables are negatively correlated with each other but together explain the target variable very well; tradeoff.

    Step 1: Evaluate Full Model
        y ~ X1 + X2 + X3 + X4
            Evaluate
            Find small F values
            Is p > 0.05?
            if yes. Remove and compare.
            NOTE: SSE df p-value
    
    SSE(residual sum of squares) will be at it's minimum
    R² (model fit) will be at it's Maximum

    In the current estimates section:
        Unique ability of each feature variable to reduce SSE is evident.

        Squared semi-partial correlations:

        sr² = F / dfres *(1-r²)

        F comes from the variable

        dfres is the DFE value

        r² is R²

    Step 2: 

        Find the smallest SS and falls outside of our stopping rule.

        Remove beds.
        Smalles SS and fails stopping rule.

        then we stop, because the rest of the variables pass our stopping rules.

        Our SSE went up, but only by 1800, so it had little effect on the model.

        DFE went up by .031
        R² went down by .0032

        hardly any contribution to the model.
        Though we removed a variable, we have a more accurate model.


## PL 15 - V12 - Stepwise Regression

    Our goal is to create the smallest SSE with the least number of variables.

    We decide using a threshold value (p-value, etc.) on the partial F statistic; unique contribution to reduction in SSE

    Good at:
     Good practical decisions
    Stepwise allows us to re-evaluate the model and add or remove variables as our model changes. 
    
    It's transparent. We can see our output at each step.

    Bad at:
     Hypothetical

### Basic stepwise process

    say V1-V5

    Add V2.

    Then add V4. Examine V2 and V4. Should they stay in the model?

    They're okay.

    The next highest R² is V5, so we add V5. Now evaluate, should all variables stay in the model? Say V4 no longer fits the p-value threshold, so we remove it.

    Now we have V1, V2, V5. V3 never has a low enough p-value, and V4 never re-enters the model, but it could if other variables change it's p-value.
    


