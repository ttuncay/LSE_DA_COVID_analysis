# LSE_DA_COVID_analysis
Use Python to analyse a data set about COVID-19 vaccinations in UK between Jan'20 to Oct'21

Week2:
There are available 3 data sets imported into notebook as followed:

1)	Cases: 
a.	7584 rows and 12 columns.
b.	Death, Cases and recovered valued are cumulative sums.  Hospitalized values can be either number of people in hospital on certain date or number of people admitted to hospital on certain date. (Need to be further explored)
c.	Descriptive analytics does not make sense on data due the cumulative sum. New column can be created to display number of death, cases and recovered people on each date.
d.	Data has only 2 rows of missing data. Those or for the Province/State: Bermuda for dates 2020-09-21 & 2020-09-22.
e.	DataFrame has default index starting from 0.

2)	Vaccinated: 
a.	7584 rows and 11 columns.
b.	Vaccinated values are equal to second dose values. (Vaccinated means received second dose)
c.	Values show number of people received shots on dates. (Not cumulative vaccinated numbers)
d.	Descriptive analytics does not fully represent the situation because data is starting back in time where there were no vaccine. Number of shots on those dates are marked as 0 which makes the statistics calculations wrong.
e.	There are no missing values.
f.	DataFrame has default index starting from 0.

3)	Tweets:
a.	3960 rows and 21 columns.
b.	Several missing values for all rows.
c.	DataFrame has default index starting from 0.

Week 3:
I had a chance to explore the data further with group by function. My primary focus for this week was on vaccination number. The data set available has all information to make the analysis. However for further studies, in order to be able to analyse/compare case numbers with vaccination I merged to data set using left join.

Below are the summary of my findings:

•	Gibraltar has the most number of vaccinated (who received 2 doses) people in UK. This is also same for number of people who received the first those and for people who received the first dose nut not the second.
 
It is interesting that the order does not change for any metric. It should be correct to say that if the state has largest number of First Dose taker they also have the largest number of fully vaccinated people and also largest number of not fully vaccinated people. (received first dose but not the second) 

•	It is interesting to see that percentage of not fully vaccinated people is very close to each other. In order to calculate this metric what I did is I find the percentage of not fully vaccinated people among the group of first dose takers.

% of not fully vaccinated = (first dose – second dose) / first dose

The order is different than the pervious finding. Turk and Caicos Islands have the biggest percentage of not fully vaccinated people in UK. However as mentioned earlier the numbers are very close and all around %4.51.

•	I had a look on how vaccination numbers are changing over days. In have the full data for almost 2 years. At this point I had a visual check and spotted some days are bigger than others. To further explore I bring weekday names to my dataframe. By visual check it is hard to talk about trends. I realized vaccination numbers are increasing as ramp up trend then decreasing a bit. Usually weekdays have more numbers than weekend. I will further analyse the trend with visuals.

Week 4:
This week I had a chance to go through my dataset with different visuals. I analysed vaccinated, deaths and recovered patient numbers in state/province breakdown. In addition, I had a chance to review how death and recovered numbers evolved overtime.

In terms of vaccination, all provinces have similar trend. People with first dose is larger than the people with 2 doses. In order to further examine and put them on same scale I also created new 2 columns which are percentage of fully vaccinated among the group who took vaccine (not on eligible person) and ratio of interest (not fully vaccinated percentage) All provinces have almost 95% fully vaccinated and 5% ratio of interest among vaccine takers.

Next, I explored deaths over time and hospitalized numbers over time. Over time visualisation can be explored best with line chart. When I checked the deaths over time, I realized others group seriously affects the visualisation and does not help to clearly see the trend. When I excluded others data, I was able to see the trend over time. I plot data 2 different methods. First checked the plot with Date data provided second I converted Date to Months and then plot. Month version has the same shape with other but show confidence interval around lines that indicated the movement within that month.
 
•	There are 2 death cycles for almost all provinces. (Which was the issue for others as well)
•	Some provinces (Anguilla, Isla of Man, Bermuda) start having a sharp increase in death numbers at the beginning of the pandemic (03/04 – 2020) whereas some others (Turk & Caicos, Gibraltar) keep themselves almost safe till Q42020. British Virgin Island remained safe from death almost till mid 2021.
•	Gibraltar province witnessed deaths later on almost end of 2020, however unfortunately it is the most hit province except locations under others.
•	Death numbers show 3 peaks so far. The third one seems to be better than previous ones (less death) although I am not able to view the full effect since last data point is 11-2021.

Lastly, I explored the recovered numbers per provinces. Plot helped me to identify the missing data in here. In all provinces recovered patient numbers are changed to 0 all at once around 08-2021. This is clearly a data quality issue. I took a note here and decide how to handle those next.
•	Similar to death data Gibraltar and Anguilla has the biggest recovered number of people.
•	Increase number on recovered patients accumulates basically within 2021. The correlation between vaccination on similar dates vs recovered numbers shall be investigated further. It is high likely as number of vaccinated people increased recovered. 

Week 5:
This week I had a chance to review tweets from May’2022 about COVID 19 pandemic. I analysed mainly the hashtags and checked what are the most common used ones. In order to explore further, I have 2 tasks in mind:
1)	I would like to explore further data with likes, retweets etc information and check how engaging are those hashtags and are there any correlation.
2)	I would like to compare hashtags provided in data set and the ones I extracted final week of the module 2. I would like to understand whether there is a change in hashtags, and any one of them increasing. To make this, I need following preparation and information:
a.	I need to convert number of times hashtags appeared to percentages. The day I check tweets may not be comparable in terms of numbers but comparing percentages should be OK.
b.	I need to check whether data provided is worldwide tweets regarding to Covid or only UK based. Plus, what was the search criteria while creating the dataset. If I am not able to access this information from Metadata, then I will simply compare my new tweets but comparison may not be ideal.

