---
layout: post
title:  "What is ZeroNet"
url-title: "What is ZeroNet"
date:   2016-03-08 22:49:21
author:
published: true
categories:
- blog

tags:
- zeronet
- p2p


img: zeronet-io.png
thumb: zeronet-logo.png
---
[ZeroNet](https://zeronet.io){:target="_blank"}{{_}} is a project that allows people to create decentalised peer to peer websites, as all websites are decentalised it is free to host, can't be geoblocked, it very resilient to censorship and is difficult to attack via DDOS. Although websites on ZeroNet are distributed across the network it is much more secure than the normal web as it uses "Bitcoin cryptography" aka websites are signed by the same public private key cryptography that is used in Bitcoin.
<!--more-->

In this blog post I aim to explain to you the basics of ZeroNet, how it works and how to use it. I have a [YouTube playlist](https://www.youtube.com/playlist?list=PLgFqcJDOq2q5orC1U4IvDBMpjezKt-X4E){:target="_blank"}{{_}} of videos I made explaining the separate parts of ZeroNet in more detail. Since making the first video ["Introduction to ZeroNet"](https://www.youtube.com/watch?v=NVg3s9bFQ0w&index=1&list=PLgFqcJDOq2q5orC1U4IvDBMpjezKt-X4E){:target="_blank"}{{_}} (3 weeks ago) ZeroNet's popularity has increased by 15-20 times; it is difficult to get an accurate estimation of the number of people using ZeroNet due to its decentalised nature (the reasons will be stated lower down). This increase in popularity is mostly due to ZeroNet being featured in [TorrentFreak](https://torrentfreak.com/play-p2p-impossible-shutdown-160301/){:target="_blank"}{{_}} due to Play a ZeroNet site that shares magnet link to movies (ZeroNet does not condone or support piracy just like the regular internet piracy sites exist).

## Sections
This post is long so I have broken it down into many subsections;

 * How to get ZeroNet
 * How does ZeroNet work?
 * Anti-Censorship
 * Some good ZeroNet sites
 * The future of ZeroNet

### How to get ZeroNet
One of the reasons why ZeroNet is so good is not only does it have a very nice user interface but it is simple to install and use. To install all you need to do is go to [https://zeronet.io](https://zeronet.io){:target="_blank"}{{_}} download the ZeroBundle for your operating system, Windows, Mac or Linux extract the zip and then click the single file to install ZeroNet. The installation is that simple, although it runs on Python 2.7 and has multiple dependencies they are all included in the bundles.

### How does ZeroNet work?
ZeroNet allows for peer to peer sharing of websites, it does this not by reinventing the wheel but by incorporating existing technologies. The main things are the `content.json`, finding peers and anonymity.

#### The content.json
A website initially consists of a file the `content.json` this file is signed by the websites owner, this signing is done by public private key cryptography using the same keys as Bitcoin uses (so you can accept bitcoin payments to your sites none .bit domain). Public private key cryptography is somewhat complex to understand on a mathematical level however all it does is allows you to verify that the `content.json` was signed by and only by the sites owner (unless they gave the key to someone else too). Websites are dynamic meaning that they can be updated, this means that many `content.json` files can be signed for by the sites owner however only one will be valid. The valid `content.json` is the file that contains within it the latest time, older signed `content.json`'s are discarded. This number could be an increasing integer e.g. 1, 2, 3 however using the time stamp is better as the chance of accidentally having two valid signed `content.json`'s would be reduced drastically.

This `content.json` contains a SHA512 hash of all the files and their sizes in bytes. This allows you to then get the files from the other peers that are seeding the website.

#### Finding peers
As ZeroNet is peer to peer you need a way to find other people that have the `content.json`, this is currently done by using regular torrent trackers (and TOR torrent trackers). When ZeroNet sends the tracker a request containing the SHA512 hash the tracker sends back a request with the IPs of the people that have that file so you can connect to them however ZeroNet does not use conventional torrenting to exchange files and thus does not allow file splitting for files larger than 1MB.

#### Anonymity
On ZeroNet users can be optionally anonymous, this is done by using [TOR (The Onion Router)](https://www.torproject.org/){:target="_blank"}{{_}}. TOR allows anyone to hide their IP address by bouncing their internet traffic through multiple encrypted proxies to an exit node. ZeroNet allows people to use TOR to hise their IP address, connections between people using TOR are done via [TOR hidden services](https://www.torproject.org/docs/hidden-services.html.en){:target="_blank"}{{_}} so TOR exit nodes are not used. This Anonymity the ZeroNet provides allows people in countries like China, Russia or Iran to have access to and easily publish information, without being traced.

### Anti-Censorship
Anti-Censorship is important, information like the [Tiananmen Square Massacre](https://en.wikipedia.org/wiki/Tiananmen_Square_protests_of_1989){:target="_blank"}{{_}} is only known to the general public because the Chinese government censorship was not strong enough to stop the spread of information. Other governments are also not immune to criticism for example with [Wikileaks](https://en.wikipedia.org/wiki/WikiLeaks){:target="_blank"}{{_}} or [Edward Snowdens leaks](https://en.wikipedia.org/wiki/Edward_Snowden){:target="_blank"}{{_}} and they too have tried to censor the spread of information from forcing [Newspapers to destroy their hard drives](http://www.theguardian.com/uk-news/2014/jan/31/footage-released-guardian-editors-snowden-hard-drives-gchq){:target="_blank"}{{_}} to death penalty or imprisonment for whistle blowers. Chelsea Manning's a whistle blower currently in prison for releasing documents to WikiLeaks and further ["threatened with indefinite solitary confinement for having an expired tube of toothpaste in her cell and being found in possession of the Caitlyn Jenner Vanity Fair issue"](http://www.theguardian.com/us-news/2015/aug/12/chelsea-manning-solitary-confinement-toothpaste-army){:target="_blank"}{{_}} which would have been given to her whilst in prison.

**This is why Anti-Censorship is important**

How does ZeroNet help with this?... Upon creating a website you are given a private key to sign for the content of the ZeroNet site (or you can choose your own keys), these keys mean that only you can sign for this ZeroNet site. The fact that the sites are verified by this key means that the network is censorship resilient, when the anonymity of TOR is included this makes the sites nearly impossible to shut down. The only way for your site to go down is if everyone on your site decides not to seed (unlikely because many people/servers are set up to host all ZeroNet sites) or you get forced to use your private key to wipe the site. If you are using TOR and leave no other traces then you will be extremely hidden this means that whistle blowers will not be found.

Due to the nature of ZeroNet you can go one step further and create a ZeroNet site (with the information on it) sign it and "forget" aka don't save the private key. If you don't have the private key then no one at all can edit the site, so no one can take it down not even you. This of course comes with the down side that you can't update your site at all.

### Some good ZeroNet sites

Ok, so some sites already hosted on ZeroNet in no order (links only work for ZeroNet);

* [ZeroID](http://127.0.0.1:43110/zeroid.bit/){:target="_blank"}{{_}}: A site that allows people to create an ID allowing them to log in to many other ZeroNet sites easily, as an owner of a ZeroNet site you can use ZeroID (or other ID services) to allow people to comment and like posts.
* [ZeroMail](http://127.0.0.1:43110/Mail.ZeroNetwork.bit/){:target="_blank"}{{_}}: A site that allows people to send messages to other ZeroIDs, the messages sent are encrypted.
* [ZeroTalk](http://127.0.0.1:43110/Talk.ZeroNetwork.bit/){:target="_blank"}{{_}}: A Reddit style website that allows people to create posts to share links, ideas, or just chat.
* [ZeroSearch](http://127.0.0.1:43110/zerosearch.bit/){:target="_blank"}{{_}}: The first (and one of many) search engine inside ZeroNet that allows you to search for sites on ZeroNet.
* [GIF Time](http://127.0.0.1:43110/1Gif7PqWTzVWDQ42Mo7np3zXmGAo3DXc7h/){:target="_blank"}{{_}}: A website that shares "GIFs" it has hundreds of "GIFs" totaling over 350 MB showing the optional files that ZeroNet can use. The GIFs are actually highly optimised GIFVs as [discussed in my previous blog post](/blog/image-formats-and-when-to-use-them){:target="_blank"}{{_}}.
* [0chan](http://127.0.0.1:43110/0chan.bit/){:target="_blank"}{{_}}: A messaging/image board that allows people to anonymously post images any text similar to 4chan.
* [0rc](http://127.0.0.1:43110/1CjR14fofbRJ54oj8A7rAfWpzpLawdP5uc/){:target="_blank"}{{_}}: A messaging room that allows large groups of people to talk about stuff similar to IRC hence the name. There are many different 0rc's for different topics.
* [ZeroWiki](http://127.0.0.1:43110/138R53t3ZW7KDfSfxVpWUsMXgwUnsDNXLP/){:target="_blank"}{{_}}: A wiki that focuses on ZeroNet, allowing user to edit and create topics.
* [ZeroPolls](http://127.0.0.1:43110/ZeroPolls.bit/){:target="_blank"}{{_}}: A site that allows people to create, participate and view the results of polls within ZeroNet.
* [0List](http://127.0.0.1:43110/0list.bit/?Home){:target="_blank"}{{_}}: A list of most ZeroNet sites so you can find loads more for whatever you want.

### The Future of ZeroNet
Zeronet is new and potentially has a big future ahead of it. The community is fairly small and the project is currently in its alpha stage this is good in some aspects as it is easier to introduce new features. [Bitmessage](https://bitmessage.org/wiki/Main_Page){:target="_blank"}{{_}} is a planned feature that will allow users to post forms, requests and other information over [Bitmessage](https://bitmessage.org/wiki/Main_Page){:target="_blank"}{{_}} this will allow ZeroNet sites to scale better because not all requests need to be sent to all ZeroNet peers. Large files (bigger than 1 MB) are not ideal for ZeroNet as it does not currently support file splitting for the downloading and uploading data, this may be introduced in the future however there would be the concern that people may make websites to stream large videos this is not good for ZeroNet especially the users who have TOR enabled. To allow large files to be transferred I2P may be incorporated however ZeroNet is far from reaching this goal if it will be introduced at all.
