Introduction
CPU performance is popularly benchmarked using various tools such as HWMonitor, 3DMark, UserBenchmark, CineBench, and more. These tools score the CPUs on their single-core and multi-core performance, depending on cache size, the number of cores, and clock speed. In most CPUs, there are 2 clock speeds - the base clock speed and the turbo clock speed. The base clock
speed is the frequency at which the CPU operates at minimum, whereas the turbo clock speed is
the maximum frequency the CPU can boost to handle heavy programs. The question we need to
solve here is: Are CPUs' boost clock speeds accurate performance measures?
As technology enthusiasts, we love to understand our hardware. We believe that there is a lot of
ignorance among gamers and general computer productivity users about the kind of machines
they drive daily. As a result, most people end up overspending on their computers. We feel that
this can be easily avoided by educating the general audience about the itty bitty details of the
components that go into their computers. We hope to shine light on one of the most important
components, the CPU of the computer.


Hypothesis
H0 -> No linear relationship between single-core scores and turbo clock speeds (ß1 = 0)
Ha- > Positive linear relationship between single-core scores and turbo clock speeds (ß1 > 0)


Methods
Users run the CineBench R23 software on their PCs and submit their scores to the CineBench
website. A random sample of this data has been used for our analysis. The data contains nine
columns (‘manufacturer’, ‘cpuName’, ‘singleScore’, ‘multiScore’, ‘cores’, ‘threads’,
‘baseClock’, ‘turboClock’, ‘type’) and 215 rows of observation of Intel, AMD and Apple CPUs.
We will perform a linear regression hypothesis test to check the linearity between single-core
scores and the turbo clock speeds of CPUs. We will be focusing on single-core evaluation scores
and turbo clock speed.


Linear regression equation (Population model):
Single Core Score = ß0 + ß1 * (Turbo Clock Speed) + ε
ß0 -> Intercept of the regression line on the y-axis
ß1 -> Slope of the regression line of single-core scores and turbo clock speeds
ε -> Error ~ N(0, σ2)


Results
Fig. 1: Single core scores vs. Turbo clock speed
Shows the relationship between single core scores and the turbo clock speeds

Conditions
We found that our scatterplot is fairly linear (Fig. 2). The variables are independent by nature of
the way the data was collected. Other conditions, such as normality of the residuals (Fig. 3) and
equal variance of the response variable (single core scores) (Fig. 4), are also satisfied.
Our regression model

Single Core Score = 72.85 + 286.78 * (Turbo Clock Speed) + 31.61
Test Statistic = 9.071 p-value = < 2e-16 Conf. Int. = (224.4601, 349.0955)
Since the p-value is less than 0.05, we reject the Null Hypothesis. Thus the single core score and
the turbo clock speeds have a positive linear relationship.

Secondary Analysis
The scatterplot shows that Apple produces high values of single core scores at low turbo clock
speeds. AMD shows a consistent increase in performance with an increase in their turbo clock
speeds, and Intel, on the other hand, offers a high variance of performance at any particular clock
speed. Thus we can say that the performance of Intel CPUs is relatively unpredictable.


Discussion
We have successfully shown that the single-core performance of CPUs increases linearly with
the turbo clock speeds. This proves the fact that, in general, a CPU that boasts a high turbo clock
speed is better for a lot of single-core applications. We have additionally compared trends of
performance increase in Apple, AMD, and Intel CPUs. A few limitations in our study come from
the authenticity of the data we used since the data comes from independent users. Additionally,
certain essential factors, such as CPU architecture, transistor size, cache, etc., are missing in our
data, influencing the performance scores considerably.


References
1. https://www.kaggle.com/datasets/alanjo/cinebench-r23-scores-may-2022
2. https://www.researchgate.net/publication/353115679_Changing_Trends_in_Computer_A
rchitecture_A_Comprehensive_Analysis_of_ARM_and_x86_Processors
