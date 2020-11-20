---
layout: post
title:  "set-solving-bot: How I automated a simple mobile game."
url-title: "set-solving-bot-automation-of-a-mobile-game"
date:   2020-11-19 20:00:00
author:
published: true
categories:
- blog

tags:
- automation


img: thumbs/automation.svg
thumb: automation.svg
---

# set-solving-bot

This project was to automate an Android app version of the card game Set, the code is [available on GitHub](https://github.com/AceLewis/set-solving-bot){:target="_blank"}{{_}}. I chose to automate ["Find a set!"](https://play.google.com/store/apps/details?id=com.nelis.set){:target="_blank"}{{_}} because it is a good copy of the real game and it has an offline high score. I don't want to cheat on an online leaderboard, this project is just for fun.
<!--more-->

<img src="/assets/img/blog/set-solving-bot/set_solving_bot.gif" width="35%" class="center-image">

I have also made a youtube video on on this project: [https://youtu.be/3PTHJjMPVyI](https://youtu.be/3PTHJjMPVyI){:target="_blank"}{{_}}

## What is Set?
Set is a card game more information about it is on [wikipedia](https://en.wikipedia.org/wiki/Set_(card_game)){:target="_blank"}{{_}}. I will however summarise the problem. The player is presented with cards that have four properties (number of shapes, shape, shading, and colour). Each property has three possibilities. The object of the game is to find a "set". A set consists of three cards that for every individual property the possibilities are all the same or all different e.g all 1's or 1, 2 and 3. Once this set is found it is removed and replaced by more cards.

In the real card game you are presented with 12 cards, there is a 96.8% chance that there is a set if no set is found then three more cards are added until 21 cards are present where there is a 100% chance of a set. In mobile phone apps this is done fixed usually by adding cards automatically but some just ensures there is a set in the cards presented and will always show a fixed number of cards. The app I have chosen uses the first method, adding cards.

## Comparing methods to find sets
Usually there are 12 cards displayed to the player, this has only 220 combinations so brute force can be used to find valid sets by checking every combination individually, I called this the brute force method.

For any two cards there is one other card needed to form a set. One other way to solve this is to look at every combination of 2 cards, work out the 'missing card' and then see if this card is present in the other cards shown. If not check the next combination of two cards. For 12 cards there are only 66 combinations however the check is harder. I called this the missing method.

I created a simple version of set [set_method_comparison.py](https://github.com/AceLewis/set-solving-bot/blob/master/set_method_comparison.py){:target="_blank"}{{_}} and used it to simulate thousands of games with a differing number of cards using both methods to find the best solution. In the real game there will only ever be 3, 6, 9, 12, 15, 18 or 21 cards, usually only 12 or 15. As shown below when trying to find all sets the missing method slower than using brute force. However in this game you do not need to find all sets just one per state. Finding just one set is much faster. As shown below there is a small advantage to the missing method in the region that is most important (12 and 15). Both methods take a fraction of a millisecond, everything else is much slower so it does not really matter what method is used. It was just interesting to find out.

Both graphs show an average of 10,000 games per number of cards.

<div class="container-half">
   <img alt="Find all graph" src="/assets/img/blog/set-solving-bot/brute_force_vs_missing_all_10000_transparent.svg"/>
   <img alt="Find first graph" src="/assets/img/blog/set-solving-bot/brute_force_vs_missing_10000_transparent.svg"/>
</div>


# How to automate the android game

So far I have described how to solve the game of Set however the main interest of this project was to learn how to automate the Android version of the game.

The problem can be separated into 3 sections:

* Getting an image of the cards
* Recognising the cards
* Clicking the cards

## Getting an image of the cards
First I was getting the phone screen from [Android Debug Bridge (ADB)](https://developer.android.com/studio/command-line/adb){:target="_blank"}{{_}}, this was however slow so in the end I used [scrcpy](https://github.com/Genymobile/scrcpy) to livestream my phone to my laptop and then take screen shots of my laptop to get the phones screen. This is a weird way to get the phones screen and has some issues with inconsistent latency however it is much faster than ADB and any other method I tried.

The latency and the animation of new cards appearing the screen meant that you are not sure what time the cards will be on the screen, this was not an issue when using ADB because it was very slow but with scrcpy it was an issue. This was fixed by repeatedly taking a screenshot and doing a simple check to see if the cards were present. If the cards had not yet been displayed it just waits a short time before taking a new screenshot. This final screenshot was cropped to get the individual cards.

## Recognising the cards
My final solution to recognise the cards was simple. Find the colour of the darkest pixel to figure out the objects colour. Threshold the cards to obtain a binary image of the card, then flood fill the background to get the filled in shapes. From this we can work out how many objects there are by detecting the edges along a strip through the centre of the filled in card (2 edges per object). The shape of the card was inferred by looking at the volume of the filled in card, the oval had the largest volume and the diamond the least. The fill of the card was calculated by subtracting the thresholded image from the background and looking at the percentage of pixels that were inside.

Images showing these steps are shown below.

<table style="width:100%">
  <tr>
    <th style="text-align:center;width:25%">Card</th>
    <th style="text-align:center;width:25%">Threshold</th>
    <th style="text-align:center;width:25%">Background</th>
    <th style="text-align:center;width:25%">Background-Threshold</th>
  </tr>
</table>

<div class="container-fourth">
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_1.png" alt="Just a card">
  </div>
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_thresh_1.png" alt="The thresholded card">
  </div>
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_background_1.png" alt="The background">
  </div>
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_background-thresh_1.png" alt="The background minus the threshold">
  </div>
  <!--Next card-->
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_2.png" alt="Just a card">
  </div>
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_thresh_2.png" alt="The thresholded card">
  </div>
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_background_2.png" alt="The background">
  </div>
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_background-thresh_2.png" alt="The background minus the threshold">
  </div>
  <!--Next card-->
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_3.png" alt="Just a card">
  </div>
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_thresh_3.png" alt="The thresholded card">
  </div>
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_background_3.png" alt="The background">
  </div>
  <div class="column">
    <img src="/assets/img/blog/set-solving-bot/just_the_card_background-thresh_3.png" alt="The background minus the threshold">
  </div>
</div>

## Clicking the cards
Again ADB was initially used but it was too slow (it takes roughly 0.25 seconds per click) so I switched to using the win32api to click the screen via [scrcpy](https://github.com/Genymobile/scrcpy).

# Final comments
My first implementation with ADB for both getting the screen and clicking the cards took 29 to 35 seconds to play the game. The final implementation with scrcpy and win32api took 4 or 5 seconds.

This was a simple project in game automation, the object detection is too simple and can't be generalised to many other games but it was fun to do.
