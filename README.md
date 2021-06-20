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

### A Tale of Two Cities
A finally got around to playing with *BeautifulSoup* to scrape (and clean) data from Sweden's [c19.se](https://c19.se/en/Sweden/Stockholm) site so that I could do some comparitive analysis. NYC cases got a lot of coverage in the news--even though NYC leaned in very hard with restrictions, testing, vaccines, etc. Stockholm got less coverage (as it was far away), even though their approach to COVID was "[unique](https://time.com/5899432/sweden-coronovirus-disaster/)" in terms of policy. 

As a person who not only _lived_ in both cities but also did _intra-city moves_ in both cities during COVID, I lived through both experiences. I had a feeling that one city was more "dangerous" than another (contrary to press coverage and rumour). As such I ran the numbers. Here is a normalised comparison:

![A Tale of Two Cities](https://github.com/JimHaughwout/my_corona/blob/main/A-Tale-Of-Two-Cities.png)

😲 It goes to show that we should trust in data. You can find the source code for this work as two additional notebooks in this repo.

> PS I was still in Sthlm in October. At that point I started to isolate to protect myself. I moved to NYC in November, only catching part of the Q4 2021 COVID wave.

### Mapping Recovery
After NYC re-opened, several people asked me what I was seeing. I added a new notebook that lets one view an interactive heat map (folium choropleth) by zipcode (`MODZCTA`). You can build interactive maps by the count of new cases and rate (per 100K people) of new cases, total cases, and total deaths. Sadly it looks like Hell's Kitchen/Time Square is now the worst place for new cases (per 100K people) after months of being a very safe place ☹️

Here is a screen shot of the latest case rate heat map:

![Choropleth Heat Map by New Case Rate per 100K](https://github.com/JimHaughwout/my_corona/blob/main/choropleth-by-new_case-rate.png)
