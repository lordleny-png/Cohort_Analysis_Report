## Cohort Analysis Report
INTERNSHIP DELIVERABLE · WEEK 02
Cohort Analysis Report
with Visual Insights 

TEAM 02
Leny NAPALA

8,536
RECORDS	16
COHORTS	5
CATEGORIES	14
FIGURES

1 · DATA CLEANING	2 · EDA & VISUALS	3 · INTERPRETATION	4 · MODELING PREP

https://drive.google.com/drive/folders/1kAQToeUu8IArtAiK5VgJatPtSMOHVv3s?usp=share_link
The link above contains all the necessary files for the report.

## 1	Data Cleaning

CONTRIBUTOR: Fatima Jaffar
## 1.1 Data Cleaning
The dataset was reviewed and cleaned before conducting the cohort analysis. The cleaning process focused on improving data consistency while avoiding unsupported assumptions about the original source data.
The following cleaning activities were performed:
●	Reviewed missing, invalid, duplicate, suspicious, and inconsistent records.
●	Validated date fields for missing values, data types, formatting, and inconsistent date relationships.
●	Identified and removed 5 QA/Test records to ensure that test entries did not affect the cohort analysis or participation results.
●	Corrected confirmed date inconsistencies where the Opportunity Start Date and Opportunity End Date had been reversed.
●	Standardized inconsistent institution names and corrected clear spelling and formatting variations.
●	Corrected institution-name inconsistencies such as duplicated words, spelling variations, and unnecessary formatting differences.
●	Institution values that could not be reliably identified, including values that appeared to be email addresses or non-institutional entries, were classified as Non-Specified.
●	Reviewed duplicate records rather than automatically deleting them without verification.
●	Negative date intervals were retained where the underlying cause could not be verified from the available source data. Negative Signup-to-Apply intervals were not manually changed because no reliable source was available to determine which date was incorrect.
The final cleaned dataset used for feature engineering contained 8,536 records.
## 1.2 Feature Engineering
Date-based, demographic, and opportunity-related features were derived from the existing dataset to support both cohort analysis and future predictive modeling.
Derived Features
These features provide additional information that can be used to identify participation patterns and can also serve as potential inputs for the predictive modeling stage.
Feature	Purpose
Signup Year	Identifies yearly learner signup patterns
Signup Month	Identifies monthly signup patterns and cohorts
Signup Day	Captures day-level signup information
Signup Day of Week	Identifies weekly signup patterns
Apply Year	Identifies yearly application patterns
Apply Month	Identifies monthly application patterns
Apply Day	Captures day-level application information
Apply Day of Week	Identifies weekly application patterns
Opportunity Start Month	Identifies the month in which an opportunity starts
Opportunity End Month	Identifies the month in which an opportunity ends
Opportunity Duration Days	Measures the duration of an opportunity
Signup to Apply Days	Measures the time between learner signup and application
Apply to Opportunity Start Days	Measures the time between application and opportunity start
Age	Provides an estimated learner age
Age Group	Groups learners into meaningful age categories

 ## 1.3 Cohort Analysis
## 1.3.1 Cohort Definition
For this analysis, learners were grouped into cohorts based on their Learner Signup Month. For example, learners who signed up during January 2023 were grouped into the 2023-01 cohort, while learners who signed up during January 2024 were grouped into the 2024-01 cohort. This approach allows participation patterns to be compared across different signup periods.
## 1.3.2 Cohort Size
The dataset contained cohorts from January 2023 to April 2024.
The largest cohorts were:
| Period | Number of records|
|---| ---|
| January 2024 |1,546 records |
| February 2024 |1,073 records |
| August 2023 |1,142 records |
| June 2023 |753 records |
| July 2023 |713 records |
| September 2023 |683 records |
| December 2023 |659 records  |


The smallest cohorts were:
| Period | Number of records|
|---|---|
| April 2024 |12 records |
| March 2024 |133 records |
| February 2023 |88 records |


## Key Observation
Learner signup volume increased considerably during 2023 and reached its highest level in January 2024, with 1,546 records. The large cohort sizes during late 2023 and early 2024 indicate a substantial increase in learner activity during this period.
FIGURE 1.3
Learner Cohort Size by Signup Month
 
Takeaway: Shows changes in learner signup volume over time.

