# Crime-Patterns-and-Resource-Allocation-Analysis


<h2>Tools Used</h2>
- <b>Python:</b> Data Cleaning, preliminary EDA 
<br/>
- <b>Tableau:</b> Dashboarding / EDA

<h2>Dataset and Description</h2>

[**Source**](https://data.longbeach.gov/explore/?orderBy=title+ASC)
<br />
<br />
<b>Size: </b> (90216, 19)
<br />
<br />
<b>Description: </b> Citywide crime statistics of LongBeach, California from 2023 to 2025. Overall, the dataset reported the time of the crime, the location of the crime in terms of district, beat, and division, and the type of crime in terms of UCR Code, Crime category, and NIBRS Offense.
<br />
<br />
<b>Features: </b>
- **date reported:** date the crime was reported
- **Hour**: hour the crime was reported
- **Reporting district:** district the crime was reported to be in.
- **Beat:** The beat the crime was reported in
- **Division:** The division the crime was reported in
- **UCR Code:** a crime classification under the Uniform Crime Reporting (UCR) Program. The Long Beach Police Department (LBPD) uses these codes to categorize crime incidents into Part I (serious/violent/property) and Part II (less serious) crimes, which allows for consistent data reporting across different law enforcement agencies.
- **Crime category**: classifying what or whom the crime offended
- **NIBRS Offense:** detailed offense recording
- **NIBRS Offense Category:** categorized offense recording
- **Offense Location:** Type of location where the crime took place (ex: commercial, residential, etc)
- **Anonymized Address:** Anonymized address

<br />
<br />


<h2>Data Cleaning</h2>

- **dealing with na values:** Some NA reporting district values at an inconsequential number, so I simply removed those values (CHECK FOR OTHER WAYS TO DEAL WITH NA VALUES)
- **feature engineering**
    - Used the **date reported** column to create hour as an integer, then **Year, month,** and **day** as objects
    - created **UCR Code (Numeric),** which contained only the numeric portion of UCR Code
    - created a **weekday** column
    - created **IsWeekend** column boolean for identifying weekend vs weekday
    - created **Season** column from **date reported**
- **Data type transformations**
    - **Beat** and **reporting district** transformed from numeric to objects.
    - ensuring **date reported** is datetime
- **Data standardizing**
    - There were some capitalization inconsistencies for the **Division** column, like some “West” and “WEST” so I applied consistent casing, choosing to make them all uppercase
    - trimmed white space from text columns
<br />
<br />

<h2>Exploratory Data Analysis</h2>
- Created time series, heat maps, bar graphs, and pie charts to compare crime incident frequencies and types across different locations and times. 
<br />
<br />


<h2>Dashboard</h2>

<img width="998" height="795" alt="Crime Patterns Dashboard" src="https://github.com/user-attachments/assets/9583f2cf-5754-4bb1-b59f-b30cdeca70dc" />



<h2>Results and Recommendations</h2>

- Every year the distribution of crime incidents follows roughly the same trend throughout the day, with crime incidents steadily decreasing from 1 am to 5 am, steadily increasing after 5 am, then peaking between hours 17 and 18, which would be between 5 and 6 PM.
- the crime incident hourly trend for winter, summer, and spring closely follow each other in quantity, while fall overall sees less hourly crime incidents

- The hourly crimes are drastically more prevalent on the weekdays vs the weekend. Perhaps a t-test can be done here too. The difference is by roughly more than a thousand. This insight suggests we should tighten security a lot more on the weekdays.

- Beats 6 and 8 are the most critical beats to target in order to reduce crime further. They account for 82.1% of the total crime in the south division from 2023-2025. 

- Beats 6 and 8 from South Division and Beats 4 and 3 from West division account for a disproportionate share of total crime incidents, each pair contributing to more than half the incidents of the district.


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
