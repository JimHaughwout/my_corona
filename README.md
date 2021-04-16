# My Corona
When searching on COVID data for my local neighborhood in NYC (Hell's Kitchen), I noticed that the NYC government was nice enough to put all of their data [online, on Github](https://github.com/nychealth/coronavirus-data). As I was stuck in quarantine and could not find an easy chart of my local data, I thought I would create my own. Here is the code to produce the analysis.

## Update
Over time, I updated this to include both a standard linear analysis as well as a log-over-log visualisation to easily detect when NYC would "bend the curve" of exponential growth. I wound up using these analyses to help pick where I lived.

### CTA vs. Borough vs. City
The notebook allows you to pick a NYC CTA (by ZIP code) and compare case rates at by CTA to its borough and the city overall. The data available for this is reported weekly, allowing a basic linear analysis. Here is an example:

![CTA](https://github.com/JimHaughwout/my_corona/blob/main/example-linear-CTA-trajectory.png)

Note: The code has both interactive plots, tables, and other aggregate snapshots.

### Detecting Exponential Growth (or Decline)
It is hard to detect when exponential growth slows to just non-exponential growth. [Aatish Bhatia](https://aatishb.com/covidtrends/) came up with a simple visualisation for this, plotting the log of growth (7-day average) over the log of total cases. As none of these analysis were available at the city level, I created one. The NYC open data set allowed me to create this at the City and Borough levels. Here is an example, captured 10 days after my second vaccination shot: 😀💉

![exponential](https://github.com/JimHaughwout/my_corona/blob/main/example-log-log-trajectory.png)

You can see how Manhattan has broken the exponential surge of growth that started around November 2020.

Note: The code does this for case rate, hospitalisation rate, and death rate. 
