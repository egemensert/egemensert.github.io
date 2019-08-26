---
layout: post
title:  "<span style='margin-bottom:-0.7em; display:block; font-size:32px;'>Characterizing Political Participation, </span><span style='font-size:20px; display:block; margin-bottom:-1.33em;'> Turkish Parliamentary Elections as a Case Study </span>"
date:   2019-08-26 18:08:22 +0200
categories: politics turkey
#feature_image: "https://picsum.photos/2560/600?image=872"
---

<style>
.footer a {
  color: white !important;
}
.footer {
  background-color:#202A4F;
}
.nav a {
  color:#202A4F;
}
.item.item--nav a {
  color:#202A4F;
}
.footer small {
  color: white;
}
a {
  color:#202A4F;
}
</style>

<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

Democracy is government by the people. Ideally, people choose their representatives
based on evaluating the candidates' agenda and determining which candidate is the best for them.
However, choosing the best candidate based on individual efforts is tiresome.
In practice, people gather in friends and family meetings and share
their political thoughts stemming from individual thinking,
people's social network and media. Consequently influencing and getting influenced
via the social network and media.

As people get influenced by the media, tailored propaganda can skew political
thought in public. If this media hold easily shareable, emotional messages, this skewing action might evolve
into a political epidemic, and in return skew public thought drastically towards the desired political
direction. This process may lead to a party gaining vast majority of votes in a region,
thereby having the same echoing thoughts getting reinforced (echo chambers)
and consequently having extremist polarization. Although measuring how media influences
voters is a cumbersome task, we can measure the vote-wise dominance of a party at a region
with a simple metric.

In this blog post, we present two metrics to measure a region's variety in political thought
and divergence of political behavior of one region from another region based on election results.
Variety is measured by the normalized entropy and divergence is measured by the Kullback-Leibler
divergence (metrics widely used in communications and computing). Let's start with the normalized
entropy.

