# Model Building Regression Models
    "All models are wrong,
    But some are useful."
        -George Box

    We're trying to mimic a real phenomenon in the real world, there are a ton of variables and they can't all be accounted for.

    We're trying to build predictions that are useful, but we must stay humble, as they cannot be perfect.

    A theme park analyst (you) will use historical data to develop regression models for a "Guess Your Weight" game designed for children and adolescents. The full model is:

        Weight = Sex + Age + Height
        y = b₀ + b₁xᵢ + b₂x₂ + b₃x₃

    The park has access to historical data on these measures for 236 children and adolescents; SEX, AGE, HEIGHT, WEIGHT

## 7 Possible Models
    1. Sex
    2. Age
    3. Height
    4. Sex, Age
    5. Sex, Height
    6. Age, Height
    7. Sex, Age, Height
   
    Model 7 is called the full model. Models 1-6 are called reduced models; sometimes called nested models.

    Which model makes the BEST predictions while also being the simplest?
    What do we mean by BEST? How do we measure which is BEST?

    P-value??

## 4 Common Techniques
    1. Forward regression (addition)
    2. Backward Regression (deletion)
    3. Stepwise Regression (addtion / deletion)
    4. Best subsets regression (all possible combinations)
   
   Note: These techniques are not without controversy. But they are a great tool for learning how basic models are created and evaluated.

## What you need to Know!
    This is not basic descriptive statistics, it's complex!
    Solid understanding of Linear Regression, Including:
        R²
        Interpretation of coefficients
        ANOVA F-Table
        SST(Total sum of Squares) = SSR (sum of squares due to regression) + SSE (sum of squares due to error)
        (in model building we are trying to reduce SSE)
        F- Statistics
        P- Values
        Correlations
        Partial Correlation
        Partial F
    Some familiarity with stats software (Excel, R, JMP, XLSTAT, etc)

    When adding variables to a model the R² will never decrease.
    At >1 variable, variables potentially start influencing each other.
    Different techniques may result in different models (They're not aiming towards one grand model, they have different methods and destinations)
    In forward regression, once a variable is in, it stays in.
    In backward regression, once a variable is out, it stays out.
    For forward, backward, and stepwise, the analyst chooses the criteria for entry and exit (usually a p-value / F / Partial F)
    R² alone is usually not sufficient to determine the best model
    Aim for a model that is simple yet fits best
    Including more variables risks overfitting the model (the more we use, the more the model moulds itself around our training data)

    
##Foreward
Step 1
    |                                                               |
    R² is 0 - 1

    x₁ -> y Lowest (R²) change

    x₂ -> y Highest (R²) change

    x₃ -> y Middle (R²) change
    
    Keep if Significant, If not then stop

    y = b₀ + b₂x₂

Step 2

    
    x₂ -> y kept from step 1

    x₁ -> y Lowest (R²) change

    x₃ -> y Highest (R²) change

    R² will never decrease below point A as variables are added.
    But the proportion of R² by each variable can change.

    Keep x₃ if significatn change, if not stop.

    y = b₀ + b₁xᵢ + b₂x₂ + b₃x₃

    x₂ -> y Kept from step 1

    x₂ -> y Kept from step 2

    x₁ -> y Added variance (R²)

    If the change is not significant, do not keep it.

##Backward
    Add all variables to the model, then remove each of them to test the change to R², if it's not a significant change to R² then we keep it out in our final model.



##Stepwise

    Stepwise regression is like a forward regression / backward combo but with three modifications:
        1. At each step, all variables are evaluated for their unique contribution to the model
        2. Once a variable is entered into the model, it might not stay in the model going forward.
        3. Variables removed at one step could reenter at a later step
     This means that how variables are related to each other, and the order they are entered, can change the makeup of the variables included in the model
     
     Rules are set for a variables to enter the model and to be removed from the model using p-values / partial F statistics

     Add x₂ first

     then add x₃ and it is much more significant than x₂


## Best Subsets

    Best subsets regression
    y = b₀ + b₁xᵢ + b₂x₂ + b₃x₃
    1. Sex              y = b₀ + b₁x₁
    2. Age              y = b₀ + b₂x₂ 
    3. Height           y = b₀ + b₃x₃   
    4. Sex, Age         y = b₀ + b₁x₁ + b₂x₂  
    5. Sex, Height      y = b₀ + b₁x₁ + b₃x₃
    6. Age, Height      y = b₀ + b₂x₂ + b₃x₃
    7. Sex, Age, Height y = b₀ + b₁xᵢ + b₂x₂ + b₃x₃
   
   We create regression models for EVERY possible combination of variable.
   In best subsets, you will never miss the best model.
   But as you add variables, the number of models grows exponentially.
   This is in essence, the brute force method.
   It may be useful when you limit variables to ~5.

