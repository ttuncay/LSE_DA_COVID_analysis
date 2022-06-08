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
