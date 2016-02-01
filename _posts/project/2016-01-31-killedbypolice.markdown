---
layout: project
title:  Killed by Police
date:   2016-01-31
date_string: January 2016
author:
published: true
# post type
categories:
- project


img:

thumb:

carousel:

other_people:

language:
- Python

tagged:
- Killed by Police
- Data

website:

about: A project scraping and processing data from killedbypolice.net
---

![Main Infographic](/assets/img/project/killedbypolice/killed-by-police.png){: .center-image }

#### About the project
This project obtained data from [killedbypolice.net](http://killedbypolice.net){:target="_blank"}{{_}} and used that data to look at the statistics of the people killed by the U.S. police force, e.g race, gender and age. The data on [killedbypolice.net](http://killedbypolice.net){:target="_blank"}{{_}} nearly always has a news articles attached the deaths are only recorded from U.S. Police and not police around the world.

#### Infographics
The code used to obtain and look at the data is available on [GitHub](https://github.com/AceLewis/killedbypolice){:target="_blank"}{{_}}, the main infographic is shown above, other infographics with just the specific area (race, gender ect.) are shown below. All killedbypolice infographics (the images) are licensed under [Creative Commons, Atribution-ShareAlike (CC BY-SA)](https://creativecommons.org/licenses/by-sa/3.0/){:target="_blank"}{{_}} so you can share them on Facebook, Twitter or other social media sites.

#### Other Infographics
* [<font size="5">Just race</font>](/assets/img/project/killedbypolice/killed-by-police-race.png){:target="_blank"}{{_}}
* [<font size="5">Just gender</font>](/assets/img/project/killedbypolice/killed-by-police-gender.png){:target="_blank"}{{_}}
* [<font size="5">Just cause of death</font>](/assets/img/project/killedbypolice/killed-by-police-method.png){:target="_blank"}{{_}}
* [<font size="5">Just age</font>](/assets/img/project/killedbypolice/killed-by-police-age.png){:target="_blank"}{{_}}
* [<font size="5">Just day of week</font>](/assets/img/project/killedbypolice/killed-by-police-days.png){:target="_blank"}{{_}}

(Please don't hotlink, just save the images and reupload)

#### The Code
This project was coded in Python 3 (although it should work in Python 2 aswell), the code is available on [GitHub https://github.com/AceLewis/killedbypolice](https://github.com/AceLewis/killedbypolice){:target="_blank"}{{_}}. The data was obtained from [killedbypolice.net](http://killedbypolice.net){:target="_blank"}{{_}} on this website there is a big table of data, the table's HTML is difficult to parser (due to broken HMTL) so I had to resort to using Selenium and Firefox to obtain the HTML for two of the years.

As mentioned in the infographic a better Histogram can be obtained using matplotlib, this is shown below. The software I used to make the infographic looked ugly when the number of bars was this high.

![Nicer Histogram](/assets/img/project/killedbypolice/nicer_histogram.png){: .center-image }

#### Comparison to the UK
I live in the UK so I would like to compare the USA police killing to the police killings here. The population of USA in 2014 was [318.9 million [REF]](http://data.worldbank.org/indicator/SP.POP.TOTL){:target="_blank"}{{_}} the population of the UK in 2014 was only [64.5 million [REF]](http://data.worldbank.org/indicator/SP.POP.TOTL){:target="_blank"}{{_}}, the population of the USA is roughly 4.94 times larger. If the rates of police killings in the UK were similar to the US we would expect (3,916/4.94) 793 people to be killed by police from May 2013 to the end of 2015.

Since May 2013 only 4 people were killed by law enforcement officers in the UK [[REF]](https://en.wikipedia.org/wiki/List_of_killings_by_law_enforcement_officers_in_the_United_Kingdom){:target="_blank"}{{_}}, so you are about 19,825% more likely to be killed by a police officer in the US than in the UK. This comparison is not that fair as people in the US have access to guns and can more easily put other peoples lives in danger, whilst in the UK guns are illegal other than shotguns and some sporting rifles with a license.
