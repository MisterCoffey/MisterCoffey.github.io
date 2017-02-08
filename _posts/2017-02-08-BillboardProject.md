---
layout: post
title: Is Song Length the 'Key' to Chart Success?
---

Does the length of a song hold the secret its success on the Billboard charts? The results are inconclusive, but there was a big difference between the length of rock songs in 2000 when compared to other genres.

Song length was not correlated to Billboard chart success in 2000. In fact, the only strong correlations were between chart positions in adjoining weeks, as demonstrated by the heat map below.

![heatmap](../images/Project2Billboard/Heat_Chart.png)

In 2000, a song was more likely to enter the charts at No. 80 than any other position. This makes sense as one would expect a song to enter towards the bottom and climb to the top.

![heatmap](../images/Project2Billboard/Histo.png)

There were of course exceptions to this rule.

Santana's 'Maria, Maria' entered the charts at No. 15, making it an outlier in terms of its initial chart position. Surprising perhaps, but consider at that point, Santana was a Woodstock legend with roughly 30 years of recording experience.

![heatmap](../images/Project2Billboard/woodstock.png)

Still, was there anything different about 'Maria, Maria' when compared to other songs?

Indeed. 'Maria, Maria' was longer than the average hit song in 2000; it was over 15 seconds longer to be precise. Moreover, 'Maria, Maria' was longer than over 50 percent of all songs that charted in year 2000.

![heatmap](../images/Project2Billboard/MariaMariavMean.png)

This begs the question of whether rock songs that charted in 2000 were different in terms of length when compared to other genres.

The mean of rock songs on the Billboard chart was 242.43 seconds. The mean of all other genres excluding rock was 238.52. A frequentist hypothesis test tells us that there is a statistically significant difference in these means.

Hit rock songs were simply longer on average than all other hit songs.

![heatmap](../images/Project2Billboard/HypothesisTestMeans.png)

So did the length of a rock song contribute to its success in 2000? It's impossible to draw a causal conclusion, as this analysis is based on observational data. Moreover, The Billboard 100 chart did not include songs that did not chart, making a comparison impossible. Nonetheless, the possible predictive value of song length is worth greater exploration.
