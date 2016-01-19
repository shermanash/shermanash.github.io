---
layout: post
title: "Obtaining High-Quality Signatures"
published: true
---






As an exercise in exploratory data analysis, we broke up into groups to obtain, digest, and analyze data in pursuit of our stated objective.  The goal was to use [MTA subway data](http://web.mta.info/developers/turnstile.html), and other sources, to determine where, and when, to optimally place workers in order to recruit potential donors to an event supporting increasing the participation of women in tech.

Our initial reaction was to find the stations with the highest traffic, but we soon realized that high-traffic stations would not necessarily net the most high-quality signatures.  For example, a high traffic station such as Times Square may contain a large number of tourists, who wouldn't be able to attend the Gala and donate.  Penn Station at 8:30 AM might have a ton of local commuters, who are also unwilling to stop and talk to our representatives.  We needed a way to determine how to balance high volume stations, with locations likely to yield quality signatures.

Our team eventually settled on using four factors to determine which stations to recommend.  The first was the average total weekly ridership for each station during a three month period (April-June 2015):

*Note that you can pan these charts by click-dragging the mouse, and zoom with the +/- buttons in the top left corner. You can also type an address in the top right to drop a pin and center the map on the specified location.  Rolling over an area will reveal additional information.  Shoutout to [CartoDB](https://cartodb.com/)
<iframe width="100%" height="720" frameborder="0" src="https://shermanash.cartodb.com/viz/13a625ea-bbac-11e5-8168-0e787de82d45/embed_map" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>

After observing that nearly all the high volume stations were in Manhattan and Brooklyn, we decided to focus solely on these two boroughs for the rest of our analysis.  Then, we pulled data from [philanthropy.org](https://philanthropy.com/interactives/how-america-gives#zip/10016), containing adjusted gross income, median charitable contribution, population and demographic statistics for each zip code.  Ultimately we decided to use "Giving Ratio", (Median Contribution / Median AGI), as an indication of which zip codes would be most likely to donate:
<iframe width="100%" height="720" frameborder="0" src="https://shermanash.cartodb.com/viz/f41c274e-baeb-11e5-86cd-0ef24382571b/embed_map" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>

To help focus on areas with a demographic likely to support our cause, we also included the percentage of people aged 25-44 in each zip code.  While traditionally older people are wealthier, and may donate more to charity, for our specific cause of Women in Tech, we assumed that the younger working generation would be more sympathetic to the cause. Here is that chart, broken down by zipcode:
<iframe width="100%" height="720" frameborder="0" src="https://shermanash.cartodb.com/viz/1ad62f5e-be45-11e5-a4ac-0e674067d321/embed_map" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>

Additionally, we wanted to position our workers in tech-friendly areas.  To do this, we obtained data from census.org containing [NAICS industry codes](http://www.naics.com/search/) for each zip code.  The census data contained the number of establishments represented by each NAICS code, and we settled on codes 51 (Information), and 54 (Scientific and Technical Services), to represent the technology sector.  The percentage of establishments from 51 and 54, divided by the total number of establishments in each zip, gave us a "Technology Ratio", shown below:
<iframe width="100%" height="720" frameborder="0" src="https://shermanash.cartodb.com/viz/0790351c-bbb0-11e5-a5ff-0ef24382571b/embed_map" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>

To combine our selected features, we first layered them on top of each other to get a general idea of the characteristics at each station:
<iframe width="100%" height="720" frameborder="0" src="https://shermanash.cartodb.com/viz/7656b866-bbb2-11e5-8ba7-0e674067d321/embed_map" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>

Then, we normalized the four features to values between 0 and 1, and multiplied them (weighted equally), resulting in a "Value" metric to determine the optimal station locations to target:
<iframe width="100%" height="520" frameborder="0" src="https://shermanash.cartodb.com/viz/0e79a27a-bb1d-11e5-aff3-0e98b61680bf/embed_map" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>

As peak travel times are weekdays during rush hours, we would recommend placing workers among those top stations during those times, probably more during the 5PM rush hour as people may be more likely to stop and chat on the way home than on the way into work.

Some areas that could use improvement would be:

*	Instead of total entries per station, analyze the density of each station entrance.  Some stations have high total entries but also lots of spread out entrances, while others have smaller total entries but are more focused on a few high volume entrances

*	Tweak the value function.  We might want to look at which factors are most important and weight those more, or find other factors such as % of population being female to include in the final value formula.

*	Split the data between work and home.  Aside from total weekly entries, 2 of our factors related to zipcode information for homes in the area, while tech ratio related to zip information for businesses, which is inconsistent and could skew the final results.
