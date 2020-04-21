# Assessing Danger of Covid 19 to US Counties with Python Analysis
Covid-19 is a global pandemic that has had an unprecedented impact of global health and economics.  The virus has spread quickly throughout the US and it has been important for both federal and local governments to take measures to protect their population.  Given the importance of monitorting the spread of the virus and slowing down the rates of infection and death, it is important that we are able to identify which areas of the US are most at risk.  We can accomplish this by using the data that we have already and performing analysis using Python.

## Business Question: Which US counties are the most vulnerable to the pandemic based on population characteristics and hospital bed availability?
We want to better understand which counties might be the most vulnerable to rapid viral spread so that these states and counties can implement social distancing policies that encourage people to stay at home, while also ensuring systems that allow access to food and essential items are in place.

## Data Question: What data and metrics can we use to show and monitor the COVID-19 pandemic in US Counties?
We’ll use data from the following sources to assess our business question:

[Johns Hopkins University Center for Systems Science and Engineering](https://github.com/CSSEGISandData/COVID-19) (COVID-19 case, death, recovered data)

[New York Times](https://github.com/nytimes/covid-19-data) (COVID-19 US county-specific data)

[American Community Survey](https://data.census.gov/cedsci/table?q=United%20States&g=0100000US.050000&tid=ACSST5Y2018.S0101&hidePreview=false&vintage=2018&layer=VT_2018_050_00_PY_D1&cid=DP05_0001E&t=Populations%20and%20People) (US county population data)

[US Census](https://www.census.gov/geographies/reference-files/2018/demo/popest/2018-fips.html) (state and county geographic data)

[Homeland Infrastructure Foundation-Level](https://hifld-geoplatform.opendata.arcgis.com/datasets/hospitals)(US hospital data)

In our Python Notebooks we’ll use the following packages to conduct our analysis:
  pandas 1.0.3, numpy 1.81.1, plotly 4.60

## Data Answer

The following refers to the python analysis conducted in [this](htps://github.com/diallo-scott/covid-19-county-risk-python-analysis/blob/master/Covid_19.ipynb) link.

When looking for which metrics can be used to monitor the Covid-19 pandemic in US Counties and mitigate the impacts, it makes sense to consider factors such as total population, number of cases and deaths, population under 18, population over 60, and the number of hopsitals and hospital beds.  We can assume that the most populous counties are at risk of the fastest spread, but the impact and death toll caused by rapid spread in metropolitan areas may be mitigated by having a larger number of hospitals.  Thus, to see how all of these factors play together we conducted a correlation analysis, and the results are displayed below.
![image](https://github.com/diallo-scott/covid-19-county-risk-python-analysis/blob/master/Plots/Covid%20Correlation%20Heatmap.png)
Bright yellow demonstrates a high degree of correlation, whereas purple is a low degree of correlation.  This chart demonstrates the intuition that there may be a relationship between total population and number of cases and deaths.  A more interesting finding from this analysis, however, is the low degree of correlation between hospital bed counts per 1000 people and number of cases and deaths per 1000 people.  Furthermore, the percentages of the population that are over 60 and under 18 did not have a high correlation with number of cases and deaths.  These two findings contradict inital intuition that having a large at risk population would correlate with more cases and deaths, but this result could also be due to some limitations of our datasets, such as underreporting of cases and a lack of sufficient testing.

This chart does provide some insight that allows us to answer our data question.  If looking to monitor the pandemic we should place a higher emphasis on those counties with high total populations and focus on bringing life saving equipment to counties with a high number of cases.  To provide more specific, insights, however we would need to find other datasets that contain more information on the other factors that are obviously contributing to the spread.  For example we may want to look at tourism rates, population density, community wealth, etc.

## Business Answer

To determine which counties are most at risk, we may want to let intuition guide our answer.  Counties that have a large percentage of population that is more vulnerable (i.e a large population below 18 or above 60) may experience faster and more fatal spread of the virus and would, therefore, be more at risk.  Counties looking to mitigate the lethal impacts of the virus would also need to have a large number of hospital beds to accomodate their infectred population.  Below are several charts that specify certain counties that may be at risk.

These are the 20 counties with the fewest hospital beds in the US.  These counties may be ill-equipped to provide life-saving services to their infected populations.
![image](https://github.com/diallo-scott/covid-19-county-risk-python-analysis/blob/master/Plots/US%20Counties%20with%20the%20Fewest%20Hospital%20Beds.png)

These two charts show 20 counties with the highest percentages of elderly and under 18 populations in the US.  The virus is more deadly for this population, so these counties want to be on high alert and take proactive measures.

![image](https://github.com/diallo-scott/covid-19-county-risk-python-analysis/blob/master/Plots/US%20Counties%20with%20the%20Highest%20Percent%20of%20Population%20Ages%2060%2B.png)
![image](https://github.com/diallo-scott/covid-19-county-risk-python-analysis/blob/master/Plots/US%20Counties%20with%20the%20Highest%20Percent%20of%20Population%20Under%20Age%2018.png)

Although the above charts can provide us with some guidance in identifying at risk counties, it would be more helpful to standardize the data for hospital beds and look at how many hospital beds a county has per 1000 people.  This led us to create a chart that combined population data with number of hospital beds per 1000 people. The axes of the following chart are percent of population above 60 and percent of population under 18.  The size of the bubbles is the number of hospital beds per 1000 people.

![image](https://github.com/diallo-scott/covid-19-county-risk-python-analysis/blob/master/Plots/Percentage%20of%20Population%20Under%2018%20and%20Over%2060%20in%20US%20Counties.png)

The counties most at risk in this chart would be those with large percentages of the population above 60 and below 18 and with a small bubble size (since size of the bubble is hospital beds per 1000).  It is interesting to note that many of the counties that appeared on the chart of the 20 counties with the highest percent of population being above 60 also have small dots on this chart.  Thus, those counties may be at a high risk of experiencing more viral spread and higher death rates due to the virus.
