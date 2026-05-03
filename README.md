# Power BI Project: School Accountability Analysis

## 1. Project Objective 🎯

The objective of this project is to clean, transform, and analyze the School Year 2022-2023 Statewide Accountability Ratings dataset to extract actionable insights regarding educational performance across various districts.

This mini project performs real-world environmental data analysis using:

- **Microsoft Excel** for data cleaning and transformation
- **Power BI** for interactive dashboard creation and insight generation

### Primary Goals 🎯

1. **Data Refinement & Standardization** - Clean the raw statewide data by removing duplicates, handling missing values (such as "Not Rated"), and ensuring numerical fields like enrollment and scores are in the correct format for calculation.

2. **Performance Categorization** - Implement logic-based "IF" columns to segment districts based on socioeconomic factors and academic success, allowing clear distinction between "High Performing" schools and those needing support.

3. **Socioeconomic Impact Analysis** - Create calculated fields to determine the actual number of Economically Disadvantaged and EB/EL (Emergent Bilingual/English Learner) students, rather than relying solely on percentages.

4. **Operational Insights** - Develop interactive summaries (Pivot Tables) to compare performance metrics such as Average Overall Scores and Student Achievement across different regions and school types.

5. **Professional Visualization** - Design a professional-grade dashboard that enables stakeholders to filter data by region or rating, providing a high-level view of the state's educational health.

By achieving these objectives, the project transforms raw administrative data into a structured analytical tool that identifies the relationship between student demographics and academic outcomes.

---

## 2. Data Sources 📦

**Source:** Texas Education Agency (TEA) - School Year 2022-2023 Accountability Ratings

