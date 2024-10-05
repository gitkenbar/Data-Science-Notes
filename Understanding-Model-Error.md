SSE - Sum of Squares Error
    Sum of squared Residuals (errors, or R²), a measure of the variability of the observations about the regression line

    SSE = sum of (observed value minus the predicted value) squared

MSE - Mean Square of Errors
    MSE s² is an estimate of sigma² the variance of the error, epsilon.
    In other words, how spread out the data points are from the regression line. MSE is SSE divided by its degrees of freedom which is 2 because we are estimating the slope and intercept.

    s² = MSE = SSE / n - 2

    Why devide by n-2 and not just N? REMEMBER, we are using sample data. It's also why we use s² and not sigma².
    This is why MSE is not simply the average of the residuals.
    If we were using population data, we would just divide by N and it would simply be the average of the residuals.

SST - Sum of Squares Total
S - Root Mean Square Error or Standard Error

    The standard error of the estimate sigma (or just "standard errror") is the standard deviation of the error term, epsilon. Now we are Un-squared!
    It is the average distance an observation falls from the regression line


    Since the MSE is s², the standard error is just the square root of MSE

    You think of s as a measure of how well the regression model makes predictions. Can be used to make prediction intervals.

R² = sum of squares regression(model) / total sum of squares

or 

R² = SSR / SST

How well does the estimated regression equation fit our data?

This is where regression begins to look a lot like ANOVA; the total sum of squares is partitioned or allocated to SSE and SSR.