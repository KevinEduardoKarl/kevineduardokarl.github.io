---
title: "New Clusters in the City: The Five Boroughs of NYC by Well-being Data"
date: 2020-04-07
tags: [exploratory analysis, data visualization, machine learning]
header:
  image:
  excerpt: "The five unique paths of NYC neighborhoods since 2015"
---

# What would the five boroughs in NYC look be if you clustered them based on how well they have fared since 2015?

In this analysis, I explored a dataset of well-being indicators broken down by Neighborhood Tabulation Areas ("NTAs") in New York City. NTAs are a geographical unit that more or less resemble what a resident would call their neighborhood. Examples would be: Lower East Side,
Flushing, or Prospect Lefferts Gardens. Where neighborhoods are quite large and possess two unique areas they are split in two: e.g. Crown Heights North and Crown Heights South.

The indicators that I examined were taken from the Wellbeing Index, a composite of many different data sources about each NTA in one place. In the Wellbeing Index, there are 5 main domains: Economic, Education, Health, Housing, Security, Safety, and Infrastructure. Each domain is composed of a number of indicators, for example, the Housing domain contains data on the % of the population that is rent-burdened and the % of homes that are overcrowded.

The data used here is the % change of each indicator between 2015 and 2019.

### Correlation Plot

To get a snapshot of how these domains might be correlated with each other, I put together a quick correlation plot:

<img src="{{ site.url }}{{ site.baseurl }}/images/corplotcity.png" alt="correlation plot by domain">

While economic and housing indicators were correlated with the overall wellbeing score, the domains themselves were not correlated with each other. Education and economic indicators were very weakly positively correlated with each other (Pearson correlation coefficient = 0.34), but that is not really a finding worth writing home about.

### Borough Snapshot

To get a stronger sense of what is going on at a borough level, I filtered the data to look at all of the indicators stacked up on top of each other in the Bronx.

<img src="{{ site.url }}{{ site.baseurl }}/images/bronxchange.png" alt="bar graph bronx wellbeing indicators">

The NTAs are ordered by negative change to positive change since 2015. One interesting thing to note is that the Health domain has decreased in practically all of the NTAs since 2015. For the NTAs who experienced the most negative change, it appears that decreases in the Housing and Infrastructure domains are some of the biggest issues facing them. For the highest few NTAs, a combination of improvements in the Safety and Economic domains seem to propel them into a higher level of overall wellbeing.

## Five New Boroughs, a Clustering Hypothesis

A borough by borough analysis is an interesting way to compare neighboring areas to each other, but a clustering analysis could be a useful way of trying to tell a few different stories about how NTAs in New York City have changed since 2015. Here I used K-means clustering to segregate the NTAs into 5 different clusters.

<img src="{{ site.url }}{{ site.baseurl }}/images/fivenew.png" alt="kmeans clustering based on wellbeing indicators new york city data">

This image places all of the NTAs into clusters based on the K-means algorithm, and leads to some fascinating results:
* **Cluster 1, Safer and More Prosperous:** In this cluster (n = 39), NTAs have made the most progress on Economic, Education, and Safety indicators of all of the clusters. Their average overall positive change since 2015 is also the highest. Examples of neighborhoods in this cluster are: Astoria, Bushwick North & South, Crown Heights North & South, Hell's Kitchen, Hunts Point, Williamsburg, and Washington Heights, to name a few. 24 out of the 39 NTAs are in Brooklyn.
* **Cluster 2, Getting Healthy but still Housing-burdened:** In this cluster (n = 31), NTAs have made the most average progress on Health, but also show the highest decrease in the Housing domain. Their average overall positive change since 2015 is second lowest. Examples of neighborhoods in this cluster are: Greenpoint, Kew Gardens, Washington Heights North, Borough Park, Maspeth, and Inwood. These neighborhoods are split across the boroughs.
* **Cluster 3, Improving Health and Economic Standards, but with degrading Infrastructure:** In this cluster (n = 37), NTAs have made considerable progress in both Health and Economic indicators, however they are decreasing along the Infrastructure domain. Examples of NTAs in this cluster are: Chinatown, Jackson Heights, Ridgewood, and Central Harlem.
* **Cluster 4, Becoming Safer, but that's about it:** In this cluster, which is by far the largest (n = 61), NTAs have made considerable progress in Safety, and mild progress on Economic indicators on average. However they are seeing significant average downturns in  Infrastructure, Housing, and Health. Examples of NTAs in this cluster are: East Harlem North & South, Lower East Side, Flushing, and DUMBO.
* **Cluster 5, Infrastructure All Stars:** This is the smallest cluster (n = 20), which has the second highest Wellbeing score overall. NTAs here have made considerable progress in developing Infrastructure, which coincides with the only cluster to show a marked improvement in Housing on average. All other indicators point up as well.,  Examples of NTAs in this cluster are: Soho, East Village, Ocean Parkway, Maspeth, and Canarsie.

Here is a summary of the clustering statistics:

<img src="{{ site.url }}{{ site.baseurl }}/images/clusterstats.png" alt="k-means cluster statistics wellbeing indicators">

### Future Inquiry

Clustering NYC neighborhoods based on their Well-being Index data is just the beginning step that can open the door to important further research questions. How can we better understand the relationships between these incredibly unique and different neighborhoods that have been grouped together? Pulling in other sources of data on these neighborhoods, including qualitative research with informed stakeholders, might expose some challenges and opportunities that these neighborhoods—which can seem to be vastly different— face in common.
