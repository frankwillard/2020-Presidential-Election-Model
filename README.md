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

| Attribute Name | Display Name | Alt Name | Type | Value Range |       Description      | Source |
| ------------- |:-------------:| :-------------:| :-------------:| :-------------:| :--------------------------:| --:|
| Incumbency Indicator | incumbency | x0 | Boolean | -1 to 1 | If the current president is running for reelection, 1 if democrat and -1 if republican. If the current president is not running, 0. | https://en.wikipedia.org/wiki/United_States_presidential_election |
| Incumbent Party Indicator | incumbent_party | x1 | Boolean | -1 to 1 | If the current president is democratic, this is a 1. If republican, this is a -1. | https://en.wikipedia.org/wiki/United_States_presidential_election |
| Consecutive Terms Indicator | consec_terms | x2 | Boolean | -1 to 1 | Indicator for whether the party in office has held office for more than one term. 1 if the democratic party has, -1 if the republican party has, and 0 otherwise. | https://en.wikipedia.org/wiki/United_States_presidential_election |
| Home State Indicator | home_state | x3 | Boolean | -1 to 1 | If the state in question is the candidate's home state: 1 if democrat and -1 if republican. If not applicable, 0. | https://en.wikipedia.org/wiki/List_of_presidents_of_the_United_States_by_home_state |
| Percentage of Black Residents | black | x4 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Hispanic Residents | hispanic | x5 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Cuban Residents | cuban | x6 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Other Non-white Residents | nonwhite | x7 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Residents Who Are 18-34 | young_age | x8 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Residents Who Are 35-64 | middle_age | x9 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Residents Who Are 65+ | old_age | x10 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Percentage of Evangelical Christian Residents | evangelical | x11 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.pewforum.org/religious-landscape-study/religious-tradition/evangelical-protestant/ https://www.thearda.com/ql2010/QL_S_ALL_1_27c.asp|
| Percentage of College Educated Residents| educated | x12 | Numeric | 0 to 100 | The percentage of residents of the given demographic statewide (out of 100). | https://www.socialexplorer.com/a9676d974c/explore |
| Annualized GDP Growth Rate | gdp | x13 | Numeric | -100 to 100 | Annualized GDP growth rate using real GDP per capita from the first and third quarters of the election year. | https://fred.stlouisfed.org/series/A939RX0Q048SBEA |
| Change in National Unemployment Rate | unemployment | x14 | Numeric | -100 to 100 | Change in national unemployment between January and September of election year. | https://fred.stlouisfed.org/series/UNRATE |
| Annual Real Disposable Personal Income Growth | income | x15 | Numeric | -100 to 100 | Annualized real disposable personal income (after-tax income adjusted for inflation) growth rate using the first and third quarter of the presidential election year. | https://fred.stlouisfed.org/series/DSPIC96 |
| Democrat State Polling | state_polling | x16 | Numeric | 0 to 100, -99999 (indicates N/A) | Average democratic vote share in an average of polls of each state as of October 25. If there is not enough polling to average, use -99999 to indicate a missing value. | https://projects.fivethirtyeight.com/polls/ |
| Indicator for Sufficient State Polling | suff_state_polling | x17 | Boolean | 0 to 1 | Indicator for whether there is enough polling to aggregate in a given state (based on FiveThirtyEight's polling average). | https://projects.fivethirtyeight.com/polls/ |
| Democrat National Polling | state_polling | x18 | Numeric | 0 to 100 | Average democratic vote share in an average of national polls as of October 25. | https://projects.fivethirtyeight.com/polls/ |
| Presence of a Viable Third Party Candidate | viable_third_cand | x19 | Boolean | 0 to 1 | Indicator for whether or not there is a third party candidate that polls at or above 5% as of October 25. | https://projects.fivethirtyeight.com/polls/ |
| Third Party State Polling | third_party_state_polling | x20 | Numeric | 0 to 100 | Average vote share received by all third party candidates in an average of national polls as of October 25 (if they receive at least 5% of the vote). If there is no candidate receiving 5%, use -99999 to indicate a missing value.| https://projects.fivethirtyeight.com/polls/ |
| Indicator for Sufficient Third Party Polling| suff_third_polling | x21 | Boolean | 0 to 1 | Indicator for whether or not there is enough polling of a third party candidate to aggregate in a givern state (based on FiveThirtyEight's polling averages). | https://projects.fivethirtyeight.com/polls/ |
| Third Party Vote Share in National Polls | third_party_national_polling | x22 | Numeric | 0 to 100 | Average vote share received by all third party candidates in an average of national polls as of October 25 (if they receive at least 5% of the vote). If there is no viable third party candidate, use 0. | https://projects.fivethirtyeight.com/polls/ |
| Net Approval | approval | x23 | Numeric | -100 to 100 | The percentage of people who approve of the way the President is handling their job minus the percentage of people who disapprove of the way the president is handling their job (based on Gallup's approval polling). Multiplied by -1 if Republican is President. | https://www.presidency.ucsb.edu/statistics/data/presidential-job-approval |
| Democratic Candidate Net Favorability | dem_favor | x24 | Numeric | -100 to 100 | Calculated by subtracting the democratic candidate's unfavorability rating from their favorability rating. Meant to show, in general, how the population feels about this candidate. | https://fivethirtyeight.com/features/trump-won-despite-being-unpopular-so-can-he-govern-that-way/ |
| Republican Candidate Net Favorability | rep_favor | x25 | Numeric | -100 to 100 | Calculated by subtracting the republican candidate's unfavorability rating from their favorability rating. Meant to show, in general, how the population feels about this candidate. | https://fivethirtyeight.com/features/trump-won-despite-being-unpopular-so-can-he-govern-that-way/ |
| Polling Variable: Expected Dem. Vote Share | polling_variable | x26 | Numeric | 0 to 100 | Used to aggregate all applicable polling data into one variable. If suff_state_polling is 1, use solely state_polling. If suff_state_polling is 0 (meaning there isn't adequate polling), use the national election vote share plus the state's average differential in the past two elections: national_polling + past_elections | Based on other variable data (see description): (state_polling * suff_state_polling) + ( (1 - suff_state_polling) * (national_polling + past_elections))|
| Third Party Expected Vote Share | third_party | x27 | Numeric | 0 to 100 | Used to aggregate all third party polling data. If viable_third_cand = 1, and suff_third_party = 1, solely use third_party_state_polling. If viable_third_cand = 1, and suff_third_party = 0, use variable third_party_national_polling as a substitute. If viable_third_cand = 0, meaning that there is no viable third party candidate, this variable = 0. | Based on other variable data (see description): viable_third_cand * ((third_party_state_polling * suff_third_polling) + ((1 - suff_third_polling) * third_party_national_polling)|
| Average Vote Differential for Past Elections | past_elections | x28 | Numeric | -100 to 100 | The average difference in Democratic share vote share between the given state and the nation as a whole over the last two elections. This variable gives us an idea of the general "lean" of the state compared to the nation in recent history and is used to help calculate polling_variable in the absense of reliable polling. | https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/42MVDX |
