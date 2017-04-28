# Does being married have an effect on your political views?
#### Apurva Raman and William Lu

Politics has often been a polarizing subject amongst Americans, and in today's [increasingly partisan](https://www.nytimes.com/2014/06/16/opinion/charles-blow-politics-grow-more-partisan-than-ever.html) political environment, that has not changed. Using data from the [General Social Survey (GSS)](https://gssdataexplorer.norc.org/), an annual study designed and conducted by the [National Opinion Research Center (NORC)](http://www.norc.org/Pages/default.aspx) at the University of Chicago, we identify variables that are correlated with a person's political views. We use a subset of data from the GSS from 1987 to 2016 and find that marital status has a suprising apparent effect on a person's political views, but after further analysis, determine that many confounding variables need to be controlled for to determine the apparent statistical effect that marital status has on political views.



[Gallup](http://www.gallup.com/poll/121571/marriage-remains-key-predictor-party-identification.aspx)






##### This. Is Garbage. <insert HTTYD music here>
At first glance, our multinomial regression shows that marital status is correlated with political views. With low p-values for all categories of political views, except for moderates, this effect is statistically significant and merits further exploration.

To determine whether or not the correlation is spurious, we identified some control variables (i.e. age and sex) that could affect marital status and political views. We then ran some multinomial regressions with these control variables, and calculated their impact on the apparent effect of marital status.

###### Table 1: Change in apparent effect of marital status when controlling for age
|     Political View     | Change in Apparent Effect |
|:----------------------:|:-------------------------:|
| Extremely Liberal      | 0.036360                  |
| Liberal                | -0.083607                 |
| Slightly Liberal       | -0.399400                 |
| Moderate               | -0.428118                 |
| Slightly Conservative  | 0.001829                  |
| Conservative           | -0.230129                 |
| Extremely Conservative | -0.578633                 |

###### Table 2: Change in apparent effect of marital status when controlling for sex
|     Political View     | Change in Apparent Effect |
|:----------------------:|:-------------------------:|
| Extremely Liberal      | -0.006281                 |
| Liberal                | -0.003963                 |
| Slightly Liberal       | -0.016306                 |
| Moderate               | -0.173345                 |
| Slightly Conservative  | 0.017816                  |
| Conservative           | 0.000432                  |
| Extremely Conservative | -0.008266                 |

###### Table 3: Change in apparent effect of marital status when controlling for age and sex
|     Political View     | Change in Apparent Effect |
|:----------------------:|:-------------------------:|
| Extremely Liberal      | 0.029851                  |
| Liberal                | -0.087238                 |
| Slightly Liberal       | -0.409193                 |
| Moderate               | -0.527251                 |
| Slightly Conservative  | 0.019678                  |
| Conservative           | -0.229796                 |
| Extremely Conservative | -0.582116                 |

Looking at the changes in apparent effect when controlling for age and sex separately, we find that age alone explains very little of the apparent effect of marital status for people who are extremely liberal, liberal, or slightly conservative. Sex alone explains very little of the apparent effect of marital status for people who are not moderate. Combined, however, age and sex explain a good proportion of the apparent effect of marital status for people who are slightly liberal, moderate, conservative, and extremely conservative. However, they do not explain all of the apparent effect of marital status.

Looking at the p-values for the regression when we control for age and sex, the effect of marital status is on the border of statistical significance for people who are slightly liberal or moderate. This means that about 59% of the apparent effect of marital status on people's political views being slightly liberal is still explained by marital status. About 47% of the apparent effect of marital status on people's political views being moderate is still explained by marital status.

While this seems promising, marital status is a variable that is confounded by many other factors in people's lives, such as race and level of education. It is entirely possible for the remainder of the apparent effect of marital status on political views to be explained by more control variables.
