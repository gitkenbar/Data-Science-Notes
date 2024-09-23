# Job Titles
Data analyst
80-90% of what a data scientist does

# Projects?
case studies


# Languages

Python - Statistical analysis and Data Engineering
SQL - Structured Query Language

# Data Science
- Data Lakes - Data Seas
- Data science is going to be an in demand job in an information saturated future. Only in demand for "larger organizations" or in large data-sets.
- Data Scientists need to have good communication and story telling skills to elaborate on what the data says.
- Data Quality > Data Quantity

# Data Monetization

# Visualization

## Developer <--


# Crash course Tl;dr
-null/alternative hypothesis- The question you go into the data-set trying to find. It frames the way to think. It proves nothing changes 
- counter-factual - attempt to prove your hypothesis wrong 

-cleaning data - anonymizing data (important for HIPA)
-


Data Science - Statistics
statistical modeling - advanced statistical modeling
linear models can accomplish a lot

y = mx + b

standard deviation
mean median mode
visualization
accessability
data preperation / cleaning / standardizing
descriptive statistics
exploratory analysis - looking for 'nuggets' of information within data like correlation between different datasets



Pre-work: 
Flipped class - Give homework then discuss it in class


Scatter Plot
Scatters all data point onto a graph
Shows data spread, compares 2 different variables on the X and Y axis
Finds correlation in dense and sparse areas

 EX:
 Income vs Years of education
 Travel Time vs Distance Travelled
 Sales volume vs Price for goods

#Line Plot
Similar to scatter plots, but points are connected
can make it easy to see trends
useful to see how data evolves over time or location
great if consecutive data points are related (continuous)

    EX:
    Distance vs. Time
    Profit vs # of employees
    Creativity vs stress

# 2-D Histogram
Allows you to see distribution of two variables relative to each other
allows you to see where both variables clumb, and how one falls of relative to the other at specific points
Hard to see in scatter graphs because equal points will just sit on top of each other

    EX:
    Ticket price vs tickets sold

# Box and Whisker Plot
Allows you to see spread of data
shows spread of data with quartiles and median
filters out statistical information and shows it visually
can be compared across different groups like bar plots

    EX:
    Ticket prices for footbal games for different teams

# Heat Map
    Lets you plot two variables and also show amount/height/intensity

    EX:
    Movement of a customer through a store

    Intensity of a flashlight over an area??

    geographic data distrubution

# Multi Variate Bar Plot
    like single bar plot but plotting several variables for one group

    EX:

    Goals score, shot taken, shots on target for several soccer teams

# Lower Dimenstional Graph
    Add an extra varialbe to plots like line and scatter plots
    same benefits as 2 dimensional plots but add an extra variable, allowing you to see extra relations

    Visualisation makes depth harder to see since every snapshot is just 2 dimensional

# 3-d Line graph
    Position of skier every second in space

## Programming

# Ease of Automation
    being able to program allows you to prototype what you have in mind
    it allows you to easily repeat and automate tasks (you're not stuck copy and pasting data here and there into equations)

# Ability to Customize
    it allows you to easily expand and progress your analysis

    You can dive in deeper once you discover more

    you can change the visualizations, statistical parameters you're looking at, and variables you're analyzing

    Make the data YOURS

## Python Libraries

# Pandas
    It's like excel but built for programming

    it easily allows you to manage, organize, and do statistical calculations on your data

# Matplotlib
    Allows all type of graphs to be used
    Visualization of your data
    Lots of customization abilities




## Intro to Statistics

# Ch. 3  -- Probability

    Probability - A mathematical statement about the likelihood that it will occur. All probabilities are numbers between 0 and 1. 0 means it will never occur, 1 means it will always occur

    The sum of the probabilities of all possible outcomes of any event is 1. This is because *something* will always happen

    Complimentary event - the event that doesn't occur

    Event E is what occurs and complimentery event E1 is what does not occur.

    if E = rain tomorrow and E1 = no rain then

    P(E) + P(E1) = 1

    Mutually Exclusive - two or more events that cannot occur simultaneously

    two events A and B are mutually exclusive if A U B = 0, that is there are no members in common

    # Factorial
        The product of all positive integers from 1 to n

        n! (n factorial) = n * (n-1) * (n-2) * etc

        0! is defined as 1

    # Combination
        A combination is a set of unordered items if we choose k distinct objects from a total of n objects then there are (n over k) different combinations, where

            (n over k) = n! / k!(n-k)!

    # Binomial Formula
        Suppose that an event occurs with probability p. Then the probability that it will occur exactly x times out of a total of n trials is

        (n over x) * p^x(1-p)^n-x = N!/x!(n-x)!* p^x(1-p)^n-x

    # Example

        Derive a formula for calculating P(x) (the probability of x successes out of n trials, where the probability of each success is p) in terms of x, n, p, and P(x-1).

        The probability of x - 1 successes is, using the binomial formula,

            P(x-1) = ( n over x-1) * p ^ x - 1(1-p) ^ n-(x-1)

                   = N! / (x-1)!(n-x + 1)! * p ^ x - 1 (1 - p) ^ n - x + 1
        
        The probability of x successes is, again using the binomial formula,

            P(x) = (n over x) * p ^ x (1 - p) ^ n - x
                 = n! / x!(n - x)! * p ^ x (1 - p) ^ n - x

        We want to find an expression K such that P(x - 1) * K = P (x). thus 

## Random Variables

# Random Variable
    A variable that may take on different values depending on the outcome of some event

    # Example
    On the AP Statistics exam, 1/5 of the class received a 5, 1/3 received a 4, 1/6 received a 3, 1/20 received a 2, and 1/3 received an 1. If x represents the score of a randomly chosen student in the class then x is a random variable that takes the values 1, 2, 3, 4, and 5.

    A random variable may be discrete ( it takes on a finite number of values) or continuous (it can take on any value in a certain interval, that is, an infinite number of values).

# Probability distribution
    A list or formula that gives the probability for each discrete value of a random variable.

# Expected Value
    definition: Also called the mean, of a random variable is the sum of the product of each possible value and it's corresponding probability. In mathematical terms, if the random variable is X, the possible values are x1, x2, ... xn, and the corresponding probabilities are P(x1), P(x2), ..., P(Xn) then

        E(X) =  Σ

    Example
        Investing in Sharma Furniture Co. has a 60% chance of resulting in a $10,000 gain and a 40% chance of resulting in a $3,000 loss. What is the expected value of investing in Sharma Furniture Co.?

        E(X) = .6 * 10000 + .4 - 3000 = 6000 - 1200 = 4800

        Thus the expected value is $4,800.

    # Variance and Standard Deviation
        Variance of a discrete random variable.
            the variance σ^2 of a random variable, which takes on discrete values x and has mean µ, is given by the equation...

        Standard deviation of a discrete random variable
            The standard deviation σ of a discrete random variable is equal to the square root of the variance, i.e. σ = √ σ^2

    # Shortcuts for Binomial Random Variables

    The past examples required a fair amount of arithmetic. To save time, there are simpler ways to find expected values, variances, and standard deviations of binomial random variables ( that is, random variables with only two outcomes)

        # Mean and Standard Deviation of a Binomial
        In a situation with two outcomes where the probability of an outcome O is p and there are n trials, the expected number of Os is np.
        That is,

            µ = np

        Furthermore, the variance σ^2 is given by the equation

            σ^2 = np(1-p)

        and the standard deviation σ by the equation

            σ = √ np(1 - p)