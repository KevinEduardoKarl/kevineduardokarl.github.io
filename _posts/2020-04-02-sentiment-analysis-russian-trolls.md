---
title: "Sentiment Analysis: Russian Trolls"
date: 2020-04-02
tags: [text analysis, social media analysis, sentiment analysis, twitter]
header:
  image:
  excerpt: "Targeting Tactics and Sentiment Analysis of Russian Trolls"
---

# How did Russian trolling campaigns differ based on the political ideology of the audience?

### Black Lives Matter: Targeting the Right or Left?

In this analysis, I used a dataset containing 10,000 tweets posted by accounts
associated with the Internet Research Agency (IRA, the Russian “troll factory”) between 2014 and 2017.  Each tweet is classified as being either "RightTroll", meaning that they were posted by accounts that targeted the American political Right, or "LeftTroll".

The specific IRA tactics I wanted to examine were any explicitly that referenced the Black Lives Matter movement to impact the 2016 election. The question is whether or not such messaging was used more on the right (perhaps to increase Republican voter turnout), or on the left (perhaps to suppress Democratic voter turnout).

The first step I took was creating a dictionary of 10 words that would be most associated with Black Lives Matter: "black, lives, matter, vote, justice, police, criminal, crime, panther, malcolm, shoot". I then split the tweets by account classification, and looked at the proportion of words in that dictionary that were used by Right Trolls vs. Left Trolls.

<img src="{{ site.url }}{{ site.baseurl }}/images/trolltarget.png" alt="russian trolls using black lives matter by ideology">

Based on the image, it is clear that this tactic was used in higher proportions on the left, in what I presumed to be an effort to suppress Democratic turnout.

### Sentiment analysis

I was also curious about how the emotional tone of the tweets differed based on which political ideology the trolls were targeting. For this analysis, I used the "sentimentr" package and it's embedded emotional vocabulary dictionaries to take a look at how the trolls diverged.

<img src="{{ site.url }}{{ site.baseurl }}/images/trollprofanity.png" alt="russian trolls profanity by ideology">

The first item I was curious about was how much profanity was used on Left accounts vs. right accounts. As you can see, the Left accounts used more profanity on average. Your guess is as good as mine.

In general, I was curious about which emotional tone the trolls struck on the Right vs. the Left. Here is how it breaks down along some core emotions.

<img src="{{ site.url }}{{ site.baseurl }}/images/trollemotions.png" alt="russian trolls emotions by ideology">

Here it is clear that accounts targeting the Right tended to rely on vocabulary that evokes anger, fear and disgust, while Left accounts used slightly more joyous language. Interestingly, the Right accounts also employed language associated with trust more than the Left accounts did. Perhaps they discovered that combining out-group messages (anger, disgust, fear) with in-group solidarity (trust), would make for a potent mix to connect and motivate a Right audience.


Here is [the link](https://github.com/KevinEduardoKarl/text-analysis/blob/master/Sentiment%20Analysis%20of%20Russian%20Trolls.R) to the some of the R code I used for this analysis.
