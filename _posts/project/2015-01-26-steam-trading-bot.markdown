---
layout: project
title:  Steam Trading Bot
date:   2015-01-26
date_string: February 2015
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
- Node.JS

tagged:
- Steam Bot
- Trading Bot
- TF2 Trading Bot

website:

about: A Steam trading bot used to automatically trade items.
---
#### Steam Trading Bot
[Steam](http://store.steampowered.com/){:target="_blank"}{{_}} is a gaming platform used by [millions of people a day](http://store.steampowered.com/stats/), users on this platform can trade items such as Trading cards, emoticons, and in game items with other people. The bot I made was able to trade all these items and was able to add and remove friends and chat with automated responses.

#### Tips and Advice
Some of my tips and advice for people that want to make their own Steam trading Bots firstly the language to choose, the two main options are C# or Node.js. For C# the main library you will use is [SteamBot](https://github.com/Jessecar96/SteamBot){:target="_blank"}{{_}}
I originally coded my first trading bot in C# and it was okay as there is lots of good documentation however I chose at the time to use Node.js as it had libraries to deal with trade offers and the C# libraries only could deal with trade requests (the older trading system). The C# libraries now fully support trade offers however I still believe that Node.js is the best language to choose for the following reasons, firstly the [SteamBot subreddit](https://www.reddit.com/r/SteamBot/){:target="_blank"}{{_}} made to to help people with issues related to the C# library often recommends Node.js now especially for new people, Node.js does not need to me compiled all you need is Node.js installed on your PC and a text editor, a big issue with C# is to run on Linux operating systems Mono has to be used this can cause many problems with different versions doing slightly different things, Mono and C# is slower than Node.js, and finally Node.js uses a lot less RAM and CPU than the C# libraries.

Now assuming you are using Node.js you have many libraries to choose from including [node-steamcommunity](https://github.com/DoctorMcKay/node-steamcommunity){:target="_blank"}{{_}}, [node-steam-tradeoffer-manager](https://github.com/DoctorMcKay/node-steam-tradeoffer-manager){:target="_blank"}{{_}}, [node-steam-user](https://github.com/DoctorMcKay/node-steam-user){:target="_blank"}{{_}}, [node-steam](https://github.com/seishun/node-steam), [node-steam-trade](https://github.com/seishun/node-steam-trade){:target="_blank"}{{_}}, [node-steam-tradeoffers](https://github.com/Alex7Kom/node-steam-tradeoffers){:target="_blank"}{{_}}, and much more however in my opinion the best libraries to use are [node-steamcommunity](https://github.com/DoctorMcKay/node-steamcommunity){:target="_blank"}{{_}} and [node-steam-tradeoffer-manager](https://github.com/DoctorMcKay/node-steam-tradeoffer-manager){:target="_blank"}{{_}} as only these two are needed to make a trading bot and you don't need to have a Steam API key.

The [SteamBot subreddit](https://www.reddit.com/r/SteamBot/){:target="_blank"}{{_}} is good for simple questions regarding Steams API and other things but do your own research before posting as most problems can be fixed with the help of Google.

Steam often goes down, sometimes just the API and sometimes more than just that it is annoying whilst testing to fond out that the reason your bot is not connecting is because Steam is down, so if you want to check use [Steam Status](https://steamstat.us/){:target="_blank"}{{_}}.

#### The End of This Bot
The bot started trading in February and little maintenance was needed however on December the 9th 2015 Steam introduced [Steam mobile](http://store.steampowered.com/mobile){:target="_blank"}{{_}} as a mandatory two factor authentication needed for instant trades. If a user did not set up Steam mobile trades will be held in escrow for 3 days as other users needed this feature the bot was broken thus forcing me to recode it. This bot used the [node-steam](https://github.com/seishun/node-steam){:target="_blank"}{{_}} and [node-steam-tradeoffers](https://github.com/Alex7Kom/node-steam-tradeoffers){:target="_blank"}{{_}} libraries however the new bot uses different libraries.

#### The Bots Life
During the 10 months the bot was operational it made over 30,000 trades to thousands of users, as the bot was set up mainly for a hobby I think that this was a success. It was very interesting and fun project, the intention of the project was not to make a profit however about £200-250 was made in the months it was running. The bot ran on a Raspberry Pi so the electric costs were negligible, and it needed no effort to run and would only be checked upon about once a fortnight.

#### The Next Trading Bot
As mentioned previously this bot no longer works however small parts of it were used in the updated bot, the new bots code uses the libraries [node-steamcommunity](https://github.com/DoctorMcKay/node-steamcommunity){:target="_blank"}{{_}} and [node-steam-tradeoffer-manager](https://github.com/DoctorMcKay/node-steam-tradeoffer-manager){:target="_blank"}{{_}} the reason for this was because [backpack.tf](https://backpack.tf){:target="_blank"}{{_}}'s [Automatic](https://bitbucket.org/srabouin/backpack.tf-automatic){:target="_blank"}{{_}} uses these libraries and if any other big changes in Steam were made in logging in and/or the trading it would be much easier to update the bot as I can just make the same changes as they do.
