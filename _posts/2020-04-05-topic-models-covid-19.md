---
title: "Topic Models: COVID19 on Twitter "
date: 2020-04-05
tags: [text analysis, social media analysis, topic models, twitter]
header:
  image:
excerpt: "Topic Models Analysis of COVID19 discourse on Twitter"
---

# How are people talking about COVID19 on Twitter?

## Descriptive analysis

For this analysis I scraped over 100,000 tweets with the word "coronavirus" that were made in English on Twitter between 01:00 GMT on April 4th and 02:30 GMT on April 5th.  After stemming words to their root characters and removing the obviously dominant terms ("coronavirus, covid" etc.), here is a word cloud of the most common two word phrases:

<img src="{{ site.url }}{{ site.baseurl }}/images/bigrams.png" alt="bigram wordcloud">

Not surprisingly, "new cases", "stay home", and "social distancing" were among the most commonly used two word terms. However, there is a lot more to unpack how information about the virus flows through the platform.

## Topic models

In order to determine the various topics that are prominent in the discourse, I ran a structured topic models analysis on the Twitter dataset. The model segregated the dataset into 10 different thematic clusters. Here are the single words most likely to be unique in each cluster (I provided the titles).

* **Topic 1 (Trump/Presidential Politics):** trump, realdonaldtrump, presid, america, lie, cnn, real, god, question, potus
* **Topic 2 (Aid and Assistance):** help, govern, busi, ventil, donat, food, money, communiti, economi, plan  
* **Topic 3 (New Cases and Deaths):** tcase, death, new, report, total, updat, number, coronavirusoutbreak, confirm, itali  
* **Topic 4 (Predictions):** still, may, year, put, chang, end, done, forc, leader, expert  
* **Topic 5 (Information Flows):** social, read, human, find, inform, stori, fear, advic, children, articl
* **Topic 6 (Personal Protective Equipment):** mask, wear, face, protect, worker, cdc, suppli, ppe, chines, wuhan
* **Topic 7 (Hospitals):** week, hospit, two, nurs, travel, symptom, treatment, drug, research, treat
* **Topic 8 (Stay Home and Social Distance):** home, stay, quarantin, stayhom, pleas, socialdistanc, safe, stayathom, love, stayhomesavel
* **Topic 9 (Imperatives):** get, just, know, right, even, thing, talk, better, believ, mean
* **Topic 10 (Spread in India and Africa):** vaccin, light, polic, africa, narendramodi, minut, indiafightscorona, name, indian, street

Now that the dataset has been modeled into different topics, we can ask some interesting questions.

### How are the topics related? Which are the most distinct and unique?

<p align="center">
  <img width="400" height="400" src="{{ site.url }}{{ site.baseurl }}/images/topicplot.png" alt="effect of topic on retweeting">
</p>

A network analysis of the topics reveals that the topic of PPE (topic 6), as well as the spread of the virus in India and Africa (topic 10), are the most distinct topics in the list. This just means that they are standalone areas of discourse which are discussed with a cohesive and unique vocabulary. Topics 3 and 7— hospitals and new cases, respectively— are closely linked topics. The rest of the topics are clustered together and have a much higher overlap in terms of thematic vocabulary.  

### Which topics are the most likely to get retweeted?

<img src="{{ site.url }}{{ site.baseurl }}/images/retweeteffect.png" alt="effect of topic on retweeting">

It appears that tweets about new cases and deaths are the most likely to get retweeted, with a statistically significant nonzero positive effect.

Tweets about staying at home and social distancing are, unfortunately, the least likely to be retweeted, and actually have a negative effect on the likelihood of a retweet. On this topic, the results also statistically significant.

Interestingly, discourse about the spread of the virus in India and Africa was statistically likely to improve the chances of a retweet. I was not aware of how the virus was spreading in those continents (well, one sub-continent technically) prior to this analysis. After being alerted to this issue in those places, further research revealed that the virus is indeed
beginning to spread rapidly across both areas.

### Which topics are the influencers more likely to tweet about?

<img src="{{ site.url }}{{ site.baseurl }}/images/influencers.png" alt="effect of topic on retweeting">

Here, I consider influencers to be accounts that have high numbers of followers. It appears that influencers also are also most likely to tweet about new cases and deaths. However, high-follower accounts were not likely to tweet about the spread of the virus in India and Africa, which could indicate that many tweets about that topic were coming from smaller accounts trying to get the word out.

Thanks for reading through my example of how to combine social media data and a structured topic models analysis to glean some interesting things about the COVID discourse.

Here is [the link](https://github.com/KevinEduardoKarl/text-analysis/blob/master/COVID%20Discourse%20on%20Twitter.R) to the some of the R code I used for this analysis.