## 1.4 Cohort Status Analysis
Learner status was analysed across signup cohorts to understand how learners progressed through the participation process. The overall status distribution was:
Status	Records
Rejected	3,563
Team Allocated	3,271
Started	761
Dropped Out	616
Waitlisted	107
Applied	105
Withdraw	84
Rewards Award	29

Key Observations
The largest status category was Rejected, with 3,563 records, followed closely by Team Allocated, with 3,271 records. The number of learners marked as Started was 761, while 616 learners were recorded as Dropped Out. The relatively small number of Rewards Award records, 29, indicates that this represents a much smaller later-stage outcome compared with the other statuses. The status distribution varied considerably across cohorts. For example, earlier cohorts contained a higher proportion of Started and Team Allocated records, while later cohorts contained a substantially larger number of Rejected records.
FIGURE 1.4
Cohort Month vs Participation Status Heatmap
 
Takeaway: Shows how learner statuses varied across signup cohorts.


## 1.5 Cohort Participation Analysis
For the purpose of this analysis, participation was operationalized using the following statuses:
Started, Team Allocated, Rewards Award
These statuses were selected to represent positive participation or progression within an opportunity.
The resulting cohort participation rates were:

Cohort	Total Records	Participated	Participation Rate
|Date|Number|Percentage|
|--|--|--|
|2023-01|219154|70.32%|
|2023-02|88	64|72.73%|
|2023-03|182	155|	85.16%|
|2023-04|280	186	|66.43%|
|2023-05|	406	284|69.95%|
|2023-06|753	560|74.37%|
|2023-07|713	428|60.03%
|2023-08|1,142	576|50.44%|
|2023-09|683	267|39.09%|
|2023-10|423	210|49.65%|
|2023-11	|224	85|37.95%|
|2023-12	|659	272|41.27%|
|2024-01|1,546	418|27.04%|
|2024-02|1,073	363|33.83%|
2024-03	|133	33|24.81%|
2024-04|12	6	|50.00%|

## Key Findings
The March 2023 cohort recorded the highest participation rate at 85.16%. Other strong-performing early cohorts included June 2023 at 74.37%, February 2023 at 72.73%, and January 2023 at 70.32%. A decline in participation can be observed across the later cohorts. Participation decreased from 60.03% in July 2023 to 50.44% in August, followed by 39.09% in September and 37.95% in November.
The January 2024 cohort had the largest cohort size, with 1,546 records, but its participation rate was only 27.04%. This indicates that a larger number of signups did not necessarily translate into a higher participation rate. The lowest participation rate among the larger cohorts occurred in March 2024 at 24.81%. The April 2024 cohort recorded a 50% participation rate, but it contained only 12 records, so this percentage should not be interpreted as representative of the overall population.

FIGURE 1.5
Participation Rate by Signup Cohort
 
Takeaway: Shows differences in participation rates between signup cohorts and highlights the decline in participation across later cohorts.

## 1.6 Opportunity Category Analysis
Opportunity categories were also compared across learner cohorts.
The categories included:
●	Competition
●	Course
●	Engagement
●	Event
●	Internship
The analysis showed that Internship opportunities represented a particularly large share of participation records in several of the larger cohorts. For example, the January 2024 cohort contained 1,329 Internship records out of 1,546 total records, making Internship the dominant opportunity category for that cohort. Similarly, August 2023 had 790 Internship records out of 1,142 records, while September 2023 had 514 Internship records out of 683 records. Courses were also a major category in several cohorts, particularly January through June 2023.
## Key Observation
The distribution of opportunity categories was not uniform across cohorts. Some cohorts were strongly concentrated in Internship opportunities, while earlier cohorts showed relatively greater representation of Courses. This indicates that opportunity type is an important variable for understanding learner participation patterns.



FIGURE 1.6
Cohort Month vs Opportunity Category Heatmap
 
Takeaway: Shows the distribution of opportunity categories across different learner cohorts.


