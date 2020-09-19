# Kickstarting with Excel

## Overview of Project

We pulled data from Kickstarter to look at their whole set of campaigns and determine factors of success. Given Fever's 
current success, likely to approach its goal, we take a dive in this data to see what conditions can benefit or detriment 
other Kickstarter campaigns.

### Purpose

The purpose of this analysis is to determine how likely a Kickstarter campaign is to succeed in relation to its launch date
and the campaign goal. 

## Analysis and Challenges

For the short of it, campaigns that start in the late spring/early summer have the highest rate of success. Also, campaigns
that have more reasonable goals, less than $5000, have a higher likelihood to succeed than those with higher goals. For a 
challenge we faced, while some observations in our data set may prove otherwise, there are not enough observations at those 
higher goal values to determine if their success truly reflects reality.

### Analysis of Outcomes Based on Launch Date

!Resources/Theater_Outcomes_vs_Launch.png

To create this graph, we formed a PivotTable where we observed the number of instances of outcomes between success/failure/canceled
and compared them to the campaign start date. We see here that campaigns that start in the late spring/early summer are more
likely to succeed than campaigns that start during the traditional holiday season (Nov/Dec). 

### Analysis of Outcomes Based on Goals

!Resources/Outcomes_vs_Goals.png

To create this graph, we looked at Campaign Goal amounts and grouped them up itno an interval as defined in the graph. We
then within each Goal group, we saw what percent of campaigns were successful, which ones failed, and which were canceled.

A `=COUNTIFS` formula was used to determine how many instances of success/failure/cancelation occurred within each goal 
interval like so: 

=COUNTIFS(Kickstarter!$D:$D, "<1000", Kickstarter!$F:$F, "successful", Kickstarter!$O:$O, "plays")

We would take our main Kickstarter sheet, define the goal range, its outcome, then stratify our data specifically to the 
plays subcategory.
 
We found that for plays, we had zero instances of cancellations. We however, do see that for smaller 
campaign goals, it does meet with a higher likelihood to succeed. This may be a contradiction based on seeing the higher 
goal amounts observe a higher success rate. This situation is explained in the next section. 

### Challenges and Difficulties Encountered

In observing the Outcomes Based on Goals data, for the lower goal values followed that of a skew right distribution until
we get to the $35000-$45000 goal marks when the success percentage shoots up, then drops back down outside of the range. 
For this set of the data, we have a limited amount of observations (n < 10) so it's difficult to tell if fundraisers with 
goals in this dollar range are properly represented. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
The launch date of a Kickstarter campaign plays a major role in determining the likelihood that the campaign succeeds. 
For the months of May and June, Kickstarter campaigns observed the highest rates of success while a campaign that started in 
December had more of the lowest. To be specific, a campaign whose start day fell in May (111 successes) had three times more 
successes than ones that started in December (37). Late spring, early summer would be the best time to start a campaign. If 
a campaign holds off til winter, their campaign may be trapped under ice, starved of pledges. 

- What can you conclude about the Outcomes based on Goals?
Another important factor in determining the success of a Kickstarter campaign is its goal amount. If the goal is too high, 
prospective pledges will be less likely to donate, leading to the demise of a campaign. Campaigns with a goal of less than
$5000 had over a 73% success rate. As the goal amount increased, the success rate formed an inverse relationship with it, 
decreasing in value significantly, to a certain point...

- What are some limitations of this dataset?
To our Outcomes Based on Goal data, there are a few successful campaigns that have a high success rate in the upper ranges 
with goals of $35000-$45000. The thing to consider there however, are the frequency of those campaigns. We do not have a 
large enough sample size within that goal range to determine if the success rate observed in this data set truly reflects 
reality. 

- What are some other possible tables and/or graphs that we could create?
To the Outcomes Based on Goal graph, if there was another graph that could include the number of backers + average donation
per campaign that could potentially paint a more complete picture of not only what drives are lower goals, but also could better
explain the reason behind the success rate of campaigns with higher goals. 
