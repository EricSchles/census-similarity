The motivation here is to expose basic insights regarding the data within and across multiple datasets.  Below are a set of basic modeling techniques.

`cat dataset.csv example.model | linear_regression`

Where example.model contains:

y ~ x1

Output:

```
Model Description:
                            OLS Regression Results                            
==============================================================================
Dep. Variable:                      y   R-squared:                       1.000
Model:                            OLS   Adj. R-squared:                  1.000
Method:                 Least Squares   F-statistic:                 3.398e+05
Date:                Wed, 28 Sep 2016   Prob (F-statistic):          7.63e-177
Time:                        07:32:49   Log-Likelihood:                -142.64
No. Observations:                 100   AIC:                             287.3
Df Residuals:                      99   BIC:                             289.9
Df Model:                           1                                         
Covariance Type:            nonrobust                                         
==============================================================================
                 coef    std err          t      P>|t|      [95.0% Conf. Int.]
------------------------------------------------------------------------------
x1             1.0302      0.002    582.959      0.000         1.027     1.034
==============================================================================
Omnibus:                       33.630   Durbin-Watson:                   0.001
Prob(Omnibus):                  0.000   Jarque-Bera (JB):                6.002
Skew:                           0.000   Prob(JB):                       0.0497
Kurtosis:                       1.800   Cond. No.                         1.00
==============================================================================

Warnings:
[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.

Analysis:

If p-value less than .05 and R-squared > .75:

We reject the null hypothesis that x1 is not significant and we see that with an R-squared of 1.000, there is clear correlation between y and x1.

If p-value less than .05 and R-squared > .4 and R-squared < .75:

We reject the null hypothesis that x1 is not significant and we see that with an R-squared of .6, there is some correlation between x1 and y.  Perhaps consider rescaling x1 and/or y by the log to deal with noisy affects.  Please note - this means the rate of change will be correlated, not the variable.  

If p-value less than .05:

We reject the null hypothesis that x1 is not significant although it appears that there is a somewhat weak correlation between y and x1.

If p-value greater than .05:

We fail to reject the null hypothesis that x1 is significant, therefore we cannot say anything meaningful about the statistical relationship between y and x1.