## 1.7 Key Insights
The cohort analysis produced several important insights:
1. Signup volume increased substantially over time — The largest cohort occurred in January 2024 with 1,546 records, indicating a major increase in learner signup activity compared with early 2023.
2. Larger cohorts did not necessarily have higher participation — Although January 2024 had the highest number of records, its participation rate was only 27.04%. In comparison, March 2023 had only 182 records but achieved an 85.16% participation rate. This suggests that increasing the number of signups alone does not guarantee stronger participation.
3. Early 2023 cohorts generally showed stronger participation — Several early 2023 cohorts recorded participation rates above 65%, while participation generally declined among later cohorts.
4. Opportunity category varied across cohorts — Internships were particularly dominant in several large cohorts, while Courses were more prominent in several earlier cohorts.
5. Status distribution indicates substantial rejection — Rejected records represented the largest overall status category, with 3,563 records. This suggests that there may be an opportunity to investigate the factors associated with rejection and identify ways to improve learner-opportunity matching.
6. Cohort size should be considered when interpreting percentages — Small cohorts, such as April 2024 with only 12 records, can produce unstable percentages. Therefore, participation rates should be interpreted alongside cohort size rather than in isolation.

 
2	Exploratory Data Analysis & Visualisations

CONTRIBUTOR:  Leny Napala
## Executive Summary
This report presents E.D.A and Visualization of Participation Trends of the week 2 workflow. The analysis uses 8,536 records from the refined RIT dataset. Its purpose is to describe participation patterns, identify changes over time, examine early engagement signals, and document remaining anomalies before modeling.
The analysis shows a strong concentration in Internship opportunities (63.4% of records). The most frequent status is Rejected (41.7%). Signup flags provide useful variables for comparing engagement outcomes.
These findings are descriptive. They identify patterns in the available data but do not establish causal relationships.
 Analysis Preparation
The week 2 analysis ready dataset includes the derived variables for EDA. Date fields were parsed with mixed-format handling because the source contains multiple date representations.
●	Date to Apply = Apply Date − Learner SignUp DateTime
●	Opportunity Duration = Opportunity End Date − Opportunity Start Date
●	Weekend Signup Flag = signup occurred on Saturday or Sunday
●	Signup Month and Signup Quarter = extracted from signup datetime
●	Engagement Outcome Flag = Positive (Started/Team Allocated), Negative (Rejected/Dropped Out/Withdraw), or Other.
●	Applied, Waitlisted and Rewards Awards were retained as Other rather than being forced into Positive or Negative.
Participation Distribution
Internship is the largest opportunity category with 5,413 records (63.4%). The most frequent status is rejected with 3,563 records (41.7%). The largest country group is United States with 3,976 records (46.6%).
## 2.1 Opportunity Category Distribution
Category	Count	Percentage
Internship	5,413	63.4%
Course	2,024	23.7%
Event	545	6.4%
Competition	425	5.0%
Engagement	129	1.5%

Internship and Course make up 87% of all signups. These two are the main categories people join. Event, Competition, and Engagement are much smaller and less popular in comparison.
## 2.2 Participation Status Distribution
Status	Count	Percentage
Rejected	3,563	41.7%
Team Allocated	3,271	38.3%
Started	761	8.9%
Dropped Out	616	7.2%
Waitlisted	107	1.3%

Most records end up as either Rejected or Team Allocated — together that's 80% of everyone. But even after someone gets allocated, some still drop out or withdraw later, so getting accepted doesn't always mean they stay engaged.
## 2.3 Participation Overtime
Signup volume varies across the observation period. The highest monthly volume is 1,546 signups in 2024-01, while the lowest is 12 in 2024-04. The category-level trend should be used to determine whether these changes are concentrated in a particular opportunity type.
## 2.4 Early Engagement Signals
The Positive outcome group has an average Days to Apply of 53.96 days, compared with 57.57 days for the Negative group.
Average Opportunity Duration is 323.80 days for Positive outcomes and 70.57 days for Negative outcomes. Missing start dates limit interpretation of this measure.
2.5 Anomalies
●	Negative Days to Apply: 101 records.
●	Negative Opportunity Duration: 0 records.
●	Unusual Age (<15 or >70): 50 records.
●	Missing Opportunity Start Date: 3,785 records.
●	Missing Current/Intended Major: 5 records.
Negative date-derived values should be flagged or excluded from relevant visual analyses according to the team's documented data-quality decision.
## 2.6 Quarterly Trend Analysis
Among complete quarters, the highest volume occurred in 2024 Q1 (2,752 signups) and the lowest in 2023 Q1 (489 signups); 2024 Q2 is excluded from this comparison since it contains only 12 records due to a data-extraction cutoff, not a genuine drop in signups. Because the dataset does not yet include a full second year, the only directly comparable year-over-year period is Q1: signups grew from 489 in 2023 to 2,752 in 2024, a roughly 5.6x increase. This should be read as a single-quarter comparison rather than evidence of a sustained annual trend, since 2024 Q2–Q4 are not yet represented in the data.


