# Overview
The purpose of this analysis was to gather data from weather stations in Oahu to vet the a business opportunity to openb a surf shop that additionally serves ice cream. For the business to be successful, the weather needs to be warm enough that people will want ice cream, and have conditions good for surfing. The weather data was stored in SQLite and I utilized python in VS Code and Jupyter Notebook to analyze the data.

# Results

- The average temperature in June on Oahu was 75 degrees, compared to 71 degrees in December. This bodes well for the ability to sell ice cream year around in Oahu.
- The minimum temperature in June is 64 degrees compared to a minimum of 56 degrees in December. So while the average temperature remains in the 70s for both months, the December low is significantly lower.
- June had 182 more data points than December, but December still had over 1,500 data points and should therfore still be reliable.

![image1](https://github.com/JFoArlas/Surfs_up/blob/main/Resources/june_temps.png)
![image2](https://github.com/JFoArlas/Surfs_up/blob/main/Resources/dec_temps.png)

# Summary

The climate in Oahu is suitable for opening a surf and ice cream shop given the consistent warm days. Additionally, if you look at the precipitation in both June and December months, there is not enough rain to deter people from surfing and wanting to buy ice cream.

The below queries pull precipitation data for June and December and place that data into a precipitation dataframe for further analysis as needed.
1. 
```
results = session.query(Measurement.date, Measurement.prcp).\
filter(extract('month', Measurement.date) == 6).all()

june_rain_df = pd.DataFrame(results, columns=['date','June Rain'])
```
2.
```
results = session.query(Measurement.date, Measurement.prcp).\
filter(extract('month', Measurement.date) == 12).all()

december_rain_df = pd.DataFrame(results, columns=['date','December Rain'])
```

You could additionally plot the temperatures as seen below to visualize just how often the temperature is actually dropping below 70 degrees and better understand the occurences of the minimum value for those months.

![image3](https://github.com/JFoArlas/Surfs_up/blob/main/Resources/june_plot.png)

![image4](https://github.com/JFoArlas/Surfs_up/blob/main/Resources/dec_plot.png)
