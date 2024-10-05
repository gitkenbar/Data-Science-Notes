##Statistics 101
## Playlist 14 Videos 1-4

## PL14 - 1 - Simple Linear Regression
 You are smart and talented. The video guy has faith in you, and so do the people around you

    Regression allows us to model mathematically the relationship between two variables.
    For now we will be working with two variables an Independant and a Dependant variable.
    We judge our models against another specific model.

# Tips for service
    As a waiter you would like to develop a model that will allow you to make a prediction about what amount of tip to expect for any given bill amount. Therefore one evening, you collect data for six meals

    But you forgot to collect meal totals, only the tips.

    Meal | Tip
    1   | $5
    2   | $17
    3   | $11
    4   | $8
    5   | $14
    6   | $6

    We only have one variable, the tip amount, the meal# is merely a discriptor.
    Without more information we can only find the mean, and the only prediction we can make is an estimate based on that. In this case, $10 is the "best-fit" estimate.
    Standard deviation is the distance between each data point and the mean.

    The distance between the mean and the data points is called "Residuals" or "error" because that's how far the data point is from the best fit line. The residuals ALWAYS add up to zero.

    In standard deviation we take the values of the residuals and square them. We're going to the same thing here

    Meal|  Residual | Residual^2
    1   |   -5      |   25
    2   |   +7      |   49
    3   |   +1      |   1
    4   |   -2      |   4
    5   |   +4      |   16
    6   |   -5      |   25

    The Squaring exaggerates the points that deviate from the mean and makes all values positive.

    We can then add up all the squared residuals, this is called the Sum of squared Errors(SSE). In this case 120. This is a super common term in statistics.

    The goal of simple linear regression is to create a linear model that minimizes the sum of squares of the residuals / error (SSE).

    We're going to make a second line through the data that will attempt to minimize the size of the squares. Which will be the "Best Fit" line. This line will "fit" the data better by reducing residuals/errors

    If our regression model is significant, it will "eat up" much of the raw SSE we had when we assumed (like this problem) that the independent variable did not even exist. The regression line will/should literally "fit" the data better. It will minimize the residuals.

    When we do SSE there will be SSE Regression and SSE Error.

    If we say a linear regression model is good it reduces the SSE by a significant amount compared to a mean best fit.


    Simple linear regression is reall a comparison of two models
        one is where the independent variable does not even exist
        and the other uses the best fit regression line
    If there is only one variable, the best prediction for other values is the mean of the "dependent" variable
    The difference betweeen the best-fit line and the observed value is called the residual (or error)
    The residuals are squared and then added together to generate sum of squares (literally) residuals / error, SSE.
    Simple linear regression is designed to find the best fitting line through the data that minimizes the SSE

### PL 14 - 2: Linear Regression, Algebra, Equations, and Patterns
    Bivariate statistics : Two variable statistics

    Correlation + Anova = Linear Regression
    ANOVA = Analysis of Variance
    Both Correlation and Regression can be plotted on a graph

    The value of one variable, is a function of the other variable.

    Ex:
    The value of y, is a function of x: y = f(x)

    The value of the dependent variable is a function of the independent variable.

    slope-intercept form of the line
    y = mx + b
    x = random variable
    m = slope of the line rise/run
    b = y-intercept (crosses y-axis)

    y-intercept is where x = 0

    Coordinate of (0, y)

    y = ß₀ + ß₁ + ε

    ß₀ (beta sub-zero) = y-intercept population perameter

    ß₁ = slope population parameter

    ε = error term, unexplained variation in y

    E(y) = ß₀ + ß₁x is the same as y = mx + b

    E(y) is the mean or expected value of y, for a given value of x

    The expected value is the mean of a small distribution for that y.

    In regression we want to have a narrow range of expected values.

    If we know the population parameters, ß₀ and ß₁, we could use the Simple Linear Regression Equation.

    E(y) = ß₀ + ß₁x

    In reality we almost never have the population parameters. Therefore we will estimate them using sample data. When using sample data, we have to change our equation a little bit.

    ŷ = ß₀ + ß₁x

    ŷ, pronounced "y-hat" is the point estimator of E(y)
    ŷ, is the mean value of y for a given value of x.

    EX:
    When conducting simple linear regression with TWO variables, we will determine how good the regression line "fits" the data by comparing it to THIS TYPE; where we pretend the second variable does not even exist; the slope, ß₁ = 0.

    In this situation, the value of ŷ is 10 for every value of x
    
    ŷ = ß₀ + ß₁x

    ŷ = ß₀ + (0)x

    ŷ = ß₀

    ß₀ = 10

    ŷ = 10


### PL14 - 2: Linear Regression, The Least Squares Method

    min Σ (yᵢ - ŷᵢ)²

    yᵢ = observed value of dependent variable (tip amount)

    ŷᵢ = estimated(predicted) value of the dependent variable (predicted tip amount)

    Plain English. The goal is to minimize the sum of the squared differences between the observed value for the dependent variable (yᵢ) and the estimated/predicted value of the dependent variable(ŷᵢ) that is provided by the regression line. Sum of the squared residuals.

    Not only that, but the sum of the squared residuals should be much smaller than when we just used the dependent variable alone; ß₁ = 0, ŷ = 10 for all values of x. That sum of squared residuals was 120.

    Step 1: Scatter Plot

    Step 2: Look for a line

    Step 3: Correlation (Optional)

    what is the correlation coefficent, r?

    in this case, r = 0.866.
    
    Is the relationship strong?

    A value close to 1 or -1 is a strong correlation, so yes.

    Step 4: Centroid
    Centroid = The average of the independent variable(x) and the dependent variable(y) on the graph

    The best fit-regression line will/must pass through the centroid.

    Step 5: Calculations

    

    ß₁ = Σ(xᵢ - x̄)(yᵢ - ȳ) / Σ(xᵢ - x̄)²

    ß₁ = slope
    Σ = sum
    xᵢ = value of the independent variable
    x̄ = mean of the independent variable
    yᵢ = value of dependent variable
    ȳ = mean of the dependent variable

    slope is the sum of the observed value of the independent variable minus the mean of the independent variable, times the product of the obeserved value of the dependent variable and the mean of the dependent variable divided by the sum of the observed value of the independent variable minus the mean of the independent variable, squared.

    We need ß₁ to calculate the y-intercept

    b₀ = ȳ - b₁x̄

    1. For each data point.
    2. Take the x-value and subtract the mean of x.
    3. Take the y-value and subtract the mean of y
    4. Multiply Step 2 and Step 3
    5. Add up all the products
    -----
    1. For each data point
    2. Take the x-value and subtract the mean of x
    3. Square step 2
    4. Add up all the products
   
   Regression line

   ȳᵢ = b₀ + b₁xᵢ

   b₀ = -0.8188 (intercept)
   b₁ = 0.1462 (slope)

    ȳᵢ = -0.8188 + 0.1462x
        or
    ȳᵢ = 0.1462x - 0.8188

    What does this mean? For every $1 the bill amount (x) increases, we would expect the tip amount to increase by $0.1462 or about 15 cents.

    If the bill amount(x) is zero, then the expected/predicted tip amount is $-0.8188 or negative 82-cents! Does this make sense? NO. The intercept doesn't have to make sense in the "real world"

    But...

    Is this model any good?? (next video)