Visualizations
FIGURE 1
Signup Distribution by Opportunity Category
 
Takeaway: Internship opportunities account for the largest share of participation

FIGURE 2
Participation Status Distribution
 
Takeaway: Rejected and Team Allocated are the two largest status groups.

FIGURE 3
Monthly Signup Volume
 
Takeaway: Signup intensity varies substantially across months

FIGURE 4
Monthly Signups by Opportunity Category
 Takeaway: Category-level trends helps identify whether overall changes are category-driven

FIGURE 5
Quarterly Signup Volume
 
Takeaway: Signups grew steadily through 2023 and peaked in 2024 Q1 at 2,752 signups; 2024 Q2 contains only 12 records due to a data-extraction cutoff and is excluded from trend comparisons

FIGURE 6
Quarterly Signups by Opportunities Category
 Takeaway: Internship opportunities consistently account for the largest share of quarterly signups, while the other categories contribute considerably fewer participants

 FIGURE 7
Day of Week x Opportunity Heatmap
 
Takeaway: The heatmap highlights combinations of signup day and category with higher participation

FIGURE 8
Days to Apply by Engagement Outcome
 
Takeaway: Application timing distributions can be compared across the outcome groups

FIGURE 9
Opportunity Duration by Engagement Outcome
 
Takeaway: Opportunity duration differs across outcome groups and should be interpreted with category

FIGURE 10
Weekend Signup by Engagement Outcome
 
Takeaway: The chart compares outcome composition for weekend and non-weekend signups.

 
## 3	Interpretation of findings

CONTRIBUTOR:  Sumiyya Zahoor
This section pulls the per-table and per-figure interpretations above into one place, draws out the difference between a learner's individual outcome and an opportunity's overall engagement quality, and summarizes which factors matter most.
Interpretation Figure 1
Internship has way more signups than any other category. Participation isn't spread out evenly — it's mostly Internship.
Interpretation Figure 2
This chart shows the same thing as the status table: most records fall into just two outcomes — Rejected or Team Allocated. Everything else is much smaller.
Interpretation Figure 3
Signups generally went up from early 2023, hit a high point of 1,546 in January 2024, then dropped sharply to just 12 by April 2024. This could mean signups follow a seasonal pattern, or it could just mean the data collection stopped around then — it's worth checking against the category breakdown before assuming interest is dropping.
Interpretation Figure 4
When we break the monthly numbers down by category, Internship is what's causing most of the ups and downs in the overall trend. Course changes more gently, and the other categories stay low the whole time.
Interpretation Figure 5
Looking at the numbers by quarter instead of by month shows the same pattern: signups grew through 2023 and peaked in 2024 Q1 at 2,752 signups — the highest quarter on record. 2024 Q2 shows only 12 records, but this reflects a data-extraction cutoff rather than an actual drop in signups, so it's excluded from quarter-over-quarter comparisons.
Interpretation Figure 6
Internship has the most signups in every single quarter, not just on average. This shows Internship's popularity is steady and consistent, not a one-time fluke.
Interpretation Figure 7
Internship gets the most signups every day, with a bit more activity around Thursday. Course follows a similar but smaller pattern. The other categories stay low no matter what day it is — so the day of the week mostly matters for the two biggest categories.


