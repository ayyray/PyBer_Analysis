# PyBer_Analysis
Analyze ride-share data and create visualizations

## Overview of Analysis:
### Purpose and Background:
After I had done a deep inspection, cleaning, and creating visualizations for PyBer using the ride-share data provided to me, (which included the following):
- Create bubble charts, box and whisker plots, and pie charts to visualize:
  - Average fare for vs. total number of rides (show in bubble chart)
  - Number of rides, fares for city type, and drivers of city type (shown in box-and-whisker plots)
  - Percent of total fares, ride, and drivers (shown in pie chart)

I then set out to create a summary DataFrame for the ride-share data based on city type. Once I had created the summary, I then wanted to present my findings in a way that was both informative and easy for the company to analyze. I did this by creating a multi-line graph that showed the weekly fares based on each city type.

## Results:

### Step 1: 
First look at the data is near impossible in detecting trends or outliers which would assist in my analysis and overall results of my project. So, the first step in the project was to create a DataFrame which would allow me to merge data sets from city data (shows city, city type, and driver count) and data from ride data (shows city, date, dare, and the ride id). The combination gave me the following DataFrame.

![image](https://user-images.githubusercontent.com/96212660/152052450-946bfdc5-5381-49c8-8760-bf87b10514cf.png)

Thanks to the creation of the DataFrame (titled: pyber_data_df) I was able to then find:

- Total rides by city type
- Total drivers by city type
- Total fares by city type
- Average fare per ride by city type
- Average fare per driver by city type

This data was useful in getting a better idea of data per city type, but the data was now in 5 separate “equations”. I created a Summary Data Frame which gathered all this data into 1 DataFrame!

![image](https://user-images.githubusercontent.com/96212660/152052703-0b611d35-d288-4317-8146-ca7ac7eaabd8.png)

### Step 2:
I wanted to create a visualization that shows the total fares per week for each city type. Through the use of the groupby() function I was able to gather the sum of fares for each day based off city type. After a little bit of cleanup and formatting (pivot() function) I created a pivot table that now used the date as the index and provided all the data aka total fares by city type based off the date! Image 1 shows the more raw and unformatted/pre-date index DataFrame and Image 2 shows the pivot table DataFrame. As you can see, the pivot table gives a better idea of just what it is exactly the data is beginning to tell us.

![image](https://user-images.githubusercontent.com/96212660/152052907-76e7c3e5-bcc1-4c3a-95f8-c6838c56d64a.png)

![image](https://user-images.githubusercontent.com/96212660/152052932-f2973118-7258-45f7-adba-f046a8ae3ab2.png)

But that was not going to tell me what I wanted to know. As I noted in my purpose, I wanted to create a multi-line graph that showed the weekly fares based on each city type. In order to accomplish this, I needed to break my data down just a little bit more.

I created a new DataFrame using the pivot table I had just created using the parameters of the dates 2019-01-01 through 2019-04-28. The results are as followed (bear in mind the image is only showing the last 5 as opposed to the entire data set out in my parameters):

![image](https://user-images.githubusercontent.com/96212660/152052997-7d8e28e8-b5a0-46c4-96c2-6b757eeb6ed7.png)

The final step to break the data down to show the sum of fares for each week meant I had to create one more DataFrame. Using the resample() function I was able to accomplish this:

![image](https://user-images.githubusercontent.com/96212660/152053060-8a60e6d1-f236-4ad6-a4bc-c5cd1a1ecea6.png)

The final step was creating a multiple line plot to show my findings. Through the careful creation of many DataFrames and a lot of cleaning of data I was able to create a line plot that shows the Total Fares by City type based off of weekly fares!

![image](https://user-images.githubusercontent.com/96212660/152053114-0e98d1ac-8788-4f15-badf-2d932fbc22ee.png)

Results of the findings show:
- Urban city is the most expensive in terms of total fares each month
- In terms of gains from start to peak:
  - Rural has the lowest with about a +300 (Fare ($ USD))
  - Suburban has second with about a +750 (Fare ($ USD))
  - Urban has the highest with about a +850 (Fare ($ USD))
- Trends in terms of spike or drops are all similar (example highest spike of total fares happened at the end of February)

Differences in ride-share data:
- Urban had 65 times more rides total than rural and 1000 more rides than suburban
- The trend of more rides applies to more drivers and more fares.
- Rural areas might have significantly less rides but their average fare per ride is the highest out of all 3. This also means that the average fare per driver is the highest as well. This correlation would indicate that the value per ride is higher in rural areas because there are less opportunities i.e. supply and demand. 

## Summary:
The results of the data show that there are disparities among the city types, I would suggest that: Fares in rural areas should be lower because unlike urban and suburban areas there is less concentration of transportation for these areas (public transportation etc.) Areas that have easy access to public transportation have the ability to decide whether or not they want to take public transportation or a ride-share. With that being said, in order to make up for the lowering of fares in rural areas, there should be an increase in fares in the urban areas. Based off the data, there is a high demand in ride-shares. If you were to raise the prices a little bit more, the demand would stay high and would in turn make you more money than if you kept the rural prices as they are. If rural prices drop then that means, there will most likely be a higher number of customers who will start using your rides-share. My final recommendation would be to lower the suburban fares but not as much as the rural fares. Similar to what we are seeing in the rural areas, there appears to be a disconnect with public transportation. I feel that the best option would be to make the ride-share option more affordable. The total number of rides in the suburban is significantly higher than the rides in the rural area but significantly lower than the rides in the urban area. All you need to do is find the sweet spot to increase the number of rides without deterring customers from utilizing your ride-share service.











