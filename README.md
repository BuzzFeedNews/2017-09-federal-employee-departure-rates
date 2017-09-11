# Federal Employee Departure Rate Analysis

This repository contains analytic code and findings related to the BuzzFeed News article, "[Trump’s Election Didn’t Spark An Immediate Exodus From The Federal Government](https://www.buzzfeed.com/jsvine/no-mass-exodus-from-federal-goverment-after-trumps-election)," published September 11, 2017. Please read that article, which contains important context and methodological details, before proceeding.

## Table Of Contents

- [Data](#data)
    - [Raw data](#raw-data)
    - [Output data](#output-data)
- [Reproducibility](#reproducibility)
- [Feedback / Questions?](#feedback--questions)

# Data

## Raw data

The analysis is based, primarily on federal payroll data [provided to BuzzFeed News by the Office of Personnel Management](https://www.buzzfeed.com/jsvine/sharing-hundreds-of-millions-of-federal-payroll-records), which we have [shared via the Internet Archive](https://archive.org/details/opm-federal-employment-data/).

This repository also includes three data-translation tables, `inputs/DTagy.txt` (for agency names), `inputs/DTocc.txt` (for occupation names), and `inputs/plan-codes.csv` (for pay-plan names). The first two are copied from the Office of Personnel Management's [March 2017 FedScope data](https://www.opm.gov/data/Index.aspx?tag=FedScope). The third was extracted from a larger data-translation table (`SCTFILE.txt`) [provided by OPM with the data above](https://archive.org/download/opm-federal-employment-data/data/1973-09-to-2014-06/).

## Output data

The [analytic code](notebooks/) in this repository produces the following outputs:

### Historical estimates

This file contains estimated quarterly departure rates, from just before George W. Bush's first election to the quarter ending March 2017. The estimations use two approaches — one based on the employer "Pseudo ID" supplied by OPM until recently, and one based unique names:

- [`historical-estimates.csv`](output/historical-estimates.csv) 

### Post-election estimates

These files contain the estimated departure rates for each quarter following the 2000, 2008, and 2016 elections:

- [`turnover-overall.csv`](output/turnover-overall.csv)
- [`turnover-by-pay-plan.csv`](output/turnover-by-pay-plan.csv)
- [`turnover-by-agency.csv`](output/turnover-by-agency.csv)
- [`turnover-by-patco.csv`](output/turnover-by-patco.csv)
- [`turnover-professionals-by-occupation.csv`](output/turnover-professionals-by-occupation.csv)
- [`turnover-attorneys-by-agency.csv`](output/turnover-attorneys-by-agency.csv)
- [`turnover-by-education.csv`](output/turnover-by-education.csv)
- [`turnover-by-college-degree.csv`](output/turnover-by-college-degree.csv)

# Reproducibility

To reproduce the findings, you'll need to do the following:

- Ensure that you have installed [Jupyter](http://jupyter.org/), [Python](https://www.python.org/), and the [pandas data-analysis library](https://pandas.pydata.org/) (version 0.19 or higher).
- Download the [OPM payroll data](https://archive.org/details/opm-federal-employment-data/) and copy the `data` folder into this directory as [`inputs/fedscope-data`](inputs/fedscope-data).
- Clear the [`output/`](output/) directory. (Shortcut: run `make clear`.)
- Use Jupyter to run each notebook in the [`notebooks/`](notebooks/) directory consecutively. (Shortcut: run `make reproduce`; requires Python 3.)

# Feedback / Questions?

Contact Jeremy Singer-Vine at [jeremy.singer-vine@buzzfeed.com](jeremy.singer-vine@buzzfeed.com).

Looking for more from BuzzFeed News? [Click here for a list of our open-sourced projects, data, and code](https://github.com/BuzzFeedNews/everything).