Interpretation Figure 8
People with a Positive outcome applied in about 54 days on average, and people with a Negative outcome took about 58 days — not a big difference. Most people in both groups actually applied pretty quickly; it's just a few slow outliers pulling the averages up.
Interpretation Figure 9
This is the clearest difference in the whole report: people with Negative outcomes were tied to short opportunities (around 70 days), while people with Positive outcomes were tied to much longer ones (around 324 days). So longer opportunities seem linked to better outcomes — but a lot of start dates are missing, so this isn't 100% certain.
Interpretation Figure 10
Whether someone signs up on a weekday or a weekend doesn't really matter , the mix of Positive and Negative outcomes is almost exactly the same either way.
3.1 Learner-Level Outcomes vs. Opportunity-Level Engagement Quality
●	Learner-level outcome: what happened to one individual signup, captured by the Engagement Outcome Flag ,Positive (Started/Team Allocated), Negative (Rejected/Dropped Out/Withdraw), or Other (Applied/Waitlisted/Rewards Award). This is the lens used in Figures 8-10.
●	Opportunity-level engagement quality: how a whole category or opportunity type performs in aggregate, its total signup volume, how steadily it draws participation month over month and quarter over quarter (Figures 3-6), and how long its typical opportunities run. This is a structural view of the opportunity, not a per-learner view.
●	These two lenses do not automatically agree. Internship has by far the highest signup volume and the steadiest category-level presence (Table 2.1, Figures 1, 4, 6), which is a strong result at the opportunity level  but high volume alone does not tell us whether individual learners in that category were more likely to reach a Positive outcome. The one link the current data provides between the two lenses is Opportunity Duration (Figure 9): Positive outcomes are tied to much longer typical durations (323.80 days) than Negative outcomes (70.57 days), so duration is, so far, the clearest bridge between an opportunity-level property and a learner-level result.
●	Caveat: the dataset does not currently include a direct category-by-outcome breakdown, so it cannot yet be confirmed whether Internship (the highest-volume category) is also the category with the best per-learner success rate, or simply the one with the most signups. A category x outcome cross-tab would be a natural next step.

## 3.2 Signals for High- and Low-Engagement Opportunities
●	Strong-engagement signal: a long-expected opportunity duration. This is the most consistent marker of eventual Positive engagement observed in the data (Figure 9).
●	Strong-engagement signal: belonging to the Internship or Course categories, since these hold both the largest signup volume and the steadiest month-to-month and quarter-to-quarter presence (Figures 4, 6) , a sign of durable rather than one-off participation.
●	Weak-engagement signal: a short, tightly clustered opportunity duration, which is the pattern most associated with Negative outcomes (Figure 9).
●	Non-signal: signing up on a weekend versus a weekday. The outcome mix is nearly identical either way (Figure 10), so this feature does not separate high- from low-engagement cases.
●	Weak/inconsistent signal: Days to Apply. Positive (53.96 days) and Negative (57.57 days) outcomes have close means and heavily overlapping distributions (Figure 8), so this should be treated as a secondary rather than primary early-warning feature.
3.3 Summary of Strongly Influential Factors
●	Strongest: Opportunity Duration. It produces the clearest, most consistent separation between Positive and Negative learner outcomes of any feature examined.
●	Second: Opportunity Category. Internship and Course dominance is the strongest driver of overall participation volume and the main source of month-to-month and quarter-to-quarter movement in total signups, though it is not yet confirmed as a driver of individual learner success.
●	Weak: Days to Apply. Only a small difference in means between outcome groups, with heavily overlapping distributions.
●	Negligible: Weekend Signup Flag. No meaningful difference in outcome composition between weekday and weekend signups.
Overall, opportunity duration is the strongest lever tied to a positive individual outcome, while opportunity category is the strongest lever tied to overall participation volume — these are two different kinds of "success" and should not be conflated. Timing-related features (Days to Apply, Weekend Signup Flag) are, at most, secondary signals. As noted throughout this report, these are descriptive associations, not confirmed causal drivers, and the duration-based findings in particular should be read alongside the large number of missing Opportunity Start Dates (3,785 records) documented under Anomalies.













## 4	Preparation for Modeling