{% raw %}
  $$ \color{#242e2b}{H(P) = \frac{1}{log|P|} \sum_{p \in P} p ~ logp}$$
{% endraw %}

<center><img src="/assets/cases.png" width="400px" height='250px'></center>

Mathematically, what entropy measures is the average randomness of a random variable. In our case,
entropy measures the average variety in political thought given a sample of voters.
Figure above illustrates two extreme cases of entropy. Colors indicate parties. In Case 1,
each party receives equal votes. If we take 100 people, we expect each party to have equal
amount of (25) supporters. This case has an entropy of 1, where the randomness or variety in
political thought is maximum. In Case 2, the green party dominates all the votes. So regardless
of how many people we take, they will all support the green party. This case has an entropy of 0,
where there is no randomness or variety in political thought.

{% raw %}
  $$ \color{#242e2b}{KL(P || Q) = \sum_{(p, q) \in (P, Q)} p ~ log \frac{p}{q}}$$
{% endraw %}

KL divergence measures how far a distribution (P) is from the reference distribution (Q). We will
use this metric to measure how different a province's political thought from the country-wide
political thought. If KL divergence is low, then province's thoughts are not much different
from the country-wide thought. If high, then country-wide thought is insufficient in explaining
the province's thought.

<h5>Use Case: Turkey</h5>
Let's try our metrics on Turkish Parliamentary Elections. Turkey is a country where Secular/Conservative,
Turkish/Ethnic debates are prominent. Each part of the debate has one or more parties associated with it.
We will not describe which party is associated with which debate in order not to skew the analysis.
Yet it is important to note that where a party lies on the Secular/Conservative-Turkish/Ethnic axis is
a key decision variable for voters.

<center><img src="/assets/histogram.png" width="450px"></center>

<span style='font-size:14px; color:gray'>
<b>Figure 1.</b> Entropy and divergence histograms. Month and year of
each election is labeled on the left vertically. Left panel includes city-wide entropy histograms
of each election since 2002 and right panel include each city's divergence from that election's country-wide
political thought. Red dashed vertical lines denote the average entropy of the election.
Histograms are colored by the average entropy of the respective year's election. Darker red denotes lower average variety in that year's election.
</span>

We observe that Turkish variety in political thought declined until 2018 elections where October 2015
election has the lowest average variety. In 2018, average variety increased for the first time since 2002.
But average variety is not the whole story. 2018's variety distribution is bimodal. That is, some of the cities,
has average variety around 0.5 whereas some has around 0.65. We will talk about the bimodality
in the next section. Let's focus on the divergence now.

Each divergence histogram is concentrated close to zero. It is okay. We expect most of the cities to have
political thought distribution close to the country-wide thought. In the end, cities' collective decision forms the
country votes. Importance is in the tail of these distributions, magnified in little
rectangles. Tail distributions indicate the amount of marginal thoughts. We can see that between 2007 and 2015, there were
greatly marginal cities. In 2018, this marginality reduced in magnitude but the amount of marginal
cities remained to be substantial. This is also associated with the bimodality. Let's investigate it.

<h5 style="margin-bottom:0.7em">Bimodality in 2018 Elections</h5>

<center><img src="/assets/entropy_vs_divergence.png" width="500px"></center>

<span style='font-size:16px; color:gray'>
<b>Figure 2.</b> Scatter plot illustrating each city on a entropy versus divergence plot. Vertical scale denotes variety,
increasing with height. Horizontal scale denotes divergence, indicating marginality as shifted towards right.
Each point's size is proportional to the city's log voter population and each point is colored by the party
having majority of the votes in the city. Ankara, the capital city of Turkey, is denoted in yellow star.
</span>

We can see that either AKP (ruling party) or CHP (main opposition party) has the majority of the votes in most
of the mainstream cities. Whereas, HDP has most of the marginal cities. Cities with larger voting
population have greater variety compared to smaller ones. We see lower variety thoughts are concentrated
on cities with AKP or HDP majority. Suggesting, these parties have strong vote basis in their respective
cities. By investigating the scatter plot, we can see, mainly, HDP majority cities create the
bimodality in 2018 elections. Choropleth maps can help us identify the spatial patterns of the bimodality.

<h5 style="margin-bottom:0.7em">Bimodality on the Map</h5>
<center><img src="/assets/entropy.png" width="500px"></center>

<span style='font-size:16px; color:gray'>
<b>Figure 3.</b> Map of Turkey colored by the city entropies of 2018 election. Darker green indicates high variety,
yellow indicates average variety and darker red indicates low variety.
</span>

Map illustrates that the western Turkey is richer in political variety compared to
the rest of the cities in the country. On the other hand,
the southeastern part of Turkey advocates for fewer types of political thought.

<center><img src="/assets/kl.png" width="500px"></center>
<span style='font-size:16px; color:gray'>
<b>Figure 4.</b> Map of Turkey colored by the city divergence. Divergence of 0.1 is assumed to be the midpoint between modes (colored in white) and any value less than 0.1 is colored in red and greater than is colored in blue.
</span>

Figure 3 and 4 show that both the high and low variety cities cluster spatially. Also, southeastern region
has a different political character that cannot be explained by the average political variety in  Turkey
and the region advocates for this strongly. Let's try to identify why.

<h5 style="margin-bottom:0.7em">Factors Influencing the Entropy and Divergence</h5>
<center><img src="/assets/population.png" width="800px"></center>

<span style='font-size:16px; color:gray'>
<b>Figure 5.</b> First row of the figure
indicates entropy versus log Voter Population, Median Annual Disposable Income and Gini Index where the last two variables are obtained
from the Turkish Statistical Institute (TurkStat) 2017 data. Second row indicates KL divergence versus the mentioned variables. Each dot indicates a city.
Trends of each subfigure is illustrated with colored lines. Color is based on the majority party in the city.
 Symbol $$\color{gray}r$$  denotes the correlation coefficient between variables, e.g. {% raw %} $$\color{gray}{r_{AKP}}$$ {% endraw %} of subfigure in first row & column
indicate the normalized correlation between entropy and log voter population. Perfect positive correlation is indicated with a
value of 1, negative correlation is indicated with a value of -1 and no correlation is indicated with a value of 0.
Symbol {% raw %} $$\color{gray}{R^2}$$ {% endraw %} indicate the goodness of fit of the lines, value of one indicates
a perfect fit. Over the figure, correlation values are high in magnitude but goodness of fit is low, indicating that there
is a strong positive or negative relationship between variables, but not linear.
</span>

According to the first column (horizontal axis is log scale), as voter population increases, political variety increases for AKP and CHP majority cities. On the other hand, political variety decreases with increasing voter population in HDP
majority cities. Divergence of AKP and CHP majority cities decrease as voter population increases and vice-versa
for the HDP majority cities.

MADI is the amount of personal income after tax deduction. For AKP and HDP majority cities,
political variety increases as MADI increases and vice-versa for CHP. That is, AKP and HDP has stronger vote basis in cities with lower MADI, and CHP holds a stronger vote basis in cities with high MADI. As MADI increases, divergence of HDP majority cities reduce greatly. This trend is also followed by AKP majority cities but with less slope. Finally, CHP majority cities' divergence increases with increasing MADI.

Gini Index is used to measure the income inequality. Lower values indicate better income equality.
Variety of AKP majority cities increases with higher Gini Index and vice-versa for CHP and HDP. Suggesting AKP voting
basis is concentrated on cities with better income equality. HDP majority cities' divergence increases drastically with
lower income equality. This trend is also followed by CHP but with less slope, vice-versa for the AKP.


<h5 style="margin-bottom:0.7em">Conclusions</h5>
Entropy and KL divergence are two metrics that can explain voter variety of countries, irrespective
of the parties and spatial scale.

Analysis on the Turkey shows western coastal regions of Turkey has
high political variety. Central Anatolian regions have medium variety and southeastern regions have low
variety, compared within Turkey. Moreover, southeastern region has drastically different voter profile
compared to the country-wide votes.

When variety of AKP majority voters is compared to Voter Population, MADI and Gini Index, we see that AKP's variety
increases with larger voter population, greater MADI and worse income equality. CHP's variety increases with larger
voter population, lower MADI and with better income equality. HDP's variety increases with smaller voter population,
greater MADI and better income equality.

Since AKP is the ruling party and CHP is the main opposition party, AKP and CHP majority cities have low divergences.
On the other hand, HDP majority cities' divergences are substantial. What can minimize the divergence of HDP are having
a smaller voting population, greater MADI or better income equality.

Assuming lower overall divergence increases country-wide political harmony, it is advised for Turkish policy makers to
focus on policies that would increase the MADI of southeastern region while assuring better income equality.

<h5 style="margin-bottom:0.7em">Caveats</h5>
This study is a reductionist one. Politics of Turkey is a complex system where individuals vote based on intricate social decision making. These results are found by analyzing three decision variables. The reality is associated with much more and there is no guarantee on these three variables being the ones that explain much of the variance.

Even assuming these three variables are the ones that perfectly explain city wide voting variety and divergence for 2018
elections, there is time and scale associated with this system. How variety in a district or neighborhood is affected is
still unknown and how the found relationships change over time (dynamics) is still a mystery. Therefore, since this post
is about a social system, please remember that this post does not show how the system works, but is a mere proxy for it.

Thank you for your time.
