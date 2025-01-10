# YouTube Watch History Analysis

## Project Overview
This project analyzes YouTube watching habits to uncover patterns and trends in category preferences, engagement metrics, and temporal variations. By combining personal watch history with additional metadata fetched via the YouTube API, the project investigates changes in viewing behavior over time and different parts of the day using statistical techniques.

## 1. Data Collection
1.	YouTube Watch History:
	•	Obtained a CSV file from YouTube containing video IDs, timestamps, and basic metadata.
2.	YouTube API:
	•	Fetched additional metadata using video IDs:
	•	Video categories (category_id),
	•	Descriptions,
	•	Engagement metrics (likes, comments, views).,

## 2. Data Preparation
1.	Data Transformation:
	•	Loaded the data into a Pandas DataFrame.
	•	Converted category_id to human-readable category_name.
	•	Added a new column duration_in_seconds, converting the duration to seconds for consistency.
	•	Created time_segment_in_day to classify video watch times into:
	•	Night (12 AM–6 AM),
	•	Morning (6 AM–12 PM),
	•	Afternoon (12 PM–6 PM),
	•	Evening (6 PM–12 AM).
2.	Exploratory Data Analysis (EDA):
	•	Identified most-watched categories and engagement metrics (e.g., likes, views).
	•	Visualized category preferences over time and time of day.

## 3. Statistical Hypotheses and Methods
3.1. Categories Over Time
Hypothesis:
	•	Null Hypothesis (H₀): Category preferences do not change significantly over time.
	•	Alternative Hypothesis (H₁): Category preferences change significantly over time.
Methods:
	•	Applied Chi-Square tests for:
	•	Quarters,
	•	Months.
	•	Compared results using:
	•	Raw counts,
	•	Proportions.
Findings:
	•	Raw counts: Significant changes in category preferences over time.
	•	Proportions: No significant changes, indicating stable relative preferences.

 3.2. Categories by Time of Day
Hypothesis:
	•	Null Hypothesis (H₀): Category preferences do not change significantly by time of day.
	•	Alternative Hypothesis (H₁): Category preferences change significantly by time of day.
Method:
	•	Chi-Square tests on time segments (Night, Morning, Afternoon, Evening).
Findings:
	•	Similar to overall time analysis:
	•	Raw counts: Significant differences in category preferences.
	•	Proportions: No significant differences.

 3.3. Total Videos and Duration by Time of Day
Hypothesis:
	•	Null Hypothesis (H₀): Total number of videos or total duration does not change significantly by time of day.
	•	Alternative Hypothesis (H₁): Total number of videos or total duration changes significantly by time of day.
Methods:
	1.	Reshaped data to aggregate video counts and durations by time_segment_in_day.
	2.	Applied:
	•	ANOVA: Significant differences across time segments.
	•	Levene’s Test: Variances were unequal.
	•	Kruskal-Wallis Test: Confirmed significant differences across time segments.
Findings:
	•	Total number of videos and total durations varied significantly across Night, Morning, Afternoon, and Evening.

## 4. Key Findings
Category Preferences:
	•	Relative preferences (proportions) remained stable over time and by time of day.
	•	Absolute counts showed significant variations, driven by changes in overall viewing volume.
 Video Counts and Durations:
	•	Significant variations across time segments (Night, Morning, Afternoon, Evening) for both metrics.


 ## 5. Limitations
1.	Data reflects personal watching habits and may not generalize to others.
2.	Assumption of watching all videos until the end may not always hold true.
3.	External factors influencing behavior (e.g., recommendations) were not analyzed.
4.	Unequal variances (Levene’s test) violate ANOVA assumptions; Kruskal-Wallis was applied as a robust alternative.

## 6. Conclusion

The project identified significant temporal patterns in my YouTube watching habits:
	•	Category preferences are influenced by time of day and time period.
	•	Absolute video counts and durations vary significantly across time segments.
	•	Stable relative preferences contrast with volume-driven absolute changes.

Future work could explore:
	•	The impact of YouTube recommendations on behavior.
	•	Predictive modeling of viewing habits.