CONTRIBUTOR: Angel Wambui
Is the Dataset Ready for Modeling?
Mostly yes, with a few things to sort out first. The dataset has been cleaned, key derived features are already built, and a clear target variable exists. That said, there are a handful of anomalies flagged during EDA that should be resolved or explicitly excluded before moving into Week 3, rather than being carried forward silently.
What's Already in Good Shape
●	A usable target variable exists: Engagement Outcome Flag, grouping records into Positive (Started/Team Allocated), Negative (Rejected/Dropped Out/Withdraw), and Other (Applied/Waitlisted/Rewards Award). This gives modeling a clear classification problem to work with.
●	Several useful derived features are already available: Days to Apply, Opportunity Duration, Weekend Signup Flag, Signup Month, and Signup Quarter.
●	Core categorical fields (Opportunity Category, Gender, Country, Status Description) are consistent enough to be encoded for modeling without major rework.
What Needs to Be Resolved First
●	101 records have a negative Days to Apply value, meaning the apply date comes before the signup date. This isn't possible and points to a data entry issue — these should be flagged and excluded from training rather than left in as-is.
●	50 records have an unusual age (under 15 or over 70). These are worth a quick manual check — a few may be genuine, but this range is unusual enough to double-check before trusting Age as a feature.
●	3,785 records are missing Opportunity Start Date, which limits how reliable Opportunity Duration is as a feature. Rather than dropping Opportunity Duration altogether, it may be worth keeping it for the ~56% of records that do have it, and adding a separate 'Has Start Date' flag so the model can account for the gap rather than being misled by it.
●	5 records are missing Current/Intended Major. This is a small enough number that these rows can either be dropped or the field simply left blank/'Unknown' without meaningfully affecting the model.

## Features Most Useful for Modeling
Based on the Phase 2–4 findings, some features carry far more signal than others though it's worth separating two different questions the data answers: what drives overall participation volume, versus what predicts an individual learner's outcome. These aren't always the same thing.

## Feature	Why it matters
Opportunity Duration	The strongest signal found so far, and the clearest bridge between an opportunity-level property and a learner-level result — Positive outcomes average 324 days vs. 70 days for Negative outcomes. Worth prioritizing, with the missing-data caveat noted above.
Opportunity Category	Internship and Course dominate overall signup volume (87% combined) and drive most of the month-to-month movement, but this is a volume signal, not a confirmed learner-outcome signal. It is not yet known whether Internship also has the best per-learner success rate, or simply the most signups. A category × outcome cross-tab (comparing Positive/Negative/Other rates within each category) should be run before treating Category as a strong predictive feature.
Days to Apply	A weak signal on its own (54 vs. 58 days between outcome groups, with heavily overlapping distributions), but may still add value combined with other features rather than used alone.
Weekend Signup Flag	Negligible outcome mix is nearly identical for weekend vs. weekday signups, so this feature is unlikely to add predictive value by itself.
Signup Month / Quarter	Useful for capturing the seasonal spike seen around January 2024, though this should be checked against category breakdowns first in case it's driven mainly by Internship signups rather than a genuine seasonal pattern.
Country	United States accounts for close to half of all records (46.6%), so this field is heavily imbalanced and may need grouping (e.g., top 5 countries + 'Other') before use.

## Forecasting Signals
Two variables carry the clearest signal for future forecasting work. Signup Quarter is the strongest candidate seasonal indicator once a second full year of data becomes available, given the growth observed across the one directly comparable period (see 2.6). Opportunity Category interacts with this seasonality: Internship drives most of the quarter-to-quarter movement (122 to 1,715 to 2,103 records across 2023 Q1, 2023 Q3, and 2024 Q1), while Course stays comparatively flat. A forecasting model may need to treat Internship's seasonal pattern separately rather than forecasting total volume as a single series.
Key observation for future modeling: the dataset currently spans only one directly comparable quarter across both years, so quarter-specific seasonal forecasts should be treated as provisional until at least one more full year of data has been collected.

## Recommended Step Before Modeling Begins
Phase 4 flagged that the dataset does not yet include a direct category-by-outcome breakdown, meaning it's still unconfirmed whether Internship's high signup volume translates into better individual learner outcomes. Building this cross-tab (Opportunity Category × Engagement Outcome) before Week 3 would clarify whether Category should be treated as a meaningful predictive feature or mainly as a volume/context variable.
## Summary
The dataset is close to modeling-ready. The target variable and most derived features are already in place, and the strongest early signal Opportunity Duration has been clearly identified. Opportunity Category drives overall participation volume, but its link to individual learner outcomes is still unconfirmed, so a category × outcome cross-tab is recommended before Week 3. The negative Days to Apply values and unusual ages should also be cleaned up or excluded, and a decision made on how to handle the missing Opportunity Start Date values so they don't distort the model rather than inform it.

Formatted, consolidated, and cross-checked by Team Lead: Soman Saleem  
All the content is generated by team members independently.

