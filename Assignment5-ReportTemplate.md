**SENG 637- Dependability and Reliability of Software Systems***

**Lab. Report \#5 – Software Reliability Assessment**

| Group: SENG637- 2   |
|-----------------|
| Jash Dubal                |   
| Steven Duong              |   
| Nikhil Naikar               |   
| Jason Xu                |
| Christopher DiMattia                |

# Introduction
In this assignment the team explored and learned about relability testing by practising with reliability assement tools and assessed hypoetheical intergretation testing data using both reliability growth testing and reliability assuessesment using a reliability demonstration chart (RDC).  The team successfully assessed the reliability of the system with the finding detailed below.

# Assessment Using Reliability Growth Testing 

The team used both the C-SFRAT and SRTAT programs to generate reliability results and found that C-SFRAT was the better choice because it was easier to use.  While both were easy to use C-SFRAT did not have any issues on startup whereas SRTAT required that the csv file be reformatted to a "txt".  It was also noted that SRTAT did not work and had multiple errors when running such as "Can't load AMD 64-bit.dll on a IA 32-bit platform" and other such errors despite selecting the correct platform and even trying different platforms (32 and 64 bit windows).


## Result of model comparison
The top two models using C-SFRAT were Discrete Weibull type III and Geometric, both with coevariance F.  In order to determine which models were the best, all the models with all covariates were run and the two models with the smallest AIC (Akaike information criterion) and BIC (Bayesian information criterion) were selected.  The reason the team used AIC And BIC instead of just SSE (sum of squared estiamte of errors)  is becuase AIC and BIC are specifically designed for model selection and they both account for model complexity whereas SSE does not.  The difference between AIC and BIC is that BIC has a stronger penalty for model complexity so it will genearlly prefer simpler models than AIC.  A deeper explaination of the difference bet AIC And BIC can be found [here](https://vitalflux.com/aic-vs-bic-for-regression-models-formula-examples/).


Results and Statistics
| Model   | MTTF| Failure Rate|
|-----------------|---|---|
| Data                       | 31/92 = 0.337 |    92/31 = 2.968 |
| Discrete Weibull type III  |  a            | a |
| Geometric                  |  a            | a|

## Result of range analysis
In order to select the best range the team used the arithmetical mean test to select which subset of data has an increasing reliability, as reliability models should only be used on data where the overall reliability is increasing as testing continues.  By plotting the time interval and cumulative errors and then calculating the inter-failure time assuming an even distribution amoungst each interval it is very obvious when the reliability growth increases or decreases.  As can be seen in the table below the reliabilty growth increaes from 1-18, after which is decreases and then eventually increases again, so for this assignment the subset of data selected is from 1-18.

| Time Interval | Cumulative Failure Count | Arithmetical mean|
|--|--|--|
|1| 2 |1|
|2|13|0.17|
|3|15|0.21|
|4|19|0.22|
|5|22|0.24|
|6|23|0.27|
|7|24|0.30|
|8|26|0.32|
|9|30|0.31|
|10|30|0.34|
|11|34|0.33|
|12|35|0.35|
|13|38|0.35|
|14|38|0.38|
|15|39|0.39|
|16|40|0.41|
|17|42|0.41|
|18|43|0.43|
|19|51|0.38|
|20|60|0.34|
|21|66|0.32|
|22|73|0.31|
|23|77|0.30|
|24|80|0.30|
|25|80|0.32|
|26|84|0.31|
|27|85|0.32|
|28|85|0.33|
|29|87|0.34|
|30|89|0.34|
|31|92|0.34|




## Plots for failure rate
and reliability of the SUT for the test data provided


## Discussion on Decision Making given a Target Failure Rate
Given a target failure rate, you can use the models to predict 

## Discussion on the Advantages and Disadvantages of Reliability Growth Analysis


# Assessment Using Reliability Demonstration Chart 

# 

# Comparison of Results

# Discussion on Similarity and Differences of the Two Techniques

# How the team work/effort was divided and managed

# 

# Difficulties encountered, challenges overcome, and lessons learned

# Comments/feedback on the lab itself
