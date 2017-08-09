---
layout: post
title: Launching a Successful Kickstarter Campaign
---

**When in Doubt Dance**

Want to launch a successful Kickstarter campaign? Follow these tips and you are more likely to succeed than not.

**Introduction**

[Kickerstarter](https://www.kickstarter.com) is a popular site for raising money for creative projects. People pitch their film or music project to the Kickstarter community, set a monetary goal and hope for the best. Sometimes the campaigns are successful, other times they are not.

I prepared this analysis in R as part of a fellowship in data science at General Assembly. The data contained information on successful and unsuccessful campaigns from 2009 t0 2012, including the category of project, the timeframe, funding information, and location among other things.

**Kickstarter Tip No. 1: Keep It Short**

Your Kickstarter campaign should run about a month. This is because successful campaigns are on average shorter (31 days) than unsuccessful ones (42 days).

This difference in the average duration of successful and unsuccessful campaigns is statistically significant.  Whether we implement a frequentist Welch's t-test (p-value = 2.2e-16), or utilize Bayesian hypothesis test (Bayes Factor (BF[H2:H1]) = 3.054464e+280), the length of a successful campaign is not equal to the length of the unsuccessful campaign. In fact, successful campaigns are demonstrably shorter.

![Duration](../images/Kickstarter/GADur.png)

My advice is to use the median duration of a successful campaign as a guide -- 31 days -- as the data is not normally distributed and is slightly right skewed, as demonstrated by the above graph.

This is not to say that a longer duration causes campaigns to fail. As discussed below, successful campaigns typically ask for lower funding, making it easier to reach a goal in 31 days. Set a high goal, and it will be very difficult to meet your goal in 31, let alone 42 days.

**Kickstarter Tip No. 2: June Is The Cruelest Month, Not April**

If you are to launch a 30 day campaign, consider launching it on April 2nd or 3rd. Do not launch it in May. This is because March, April & May are the most popular months to obtain funding on Kickstarter.  May is the most popular of all, and June is the least popular.

Furthermore, the first & second of the month are the most popular funding days. By launching at the beginning of April, you can take advantage of this phenomenon. By avoiding a May launch, you avoid ending your campaign in June, which is unpopular.

![Months](../images/Kickstarter/GAmonths.png)

*(May is the best month to end a campaign; June is the worst)*

The reasons for the May/June discrepancy are beyond the musings of this post. One thought is that tax refunds put people in a more charitable mood. Another is that June is the beginning of summer and people are funding vacations over Kickstarters. I could not tease a good theory out of the data.  

**Kickstarter Tip No. 3: Lower Your Expectations"**

Successful campaigns set lower goals. A goal of $3,000 is a terrific place to start as this is the median for successful campaigns. Unsuccessful campaigns in contrast have a higher median of $5,000, with an mean of $16,351.

**Kickstarter Tip No. 4: The More Levels the Better**

Kickstarter allows participants to set different levels of support. Successful campaigns have a mean of eight (8) and median of seven (7) fundraising levels. The distribution is extremely right skewed, making the median a good place to set levels. There is no downside to setting a few more levels, so feel free to set ten (10) if you think it helps.

**Kickstarter Tip No. 5: Money Loves Music, Movies, Design & Games**

Film, music, design and game projects attract the most funding on Kickstarter, but launching a campaign in these areas does not guarantee success. You are more likely to win a coin toss than you are to win funding for your film project.

Our dataset contains over $50m in successful film campaigns, and over $36m in successful music projects. Though film attracts the most funding, it is less successful than  has the higher rate of success than film. Though 62% of music campaigns are successful, less than half of all film (47%), design (41%) & game (36%) campaigns are successful.

![Catgories](../images/Kickstarter/GAPlot.png)

*(Most Kickstarter campaigns are film related, though there are more successful music related campaigns than film. Notwithstanding the lower film success rate, film projects still raise more money than music projects. Notice the success rate of dance related campaigns)*

**Kickstarter Tip No. 6: Publish and Perish**

Publishing is the third most popular Kickstarter category. Unfortunately, publishing has the second lowest success rate (35 percent). Need help publishing a book, don't expect success on Kickstarter.

**Kickstarter Tip No. 6: When in Doubt Dance**

Dance is the least funded category on Kickstarter, but it has the highest success rate (69 percent). In fact, art, music, theater & dance are the only categories where over 50 percent of campaigns are successful.  

**Kickstarter Tip No. 8: Use Logistic Regression to Predict Whether Your Campaign**

We can build a simple algorithm that predicts the potential success of a Kickstarter campaign with 68 percent accuracy.

We model uses logistic regression and simply assesses the probability of whether whether a campaign will successful or not.

We can train a decent the model on the following variables: 1. The category and subcategory of the campaign; 2. The funding goal; 3. the number of fundraising levels; 4. the duration of the campaign; 5. the day the campaign succeeded; and 6. the month the campaign achieved succeeded.

![model](../images/Kickstarter/Model.png)

*(R code for logistic regression model. This model performed 68 percent accuracy on a test set)*

Let's put our model to the test on actual Kickstarter campaigns. I arbitrarily selected two campaigns: *[Love Found]*(https://www.kickstarter.com/projects/makehistory/lovefound-by-jon-rua), a dance project; and *[Renegade Repos]*(https://www.kickstarter.com/projects/1707992326/renegade-repos-web-show?ref=nav_search), a web show.

***Love Found***

*Love Found* is an example of a project with high probability of success. It is a dance project, which always have a high probability of success. The campaign is 30 days in length and sets a reasonable goal of $6,000, with 13 fundraising levels. If you will recall, anything over eight levels is preferable.

![model](../images/Kickstarter/Love.png)

Our algorithm tells us that *Love Found* has a 85 percent probability of success. It would have had an even higher probality of success (94 percent) had it set a goal of $3,000 with more levels, and ended in May.

*Renegade Repo* is an example of a project with a low probability of success. The campaign has features typical of unsuccessful Kickstarters: 1. It is longer than a successful campaign (45 days); 2. it is a video project, which fail more often than not; 3. the fundraising goal is high at $65,000; and 4. it sets fewer than eight fundraising levels.

![model](../images/Kickstarter/Renegade.png)

Our algorithm tells us that *Renegade Repo* has a 3.7 percent probability of success. *Renegade Repo* would have 94 percent probability of success if it: 1. lowered its goal to $3,000; 2. greatly increased its number of fundraising levels; 3. lowered its duration to 30 days; and 4. ended the campaign in early May.
