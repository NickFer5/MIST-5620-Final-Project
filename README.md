---
subtitle: "[]{#_ws3n5yfypyj .anchor}Mariana Rojas (CRN 67558)"
title: "[]{#_hah77m82os26 .anchor}MIST 5620 Project Report"
---

### Allison Keonhothy (811816282)

### Carson Harris (811210096)

### Corbin Gay (811654274)

### Emil Kali (811981048)

### Luke Lambert (811455966)

### Nicholas Ferington (811163989)

### 

### 

### 

We have chosen to work with eight data sets all coming from [[Georgia
Data]{.underline}](https://georgiadata.org/data/data-tables) , a
resource maintained by the University of Georgia and the Carl Vinson
Institute of Government. These institutions gather publicly available
data to support research, policymaking, and community development
efforts. Exploring issues like poverty, housing insecurity, labor
participation, and demographics, we were able to explore how these
factors may relate to county-level crime. Understanding these
associations can help inform future policy decisions around education,
housing, and economic development aimed at reducing crime in Georgia
communities.

Before identifying which questions need to be pursued, it's important to
consider the key stakeholders involved. At the forefront are individuals
living in Georgia counties, including local communities, law
enforcement, and victims of crime who are directly impacted. In the
background stakeholders may include educators, policymakers, and state
officials who influence or are influenced by crime trends. Our analysis
uses a multiple linear regression model to explore how socioeconomic and
demographic factors relate to crime rates at the county level. These
relationships help shape the questions we pursue and provide insight
into the drivers of crime across the state.

From a holistic standpoint, we aim to understand whether economic and
demographic factors are associated with higher crime rates across
Georgia counties. Specifically, how might variables such as poverty,
housing insecurity, labor force participation, and demographic
composition influence crime? To explore this, we ask: What proportion of
the variation in crime rates can be explained by poverty levels? Do
labor force participation rates correlate more strongly with certain
types of crime, such as poverty versus violent crime? How might housing
insecurity contribute to county-level crime rates, and could
improvements in employment be associated with reductions in both crime
and poverty?

By answering the proportion of crime rates associated with poverty,
labor participation, housing, and background demographics, we can get
more precise insights at the direct and immediate impact, apart from
just observing a possible correlation. Answering these questions can
make resource allocation for county officials more efficient if we
observe how these variables impact one type of crime versus another.
Additionally, understanding patterns in housing and employment may
reveal how they influence poverty rates, which in turn could help
explain broader crime trends across Georgia.

Data for the project was sourced from the Georgia Data Portal, which
features publicly available datasets on social, economic, and
demographic metrics. Crime statistics were provided by law enforcement
and justice records, while population figures were drawn from census
reports. We joined eight datasets into a single file, resulting in over
200 variables spanning poverty, housing, employment, education, and
demographic indicators. The data was downloaded in Excel format and
preprocessed to remove missing values, standardize variable names, and
ensure consistency across counties. Some counties were filtered out to
enhance precision and maintain data quality for the final analysis.

This information aligns with the research question by offering reliable,
government-backed data at the county level across a range of
socioeconomic indicators. While the crime data reflects 2023, several
variables are drawn from 2020-2022, offering recent historical context
for understanding conditions leading up to reported crime rates. The
geographic detail enables localized, county-level analysis, and by
integrating multiple variables from credible sources, the combined
datasets strengthen the reliability of our exploratory findings. This
approach supports meaningful comparisons across counties while reducing
bias and improving the validity of our statistical analysis.

For our analysis, the main target of interest was the 2023 total crime
per 100,000 residents at the county level in Georgia. The goal was to
explore how various factors are associated with differences in total
crime rates across counties. While high school graduation rate was
initially considered, our final model focuses on variables that are more
consistently available, statistically significant, and better suited to
capturing associations with crime. This approach allowed for a more
comprehensive exploration of the underlying factors contributing to the
variation in county-level crime rates.

The descriptive statistics and correlations attained while making the
data manipulations in R proved to be very helpful. Our datasets were
categorized by counties in GA. In our datasets we have a total of 159
counties equating to 159 data points. By reviewing the summary
statistics, we gained insight into the distribution of variability of
factors. The correlation matrix revealed several notable patterns.
Renter-occupied housing and child poverty showed positive correlations
with crime rate, suggesting that housing instability and economic
hardships may be linked to higher crime. Oppositely, senior poverty
showed a slight negative correlation with crime. Black birth, while
positively correlated in isolation, had a negative coefficient in the
regression model due to multicollinearity with other variables. The
descriptive statistics are useful in gathering an overall look of our
datasets and support the selection of variables that were both
statistically meaningful and socially relevant.

Our target variable was total crime per 100,000 by county. It is a
numeric, continuous variable that represents the number of crime
incidents that were recorded in each county in 2023, standardized by
population size. This rate was already calculated in the original crime
dataset, which allowed us to work directly with standardized crime
figures across counties. It allowed us to make comparisons without
manually having to adjust for population.

The method we used for creating our model was a multiple linear
regression. The original number of variables from all of our datasets
combined exceeded 200. It was important for us to utilize only the
variables that best answered our research questions and explained
variation in crime. We also had to ensure that the number of
observations was sufficient for the amount of variables we would use for
our model. We felt a multiple linear regression was useful because crime
is an extremely complex topic and can be explained by a multitude of
different variables. A multiple linear regression allows us to analyze
the impact of each individual predictor, and how important each variable
truly is in explaining crime. This also allows us to make our
recommendations based on what we learned from the model. For example,
observing that housing insecurity may have an impact on crime could lead
governments and policy makers to invest more into public housing.

In order to address overfitting, we verified that each variable was
explainable, relevant, and non-redundant. For example, we removed a
variable called "Months reported" from our model, which decreased our
R-square from above 0.5 to 0.47. This is because the variable described
how often a county reported crimes between months and therefore was
slightly redundant, as we would be using crime reports to predict crime
itself.

Our multiple linear regression resulted in an R-squared value of 0.47.
This is considered a moderate fit for social science research. This
result indicates that 47% of the variation in crime can be explained by
our model and its predictors. The adjusted R-squared of 0.454 further
confirms a moderate fit. Our model revealed statistically significant
associations, but it is important to remember that correlation does not
imply causation. Several predictors showed statistically significant
associations. Child and family poverty, as well as renter-occupied
housing, were positively associated with higher crimes. In contrast,
senior poverty and labor force participation were negatively associated
with crime. Interestingly, while black births showed a positive trend in
a bivariate plot, the regression model estimated a negative coefficient.
This likely reflects multicollinearity with other variables, such as
child poverty and labor force participation. It is important to note
again that this is a correlational analysis and we are not making causal
inferences. However, this model is helpful in answering our question and
provides valuable insights into broader socioeconomic factors that may
relate to crime across the state.

Our analysis faced several limitations that are important to consider
when interpreting the results. Our analysis is based on data from all of
Georgia\'s counties, which is 159. We utilized eight different datasets,
joined together with over 200 variables. Although we had lots of
features to choose from, the number of variables that we could include
in our model without overfitting was extremely restricted. Since our
sample size is relatively small our model complexity is limited,
reducing our overall ability to capture all of the factors that
influence crime. Additionally, while our target variable, total crime
per 100,000, was from 2023, many of our predictor or control variables
were only available for earlier years. This temporal mismatch was not
due to oversight, but rather a limitation of the available public
datasets from Georgia Data. In many cases, socioeconomic trends like
poverty and housing insecurity change gradually over time, so using
slightly older data still provides meaningful context for understanding
crime patterns in 2023.

While we identified multicollinearity between some predictor variables,
particularly between child poverty, labor force participation, and black
birth rates, we chose to keep these variables in our final model. Since
this is an explanatory model, our goal was to uncover potential
associations between socioeconomic factors and crime, not to isolate
precise causal effects. Leaving these correlated variables allowed us to
capture broader community-level conditions that may influence crime,
even if their coefficients should be interpreted with caution.
Furthermore, all variables included were significantly significant in
initial testing, so removing them would have reduced the overall
explanatory power of the model and would have eliminated important
social context. In addition to this crime is extremely complicated in
that it is influenced by a wide range of social, economic, and even
cultural factors that are hard to measure and account for. So it is
important for our model to be used to identify meaningful associations
that could be used to inform policy decisions rather than make causal
claims.

We recommend using our model for explanatory insights to guide policy
and community action. Policymakers and community leaders can use these
insights to guide strategies aimed at reducing crime in Georgia.
Counties with high crime rates consistently exhibit socioeconomic
challenges such as elevated child and family poverty, housing
instability, and lower labor force engagement. Addressing these root
causes through investments in affordable housing, workforce development,
and poverty reduction programs may result in significant benefits. In
addition, we encourage the use of this model to identify high-risk areas
and allocate resources more effectively. This must be done in
collaboration with local organizations, social service workers, and law
enforcement. Lastly, we encourage this model to be continually refined
by using new data and also exploring specific types of crime to provide
further strategies.

## 

## 

## 

## 

## 

## 

## 

## Model Predictors

| Variable Name                                           | Description                                                                            |
|---------------------------------------------------------|----------------------------------------------------------------------------------------|
| 2022 Related Children in Families, Age 5-17, in Poverty | Number of children ages 5-17, living below the poverty threshold                       |
| 2018-2022 Persons Age 65 and Over in Poverty, Percent   | Percentage of individuals ages 65+ who fell below the poverty threshold from 2018-2022 |
| 2018-2022 Families Below Poverty Level, Percent         | Percentage of families who fell below the poverty threshold from 2018-2022             |
| 2023 Labor Force Employed                               | Number of individuals who were employed (part/full-time) in 2023                       |
| 2023 Black Births                                       | Number of births in 2023 where the child born was of Black/African-American descent    |
| 2018-2022 Renter-Occupied Housing Units, Percent        | Percentage of housing units that are renter-occupied from 2018-2022                    |

## Correlation Matrix![](media/image5.png){width="6.5in" height="1.8611111111111112in"}

## Descriptive Statistics

![](media/image1.png){width="6.5in" height="2.1666666666666665in"}

## 

## 

## 

## Visualizations

![](media/image7.png){width="3.127858705161855in"
height="3.8281255468066493in"}![](media/image3.png){width="3.1406255468066493in"
height="3.8621194225721784in"}

![](media/image2.png){width="3.1458333333333335in"
height="3.906590113735783in"}![](media/image8.png){width="3.2239588801399823in"
height="3.9451071741032373in"}

![](media/image6.jpg){width="3.1689818460192476in"
height="3.967668416447944in"}![](media/image4.png){width="6.286458880139983in"
height="4.83573709536308in"}

## Appendix  {#appendix}

Tools Used

1.  Tableau

    a.  Components Used:

        i.  Data connections: fullJoinDF_Cleaned.xlsx (merged dataset of
            > 8 sources including poverty, labor, births, housing, etc.)

        ii. Visualizations: Scatterplots showing the associations
            > between socioeconomic indicators and total crime rate per
            > 100,000 residents across Georgia counties

Reproducibility Instructions

a.  Open Tableau Desktop, connect to the data sources, and create a
    > relationship between juvenile_court_comm and graduates_county
    > sheets

b.  Scatterplots:

    i.  Drag 2023 Total Index Crime Rate per 100,000 Population to Rows

    ii. Drag the relevant predictor variable to Columns

    iii. Set mark type to circle

    iv. Add a trend line from the analytics pane

    v.  Clean up titles, axis labels, and formatting

c.  Map and Bar Chart:

    i.  Map

        1.  Drag Count on the canvas

        2.  Drag 2023 Total Index Crime Rate per 100,000 Population to
            > Color

        3.  Format color scale for clarity

    ii. Bar Chart

        1.  Drag County to Rows

        2.  Drag 2023 Total Index Crime Rate per 100,000 Population to
            > Columns

        3.  Sort descending

        4.  Add filter to show only top 10 values
