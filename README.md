# BayAreaBikeShare


## Part 1 ReadMe

Input Files: 
**GDA DATA.csv**: The data given by the home test.
**Station.csv**: The geolocation data of each station.

The analysis is in [Analysis Section](#Analysis) and done by Python and Tableau. 

The code of analysis is in [**python.ipynb**](/python.ipynb) . Please use Jupyter Notebook to open the python file.

Visualization is in Tableau. Please read the instructions in [Instruction Section](#Instruction) below.


## Part 2 Instruction <a name="Instruction"></a>

Here is the instruction to use Tableau:

### Tableau
  Note: If you cannot open the file. You can see and download the files here: 
  
  [BAB-Book1](https://public.tableau.com/profile/jianyuan.zheng#!/vizhome/BABK-piechart/StartStations)
  
  [BAB-Book2](https://public.tableau.com/profile/jianyuan.zheng#!/vizhome/BAB-Book2/Throughoutbydays)

### BAB-Book1

Input file: **output.csv**

There are 7 sheets and 1 dashboard in this book:

**Start Station**: A tool to monitor that the number of trips by Start Stations. The size of circle is the amount of throughput.

The basic instruction is as follows.

  1.	Move the mouse on any cirle, which will show the information about this station.
  2.	There is a bunch of filters could be used on the right side of windows.
  
    a.	Weekend or no:  2-choice Filter to choose the weekends or weekdays.
    b.	Subscriber Type : 2-choice Filter to choose the type of riders.
    c.	Start Landmark: A Filter that you can pick any city you want.
    d.	End Landmark: A Filter that you can pick any city you want.
    e.	Start Station: A Filter that you can pick any start station you want.
    f.	End Station: A Filter that you can pick any start station you want.
    g.	Sum(Trip): A Range Filter that you can move the buttion to filter out the stations by Tips.
    
  3.	If you want to check a specific location, you can zoom in and move the view by scrolling up your wheel on your mouse or clilcking an icon of “+” at the upper left conner.
  
**End Stations**: That sheet is similar with Start Station.

**Dashboard 1**: The top left pie chart describes stations by cities. The top right pie chart describes trips by cities. The bottom left pie chart describes trips by subscribe type.

	Sheet2, Sheet3, Sheet4 are used to make Dashboard 1.
	
**Daily Usage**: Daily Usage of bikes.

**Monthly Usage**: Monthly usage of bikes.

### BAB-Book2

Input file: **tranport.csv**

There are 2 sheets in this book:

**Hourly Throughput**: A tool to monitor that stations’ throughput and riders’ behavior hourly. The red/pink circle in the picture means more bikes picked up than bikes dropped in the station. The blue circle means more bikes dropped than bikes picked up in the station. The size of circle is the amount of throughput.

The basic instruction is as follows:

  1.	Move the mouse on any cirle, which will show the information about this station like througput .
  2.	There is a bunch of filters could be used on the right side of windows. 
  
    a.	Weekend or no:  2-choice Filter to choose the weekends or weekdays
    b.	Hour : multiple choices Filter which you can pick any hour in a day.
    c.	Subscriber Type : 2-choice Filter to choose the type of riders.
    d.	Month(Date): multiple choices Filter that you pick the month
    e.	date: a move button Fitler to choose the range of date. Be carefule to use with ‘Month(Date)’
    f.	Landmark: A Filter that you can pick any city you want.
    g.	Station: A Filter that you can pick any station you want.
    
  3.	If you want to check a specific location, you can zoom in and move the view by scrolling up your wheel on your mouse or clilcking an icon of “+” at the upper left conner.

**Throughout by days**:  This chart shows the daily throughputs by hours for each station. Columns are stations. 

  1.	Rows are throughput along month (this metrics could be changed to day/year by right clicking the button in blue square and selecting month and day).
  2.	There is a bunch of filters could be used on the right side of windows. 
  
    a.	Weekend or no:  2-choice Filter to choose the weekends or weekdays
    b.	Hour : multiple choices Filter which you can pick any hour in a day.
    c.	Subscriber Type : 2-choice Filter to choose the type of riders.
    d.	Month(Date): multiple choices Filter that you pick the month
    e.	date: a move button Fitler to choose the range of date. Be carefule to use with ‘Month(Date)’
    f.	Landmark: A Filter that you can pick any city you want.

## Part 3 Analysis <a name="Analysis"></a>

### What is the San Francisco’s bike share program?

The bikes of San Francisco’s bike share program cannot pick up and drop off at any arbitrary point in the city. Instead, riders can pick up and drop off bikes at finite number of stations across the city.  

![Overview](/Pic/Geo.PNG) 

![Pie Chart](/Pic/Pie%20Chart.PNG) 

The data we analyze here came from rides between March 1st, 2014 and August 31,2014.

There are 71 stations across 5 cities. Most stations are in San Francisco and Most trips took place in San Francisco. 
_____________________________________________________________________________________

### How much is the Bike used and who use the Bike?

![Trips per day](/Pic/Trips%20per%20day.png) 

The figure clearly shows the number of trips changes as a cycling pattern. It drops on weekends. 

![Trips by SubScriber Type](/Pic/Trips%20by%20Subscriber%20Type.PNG) 

83% of trips are that Subscribers ride. The rest are Customers.

Here’s a graph of monthly usage:

![Trips per month](/Pic/Trips%20per%20month.png) 

That’s strange! The total trips keep increasing from March to July but stay steady in August. The trips by subscriber have similar pattern but that by customers slowly increase over months. I guess we don't have enough bikes in the market, which suggest we should add more bikes. 

_____________________________________________________________________________________

### When is the Bike used? 

Let’s see the behavior of customers after grouping trips by weekday. The program gets more usage on weekdays than on weekends. The weekday trips are overwhelmingly driven by subscribers, but the weekend trips by customers outnumber the weekend trips by subscribers.  

![Trips by Weekday](/Pic/Trips%20by%20Weekday.png) 

If we look at trips by hour of the day, weekday riders, most of which are subscribers, primarily use bikes to commute to and from work, with peak hours from 6–10 AM and 3–7 PM. On the other hand, surprisingly subscribers and customers both prefer a more leisurely schedule, with most weekend rides occurring in the mid afternoon hours: 

Left Figure:  Trips by hour -Weekend             |  Right Figure: Trips by hour -Weekday
:-------------------------:|:-------------------------:
![Left Figure:  Trips by hour -Weekend](/Pic/Trips%20per%20hour-Weekend.png)  |  ![Right Figure: Trips by hour -Weekday](/Pic/Trips%20per%20hour-Weekday.png)
                         
From these usage behaviors in right figure, we can clearly say that subscribers and customers are commuters and tourists, respectively. 

![Trips per duration(hour)](/Pic/Trips%20per%20duration(hour).png)

Let’s see trips group by duration(hour). The chart shows that all riders intend to drive in a short time. Almost all subscribers use the Bike less than 1 hour. The trips lasting more than 1 hour are basically used by customers. 

![Trips per duration(min)](/Pic/Trips%20per%20duration(min).png)

Now group trips by duration(min). It’s obvious to see the subscribers take the bike mostly less than 30 mins. The most common duration that subscribers ride is 5-10 min. The trips by customers fall along a long-right tailed and bell-shaped distribution. Most customers also ride the Bike less than 30 min.
 
Combined that information above, I recommend construct a price plan by subscriber type and duration. For example, we can offer the subscriber unlimited 45-mintue trips at any price less than (the price per day*365 days) and penalty the trips who is longer than 45 minutes. For customers, we could offer unlimited 2 hours pass over a whole day or a 24-hour period.

### Stations and Bikes - Where is the Bike used and where do riders go? Which bikes are used?

The usage behavior between subscriber and customer is quite different, which lead to the stations are unbalanced. In other words, the logistic of running a bike share system is make the Bike available in each station.  If station A starts the day with lots of bikes, but people take them out to other stations and nobody returns any bikes to A, then A will run out of bikes. Therefore, the transportation of bikes between stations is important.  

![](/Pic/Figure10.png)

The first figure is top 10 most popular start station for the customer and the second is that for subscriber. The size of circle is the number of trips. The bigger the circle is, the more trips the start stations have. (Those figures are not in the same scale. Be cautious to compare those figure by size of cycle.) 

The top 10 most popular start stations for the customer shows customers heavily use start stations along the seashore and stations near lots of places of interest in downtown. However, start stations where subscribers, known as commuters, pick up the Bike are in the southeastern part of SF, where the place the commuter works nearby. 

The data offer me a chance to measure the throughput of stations by calculate the difference between the Bike departing and the Bike arriving in same station.

Recall 74.3% of trips are took by subscriber in San Francisco. Subscribers almost use to the Bike commute in weekdays with peak hours from 6–10 AM and 3–7 PM. The big traffic would be alleviated if the Program could transport the bike on advance. 

To monitor the stations’ throughput and the riders’ behavior hourly, I develop the tools in Tableau. Those are interactive graphs which you can play around.

Here are screenshots of ‘Hourly Throughput’ in ‘BAB-Books2’.

![Diff between in and out 6-10 am](/Pic/Diff%20between%20in%20and%20out%206-10%20am.PNG)

This picture shows the throughput of each station by subscriber from 6–10 AM. The red/pink circle in the picture means more bikes picked up than bikes dropped in the station. The blue circle means more bikes dropped than bikes picked up in the station. Size of circle is the amount of throughput.

It’s obvious to see those red stations are in the walking distance of Caltrain, BART stops and Ferries. 
 
![Diff between in and out 3-7pm](/Pic/Diff%20between%20in%20and%20out%203-7pm.PNG)

Similarly, this picture shows the throughput of subscriber in each station from 3–7 PM. 
 
Those stations near Caltrain, BART stops and Ferries turn blue. That means off-work Subscriber all move to Caltrain, BART stops and Ferries.

Here are screenshots of ‘Throughput by days’:  

![Throughput%20by%20days.PNG](/Pic/Throughput%20by%20days.PNG)

Columns are stations. Rows are throughput along month (this metrics could be changed to day/year by right clicking the button in blue square and selecting month and day).  This chart shows the daily throughputs by hours for each station in weekday are similar, while the daily throughputs by hours for each station in weekends vary every day.  
 
 ![](/Pic/test2png.png)
 
This figure is the frequencies plot of trips by bikes. A half of bicycles were used in average 74 times and another half around 470 times. In the ideal case (all bicycles are used equally often) each bicycle would be used 332 times.

### Recommendation

Hence, I suggest transport the Bike twice a day to solve the traffic problem. The first transportation time is the noon between 10Am and 3pm when we move the Bike from stations near Caltrain, BART stops, and Ferries to nearby stations. In the night after 7pm, the program should start to move the Bike to stations near Caltrain, BART stops, and Ferries from nearby stations so that the morning commute traffic next day.

For the unbalanced bicycles usage, I recommend bicycles heavily used in areas with high traffic should be moved to stations with low traffic, while bicycles which are almost new should be moved from stations with low traffic to stations with high traffic. Although moving bicycles is a cost, in my humble opinion, the right way to do this transfer is to do it along the regular bicycle transfer caused by imbalanced stations usage.

Several dimensions were not explored in this analysis. One is the influence of weather. My guess that customers are more vulnerable of weather than subscribers. We can combine the weather factor into analysis to predict the traffic in the future. Another one is the popularity of each station among subscribers vs customers. Bikes are better local substitutes of other transportation tools. According to the behavior of customers vs subscribers described above, we could identify stations more popular with tourists or with commuters and potentially identify areas of the city with demand for future stations. The other one is the terminal in each station. The unbalance usage shows in stations and bike. It might show in terminals as well.  
