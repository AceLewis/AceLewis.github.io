---
layout: post
title:  "The Secret Santa problem"
url-title: "The Secret Santa problem"
date:   2016-11-08 23:01:00
author:
published: true
categories:
- blog

tags:
- data
- maths


img: secret-santa.svg
thumb: ../secret-santa.svg
---
This is a blog post that discusses the probability of a successful Secret Santa draw and how the probability changes with the number of people in the group.

The Secret Santa draw is a simple pick names from a hat that contains everyone's name, success is defined by everyone having a name that is not themselves.
<!--more-->

## Sections
 * The problem
 * The brute force method
 * The smart way (aka Maths)
 * The results
 * The solution

## The problem
Ok so this problem arose from a discussion I had a week ago when we were deciding on what to do for Christmas, we were talking about how we should do a Secret Santa and if we were to randomly shuffle two arrays and pair everyone up then what is the probability that the draw will be successful with everyone getting someone else's name. Some people thought that the probability would decrease as the number of people in the group increased and others argued that the opposite would be true. I was interested in this problem so much that I decided to try and solve it, this problem has been solved before but I have provided graphs of the probability with the number of people within the group and show two unique solutions the ugly brute force way (not really a solution just an accurate estimate) and the much more elegant mathematical solution. Code for both of these solutions is provided on my [GitHub here](https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/The_Maths_of_Secret_Santa/secret_santa.py){:target="_blank"}{{_}}.

## The brute force method
Ok so the easiest 'solution' to understand would be to make some code that did this process thousands of times so you can average to get the percentage of times the draw is successful. This is easy to understand but only gives you a estimate and does not give you much insight into the real solution. The full code for both solutions is available on [GitHub](https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/The_Maths_of_Secret_Santa/secret_santa.py){:target="_blank"}{{_}} but I have broken it down here.

First make a function that does the equivalent of picking names out of a hat and sees if the draw was successful;

<script src="http://gist-it.appspot.com/github/AceLewis/AceLewis-Miscellaneous-Code/blob/master/The_Maths_of_Secret_Santa/secret_santa.py?slice=5:10&footer=minimal" ></script>

Next create a function to find the average percentage of successful draws out of the hat;

<script src="http://gist-it.appspot.com/github/AceLewis/AceLewis-Miscellaneous-Code/blob/master/The_Maths_of_Secret_Santa/secret_santa.py?slice=12:18&footer=minimal" ></script>

The next function just finds the percentage of successful draws up to `num_to`;

<script src="http://gist-it.appspot.com/github/AceLewis/AceLewis-Miscellaneous-Code/blob/master/The_Maths_of_Secret_Santa/secret_santa.py?slice=20:26&footer=minimal" ></script>

This is all the code behind calculating the average percentage of successful draws, the code to plot is trivial. The plot for the estimated percentage of successful draws is shown below;

<img src="/assets/img/blog/secret-santa/Estimated_percentage_of_successful_compressed.svg" width="80%" class="center-image">

## The smart way
The brute force method is easy to understand however it only gives us an estimate and it is computationally expensive. By doing the maths for this we can gain more insight into the solution and can find the actual percentage of successful draws very quickly. We can use the estimates calculated in the brute force method to compare to the actual values to verify both methods.

I was going to initially write the maths for this in this post however it has been done very well before [here](http://mindyourdecisions.com/blog/2015/12/06/secret-santa-surprising-probability-sunday-puzzle/){:target="_blank"}{{_}}. So using this equation in the code (and not summing to infinity) we get;

<script src="http://gist-it.appspot.com/github/AceLewis/AceLewis-Miscellaneous-Code/blob/master/The_Maths_of_Secret_Santa/secret_santa.py?slice=46:49&footer=minimal" ></script>

This gives us a graph as shown below;

<img src="/assets/img/blog/secret-santa/Actual_percentage_of_successful_compressed.svg" width="80%" class="center-image">


## The results

<div class="container-half">
   <img alt="Estimated percentage" src="/assets/img/blog/secret-santa/Estimated_percentage_of_successful_compressed.svg"/>
   <img alt="Actual percentage" src="/assets/img/blog/secret-santa/Actual_percentage_of_successful_compressed.svg"/>
</div>

When you compare these graphs you can see that they are very similar, this shows that the brute force method gave a good estimate. The results shows that for a group greater than 5 the percentage of a successful draw is about 37% and does not increase or decrease significantly. The success percentage tends to 1/e where e is the exponent. This shows that it is most likely that you will have to re-draw if you were to use a simple name in hat method.

## The solution
The solution to a Secret Santa in code (a real world analogy will be used at the end too) is randomly shuffle the array of names/emails, copy this list to a new variable and rotate it by a number that when you divide by the number of people in the group does not give you 0 (aka rot_num % num_people != 0) you can just rotate by 1 because that always satisfies this criteria then pair the people in the new list with people in the old list. This ensures that every person does not get themselves and also that everyone will get a present.

The real world solution without using someone outside of the group and also if you don't want to use code (because you would have to set it up to email people and delete the emails it sent) is to use an envelope for every person in the group. Every person writes their own name on a folded piece of paper and on the face of their envelope. This piece of paper goes in to their own envelope (the envelope is not sealed), this is analogous to having two arrays that are the same. You then shuffle the envelopes face down so the names can't be seen, once shuffled you arrange the envelopes face down in a line. The names on the envelopes are not known! You then take the name out of each envelope and put it into the envelope to the right (the one on the far right goes into the far left one) the names on the papers should never be visible as the paper is folded. The envelopes are then shuffled again and re-distributed to the people whose name is on the face of the envelope. This ensures that no-one gets their own name and nobody knows who is giving a present to whom.

You can also use online services for this but they may sell your email to spammers.
