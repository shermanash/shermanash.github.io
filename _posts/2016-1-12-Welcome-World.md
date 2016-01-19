---
layout: post
title: "Obtaining High-Quality Signatures"
published: true
---



As an exercise in exploratory data analysis, we broke up into groups to obtain, digest, and analyze data in pursuit of our stated objective.  The goal was to use MTA subway data, and other sources, to determine where, and when, to optimally place workers in order to recruit potential donors to an event supporting increasing the participation of women in tech.

Our initial reaction was to find the stations with the highest traffic, but we soon realized that high-traffic stations would not necessarily net the most high-quality signatures.  For example, a high traffic station such as Times Square may contain a large number of tourists, who wouldn't be able to attent the Gala and donate.  Penn station at 8:30 AM might have a ton of local commuters, who are also unwilling to stop and talk to our representatives.  We needed a way to determine how to balance high volume stations, with locations likely to yield quality signatures.

Our team eventually settled on using four factors to determine which stations to recommend.  The first was the average total weekly ridership for each station during a three month period:
<iframe width="100%" height="520" frameborder="0" src="https://shermanash.cartodb.com/viz/13a625ea-bbac-11e5-8168-0e787de82d45/embed_map" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>

After observing that nearly all the high volume stations were in Manhattan and Brooklyn, we decided to focus solely on these two boroughs for the rest of our analysis.  Then, we pulled data from [philanthropy.org](https://philanthropy.com/interactives/how-america-gives#zip/10016), containing adjusted gross income, median charitable contribution, population and demographic statistics for each zip code.  Ultimately we decided to use "Giving Ratio", (Median Contribution / Median AGI), as an indication of which zip codes would be most likely to donate:
<iframe width="100%" height="520" frameborder="0" src="https://shermanash.cartodb.com/viz/f41c274e-baeb-11e5-86cd-0ef24382571b/embed_map" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>

To help focus on areas with a demographic likely to support our cause, we also included the percentage of people aged 25-44 in each zip code.  While traditionally older people are wealthier, and may donate more to charity, for our specific cause of Women in Tech, we assumed that the younger working generation would be more sympathetic to the cause. Here is that chart, broken down by zipcode:
<iframe width="100%" height="520" frameborder="0" src="https://shermanash.cartodb.com/viz/1ad62f5e-be45-11e5-a4ac-0e674067d321/embed_map" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>

Finally, we wanted to position our workers in tech-friendly areas.  To do this, we scraped data from census.org containing [NAICS industry codes](http://www.naics.com/search/) for each zip code.  The census data contained the number of establishments represented by each NAICS code, and we settled on codes 51 (Information), and 54 (Scientific and Technical Services), to represent the technology sector.  The percentage of establishments from 51 and 54, divided by the total number of establishments in each zip, gave us a "Technology Ratio", shown below:

