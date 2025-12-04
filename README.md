# Google Data Analytics Capstone: Cyclistic Bike-Share Analysis

## Executive Summary
This case study analyzes historical trip data from **Divvy**, a bike-share program in Chicago, to identify behavioral differences between annual members and casual riders. The analysis reveals distinct usage patterns: annual members predominantly use the service for weekday commuting, while casual riders use it primarily for weekend leisure. These insights support a marketing strategy focused on converting high-frequency casual riders by highlighting the cost-effectiveness and convenience of membership for both commuting and regular recreation.

---

## Business Task
**Objective:** Design marketing strategies aimed at converting casual riders into annual members by understanding how they use Divvy bikes differently.

**Key Stakeholders:**
*   **Director of Marketing** 
*   **Cyclistic Marketing Executive Team**

---

## Data Source & Integrity
The analysis is based on 12 months of historical trip data (December 2020 - November 2021) provided by Motivate International Inc.
*   **Source:** [Divvy Data](https://divvy-tripdata.s3.amazonaws.com/index.html)
*   **License:** [Data License Agreement](https://ride.divvybikes.com/data-license-agreement)
*   **Privacy:** Data has been anonymized (no personally identifiable information).

---

## Methodology
The analysis was conducted using **R** for data processing and visualization, utilizing the `tidyverse` ecosystem.

### Data Pre-processing
1.  **Consolidation:** Merged 12 monthly CSV files into a single dataset (~5 million records).
2.  **Feature Engineering:** 
    *   Extracted date components (Month, Day, Year, Day of Week).
    *   Calculated `ride_length` (difference between start and end times).
3.  **Data Cleaning:** 
    *   Removed entries with negative ride lengths (system errors).
    *   Validated station names and ride IDs.

---

## Analysis & Key Findings

### 1. Weekly Usage Patterns (Commute vs. Leisure)
There is a clear divergence in when different user groups utilize the service.

*   **Annual Members:** Usage remains relatively stable throughout the weekdays (Mon-Fri), indicating routine, utilitarian use likely associated with commuting to work or school.
*   **Casual Riders:** Usage peaks significantly on Saturdays and Sundays, suggesting leisure-oriented behavior.

![](images/number_of_rides_chart.png)

### 2. Ride Duration Analysis
Casual riders tend to keep bikes for significantly longer durations compared to members.

*   **Mean Ride Time:** Casual riders average significantly longer trips than members.
*   **Consistency:** The standard deviation for casual riders (approx. 15,794 seconds) is nearly 10x that of members (approx. 1,671 seconds). This confirms that member behavior is highly predictable and routine, whereas casual rider behavior is sporadic and variable.

![](images/average_ride_time_chart.png)
![](images/median_ride_time_chart.png)

### 3. Distribution of Trip Lengths
The histogram below highlights the distribution of ride lengths. Member rides are heavily concentrated in the shorter duration range (left-skewed relative to casuals), further supporting the "point-to-point" commute hypothesis. Casual rides show a "long tail" distribution, typical of recreational rides that lack a strict time constraint.

![](images/ride_time_histogram.png)

---

## Recommendations

Based on the data evidence, the following strategies are recommended to convert casual riders into members:

1.  **"Commuter Challenge" Campaigns:** Since a portion of casual riders do ride on weekdays, target them with messaging about the cost savings of membership for daily commuting. Use the consistent weekday usage of current members as a testimonial benchmark.
2.  **Weekend Membership Specials:** Develop a "Weekend Warrior" mini-membership or promote the annual pass as a way to unlock unlimited weekend leisure rides, specifically targeting the high volume of Saturday/Sunday users.
3.  **Usage-Based Triggers:** Implement in-app notifications for casual riders who exceed a certain trip duration or frequency in a month, showing them how much they would have saved as an annual member.

---

## Future Analysis Opportunities
To further refine this analysis, the following steps could be taken (future iterations):
*   **Hourly Analysis:** breaking down data by hour of the day would definitively confirm peak commute times (e.g., 8 AM and 5 PM peaks for members). Understanding hourly trends could open the door for hour-based notifications to influence behavior.
*   **Station Analysis:** Identifying which stations are most popular for casual riders could help target physical advertising.
*   **Granular Filtering:** Further cleaning to remove rides under 60 seconds (likely false starts) would improve the accuracy of the mean ride time metrics.

---
*Analysis performed with R Studio and Excel.*
