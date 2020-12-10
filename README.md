# 2020-Presidential-Election-Model
Machine Learning Presidential Election Model by Individual State Vote Share (Completed 11/02)

Final Regression:

y- Democratic Vote Share for a given state

ŷ = 0.251150 * incumbency - 1.110680 * consec_terms + 1.614704 * home_state + 0.036132 * black + 0.035016 * hispanic - 0.136206 * cuban + 0.025504 * nonwhite - 0.111260 * pca1 - 0.062855 * evangelical + 0.014444 * educated - 0.110635 * pca2 + 0.671394 * polling_variable – 0.156228 * third_party + 0.329908 * past_elections + 17.4902

PCA1: Incorporates three variables
1. young_age
2. middle_age
3. old_age

PCA2: Incorporates three interaction terms
1. incumbent_party * gdp
2. incumbent_party * unemployment
3. incumbent_party * income

## Data Dictionary

| Attribute Name | Display Name | Alt Name | Type | Value Range | Description | Source |
| ------------- |:-------------:| :-------------:| :-------------:| :-------------:| :-------------:| -----:|
| Incumbency Indicator | incumbency | x0 | Boolean | -1 to 1 | If the current president is running for reelection, 1 if democrat and -1 if republican. If the current president is not running, 0. | https://en.wikipedia.org/wiki/United_States_presidential_election |
| Consecutive Terms Indicator | consec_terms | x2 | Boolean | -1 to 1 | Indicator for whether the party in office has held office for more than one term. 1 if the democratic party has, -1 if the republican party has, and 0 otherwise. | https://en.wikipedia.org/wiki/United_States_presidential_election |
| Home State Indicator | home_state | x3 | Boolean | -1 to 1 | If the state in question is the candidate's home state: 1 if democrat and -1 if republican. If not applicable, 0. | https://en.wikipedia.org/wiki/List_of_presidents_of_the_United_States_by_home_state |
| Percentage of Black Residents | black | x4 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Hispanic Residents | hispanic | x5 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Cuban Residents | cuban | x6 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Other Non-white Residents | nonwhite | x7 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Residents Who Are 18-34 | young_age | x8 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Residents Who Are 35-64 | middle_age | x9 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Residents Who Are 65+ | old_age | x10 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
