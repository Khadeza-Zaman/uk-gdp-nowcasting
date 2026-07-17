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

  