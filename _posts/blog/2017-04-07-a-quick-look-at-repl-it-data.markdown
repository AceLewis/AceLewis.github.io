---
layout: post
title:  "Statistics of code shared on repl.it"
url-title: "Statistics of code shared on repl.it"
date:   2017-04-07 22:00:00
author:
published: true
categories:
- blog

tags:
- repl.it
- data


img: thumbs/repl-it_logo.svg
thumb: repl-it_logo.svg
---

[Repl.it](https://repl.it/){:target="_blank"}{{_}} is a code sharing website that also allows you to run the code in the browser, it is very useful for testing languages quickly and easily and sharing code with someone where they can see the output. I have also had fun making the graphs look nicer than Matplotlib's default graphs.
<!--more-->

I am going to present an overview of the data I have gathered from [repl.it](https://repl.it/){:target="_blank"}{{_}}, I also will make a blog post on how the data was gathered and show the code used on GitHub.

## Sections

 * What is the repl.it?
 * What is the data?
 * Number of code shares over time
 * Total language percentage
 * Language percentage over time
 * Python 2 vs Python 3

## What is the repl.it?
[Repl.it](https://repl.it/){:target="_blank"}{{_}} is a website for sharing and also executing code from within the browser without installing anything, 33 languages are currently supported. The benefits of sharing code via [repl.it](https://repl.it/){:target="_blank"}{{_}} is the person you have shared code with can run it without installing anything, and also you can ensure that the code is run in the correct version of the language. I find it useful when I want to see how code runs on Python 2 vs Python 3 without installing both versions. Also it allows me to code on devices that I can not install languages on e.g mobile phones, tablets.

## What is the data?
The data I have gathered is strictly from saved code, when you want to share code on repl.it you click a button to create a unique link. I have gathered all the data from people saving code and used this data, my data does not include code that was written and run on repl.it but not saved.

## Number of code shares over time
The simplest statistic to look at is the number of code share over time, this will give us a good indication of how the popularity of [repl.it](https://repl.it/){:target="_blank"}{{_}} has changed.

<img src="/assets/img/blog/repl-it-data/amount-of-code-saved-per-month.svg" width="80%" class="center-image">

As can be seen from this graph we can see that the popularity of the website has increase rapidly in the past few months, this is brilliant for the company and great for the users as you have more security that the service will keep running. This increase in users coincides with the introduction of the [repl.it blog](https://repl.it/site/blog){:target="_blank"}{{_}} and also the introduction of features such as code [autocomplete](https://repl.it/site/blog/autocomplete){:target="_blank"}{{_}} and the ability to use [any package in Python that is available on PyPi](https://repl.it/site/blog/python-import){:target="_blank"}{{_}}.

## Total language percentage
One interesting piece of trivia would be to look at the languages shared on repl.it, this does have a correlation with the popularity of a language however should not be trusted that much as an indicator because more commercial languages would not be on repl.it as much as employees would not be allowed to save code on the website.

<img src="/assets/img/blog/repl-it-data/language-pie-chart.svg" width="80%" class="center-image">

So from the data we can see that Python is by far the most shared language on repl.it with nearly half of the total shares, and nearly all the code shares are from only a few languages Python, JavaScript, Ruby, Java and C++. This information would be incredibly useful if you want to set up a competing service as you would be able to see what languages you could focus on.

## Language percentage over time
Something else I found interesting was how the language percentage has changed over time, I wanted to know if one language has gotten more poplar or less popular over time. To see this I grouped the languages into their calendar months and saw how the percentage of language shares changes in time.

<img src="/assets/img/blog/repl-it-data/language-stackplot.svg" width="80%" class="center-image">

From the graph it shows that Python has increased slowly over time and JavaScript also seems to have increased however these percentages are not very significant. Java, C++, C and web projects which are the 4th-7th most popular languages are all added somewhat recently and all seem to be growing in popularity since mid 2014 (web projects being introduced late 2015). The other languages shared on repl.it have been decreasing in popularity too

## Python 2 vs Python 3
Python 2 is being depreciated in 3 years so it would be good to look at the percentage of people using Python 2 and Python 3.

<img src="/assets/img/blog/repl-it-data/python-2-vs-3.svg" width="80%" class="center-image">

Python 3 was introduced to repl.it in late 2014 and has quickly become the most dominate version of the language now with 80% of the total shares. This is promising for Python as it shows that the future of the language is being widely adopted, the actual rate of adoption is probably lower due to corporations that still use Python 2 but will have rules against sharing code and hopefully their employees would not upload the code to repl.it.

### The code
The code used to gather the data and to make the estimations was done in Python, it will be uploaded to [my GitHub](https://github.com/AceLewis){:target="_blank"}{{_}} soon so follow me if you want.

I am going to be doing a few more blogs on topics like this so if you are interested then maybe you should bookmark me.
