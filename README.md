# **Surf Up**

## **Project Overview**

This project is a hypothetical investment opportunity. Where a data analyst performs weather data analysis to predict the possible impact of precipitation and temperature on the profitability of a surf and shake shop in Oahu, Hawaii. The shop would sell surfboards and ice cream for local and tourist. He/she needs an investor backing to get the project started. The data analyst put a strong investment plan and reach out to potential investor. After pitching the plan, the investor asked to see analysis to weather data in Oahu. He/she also informed the data analyst that it would also be interesting to think about the plan longer term, if the shop on Oahu does well, the plan could expand to other islands. Or in case Oahu does not turn out to be a good fit to be able to use the same analysis to test other options.

The investor provides weather measurements from multiple weather stations on Oahu and a across multiple years. SQLite was used to store the weather data *(hawaii.sqlite)* and Python, Panda and SQLAlchemy were utilized to run the analysis.

One thing the investor mentioned to take in consideration while doing the analysis is the amount of precipitation on Oahu. There needs to be enough rain to keep everything green, but not so much that would lead to losing out on that ideal surfing and ice cream weather. So, analyzing the perception on chosen 12 months of the dataset was the starting point. *(Output File: climate_analysis.ipynb)*

As the investor like the precipitation analysis, he/she wants more information about temperature trends before opening the surf shop. Specifically, he/she wants temperature data for the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round.

Therefore, two technical analysis deliverables were done *(Output File: SurfsUp_Challenge.ipynb)*

## **Results:**

- **Deliverable 1: Determine the Summary Statistics for June**

![](https://github.com/Bayan-daux/Surfs_Up/blob/main/June_statistics.PNG)

*Fig. 1 - June Temperature Statistic*

- **Deliverable 2: Determine the Summary Statistics for December**

![](https://github.com/Bayan-daux/Surfs_Up/blob/main/Dec_statistics.PNG)

*Fig. 2 - December Temperature Statistic*

### **Outcomes:**

1. The standard deviation for June is lower (3.26) December (3.75) but very slight difference.
2. Have similar average highs and low temperature in both June (85, 63) and December (83, 56) and the difference between the minimum and maximum for June is (21) which is lower than December (27).
3. Looking at the number in both month shows that the weather is warm all year round. Which makes it perfect to enjoy the beach or the water almost al year along. Therefore, an ice cream and surf equipment business would have great chance for success.

## **Summary**

Even though the above results show great potential for the business profitability, there are other aspect of the weather data could be explored and analyzed to give a clearer and more accurate picture. It would worth the time to run the results for all the months and use the same query for precipitation for the same range of dates. As in the code and following results:

```

session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()
june_rain_results = []
june_rain_results = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==6).all()
df = pd.DataFrame(june_rain_results, columns=['date','June Precipitation'])
df.set_index(df['date'], inplace=True)
df.describe()
```
![](https://github.com/Bayan-daux/Surfs_Up/blob/main/June_Rain_statistics.PNG)

*Fig. 3 - June Precipitation Statistic*

Also depending only on weather data to decide about starting such a business would not be ideal. Other aspect such already establisher competitor worth to be explored.# Surfs Up
