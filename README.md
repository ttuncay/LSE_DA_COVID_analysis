# LSE_DA_COVID_analysis
Use Python to analyse a data set about COVID-19 vaccinations in UK between Jan'20 to Oct'21

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

I had a chance to explore the data further with group by function. My primary focus for this week was on vaccination number. The data set available has all information to make the analysis. However for further studies, in order to be able to analyse/compare case numbers with vaccination I merged to data set using left join.

Below are the summary of my findings:

•	Gibraltar has the most number of vaccinated (who received 2 doses) people in UK. This is also same for number of people who received the first those and for people who received the first dose nut not the second.
 
It is interesting that the order does not change for any metric. It should be correct to say that if the state has largest number of First Dose taker they also have the largest number of fully vaccinated people and also largest number of not fully vaccinated people. (received first dose but not the second) 

•	It is interesting to see that percentage of not fully vaccinated people is very close to each other. In order to calculate this metric what I did is I find the percentage of not fully vaccinated people among the group of first dose takers.

% of not fully vaccinated = (first dose – second dose) / first dose

The order is different than the pervious finding. Turk and Caicos Islands have the biggest percentage of not fully vaccinated people in UK. However as mentioned earlier the numbers are very close and all around %4.51.

•	I had a look on how vaccination numbers are changing over days. In have the full data for almost 2 years. At this point I had a visual check and spotted some days are bigger than others. To further explore I bring weekday names to my dataframe. By visual check it is hard to talk about trends. I realized vaccination numbers are increasing as ramp up trend then decreasing a bit. Usually weekdays have more numbers than weekend. I will further analyse the trend with visuals.
