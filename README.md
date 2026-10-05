Objective
Clean and prepare daily page-view data
Remove extreme values that could distort the analysis
Compare average page views across years and months
Identify long-term traffic trends
Examine monthly seasonality
Visualize findings using bar charts and box plots
Dataset

The dataset contains daily FreeCodeCamp forum page views with:

date — Date of the observation
value — Number of daily page views

The date column was parsed as a datetime index to support time-based analysis.

Data Cleaning

To reduce the effect of unusually high or low traffic days, observations below the 2.5th percentile and above the 97.5th percentile were removed.

df = df.loc[
    (df['value'] >= df['value'].quantile(0.025)) &
    (df['value'] <= df['value'].quantile(0.975))
]

This keeps the middle 95% of observations for the analysis.

Analysis
Monthly Average Page Views

The data was grouped by year and month to calculate average daily page views for each month.

This was used to create a grouped bar chart comparing monthly traffic across years.

The analysis shows a substantial increase in average forum page views over the period, with 2019 generally recording much higher traffic than the earlier years.

Year-wise Trend

A box plot was created to compare the distribution of daily page views across each year.

This helps visualize how the overall level and spread of forum traffic changed from 2016 through 2019.

Monthly Seasonality

A second box plot compares page-view distributions by month.

This provides a view of recurring seasonal patterns and differences in typical forum traffic throughout the year.

Visualizations

The project includes:

Monthly Average Page Views Bar Chart
Compares average daily page views by month and year.
Year-wise Box Plot
Shows the distribution and trend of daily page views across years.
Month-wise Box Plot
Shows seasonal differences in page views across months.
Tools & Technologies
Python
Pandas
NumPy
Matplotlib
Seaborn
Jupyter Notebook
Skills Demonstrated
Data cleaning
Date/time manipulation
Data aggregation
Percentile-based outlier filtering
Time-series analysis
Trend analysis
Seasonality analysis
Statistical visualization
Python data analysis
Key Takeaway

The analysis demonstrates how historical web traffic data can be transformed into useful insights by combining data cleaning, time-based aggregation, and visual analysis. The results show strong growth in FreeCodeCamp forum traffic between 2016 and 2019 while also allowing yearly and monthly patterns to be compared.

Project Structure
FreeCodeCamp-Forum-Page-Views/
├── page_views.ipynb
├── fcc-forum-pageviews.csv
└── README.md
