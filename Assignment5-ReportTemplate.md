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
In this assignment the team explored and learned about dependability and relability testing software systems.  The team gained hands-on experience by utilizing reliability assessment tools and evaluating hypothetical interpretation testing data. This evaluation encompassed both reliability growth testing and reliability assessment, employing a reliability demonstration chart (RDC). The team achieved a successful assessment of the system's reliability, and the resulting findings are elaborated below.


# Assessment Using Reliability Growth Testing 

The team utilized both the C-SFRAT and SRTAT programs to generate reliability outcomes. They determined that C-SFRAT stood out as the preferable choice due to its user-friendly nature. While both programs were user-friendly, C-SFRAT distinguished itself by not encountering any startup issues. In contrast, SRTAT necessitated reformatting the CSV file into a text file before it could be initiated.  It was also noticed by several members that SRTAT encountered errors during execution. These included errors such as "Can't load AMD 64-bit.dll on an IA 32-bit platform" and other similar errors. These errors persisted despite selecting the correct platform and even attempting various platforms (32 and 64-bit Windows).


## Result of model comparison
Of the models assessed using C-SFRAT, the top two were the Discrete Weibull type III and Geometric model, both using the covariance F. To determine the optimal models, all models with all covariates were executed, and the two models with the lowest AIC (Akaike information criterion) and BIC (Bayesian information criterion) values were chosen.  The rationale for utilizing AIC and BIC, instead of solely relying on SSE (sum of squared estimate of errors) or PSSE (predictive sum of squares error), stems from their suitability for model selection. Both AIC and BIC are explicitly tailored for this purpose, taking into account the complexity of the model, a feature SSE and PSSE lacks (AIC and BIC penalize for model complexity, so there is less chance of overfitting).  The distinction between AIC and BIC is in their treatment of model complexity. BIC applies a more stringent penalty for model complexity, leading it to favor simpler models over AIC. For a more thorough understanding of the contrast between AIC and BIC, refer to this [link](https://vitalflux.com/aic-vs-bic-for-regression-models-formula-examples/).

The AIC for the Discrete Weibull type III and Geometric models were 122.199 and 125.323 respectively while the BIC was 127.935 and 129.625 for the Discrete Weibull type III and thet Geometric models respectively.

Results and Statistics
| Model   | MTTF| Failure Rate|
|-----------------|---|---|
| Data                       | 31/92 = 0.337 |    92/31 = 2.968 |
| Discrete Weibull type III (all data)  | 31/92 = 0.337 |    92/31 = 2.968 |
| Geometric (all data)                  |  31/92 = 0.337 |    92/31 = 2.968 |
| Discrete Weibull type III (subset, effort per interval = 36)  |  31/92.922 = 0.334            | 92.922/31 = 2.997 |
| Discrete Weibull type III (subset, effort per interval = 0)  |  31/50.074 = 0.619            | 92.922/31 = 1.615 |
| Geometric (subset, effort per interval = 0)                  |  31/47.151 =  0.657           | 47.151/31 = 1.521|

## Result of range analysis
To determine the optimal range, the team employed the arithmetic mean test. This test helped identify a subset of data with consistently improving reliability. As mentioned in the lecture notes, it's important to apply reliability models exclusively to data showing a consistent increase in reliability during testing.  The approach involved creating a graph displaying time intervals and cumulative errors. By calculating inter-failure times with the assumption of an even distribution across each interval, it became clear when reliability growth was on the rise or decline.  The data table below demonstrates this pattern. Reliability growth is evident from intervals 1 to 18, followed by a decline from intervals 19 to 24, and a subsequent increase from intervals 25 to 31. Therefore, for this task, the chosen data subset comprises intervals 1 to 18 and 25 to 31. Unfortunately, the C-SFRAT software lacks the flexibility to analyze subsets that don't initiate from time interval 0 due to several errors encountered, an example of which can be found [here](https://github.com/seng637-summer/seng637-a5-chd-vicis/blob/main/media/error.png), so the intervals from 25 to 31 were not analyzed.

The team also manipulated the "effort per interval" to try and match the models using the subset of data (intervals 1-18) with the full set.  This was only achieved with the Discrete Weibull type III and with an effort per interval of 36.  The Geometric model never obtained similar results to the actual full set.  As mentioned in the software tool guide found [here](https://www.sciencedirect.com/science/article/pii/S2352711021001588), this hyperparameter can be interpreted as "the testing schedule, but can also be used to predict field defect or vulnerability discovery in the case where covariates correspond to the intensity of various types of attack leveled against a system in its operational environment".  Without more information on the hypothetical test data and why there was a sudden spike in unreliability, it's not meaningful to interpret why the effort per interval would be 36 and if that model can be used for future predictions.

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

MVF Graph - Full Set

<img src="https://github.com/seng637-summer/seng637-a5-chd-vicis/blob/main/media/fullset.png" alt="MVF Graph - Full Set" width="641" /><br>


Intensity Graph - Full Set

<img src="https://github.com/seng637-summer/seng637-a5-chd-vicis/blob/main/media/fullset_i.png" alt="Intensity Graph - Full Set" width="641" /><br>


MVF Graph - Subset with increasing Reliabilty

<img src="https://github.com/seng637-summer/seng637-a5-chd-vicis/blob/main/media/subset.png" alt="MVF Graph - Subset with increasing Reliabilty" width="641" /><br>


Intensity Graph - Subset with increasing Reliabilty

<img src="https://github.com/seng637-summer/seng637-a5-chd-vicis/blob/main/media/subset_i.png" alt="Intensity Graph - Subset with increasing Reliabilty" width="641" /><br>


MVF Graph - Subset with increasing Reliabilty and effort per interval of 36

<img src="https://github.com/seng637-summer/seng637-a5-chd-vicis/blob/main/media/subset-effort.png" alt="MVF Graph - Subset with increasing Reliabilty and effort per interval of 36" width="641" /><br>


Intensity Graph - Subset with increasing Reliabilty and effort per interval of 36

<img src="https://github.com/seng637-summer/seng637-a5-chd-vicis/blob/main/media/subset-effort-i.png" alt="Intensity Graph - Subset with increasing Reliabilty and effort per interval of 36" width="641" /><br>



## Discussion on Decision Making given a Target Failure Rate
When businesses are in the process of software development and testing, they often establish a target failure rate that they consider acceptable. By utilizing reliability growth analysis, testers can assist the business in determining whether it is achieving or falling below its desired failure rate. If the target isn't being met, the business can take corrective measures to address the issue. Reliability growth analysis also provides insights into the impact of specific software changes, guiding the business in understanding the implications of such changes for future modifications. This is particularly valuable for budgeting purposes. For example, software companies frequently introduce new features of varying sizes and scopes. When deciding the extent of testing required to maintain an acceptable failure rate, the business can refer to past data and existing growth analysis to assess the value of each feature. In essence, reliability growth analysis is indispensable for businesses as it aids in planning, budgeting, pinpointing problematic areas, and reducing a high failure rate.

## Discussion on the Advantages and Disadvantages of Reliability Growth Analysis
Advantages
* Reliability growth analysis offers significant utility for long-term planning, helping businesses allocate resources and funds for testing while predicting its impact on future defect detection.
* It's a straightforward analysis, relying solely on metadata from testing data.  It's fast to compute generally speaking.
* With sufficient context, it can identify problematic areas. For instance, if reliability suddenly deteriorates coinciding with the rollout of a particular feature, the analysis can quantify the feature's impact on metrics like MTTF or other reliability measures.
* It validates developers' efforts; increasing reliability and extended mean time between failures reflect the team's effective work.  This helps management gauge if their team is performing.

Disadvantages
* High-quality data is essential. Often, data lacks usefulness without additional context. In this assignment, for instance, reliability dropped suddenly around time interval 18, which is challenging to interpret without context and the true MTTF may be a subject of debate. 
* Reliability growth analysis relies on models and statistical assumptions, which may or may not hold true.
* It becomes severely limited with insufficient data; a substantial dataset is a prerequisite for meaningful analysis.  In this assignment there was only 31 intervals when ideally there should be far more.
* Software is dynamic and constantly evolving. While reliability growth analysis is crucial, it must be reevaluated whenever significant software changes occur.

# Reliability Demonstration Charts

1. Upon evaluation of the system's reliability metrics, the threshold for an acceptable Mean Time To Failure (MTTF) was delineated. We employed a trial-and-error method to iteratively adjust the Failure Input Output (FIO) to ascertain this. After multiple iterations, it was ascertained that the FIO aligned precisely at a ratio of 750/31, translating to approximately 24.194 failures per interval. Consequently, this results in an MTTF of 0.0413, establishing our operational reliability benchmark.

<img src="https://github.com/seng637-summer/seng637-a5-StevenD24/assets/105379503/fa651375-d652-457a-b185-00b953e49032" alt="RDC MTTFmin Normal" width="641" /><br>

2. Upon further examination of the system's reliability metrics, we assessed a scenario with an MTTF value that's precisely half the previously established minimum. Through our evaluations, this translated to an MTTF of 0.0823. To derive this, the Failure Input Output (FIO) was adjusted and determined to be at a ratio of 375/31, which is approximately 12.096 failures per interval. Under these parameters, it was observed that the System Under Test (SUT) almost instantaneously transitioned into the reject region.   
     
<img width="641" alt="image" src="https://github.com/seng637-summer/seng637-a5-StevenD24/assets/105379503/6c186a99-120c-4b3c-a17b-008e6d3f350a"><br>

3. Further into our systematic analysis of the system's reliability metrics, we investigated a scenario benchmarked at double the initial minimum MTTF. This exploration yielded an MTTF value of 0.0207. To achieve this, the Failure Input Output (FIO) was meticulously adjusted, settling at a ratio of 1500/31. This equates to approximately 48.387 failures per interval. Notably, with these parameters in play, the System Under Test (SUT) made a swift transition into the accepted region.
     
<img width="641" alt="image" src="https://github.com/seng637-summer/seng637-a5-StevenD24/assets/105379503/09a3f064-ea79-4309-844e-1796b6cb43f4">

### Advantages

1. **Explicit Risk Quantification**: RDC allows decision-makers to weigh the consequences of release decisions through explicit risk parameters like α (producer's risk threshold), β (customer's risk threshold), and γ (the discrimination ratio).

2. **Easy Decision Making**: It provides three different regions that reflect whether the system should be accepted, needs more testing, or should be rejected. This allows flexibility in decision-making and potentially helps in reaching a conclusion more quickly.

3. **Integration with Existing Tools**: RDC.xls is developed to work within Microsoft Excel, a commonly used tool in many organizations. It accepts the same failure data required for other reliability tools like CASRE, making integration and application easier.

4. **Open Source**: As an open-source tool, RDC allows for broader accessibility and can be modified to fit specific organizational needs.

### Disadvantages

1. **Complexity in Implementation**: The creation of RDC in Excel was noted to require considerable experimentation to achieve the desired graph. Some rewriting of the form of equations was also needed. Thus, using and adapting the tool might require some technical expertise and effort.

2. **Compatibility Issues**: The Excel macros and programming in the spreadsheets was dated and our group experienced compatibility issues with the spreadsheet with the newer versions of the Microsoft Excel on macOS. 

3. **Possibility of Incorrect Parameters**: The decision to accept or reject a system depends on the risk thresholds set by the producer. Incorrectly set parameters might lead to wrong decisions such as rejecting a satisfactory system or accepting an unsatisfactory one.

# Comparison of Results


# Discussion on Similarity and Differences of the Two Techniques
