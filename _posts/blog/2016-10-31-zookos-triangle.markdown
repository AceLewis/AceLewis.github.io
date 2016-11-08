---
layout: post
title:  "Zookos triangle"
url-title: "Zookos triangle"
date:   2016-10-31 21:31:00
author:
published: true
categories:
- blog

tags:
- dns
- p2p
- zookos triangle

img: thumbs/Zookos_Triangle.png
thumb: Zookos_Triangle.png
---
Zookos triangle states that for a domain name in a DNS (Domain Name System) can not be human readable, secure AND decentralized. It can be up to two of the three but not all three, how true is the statement?
<!--more-->

So whilst writing this there was a [big internet outage of Dyn DNS a very popular DNS provider due to a DDOS](https://www.theguardian.com/technology/2016/oct/26/ddos-attack-dyn-mirai-botnet){:target="_blank"}{{_}}... I may now also talk about DOS and DDOS' in a different blog post because they are very interesting and often are often not well explained or not gone into enough detail about all the types of DDOS' there are. This DDOS highlights some of the vulnerabilities that I have covered in this blog post.

## Sections
So I have broken this post into a few sections

 * What is DNS anyway?
 * What is Zookos triangle
 * How does normal DNS stand up
 * Examples of alternative DNS's
 * Problems with NameCoin
 * AceLewis' Square

### What is DNS anyway?
DNS or Domain Name System is a useful tool that most of us use every day, the Internet simply allows computers to communicate with each other. On the internet each computer has an IP address e.g. 46.51.197.89 that is used to receive data however when connecting to a website people don't want to type the IP address, they would much prefer to type a memorable domain name. [http://46.51.197.89/](http://46.51.197.89/){:target="_blank"}{{_}} is an IP address for DuckDuckGo however most people will just type in [https://duckduckgo.com](https://duckduckgo.com){:target="_blank"}{{_}} (the same can be said for Google, Bing ect). DNS is just the thing that turns this easy to remember domain into an IP address so you can connect to the website. Domain names also allow one IP address to host multiple websites because the request has the domain name attached so you know what website the user is trying to connect to.

### Zookos Triangle
This blog post centres around Zookos triangle so I should go into more detail on what it is, although it was proposed for any key-value pair it is mostly applied to domain names. So, to paraphrase Zooko stated that an ideal DNS would posses these three properties;

* It would be human readable - aka domain names would be something easy to remember like acelewis.com not a random arrangement of letters e.g. 3g2upl4pq6kufc4m.onion (DuckDuckGo's Tor Hidden Service)
* It would be secure - this means that when you type in acelewis.com you are 100% sure that you are directed to the correct website and the request was not changed by a malicious person.
* It would be decentralized - so the DNS system is not run or owned by one big company but is distributed.

So lets compare to the normal DNS we use every day, is it human readable? Hell yeah, I bet you remember many domain names like facebook.com, google.com, youtube.com and many more. So it has checked off the first requirement lets see how well it does on the rest.

Is normal DNS secure? No, not at all. Websites can be blocked via DNS like [most piracy websites in the UK](https://en.wikipedia.org/wiki/List_of_websites_blocked_in_the_United_Kingdom#Court_ordered_implementations_targeting_copyright_and_trademark_infringement){:target="_blank"}{{_}}, not only that but when Pakistan blocked YouTube via DNS the DNS block accidentally propagated through to DNS servers in other countries causing YouTube to be blocked world wide for about 2 hours [[REF]](https://www.cnet.com/uk/news/how-pakistan-knocked-youtube-offline-and-how-to-make-sure-it-never-happens-again/){:target="_blank"}{{_}}. Not only is DNS easily blockable but you can't ever own a domain, it can be taken off you for any reason for example the country disliking LGBT, Atheism [[REF]](https://en.wikipedia.org/wiki/.ly#Domain_hacks){:target="_blank"}{{_}}. Also whilst I was writing this post Dyn DNS a popular DNS provider was DDOSed leading to the inability of many Americans and Europeans to access websites for most of the day [[REF]](https://www.theguardian.com/technology/2016/oct/26/ddos-attack-dyn-mirai-botnet){:target="_blank"}{{_}}, this shows how the centalised nature of DNS is an inherent problem.

Is it decentralized? Nope, not at all. Regular DNS is so centralized it is untrue, all domains are basically owned by one organisation ICANN (The Internet Corporation for Assigned Names and Numbers) they are responsible for rules for domain names e.g having to submit your name and address when registering a domain. ICCAN don't directly sell domains but effectively sell the rights to sell certain domains to other companies, these companies also don't directly sell domains but then sell the rights to sell domains to domain registrars (which in turn often don't sell directly but sell their domains by using other companies). That may be slightly confusing but basically when you buy a domain e.g. a .com domain you can but it from a company (in this case we will use NameCheap) and that company can actually get their domains from a different company (In this case is eNom although they seem to not publish this fact [[REF]](https://www.namecheap.com/support/knowledgebase/article.aspx/260/8/what-is-an-ips-tag){:target="_blank"}{{_}}) who get their domains from the company that has the right to sell .com domains (It is hard to find this out) and they get their domains from ICCAN. So not only is your domain centralised by the company you directly buy it off but it is centralised all the way up to the top. This centralisation means that any company that deals with your domain may have to remove you access for any reason, e.g many websites owned by an English man living in Spain some of which focused on Cubas history, literary and promoted Cuba to Italian and French tourists were taken down due to the United States embargo against Cuba [[REF]](http://www.nytimes.com/2008/03/04/us/04bar.html){:target="_blank"}{{_}}). This shows that although breaking no laws, your domains can be seized by a government of a country you are not from and don't live in. There are loads more examples of this.

I have faced a problem with ICANN too, one day I wanted to show a friend [https://zero.acelewis.com](https://zero.acelewis.com){:target="_blank"}{{_}} and when I typed it in I didn't go to my website but to a landing page telling my that the owner of the website (me) had not verified the information provided to the WHOIS. When you register a domain you have to say your name, address and email this data is then publicly available. When registering my domain I verified my email but it turns out you need to re-verify your email every year and I had forgotten to do so. This meant that the domain I had paid and registered was no longer working all because I forgot to re-verify my email address. Not only do I think that you shouldn't have to provide this information as it reduces anonymity so is a prime target for spammers [[REF]](https://www.icann.org/en/system/files/files/sac-023-en.pdf){:target="_blank"}{{_}} stalkers or people attacking you because they hate the content your are publishing e.g. LGBT, Atheism, or social/political views [[REF]](http://awesomelytechie.com/privacy-bloggers-protect-stalkers-trolls/){:target="_blank"}{{_}}. I was left with no choice but to re-verify my email address and having to deal with the spam from people scraping WHOIS data, once I did I had to wait a very long time before ICCAN then allowed my domain to point back to my website.

### The alternatives
Regular DNS is not the only DNS system that exists, there are many more I will cover the main ones;

* Tor hidden services
Tor has possibly the most well known alternative domain name system that they use for their Tor hidden services. The domains are cryptographically secure, if you own a domain then without someone getting access to your server nobody can take it away from you and people will know that they are connecting to you. The domains are not held by one party so are decentralized however the domains are not human readable. Most Tor domains look like  this 3g2upl4pq6kufc4m.onion however this problem can be somewhat alleviated by using tools that keep randomly generating domain names and by brute force e.g [Scallion](https://github.com/lachesis/scallion){:target="_blank"}{{_}}, this tool can make the first few characters fit a pattern or word. The big problem with making custom Tor domains is that it will take a long time and a lot of computing power for very custom domains [[REF]](https://github.com/lachesis/scallion){:target="_blank"}{{_}}.

* ZeroNet
ZeroNet is a P2P way of hosting and viewing websites, [I have made a post about ZeroNet previously if you want to know more about it](./blog/about-zeronet){:target="_blank"}{{_}} however in this post I will focus solely on how domain names work. A side note, Mailstrom by bittorrent also exists and operates in a somewhat similar way but I will focus on ZeroNet because it is open source and better in most ways. ZeroNet domains (that don't use Namecoin) are just Bitcoin public keys so start with a 1 and have random letters after it e.g 1BvBMSEYstWetqTFn5Au4m4GFg7xJbNVN2 this public key, it is that simple. This public key is then hashed to find peers that are seeding the website, public private key cryptography is then used to verify that the site you have connected to is the correct site. These domains are cryptographically secure, and are decentralised however they are not human readable. Human readable domains are available to register through Namecoin however the domains for most users are not resolved directly through Namecoin but are resolved through ZeroName a ZeroNet site that lists all .bit domains that point to a ZeroNet address so it is not truly decentralised or secure that being said it is a "proxy" to Namecoin that is both decentralised and secure. Like with Tor hidden services you can use brute force to get a vanity domain, I made [a video showcasing how to do this on my YouTube channel](https://www.youtube.com/watch?v=dBkg837jpZ4){:target="_blank"}{{_}} where I got the ZeroNet domain [http://127.0.0.1:43110/1LennyjL5VUTvwiLtBUjMrZ85gCbVe1dj1](http://127.0.0.1:43110/1LennyjL5VUTvwiLtBUjMrZ85gCbVe1dj1){:target="_blank"}{{_}} [(ZeroNet Proxy of link)](https://zero.acelewis.com/#1LennyjL5VUTvwiLtBUjMrZ85gCbVe1dj1/){:target="_blank"}{{_}}.

* Namecoin
[Namecoin](https://namecoin.org/){:target="_blank"}{{_}} is the DNS that 'squares' Zookos Triangle, it is the first ever solution to the problem and is still the most used solution. Namecoin is also the first fork of Bitcoin after an idea proposed by Arron Swartz to store information in a blockchain [[REF]](http://www.aaronsw.com/weblog/squarezooko){:target="_blank"}{{_}}. I will make a new blog post after this that will go more into blockchains. So Namecoin is technically a cryptocurrency however it has a cool feature that you can save upto 520 bytes [REF](https://namecoin.org/){:target="_blank"}{{_}} of information in a transaction; this information is often used to store DNS entries. This allow you to own domains that end in .bit e.g acelewis.bit. This is an oversimplification but basically by looking at the transactions within the last 6 months in the blockchain you can see what the domain e.g. acelewis.bit points too. Every 6 months-ish the owner of the domain has to renew it, at any time the owner can update the DNS so he/she can change where the domain points too. Namecoin is a digital cryptocurrency so it costs to do these transactions however the cost is so small it is basically free (under £0.04 for over 10 years). Namecoin provides human readable domains, the domains are cryptographically secure and the system is 100% decentralised, this seems perfect but I will go into the cons in its own section.

### The down sides of Namecoin
This section can be summarized in two words, the blockchain. Namecoin relies on blockchain technology, because of this if you want to use Namecoin as intended you need to download the whole blockchain because you need to know every transaction that as ever happened in the whole history of Namecoin just to verify what the domain name points to. Currently the blockchain is 4.6 GB [[REF]](https://bitinfocharts.com/namecoin/){:target="_blank"}{{_}} so you would need to download 4.6 GB just to resolve a domain, this basically makes Namecoin unusable on phones, tablets, Chromebooks and makes it impractical on laptops and desktops. The size of the blockchain is increasing too and will get bigger and bigger as time goes by. The problem of downloading the blockchain can be alleviated by using an external business that you send your DNS queries to and they resolve them for you however this defeats the purpose of Namecoin because it is now no longer decentralised and no longer secure.

### Do we need domains to be human readable?
Most of the websites I visit are in my bookmarks and the othe websites I visit are auto completed for me after I type the first few letters. When I am not on my own computer I often forget if the website I want to visit is a .com, .org or .net so I end up googling it anyway... This has made me think, most websites I visit I click on a link I don't type the URL in so do we really need domains that are human readable?

It does help if you need to share your site in a non-digital manner e.g. in a print advert, or telling a friend. It also means that people making copy-cat/phishing websites have a much harder job because they need to get a URL that looks similar to the real URL, this is not really true they often use load of subdomains e.g accounts.google.com.servicelogin.service.mail.continue.https.mail.google.com.mail.identifier.fakewebsite.com and many users will just look at the start of the domain and not notice that the real website is actually fakewebsite.com. Not having human readable domains could also increase security by virtually eliminating typo squatting a very common way to trick users into providing their details by making a phishing website or other scam website e.g. http://faecbook.com/ (don't go to it).

### AceLewis' Square
Ok so the name may be a bit of a joke but Zookos triangle misses out on one important factor, usability/longevity these two go hand in hand so are the same thing. Current blockchain technology is not usable and has limited longevity due to the increasing storage required to download the whole blockchain. I think Namecoin is brilliant however to successfully create a DNS replacement it needs to be much more user friendly, I don't know how you could satisfy Zookos Triangle without a blockchain but to make a DNS replacement a newer technology needs to be created (or we just ignore the need for human readability).

So a perfect DNS would be;

* Human readable
* Secure
* Decentralized
* Usable