- **Size:** 10,253 records across 39 feature columns
- **Reference:** [Data source link](https://discord.com/channels/1454334800264695962/1456958759665664152/1488586764854759454)

---

## 3. Statement of the Problem 

Statewide accountability data is often released in massive, complex datasets that are difficult for educators, administrators, and stakeholders to interpret in their raw form. Without proper data cleaning and transformation, several key issues arise:

### Key Issues 

1. **Data Complexity & Noise** - Raw datasets contain thousands of rows with inconsistent formatting, missing values (e.g., "Not Rated" or "."), and redundant information that obscures actual performance trends.

2. **Lack of Actionable Metrics** - Standard reports provide percentages (e.g., % Economically Disadvantaged), but lack specific headcounts and categorical groupings (such as "High Poverty" vs. "Low Poverty") required to allocate resources or identify student needs effectively.

3. **Fragmented Performance Views** - Difficult to identify the relationship between a school's socioeconomic status and academic success (Overall Rating) without custom logical grouping and calculated fields.

4. **Absence of Visual Clarity** - Static spreadsheets do not allow dynamic filtering needed to compare different regions (e.g., Kilgore vs. San Antonio) or school types, making it hard to identify underperforming districts.

### The Goal 🎯

By addressing these problems through data cleaning and calculated "IF" columns, this project transforms a "noisy" administrative file into a functional analytical tool. This enables stakeholders to move from simply viewing data to understanding the specific factors influencing school accountability ratings.

---

## 4. Entity & Geographic Attributes 🧭

These columns identify the school district and its administrative location within the state system.

| Attribute Name | Data Type | Description |
|---|---|---|
| District | Text | The name of the school district (e.g., Cayuga ISD) |
| Code | Text | The classification code for the district (e.g., ISD) |
| District Code | Numeric | Unique legislative identification number for the district |
| Region Code | Numeric | The Education Service Center (ESC) region number (1–20) |
| Region City | Text | The city where the regional administrative office is located |
| County | Text | The Texas county where the district resides |
| School Type | Text | The level of the entity (e.g., District, Elementary, High School) |

### Socioeconomic & Demographic Attributes 📊

These features describe the student population and are used to calculate the impact of poverty and language barriers on school success.

| Attribute Name | Data Type | Description |
|---|---|---|
| Number of Students | Numeric | Total student enrollment for the academic year |
| % Econ. Disadvantaged | Percentage | The portion of students eligible for free or reduced-price lunch |
| % EB/EL Students | Percentage | The portion of Emergent Bilingual or English Learner students |
| Econ Disadv Count | Numeric | (Calculated) The estimated total number of economically disadvantaged students |
| EB/EL Count | Numeric | (Calculated) The estimated total number of students requiring language support |
| Poverty Status | Text | (Logical IF) Categorizes districts as "High Poverty" (>60%) or "Low Poverty" (≤60%) |

### Performance & Accountability Attributes 📌

These attributes represent the core ratings and scores assigned by the Texas Education Agency.

| Attribute Name | Data Type | Description |
|---|---|---|
| Overall Score | Numeric | A scaled score (0–100) combining all performance domains |
| Overall Rating | Text | The letter grade (A, B, C, D, or F) assigned based on the Overall Score |
| Student Achievement | Rating/Score | Measures STAAR results, graduation rates, and college/career readiness |
| School Progress | Rating/Score | Evaluates academic growth and performance relative to similar schools |
| Closing the Gaps | Rating/Score | Measures how well the school supports specific student subgroups |
| Performance Level | Text | (Logical IF) Classifies districts as "High Performing" (A/B) or "Needs Improvement" (C/D/F) |
| Postsecondary Readiness | Text | Indicates if the district earned a distinction for preparing students for life after high school |

---

## 5. Tools & Technologies 🛠️

### Microsoft Excel 🧮
- Data Cleaning
- Data Transformation
  - Removing duplicates
  - Handling missing values
  - Standardizing formats
  - Conditional Formatting
  - Pivot tables

### Power BI 📊
- Data modelling
- DAX calculations
- Interactive dashboard creation
- Risk categorization
- KPI computation
- Drill-down analysis

---

## 6. Technical Stack: Microsoft Excel 🧪

Excel served as the primary engine for data engineering and initial analytics. The following workflows were implemented to transform the raw TEA (Texas Education Agency) data into a structured format.

### 6.Data Cleaning 🧹

The first phase involved auditing the raw dataset to ensure integrity and consistency.

- **Removing Duplicates** - Scanned the dataset for redundant entries, particularly focusing on District Code to ensure each administrative entity was represented only once.

- **Handling Missing Values** - Addressed null entries and placeholder characters (like "." or "Not Rated"). Numerical gaps were handled to prevent calculation errors, while categorical gaps were standardized to "N/A" or "Unrated" for clarity.

- **Standardizing Formats** - Converted columns to appropriate data types—ensuring student counts are integers, scores are decimals/numbers, and regional codes maintain leading zeros where necessary.

### 7. Data Transformation 🔄

Advanced features were used to create new intelligence from existing attributes.

- **Calculated Columns** - Leveraged arithmetic formulas to derive student headcounts (Econ Disadv Count, EB/EL Count) from total enrollment and percentage data.

- **Logical "IF" Functions** - Implemented conditional logic to segment data into actionable categories:
  - Poverty Status: "High Poverty" or "Low Poverty"
  - Performance Level: "High Performing" or "Needs Improvement"

### 8. Data Analysis & Visualization 📈

- **Pivot Tables** - Generated multi-dimensional summaries to aggregate performance scores by Region City and Poverty Status, allowing comparison of average scores across different geographic areas.

- **Conditional Formatting** - Applied color scales (Green-Yellow-Red) to Economically Disadvantaged and EB/EL Students percentages, highlighting specific "High Performing" districts using rule-based formatting to make outliers immediately visible.

- **Slicers & Filters** - Integrated interactive slicers into the final sheet, allowing users to dynamically filter the entire dataset by County or School Type without modifying the underlying formulas.

---

## 9. Data Model Architecture 🧱

For the accountability project, the model follows a **Star Schema** approach, where the cleaned accountability data acts as the primary table, supported by lookups for regions and counties.

A robust data model ensures that when you filter by a "Region City," all related charts update instantly and accurately.

### 1. Relationship Management 🔗

- **One-to-Many (1:\*)** - A relationship where a single record in a lookup table (like a list of all 20 Regions) relates to many records in the fact table (the hundreds of school districts in those regions).

- **Directionality** - Relationships are set to "Single" direction to ensure data flows from your filters (Slicers) down to your results.

### 2. Fact and Dimension Tables 🗂️

- **Fact Table** - "Fact Accountability Data" containing all the performance scores, ratings, and student counts.

- **Dimension Tables** - Supporting tables that contain unique lists of attributes, such as a dedicated "Region" table.

---

## 10. DAX (Data Analysis Expressions) 🧠

DAX is the formula language used in Power BI to create custom calculations. Unlike standard Excel formulas, DAX is designed to work over entire tables and respond to report filters.

For this project, the following DAX measures were implemented to drive the dashboard:

### 1. Basic Aggregations ➕

These measures provide the "Big Numbers" (Cards) at the top of your dashboard.

- **Total Students** - Sum of all students across selected districts
- **Average Overall Score** - Mean performance score providing a benchmark for comparison

### 2. Calculated Measures (Logic-Based) 🧠

These measures allow for dynamic counting of schools based on their performance.

- **High Performing Count** - Number of districts achieving A/B ratings

### 3. Advanced Context DAX 🔍

Useful for comparing a specific district's performance against the state average.

- **% of Total Enrollment** - District enrollment as percentage of state total

---

## 10. Dashboard Overview 📊
<img width="546" height="344" alt="Screenshot_20260503_175239_Chrome" src="https://github.com/user-attachments/assets/7e9b35fc-1031-4a82-8a7a-643f61504de7" />

The dashboard is designed with a hierarchical flow: starting with high-level Key Performance Indicators (KPIs) at the top, followed by Geographic and Categorical distributions, and concluding with Correlation Analysis to explore the "why" behind the numbers.

### 1. Key Performance Indicators (KPI Cards) 🧾

The top of the report features dynamic cards that provide an immediate summary of the state's educational landscape. These numbers update automatically as users apply filters.

- **Total Enrollment** - A summation of all students across the selected districts
- **Average Overall Score** - The mean performance score, providing a benchmark for comparison
- **% High Performing** - The percentage of districts that achieved an 'A' or 'B' rating

### 2. Geographic Distribution (Map Visual) 🗺️

Using the County and Region City attributes, a map visualizes performance across Texas.

- **Logic** - Bubbles are sized by Number of Students and colored by Overall Rating
- **Insight** - Identifies if certain regions (e.g., urban vs. rural) are disproportionately struggling or succeeding

### 3. Performance Segmentation (Bar & Donut Charts) 📊

To understand the "grade" distribution, categorical charts are used:

- **Rating Distribution (Donut Chart)** - Shows the percentage of districts falling into each grade category (A, B, C, D, F)
- **Regional Comparison (Clustered Bar Chart)** - Compares the Average Overall Score across different Education Service Centers (ESCs), highlighting which regional offices are seeing the best student outcomes

### 4. Correlation Analysis (Scatter Plot) 📉

One of the most critical views in the report is the relationship between socioeconomic factors and academic results.

- **X-Axis** - % Economically Disadvantaged
- **Y-Axis** - Overall Score
- **Trend Line** - A linear regression line is added to visualize the correlation
- **Insight** - Typically reveals the "Achievement Gap," showing how higher poverty levels often correlate with lower accountability scores, prompting discussions on resource allocation

### 5. Regional Performance Comparison (Column Chart) 🌍

The column chart compares Average Overall Scores across different administrative entities.

- **X-Axis (or Y-Axis for Bar)** - Education Service Centers (ESCs) or Region Cities (e.g., Kilgore vs. San Antonio)
- **Values** - The mean Overall Score, providing a benchmark for regional health
- **Insight** - Highlights which regional offices are seeing the best student outcomes and which are facing more significant challenges

### 6. Interactive Features (Slicers & Cross-Filtering) 🧩

The true power of the analysis lies in its interactivity:

- **Slicers** - Users can filter the entire report by Region, School Type (District vs. Campus), or Poverty Status (High vs. Low)
- **Cross-Highlighting** - Clicking on the "F" segment in the Donut Chart instantly filters the map and scatter plot to show only those failing districts, allowing for rapid root-cause analysis

### 11. Summary of Insights Derived 📝

- **Equity Gaps** - Data clearly visualizes the impact of economic status on performance levels
- **Regional Excellence** - Identification of specific regions that are "beating the odds" (High Poverty but High Performing)
- **Scale of Impact** - By using calculated Econ Disadv Count, administrators can see not just percentages, but the actual number of students affected by performance fluctuations

---

## 12. Descriptive Analysis 🔍

The Descriptive Analysis and Insights & Conclusions sections provide a data-driven summary of the 2022-2023 Texas accountability landscape, highlighting performance trends and the impact of socioeconomic factors.

The descriptive analysis provides a snapshot of the dataset's central tendencies and distributions. For the 1,208 school districts analyzed, the following metrics were observed:

### * Key Summary Statistics 📌

- **Average Overall Score** - The statewide mean score is 78.03, indicating a "C" to "B" average performance across Texas
- **Enrollment Scale** - Student populations vary significantly, ranging from small rural districts (8 students) to massive urban centers (nearly 190,000 students), with a mean enrollment of 4,556
- **Economic Landscape** - On average, 61.6% of students are classified as economically disadvantaged, highlighting the broad necessity for poverty-aligned educational support

### * Rating Distribution 📊

The state's accountability grades follow a bell-curve distribution centered on a "B" rating:

- **Grade A** - 10.6% (Top Tier Performance)
- **Grade B** - 39.7% (High Performing)
- **Grade C** - 31.6% (Moderate Performance)
- **Grade D** - 13.9% (Needs Improvement)
- **Grade F** - 3.4% (Academically Unacceptable)

---

## 11. Insights & Conclusions 💡

### 1. The Poverty-Performance Correlation 📈

There is a statistically significant gap in performance based on economic status. The Low Poverty districts (≤60% disadvantaged) maintain an average score of 82.8, while High Poverty districts (>60% disadvantaged) average 74.5. This 8.3-point disparity confirms that socioeconomic challenges continue to be a primary predictor of academic scores.

### 2. Identifying "Resilient" Districts 🌟

A critical insight from the data is the presence of "Resilient" districts. Despite the overall trend, 36.2% of High Poverty districts managed to achieve a High Performing (A or B) rating. These districts serve as vital benchmarks for success, proving that effective leadership and instructional strategies can overcome economic barriers.

### 3. Regional Performance Disparities 🌍

Geographic location plays a role in district outcomes. Regions centered in Wichita Falls (Avg: 83.2) and Lubbock (Avg: 82.0) lead the state in average accountability scores. Conversely, large metropolitan regions like San Antonio (Avg: 72.4) and Austin (Avg: 74.2) face more significant challenges in lifting aggregate performance levels.

### 4. Impact of the EB/EL Population 🗣️

Districts with high percentages of Emergent Bilingual (EB) students often show lower "Student Achievement" scores but higher "School Progress" scores. This suggests that while these students may start further behind, the districts are successfully demonstrating high levels of individual student growth over time.

### ** Summary 🧾

The analysis reveals that while the Texas education system is generally healthy (with over 50% of districts earning an A or B), there remains a systemic achievement gap linked to poverty. Future resource allocation and policy interventions should focus on the 36.2% of resilient high-poverty districts to replicate their models in lower-performing areas. The use of Power BI and Excel in this project has successfully converted stagnant administrative data into a dynamic roadmap for educational improvement.

---

## 13. Diagnostic Analysis 🩺

While Descriptive Analysis tells us what the data looks like, Diagnostic Analysis explores the **why** behind the results. In this project, we investigated the underlying factors and correlations that influence district accountability scores.

### * Correlation Analysis: The Impact of Poverty 📉

A primary goal was to diagnose the relationship between student demographics and performance scores.

- **Correlation Coefficient** - There is a negative correlation of -0.43 between % Economically Disadvantaged and the Overall Score
- **The "Why"** - This statistical diagnostic confirms that as the concentration of poverty increases, the accountability score tends to decrease. This suggests that the "Achievement Gap" is not just a perception but a systemic reality in the dataset, likely driven by differences in access to external resources, tutoring, and stable home environments

### * The EB/EL Resilience Factor 💪

Interestingly, the diagnostic revealed a very weak correlation (-0.11) between the percentage of EB/EL (Emergent Bilingual) students and the Overall Score.

- **Insight** - Unlike poverty, which has a strong negative pull on scores, having a high percentage of English Learners does not automatically result in a low score
- **The "Why"** - This suggests that many districts have developed effective ESL/Bilingual programs that help these students achieve growth, which is a major component of the "School Progress" domain

### * Outlier Analysis: "The Resilient vs. The Struggling" 🚨

By filtering the data for outliers, we identified districts that defy the expected trends.

#### * Resilient Districts (High Poverty, High Performance)

We identified several "Resilient" districts that maintain an 'A' Rating despite having over 75% economically disadvantaged students.

- **Examples** - Heritage, Amigos Por Vida-Friends For Life, and Alief Montessori Community
- **Diagnostic Conclusion** - These districts prove that socioeconomic status is not destiny. Their success suggests that factors not captured in the raw data—such as strong leadership, specialized curriculum, or high community engagement—are effectively neutralizing the impact of poverty

#### * Underperforming Low-Poverty Districts

Conversely, we identified districts with low poverty (<40%) that received 'C' or 'D' ratings.

- **Examples** - Salado, Krum, and Navarro
- **Diagnostic Conclusion** - These districts indicate that lack of poverty does not guarantee success. The "Why" here may involve stagnating growth metrics or failure to meet "Closing the Gaps" targets for specific subgroups, highlighting that even well-resourced districts must focus on continuous improvement

### * Regional Trends 🌏

The diagnostic analysis showed that larger metropolitan regions like San Antonio and Austin (Average Scores: ~72-74) struggle more than smaller regions like Wichita Falls (Average Score: 83.2).

- **The "Why"** - Larger districts often face more complex administrative challenges, higher student mobility, and deeper pockets of urban poverty that require more localized, intensive interventions than smaller, more cohesive rural or suburban districts

### ** Diagnostic Summary 📋

| Variable | Influence on Score | Diagnostic Takeaway |
|---|---|---|
| Poverty % | Significant Negative | Poverty remains the strongest demographic predictor of lower scores |
| EB/EL % | Minimal Influence | Language barriers are being overcome more effectively than economic ones |
| Geography | Moderate Influence | Urban centers face higher "score drag" compared to mid-sized regional hubs |
| District Scale | Neutral | Large-scale enrollment does not correlate directly with scores; both small and large districts appear in the 'A' and 'F' categories |

---

## 14. Predictive Insight 🔮

Predictive Insight moves beyond explaining the past to forecasting future outcomes. By applying statistical modeling to the 2022-2023 accountability data, we can identify which variables serve as the strongest leading indicators of a district's future success.

### * Regression Modeling: The Forecasting Engine 📈

Using Linear Regression, we analyzed the predictive power of demographic factors on a district's Overall Score. The model revealed that while socioeconomic status is a major factor, it is not the only driver of performance.

- **Poverty as a Predictor** - The model indicates a coefficient of -21.48 for Economic Disadvantage
  - **Predictive Insight** - For every 10% decrease in a district's poverty level, the model predicts an average increase of 2.15 points in their Overall Score

- **The Growth Factor (EB/EL)** - Interestingly, the % EB/EL Students attribute has a slightly positive coefficient (+3.46) when controlled alongside poverty
  - **Predictive Insight** - This suggests that districts with robust language support programs can actually leverage student growth metrics to maintain or improve their overall ratings, regardless of language barriers

### * Probability of Success (Binary Classification) 🧠

Based on historical data patterns, we can calculate the Probability of Achievement.

- **High Poverty / High Performance (The 36% Rule)** - The model shows that a "High Poverty" district currently has a 36.2% probability of achieving an 'A' or 'B' rating
- **Targeted Identification** - We can use this logic to flag "At-Risk" districts—those whose current scores are significantly lower than what the model predicts for their demographic profile. These districts are statistically underperforming and should be the primary focus for diagnostic audits

### * Summary of Predictive Conclusions 📝

| Predictive Metric | Finding | Strategic Action |
|---|---|---|
| Poverty Sensitivity | High (-2.15 pts per 10% change) | Prioritize state funding to districts hitting the 60% poverty threshold |
| Growth Potential | Positive correlation with EB/EL support | Expand bilingual programs to maximize "School Progress" points |
| Unexplained Variance | 79% (R² = 0.21) | Focus on non-demographic factors like teacher quality and leadership, as they dictate the majority of the score |

---

## 15. Prescriptive Insight 🧭

Prescriptive Insight represents the final and most advanced stage of the data analytics lifecycle. While predictive analytics tells us what is likely to happen, prescriptive analytics recommends specific actions to optimize those outcomes.

Based on the diagnostic and predictive patterns identified in the school accountability data, the following strategic prescriptions are recommended to improve statewide educational performance.

### * Resource Allocation: The 60% Poverty Threshold 💰

The data shows a significant performance drop-off once a district exceeds 60% economic disadvantage.

- **Prescription** - Implement a "Socioeconomic Buffer Fund." Districts that cross the 60% poverty mark should receive automatic increases in per-pupil funding specifically earmarked for wraparound services (nutrition, health, and counseling) to mitigate the external factors that the diagnostic analysis proved are dragging down scores

### * Instructional Strategy: Replicating the "Resilient 36%" 🧑‍🏫

We identified that 36.2% of high-poverty districts are "High Performing" (A/B rated).

- **Prescription** - Establish a "Resilience Mentorship Program." Low-performing high-poverty districts should be paired with one of the identified resilient districts (e.g., Heritage or Alief Montessori) for a formal knowledge-exchange program
- **Action** - Conduct audits of the resilient districts' master schedules and teacher coaching models to create a "Success Template" for struggling peers

### * Language Support: Prioritizing Growth Metrics 🌐

The predictive model showed that EB/EL populations do not necessarily lower overall scores because they drive high "Academic Growth" points.

- **Prescription** - Shift the focus for high-EB/EL districts from "Student Achievement" (raw STAAR scores) to "School Progress" (Growth)
- **Action** - State-level evaluations for these districts should place a 10% higher weight on the Growth domain. This incentivizes schools to focus on individual student progress, which the diagnostic analysis proves is their greatest area of strength

### * Early Warning System: Predictive Performance Flags 🚨

The project's predictive model can identify districts whose current performance is significantly lower than their "predicted score" based on demographics.

- **Prescription** - Launch a "Predictive Intervention Dashboard" for TEA administrators
- **Action** - Any district underperforming its predicted model score by more than 10 points should be flagged for a Level 1 Diagnostic Review before the next academic cycle. This allows for proactive intervention rather than waiting for a failing grade to be published

### ** Summary of Prescriptive Actions 📝

| Challenge Identified | Prescriptive Action | Target Outcome |
|---|---|---|
| High Poverty Drag | Automated Funding Boosts at 60% threshold | Neutralize socioeconomic "score drag" |
| Achievement Gap | Mentorship from the "Resilient 36%" | Replicate proven leadership models |
| Language Barriers | Increase weighting on Growth metrics | Reward progress over raw testing data |
| Underperformance | Proactive flags based on predictive model | Prevent district failure before it occurs |

### *** Conclusion: The Path Forward 🚀

The prescriptive stage transforms this project from a report into a strategic roadmap. By shifting from reactive grading to proactive resource allocation and mentorship, the state can begin to decouple a student's socioeconomic background from their academic destiny. The integration of Excel for data cleaning and Power BI for predictive modeling ensures that these prescriptions are based on empirical evidence rather than intuition.

---

## 16.Final Conclusion ✅

The Conclusion of this project synthesizes the technical workflows and analytical findings to provide a final assessment of the Texas school accountability landscape for the 2022-2023 academic year.

### 1. Project Summary 📌

This project successfully transformed a high-volume, complex administrative dataset into a structured analytical tool. By utilizing Microsoft Excel for rigorous data cleaning and Power BI for advanced data modeling and DAX integration, we transitioned from raw data points to strategic educational insights.

### 2. Key Takeaways ✨

1. **Technical Achievement** - The insertion of calculated "IF" logic columns (such as Poverty Status and Performance Level) allowed for a more nuanced analysis that standard administrative reports often overlook. This proved that data transformation is essential for identifying the specific needs of different student populations.

2. **Socioeconomic Reality** - The diagnostic analysis confirmed that while poverty (Economically Disadvantaged status) remains a significant predictor of performance, it is not an absolute barrier. The identification of the "Resilient 36%"—high-poverty districts achieving A or B ratings—highlights the success of specific instructional models.

3. **Actionable Intelligence** - Through predictive and prescriptive insights, the project moved beyond historical reporting to offer a roadmap for future interventions, specifically recommending resource allocation shifts at the 60% poverty threshold and mentorship programs between resilient and struggling districts.

## 17. Final Assessment Conculsion ✅

The 2022-2023 accountability data reveals a resilient but challenged educational system. While the "Achievement Gap" persists, the data demonstrates that significant academic growth is occurring in districts regardless of their demographic makeup.

By continuing to use data-driven frameworks to identify outliers and replicate success, education stakeholders can move toward a more equitable system where a district's socioeconomic profile no longer dictates its academic destiny. This project serves as a template for how data analytics can be leveraged to drive social and educational reform.

This analysis successfully demonstrates the utility of data-driven decision-making in education. The resulting dashboard provides stakeholders with a powerful tool to monitor and improve school performance statewide.
