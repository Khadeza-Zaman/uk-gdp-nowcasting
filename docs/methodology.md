# Methodology

## Data and stationarity
- Source: ONS "GDP monthly estimate" dataset, filtered to three series: 
  Monthly GDP (A--T), Index of Production (B--E), Index of Services (G--T)
- Sample: January 1997 onward (earliest available for monthly GDP)
- All three series are non-stationary in levels (p=0.71, 0.06, 0.79) - 
  expected, since these are index levels that trend upward over time
- Converted to month-on-month growth rates before modeling

## Growth rate conversion
- Converted all three series to month-on-month growth rates (pct_change)
- ADF test on growth rates: gdp_growth p<0.001, production_growth p<0.001, 
  services_growth p<0.001 - all stationary, confirms growth rates (not 
  levels) are the right basis for modeling

  ## Bridge equation (OLS)
- Regressed quarterly GDP growth on quarterly-averaged production_growth 
  and services_growth
- Full sample (1997-2026, includes COVID): R-squared=0.752, but Jarque-Bera 
  = 3033 (extreme non-normality), production_growth not significant (p=0.55)
- Excluding COVID (2020Q1-2021Q2): R-squared=0.528, Jarque-Bera=22.3 (far 
  more reasonable), production_growth closer to significant (p=0.09), 
  services_growth remains dominant either way (p<0.001)
- Conclusion: a substantial share of the full-sample R-squared was driven 
  by both GDP and the indicators reacting to the same shock simultaneously, 
  not genuine explanatory power. The COVID-excluded R-squared (0.53) is 
  the more honest estimate of how well these monthly indicators nowcast 
  GDP in normal conditions
- services_growth dominates in both specifications, consistent with 
  services being ~80% of UK GDP