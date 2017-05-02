# Does being married have an effect on your political views?
#### Apurva Raman and William Lu

Politics has often been a polarizing subject amongst Americans, and in today's [increasingly partisan](https://www.nytimes.com/2014/06/16/opinion/charles-blow-politics-grow-more-partisan-than-ever.html) political environment, that has not changed. Using data from the [General Social Survey (GSS)](https://gssdataexplorer.norc.org/), an annual study designed and conducted by the [National Opinion Research Center (NORC)](http://www.norc.org/Pages/default.aspx) at the University of Chicago, we identify variables that are correlated with a person's political views. We find that while marital status has a statistically significant apparent effect on political views, that apparent effect is drastically reduced when including confounding variables, particularly religion.

### Defining the Problem

We're not the only ones looking at this: [Gallup](http://www.gallup.com/poll/121571/marriage-remains-key-predictor-party-identification.aspx) investigated this in 2009 and found that "married Americans tilt Republican; unmarried Americans, Democratic." To further investigate the apparent effect and check whether that holds over a longer period of time, we use a subset of GSS data from 1987 to 2016 and find that while marital status appears related to a person's political views, further analysis shows that many confounding variables need to be controlled for.

Other than time span and dataset, our analysis differs from Gallup's in the way that we look at political views. Gallup only has three options: Republican, Democrat, and Independent. The GSS allows us to have a more granular view of people's political views: a Likert scale from 1-7, with 1 being extremely liberal and 7 being extremely conservative. This does not tie respondents down to a specific political party, and we think it more accurately represents people's real political views.

### Married Americans Tilt Conservative; Unmarried Americans Tilt Liberal

![marriage_punchline](https://github.com/williamalu/data_science_politics/blob/master/Plots/marriage_punchline.png)

Breaking down the GSS data and sorting people by marital status allows us to see what proportion of respondents, given their marital status, fall into each political viewpoint. While many respondents considered themselves political moderates, a trend is still visible. Married and widowed respondents skewed more conservative while respondents who have never been married or are separated skewed more liberal. Divorced respondents were somewhere in between. However, many other factors, such as age, sex, and religion may be influencing the trend that we see.

### Marital Status Correlation Significantly Impacted by Religion

To analyze the apparent effect of marital status on a respondent's political views, we treat the Likert scale as a linearly increasing scale and utilize linear regressions to find correlations between marital status and political views while controlling for confounding variables. This means that we make the assumption that responses on the political views scale are equally spaced, which is not necessarily true. However, modelling the Likert scale as linear does not significantly impact our analysis because we are interested in the relationship between marital status and political views and not necessarily trying to predict a person's political views given their marital status.

In addition, we do not try to analyze absolute apparent effect size using the coefficient that a linear regression returns. Our linearization of the Likert scale is not accurate and interpreting a discrete variable as a continuous one is not useful.

We begin by finding that marital status has a statistically signficant correlation with political views (p-value < 0.001). Then, we add in some standard control variables: age, sex, race, education (highest degree obtained), class (calculated social economic index), and household income. This reduces the apparent effect of marital status on political views by 33.9%. However, when you add religion to the mix, the apparent effect of marital status on political views is further reduced by another 38.3%, which means only 27.8% of the original apparent effect of marital status remains.

### Marital Status Correlation Not Impacted by Income

Surprisingly, income has a very small effect on political views when used as a control for marital status. The effect size relative to marital status is many orders of magnitude smaller, while still remaining statistically significant (p-value < 0.001).

![income_cdf](https://github.com/williamalu/data_science_politics/blob/master/Plots/cdf_income.png)

Graphing the CDF of income shows us that it is a long-tailed distribution, as expected, and this is also reflected in our graph of income broken down by political views.

![income_hexbin](https://github.com/williamalu/data_science_politics/blob/master/Plots/income_hexbin.png)

There is a long tail on the right of the income spectrum, which mirrors what we saw in the CDF. The data, as shown here, is jittered to better show density of incomes and political views. We see that most people have household incomes around the $25,000-50,000 range and that, consistent with our findings earlier, the vast majority of respondents consider themselves moderates. This is why income has such a small effect size relative to marital status: across the political spectrum, most people make an "average" amount of income.

### Does being married have an effect on your political views?

Yes, but after controlling for confounding variables, the apparent effect of marital status significantly decreases. Of the control variables we used, religion decreased the apparent effect of marital status the most while income decreased it the least.
