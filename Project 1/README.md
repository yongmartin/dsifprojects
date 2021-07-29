# Project 1 - Study of ACT and SAT across US States

## Background
SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. These scores are used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

## Problem Statement
To present recommendations to the US Department of Education on how to improve the participation rate and scores of the SAT & ACT standardized tests by studying them against the US states.

## Data Sources
- [2019 ACT Scores by State](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)
- [2019 SAT Scores by State](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent)
- [US Geographic Regions from US Census Bureau](https://www.census.gov/geographies/reference-maps/2010/geo/2010-census-regions-and-divisions-of-the-united-states.html)
- [State-Administered Test Policy for SAT](https://blog.prepscholar.com/which-states-require-the-sat)
- [State-Administered Test Policy for ACT](https://blog.prepscholar.com/which-states-require-the-act-full-list-and-advice)
- [Geometry for US map from US Census Bureau 2018](https://www.census.gov/geographies/mapping-files/time-series/geo/carto-boundary-file.html)

## Summary

1. ACT has higher participation rates than SAT across states:
  - There are more states with 100% participation in ACT than SAT (15 states vs 8 states)
  - The states with bottom 10 participation rates for ACT has a participation range of: 6-22% while for SAT: 2-4%

  <p align=”center”>
    <img src="./img/2019 Participation Rate.png" width="500">
  </p>


2. There seems to be an inverse correlation between SAT test participation rate and ACT test participation rate. From the chart below, we can see that states are concentrated on top left and bottom right corners - states with high participation rates in 1 test generally has much lower participation in the other.

  <p align=”center”>
  <img src="./img/State Participation.png" width="500">
  </p>


3. When we combine SAT and ACT participation rates, there are many states which have combined participation rate of less than 100%. This hinted to a gap where there are pockets of students not taking either of the tests. The top 5 states lagging behind are: Iowa (69%), Kansas (72%), South Dakota (75%), Alaska (79%) and New Mexico (81%)

  <p align=”center”>
  <img src="./img/Combined SAT + ACT Participations.png" width="1000">
  </p>


4. There seems to be a positive correlation between test participation rate to state policy on administering / offering tests. States with such policies have high participation rates, as can be observed when comparing the chart below to the previous one.

  <p align=”center”>
  <img src="./img/State Policy.png" width="1000">
  </p>


5. Based on 2019 data, 2 states are lagging behind on both SAT and ACT scores, which are Oklahoma and South Carolina. Both the average SAT and ACT scores in these 2 states are lower than 25th percentile in each test.

## Limitations:
1. The participation rate used in analysis is the % against the population of that state. Hence, higher participation rate for ACT on average does not necessarily mean that there are more ACT takers in hard numbers. This is because 500 students may be close to 100% in 1 state but only 10% in another.
2. Analysis into regional differences may not work well for the US, as initiatives and policies are usually mandated at state or national level.

## Conclusion and Recommendations
1. In order to improve either SAT or ACT participation rates, support state-level effort to move towards administering / offering tests to students in their state
2. Allocate effort to improve test participation rates in the following states (in order of decreasing urgency): Iowa, Kansas, South Dakota, Alaska, and New Mexico. This can be done for example by lending a exam fee waiver to students of less-privileged background
3. Focus effort to improve students with struggling test score in Oklahoma and South Carolina.

## Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|All|The state in the US where the data is from. There are 51 states here (50 US states + 1 District of Columbia)|
|sat_participation_rate|float|SAT|How many students in the state takes up SAT, ranging from 0-1 (where 0 means no participation and 1 means full participation)|
|sat_read_write_ave_score|int|SAT|Average of SAT reading + writing score in the state, ranging from 200-800 (higher value means better result)|
|sat_math_ave_score|int|SAT|Average of SAT math score in the state, ranging from 200-800 (higher value means better result)|
|sat_total_score|int|SAT|Total of average SAT reading + writing and math score in the state, ranging from 400-1600 (higher value means better result)|
|act_participation_rate|float|ACT|How many students in the state takes up SAT, ranging from 0-1 (where 0 means no participation and 1 means full participation)|
|act_composite_score|float|ACT|Average score of all ACT subjects in the state, ranging from 1-36 (higher value means better result)|
|region|object|State Region|The region where the state is classifed into, according to US Census Bureau 2010 data (could be 1 of 4 values: West, Midwest, Northeast, South)|
|division|object|State Region|The division where the state is classifed into, according to US Census Bureau 2010 data. This is a further breakdown of the region (could be 1 of 9 values: West South Central, East South Central, Pacific, Mountain, New England, Middle Atlantic, South Atlantic, West North Central, East North Central)|
|sat_administered|object|State Administered|An indicator if the state has a SAT state-administered policy in place (NaN = no policy, "Required" = the state requires students to take SAT test (for free) to graduate, "Offered" = the state offers students the opportunity to take SAT test for free)|
|act_administered|object|State Administered|An indicator if the state has a ACT state-administered policy in place (NaN = no policy, "Required" = the state requires students to take ACT test (for free) to graduate, "Offered" = the state offers students the opportunity to take ACT test for free)|
