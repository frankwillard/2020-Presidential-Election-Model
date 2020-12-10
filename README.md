# 2020-Presidential-Election-Model
Machine Learning Presidential Election Model by Individual State Vote Share (Completed 11/02)

Final Regression:

y- Democratic Vote Share for a given state

ŷ = 0.251150 * incumbency - 1.110680 * consec_terms + 1.614704 * home_state + 0.036132 * black + 0.035016 * hispanic - 0.136206 * cuban + 0.025504 * nonwhite - 0.111260 * pca1

PCA1: Incorporates three variables
1. young_age
2. middle_age
3. old_age

## Data Dictionary

| Attribute Name | Display Name | Alt Name | Type | Value Range | Description | Source |
| ------------- |:-------------:| :-------------:| :-------------:| :-------------:| :-------------:| -----:|
| Incumbency Indicator | incumbency | x0 | Boolean | 0-1 | If the current president is running for reelection, 1 if democrat and -1 if republican. If the current president is not running, 0. | https://en.wikipedia.org/wiki/United_States_presidential_election |
