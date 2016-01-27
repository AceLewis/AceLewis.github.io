---
layout: project
title:  Steam Trading Bot with 2FA
date:   2015-12-28
date_string: December 28th 2015
author:
published: false
# post type
categories:
- project


img:

thumb:

carousel:

other_people:

language:
- Node.JS

tagged:
- Steam Bot
- Trading Bot
- Two Factor Authentication

website:

about: An updated Steam trading bot.
---
#### Steam Trading Bot
[Steam](http://store.steampowered.com/){:target="_blank"}{{_}} is a gaming platform used by [millions of people a day](http://store.steampowered.com/stats/){:target="_blank"}{{_}}, users on this platform can trade items such as Trading cards, emoticons, and in game items with other people. I originally coded a Steam trading bot in February 2015 however as discussed in [that projects page](/project/steam-trading-bot){:target="_blank"}{{_}} Steam updated the trading and log on system to use a mobile application to do instant trades. As a result the bot was recoded from scratch biased on different libraries.

#### Tips and Advice
Making a Steam trading bot is fun and if you want to make one too you can see the tips and advice from [my first bot's project page.](https://acelewis.com/project/steam-trading-bot){:target="_blank"}{{_}}

#### This Bot
As of the 28th of December I finished the main part of my bots code required to trade, unlike the pervious bot that this one takes over whose main libraries were [node-steam](https://github.com/seishun/node-steam){:target="_blank"}{{_}}, [node-steam-trade](https://github.com/seishun/node-steam-trade){:target="_blank"}{{_}}, and [node-steam-tradeoffers](https://github.com/Alex7Kom/node-steam-tradeoffers){:target="_blank"}{{_}} this bot uses mainly [node-steamcommunity](https://github.com/DoctorMcKay/node-steamcommunity){:target="_blank"}{{_}} and [node-steam-tradeoffer-manager](https://github.com/DoctorMcKay/node-steam-tradeoffer-manager){:target="_blank"}{{_}} both of which were made by [DoctorMcKay](https://www.doctormckay.com/){:target="_blank"}{{_}}.

These libraries were chosen mainly because they were the first to patch for the Steam escrow and because the [DoctorMcKay](https://www.doctormckay.com/){:target="_blank"}{{_}}'s libraries are documented much better than others, it also has a few more benefits like not needing a Steam API key and [DoctorMcKay](https://www.doctormckay.com/){:target="_blank"}{{_}} seems much nicer than other library owners when responding to people in the issues part of the Github repository even if the people are flagging an issue when it is not a problem with the library/package.

#### What's Left?
As of the today 31st of December 2015 there have been a few issues but they have been fixed, I am still monitoring the bot's trades to see if it is declining and accepting the correct trades. It does not yet have all the chat responses as I will focus on them once I know for sure the trading is sorted out. I also have not implemented the auto accepting of friends yet however I will in the future.
