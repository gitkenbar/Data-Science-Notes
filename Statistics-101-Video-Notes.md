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

