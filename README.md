


---

# **NYC Taxi Revenue and Surcharge Analysis: Temporal and Behavioral Insights**
## Contributors 
Neha Shastri, Glenn Castellino, Hyunjin YU, Quan Nguyen, Yifeng Chen
---
## **Overview**

This project provides an in-depth analysis of taxi ride patterns in New York City (NYC), with a particular focus on the revenue and surcharge contributions across different hours of the day, alongside trends in tipping behavior. The project leverages datasets from NYC’s Green and Yellow taxi rides to explore how various factors like fare structure, surcharges, and customer behavior (tipping) evolve over time and at different times of the day.

The goal of this analysis is to extract actionable insights regarding:
- How consumer behaviour changes with increase in fare.
- Temporal trends in tipping behavior.
- Patterns of ride frequency and fare contribution based on the hour of the day.

This analysis is critical for transportation policy-making, optimizing driver operations, pricing strategies, and providing insights into customer behavior.

---

## **Dataset Information**

This analysis primarily uses two datasets: `df_green` and `df_yellow`, which represent rides from NYC’s **Green** and **Yellow** taxis, respectively. Key columns include:
- **pickup_hour**: The hour of the day (0-23) when a ride began.
- **pickup_date**: The date when a ride started.
- **total_amount**: The total fare for the ride, including surcharges.
- **total_surcharge**: Surcharges such as congestion fees and improvement charges.
- **tip_amount**: The tip provided by the passenger.
- **trip_distance**: The total distance of the trip.

### Data Preparation
- The `pickup_hour` is extracted from the pickup timestamp to examine how revenues and tipping behavior vary over time.
- The analysis filters the dataset to examine trends for the year 2023.
- Temporal resampling is used to analyze weekly or monthly trends in revenue and tipping behavior.

---

## **Key Analysis and Visualizations**

### 1. **Revenue vs. Surcharge Contribution Per Hour of the Day**
**Objective:** Understand how much of the revenue during each hour of the day comes from surcharges, versus how much comes from regular fare contributions.

- **Insight:** Surcharges such as congestion and improvement fees may have a significant contribution during specific hours, particularly in peak hours when traffic is heaviest.
- **Visualization:** A stacked bar chart that breaks down revenue into fare contribution and surcharge contribution for each hour of the day.

**Methodology:**
- Group the data by `pickup_hour`.
- Calculate **average revenue per hour** (instead of total revenue) to better reflect the revenue patterns normalized by the number of trips.
- Calculate the average surcharge and fare contribution per hour.
  
The visualization helps identify how surcharges affect the total revenue and offers insights into potential fare structure adjustments during peak hours.

### 2. **Temporal Trends in Average Tip Amounts**
**Objective:** Explore how average tipping behavior changes over time, which may reflect seasonal patterns, economic changes, or service quality shifts.

- **Insight:** Tipping patterns may vary by week or month and provide an indication of customer satisfaction or broader economic factors.
- **Visualization:** A line chart showing the trend of **average tip amounts** over time, resampled weekly or monthly.

**Methodology:**
- Resample the data weekly (`'W'`) to compute the average tip amount for each week.
- Visualize the temporal trend for both Green and Yellow taxis, comparing tipping patterns between them.

### 3. **Rolling Mean of Tip Amounts (Green Taxis)**
**Objective:** Smooth out short-term fluctuations in the tipping data to highlight longer-term trends.

- **Insight:** The rolling mean helps to smooth out short-term volatility and highlights general trends in tipping over time.
- **Visualization:** A line chart with both the original weekly tipping trend and a rolling 4-week average for Green taxis.

**Methodology:**
- A 4-week rolling average is applied to the **average tip amount** for Green taxis.
- Overlay the rolling mean on the original tipping trend to show smoothed, long-term behaviors.

### 4. **Comparing Tipping Trends Between Green and Yellow Taxis**
**Objective:** Compare how tipping behavior differs between NYC’s Yellow and Green taxis over time.

- **Insight:** Tipping behavior may differ based on taxi types (Yellow vs. Green), revealing important customer behavioral patterns.
- **Visualization:** A combined line chart comparing the **average tip amount** for Yellow and Green taxis over time, helping to identify any discrepancies between the two services.

**Methodology:**
- Use resampled weekly data for both taxi types and plot them on the same chart for direct comparison.
- The resulting plot shows tipping patterns across different weeks in 2023 for both services.

---

## **Project Components**

1. **Data Cleaning and Preprocessing:**
   - Ensure proper datetime handling and extraction of the `pickup_hour`.
   - Filter the data to focus on rides in 2023, eliminating any historical data that may skew the analysis.

2. **Revenue and Surcharge Analysis:**
   - A core focus of this analysis is the relationship between total revenue and surcharges. This offers insights into how much of the ride fares are comprised of mandatory surcharges, especially during peak hours.

3. **Tipping Behavior Analysis:**
   - The tipping trends are explored temporally and comparatively across the two taxi services. Both weekly and rolling averages are used to provide a comprehensive view of tipping behavior.

---

## **How to Run the Analysis**

1. **Load Data:**
   - The analysis assumes that `df_green` and `df_yellow` are pandas DataFrames containing the Green and Yellow taxi ride data, respectively.

2. **Install Necessary Libraries:**
   - The project uses Python with common data analysis and visualization libraries:
     ```bash
     pip install pandas matplotlib seaborn
     ```

3. **Run the Code:**
   - Execute the code in a Python environment or Jupyter notebook. You can use the provided scripts to generate the visualizations and analyze the data.

---

## **Key Takeaways and Insights**

- **Surcharge Contribution:** Surcharges make up a significant portion of the total revenue during peak hours, especially in areas with high congestion.
- **Tipping Trends:** Tipping behavior follows temporal patterns, possibly reflecting seasonal shifts or changes in customer satisfaction. Comparing tipping across Green and Yellow taxis reveals subtle differences in customer behavior.
- **Rolling Averages for Tipping:** The rolling mean of tips provides a smoother view of trends and helps filter out weekly or daily fluctuations, offering a clearer view of long-term tipping behavior.

---

## **Next Steps and Improvements**

- **Seasonal Analysis:** Expand the analysis to explore how tipping and revenue change across different seasons, especially with data covering multiple years.
- **Predictive Modeling:** Apply machine learning to predict how surcharges and tips are likely to evolve based on external factors such as weather, holidays, or city events.
- **Geospatial Analysis:** Incorporate geographic data to analyze tipping behavior and surcharge contributions by specific locations within NYC, identifying high-revenue zones or underserved areas.

---

## **Conclusion**

This project provides a comprehensive look at revenue patterns, tipping behavior, and surcharge contributions in NYC taxis. By analyzing both Yellow and Green taxis, it uncovers valuable insights into how different taxi services perform across different times of day, offering opportunities for operational optimization and strategic decision-making.

---


