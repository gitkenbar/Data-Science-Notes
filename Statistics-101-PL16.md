# Logistic Regression
## PL-16: Logistic Regression, an Introduction
    As a first-time home buyer you are busy organizing your financial records so you can apply for a home mortgage. As part of this process you order a copy of your credit report to check for errors and gauge your credit score which can range from 300 to 850. Lenders will factor in your credit score when deciding to approve or not approve you for a mortgage. Turns out your score is 720.

    While doing your research you find some raw data online showing 1000 applicant credit scores and whether or not the application was approved (yes/no).

    Using the data you found, you would like to do the following:

        1. Develop a model that will provide the probability and the odds of being approved for any given credit score.
        2. Discover approximately what credit score is associated with a probability of 50% (the odds are even) for being approved.
        3. Input your score of 720 into the model to determine the probability and odds of you being approved for a mortgage.
        4. Determine how improving your credit score from 720 to 750 would effect your probability and odds for being approved for the mortgage.

    Logistic regression seeks to:
        model the probability of an event occuring depending on the values of the independent variables, which can be categorical or numerical
        Estimate the probability that an event occurs for a randomly selected observation versus the probability that the event does not occur
        Predict the effect of a series of variables on a binary repsonse variable
        classify observations by estimating the probability that na observation is in a particular category (such as approved or not approved in our problem)   

    Why other regression procedures will not work:
        Simple linear regression is one quantitative variable predicting another
        Multiple regression is simple linear regression with more independent variables
        Nonlinear regression is still two quantitative variables, but the data is curvilinear.
    
    Running a typical linear regression in the same way has major problems:
        Binary data does not have a normal distribution, which is a condition required for most other types of regression
        Predicted values of the DV can be beyond 0 and 1 which violates the definition of probability
        Probabilities are often not linear such as "U" shapes where probability is very low or very high at the extremes as x-values

## PL-26: Logistic Regression Probability, Odds, and Odds Ratio
                  outcomes of interest 
    Probability =  -----------------
                  all possible outcomes


    odds = P(occuring) / P(not occuring)

    odds = p / 1 - p

    Fair coin flip

    odds (heads) = 0.5/0.5 = 1 or 1:1

    fair die roll

    odds (1 or 2) = 0.333 / 0.66 = 1 / 2 or 1:2

    Deck of playing cards

    odds (diamond card) = 0.25 / 0.75 = 1/3 = .333 or 1:3

    the Odds ratio is exactly what it says it is, a ratio of two odds

    Loaded coin flip

    P(heads) = 7/10 = .7

    odds (heads) = .7/.3 = 2.333

    Odds ratio in logistic regression

    The odds ratio for a variable in logistic regression represents how the odds change with a 1 unit increase in that variable holding all other variables constant

    For (fictitious) example:
        Body weight and sleep apnea(two categories: apnea/no apnea)
        Weight variable had an odds ratio of 1.07
        this means a one pound increase in weight increases the odds of having sleep apnea by 1.07 (not high b/c we are looking at a small increment (1lb))
        a ten pound increase in weight increases the odds to 1.98, or almost doubles a person's odds of having sleep apnea and a 20 pound increase raises the odds to 3.87 or almost 4x greater (we will learn how to calculate that later)
        This ratio holds true at any weight

        It is very important to separate probability and odds

        In the previous example a person gaining 20 pounds increases their odds of sleep apnea by almost a factor of 4 regardless of their starting weight

        However the probability of having apnea is lower in people with lower body weight to begin with

        so while the odds are 4x greater, the probability may still be low

        basically what this means is that the odds can have a large magnitude even if the underlying probabilities are low.

    
## PL-16: Logistic Regression, Logit and Regression Equation
    Bringing back Bernoulli
        The dependent variable in logistic regression follows the Bernoulli distribution of probablity having an unknown probability, p
        Remember that the Bernoulli distribution is just a special case of the Binomial distribution where n = 1 (just one trial)
        Success is "1" and failure is "0"
        So the probability of success is p and failure is q = 1 - p
        In logistic regression we are estimating and unknown p for any given linear combination of the independent variables
        Therefore we need to link together our independent variables to essentially the Bernoulli distribution; that link is the logit (low-jit)

        In logistic regresioon we do not know p like we do in Binomial (Bernoulli) distribution problems. The goal of logistic regression is to estimate p for a linear combination of the independent variables. Estimate of p is p-hat (ȳ)

        To tie together our linear combination of variables and in essence the Bernoulli distribution we need a function that links them together, or maps the linear combination of variables that could result in any value onto the Bernoulli probability distribution with a doman from 0 to 1. The natural log of the odds ration, the logit, is that link function.

        ln(odds) ( p  / 1-) is the logit(p) OR ln(p)-ln(1-p) = logit(p)

        Reminder: logₑx=ln x

    What is the Inverse Logit?
        In our logit link function graph, 0 to 1 ran along the x-axis but we want the probabilities to be on the y-axis. We can achieve that by taking the inverse of the logit function

            logit(p) = ln( p / 1 - p)
            where p is between 0 and 1
            