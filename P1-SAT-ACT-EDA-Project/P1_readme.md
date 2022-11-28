# Project 1: SAT/ACT Score EDA through Pandemic
#### Exploring the changes in standardised testing through the pandemic years (2020 and 2021) and observing its impacts through a couple of lenses

In the past year, articles like this one from [Forbes](https://www.forbes.com/sites/michaeltnietzel/2021/10/13/the-number-of-students-taking-the-act-dropped-22-this-year/?sh=664f37f7c60a) have aluded to a greater movement of colleges away from requiring standardised testing as part of their assessment criteria, quite possibly catalysed by the constraints brought along by the global COVID pandemic.

This EDA project will focus on the following:
1. To look at the scores and participation rates directly - to observe the trends of their development and fluctuation to both localised and external factors over the years. This will largely focus on the 2017 to 2021 mean scores and participation rates, sorted by state; the latter two years of which as a proxy to COVID pandemic-related geopolitical effects.  

2. Extrapolate and explore other possible correlated metrics that may highlight a <b><i>disparity in impact</i></b> in some way on some states rather than others. Whilst there are many parameters and socio-political factors to choose from, this project will focus on i) <b>State Government Affiliation</b> (that is to say, which one of th bi-partisan parties control the politics in a given state), and ii) <b>population demographic</b> in any given state.

## Results and Conclusions
### Part 1.1: SAT Scores
Whilst 2019 and 2020 were fairly close in their distribution of SAT participation, and 2017 and 2018 show similar behaviour too, the participation of SAT presents a significant decrease in 2021.

Another observation is that prior to 2021, the trend of participation was actually going up, peaking in 2020, followed by a significant decrease of 2021 participation rates.

### Part 1.2: ACT Scores
Just like the graph for the <i>SAT participation</i>, we notice a similar impact to ACT participation - a shift to the left in the participation rate for ACT tests in year 2021 compared to previous years.

The differences in movement between years (that is, quantifying the <i>change</i> in participation over each year) also supports this narrative - showing significant consistency from years 2017 to 2020, and showing a significant negative movement in 2021.

To support these claims numerically, two tests were conducted, namely:
1. ANOVA on the means of 2017 to 2020, to test whether the means of the 4 years remained consistent, and;
2. T-test for year 2021 against the other 4 years, to test whether 2021 truly had statistically deviated from the norm set by the previos 4 years.

The aforementioned statistical tests support our conjectures (at a 5% significance level), that:
1. The participation rates of 2017 - 2020 remained statistically unchanged, and;
2. The 2021 participation rates saw a significant change (decrease), compared to previous years.

There could be a couple of reasons for this (not limited to):
1. During the initial part of the pandemic, there was some legislation which improved the average candidates ability (be it through material or exam fee subsidy) to sit for the SATs;
2. From 2020 through to 2022, there was a shift in thinking from a lot of colleges about whether standardised testing was even necessary. This led to huge shift in requirements in the education industry in America, with many colleges moving away from requiring SAT or ACT scores for admission, though they were still optional and used if available.

### Part 1.3: Quick look at correlation of mean scores and participation
It would seem that there is some correlation between mean and participation rate; that is, the low the overall participation rate, the higher the average mean score is in that state. The effect seems to be more pronounced for the SATs than ACTs.

This is probably indication of some form of 'survivorship bias', whereby as you go through from a larger pool of candidates to a smaller pool, the people left in the pool are more likely to be more motivated, more driven, and generally more capable to get better test scores, the effect of which would be interesting to explore in the future. These insights however, are outside the scope of this exploratory analysis.

### Part 2: Mapping Other Factors and Studying Correlation
### Part 2.1: Looking at State-Government Affiliation
Year-on-year, we do not immediately notice any hard trends in the data. If anything, the states seem all over the place, with a bit of clustering. What does stand out however, is the following couple of observations:

1. There seems to be some bias when it comes to which test a state seems to favour, and its political affiliation at the time. Republican-trifecta states tend to favour the ACT standardised test (to some extent), whilst the Democratic-trifecta states seem to favour the SAT standardised test.
2. If we compare 2021 to the other years, we do notice a significant shift in the distribution towards less participation overall, aligning with our understanding from the Forbes article.

Looking more closely at the participation rates of each bi-partisan affiliation in isolation, the clustering of bias towards each test, that is ACT for Republican states and SAT for Democratic states, become more prominent. Its important to point out, though, that there is also significant scattering <i>not in</i> the extreme clusters of high/low ACT/SAT participation for Republican states, and low/high ACT/SAT participation for Democratic states.

By looking at the correlations between affiliation and SAT/ACT participation, our conjectures are somewhat confirmed, with a 39%/-30% correlation of Republican states towards ACT/SAT participation respectively, and a -42%/36% correlation for ACT/SAT participation for Democratic states.

This is strong evidence that, while not significant enough to be a powerful indicator, the affiliation of the state-government does perhaps reflect the intrinsic attitude of the underlying population; that a population likely to vote in a Republican government would also favour the ACT over the SAT, and vice versa.

Curiously, when comparing mean scores within state-government affiliation, we notice that the correlation we observed in 1.3 holds true, that on average Republican states had better mean scores in SAT than ACT, and the opposite for Democratic States.

### Part 2.2: Looking at Population Demographics (by race)
Initially I was thinking of using a catergorical assignment of race to the existing scatterplot of mean vs participation. However, plotting simply a "White vs x" format may not be useful in America's case, since there are only two states that have a non-white majority. Thus we will need to find another reasonable split in order to make any meaningful findings.

Much to my surprise, by looking at the correlations of score to population race proportions, there does not seem to be much of a relationship between the proportions of racial demographic in a given state, and its participation rates or mean scores in the ACTs. This relationship seems to be the same for the SATs as well.

Looking at the correlation plots for the demographic proportions to mean scores and participation rates of the two standardised tests, we can probably conclude that these metrics are not very related, since they have < 50% correlation (even <25%) in relation to test scores.

With correlation scores like these it informs us that any other investigation into the population demographic spread with regards to the standardised test scores would be quite redundant.

### Part 3: Conclusions
From the study we have conducted, we can conduct a few things about the state of standardised tests following the pandemic:
1. The data does seem to support the conjecture that standardised testing participation rates are on the fall, and we may very well be witnessing the start of the end for standardised tests as a cornerstone of educational gatekeeping to colleges moving forward.

2. In the future, because of the shift to less participation (arguably indicating a shift towards a more optional mindset), there seems to be a preference within communities towards either one of the available tests, should a candidate decide to take them. This preference too seems somewhat linked to party-alignment, which would also be correlated to the state-government affiliation at the policy-making level.

3. Whilst there may still be disproportionate demographical effects at play, high-level racial population proportion is not a good proxy for inferring any useful information about the SAT/ACTs.

### Part 3.1: Limitations
- There are countless other dimensions of which we can analyse the effects of COVID and changing industry sentiments towards standardised testing, and in this EDA we have just looked at a couple.

- As educational policies evolve over time, some of the factors discussed may or may not become relevant. Perhaps even, there is even a chance that standardised tests as we know it would be phased out entirely, making any analysis on the current system obselete, or at least redundant.