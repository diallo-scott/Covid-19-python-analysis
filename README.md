# Assessing Impact of Covid 19 on US Counties using Python Analysis
Covid-19 is a global pandemic that has had an unprecedented impact of global health and economics.  The virus has spread quickly throughout the US and it has been important for both federal and local governments to take measures to protect their population.  Given the importance of monitorting the spread of the virus and slowing down the rates of infection and death, it is important that we are able to identify which areas of the US are most at risk.  We can accomplish this by using the data that we have already and performing analysis using Python.

## Business Question: Which US counties are the most vulnerable to the pandemic based on population characteristics and hospital bed availability?
We want to better understand which counties might be the most vulnerable to rapid viral spread so that these states and counties can implement social distancing policies that encourage people to stay at home, while also ensuring systems that allow access to food and essential items are in place.

## Data Question: What data and metrics can we use to show and monitor the COVID-19 pandemic in US Counties?
We’ll use data from the following sources to assess our business question:

Johns Hopkins University Center for Systems Science and Engineering (COVID-19 case, death, recovered data)

New York Times (COVID-19 US county-specific data)

American Community Survey (US county population data)

US Census (state and county geographic data)

Homeland Infrastructure Foundation-Level(US hospital data)

In our Python Notebooks we’ll use the following packages to conduct our analysis:
  pandas 1.0.3, numpy 1.81.1, plotly 4.60

## Data Answer

The following refers to the python analysis conducted in [this](htps://github.com/diallo-scott/covid-19-county-risk-python-analysis/blob/master/Covid_19.ipynb) link.

When looking for which metrics can be used to monitor the Covid-19 pandemic in US Counties and mitigate the impacts, it makes sense to consider factors such as total population, number of cases and deaths, population under 18, population over 60, and the number of hopsitals and hospital beds.  We can assume that the most populous counties are at risk of the fastest spread, but the impact and death toll caused by rapid spread in metropolitan areas may be mitigated by having a larger number of hospitals.  Thus, to see how all of these factors play together we conducted a correlation analysis, and the results are displayed below.
