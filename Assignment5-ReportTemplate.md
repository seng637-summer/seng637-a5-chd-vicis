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

The team used both the C-SFRAT and SRTAT programs to generate reliability results and found that C-SFRAT was the better choice.  While both were easy to use C-SFRAT did not have any issues on startup whereas SRTAT required that the csv file be reformatted to a "txt" and it also provided far fewer choices for model selection and so C-SFRAT was used.


## Result of model comparison
The top two models using C-SFRAT were Discrete Weibull type III and Geometric, both with coevariance F.  In order to determine which models were the best, all the models with all covariates were run and the two models with the smallest AIC (Akaike information criterion) and BIC (Bayesian information criterion) were selected.  The reason the team used AIC And BIC instead of just SSE (sum of squared estiamte of errors)  is becuase AIC and BIC are specifically designed for model selection and they both account for model complexity whereas SSE does not.  The difference between AIC and BIC is that BIC has a stronger penalty for model complexity so it will genearlly prefer simpler models than AIC.  A deeper explaination of the difference bet AIC And BIC can be found [here](https://vitalflux.com/aic-vs-bic-for-regression-models-formula-examples/).


Results and Statistics
| Model   | MTTF| Failure Rate|
|-----------------|---|---|
| Data                |   31/92 = 0.337 |    a |
| Discrete Weibull type III              |  a | a |
| Geometric               |  a | a|

## Result of range analysis
XYZ

## Plots for failure rate
and reliability of the SUT for the test data provided


## Discussion on Decision Making given a Target Failure  Rate


## Discussion on the Advantages and Disadvantages of Reliability Growth Analysis


# Assessment Using Reliability Demonstration Chart 

# 

# Comparison of Results

# Discussion on Similarity and Differences of the Two Techniques

# How the team work/effort was divided and managed

# 

# Difficulties encountered, challenges overcome, and lessons learned

# Comments/feedback on the lab itself
