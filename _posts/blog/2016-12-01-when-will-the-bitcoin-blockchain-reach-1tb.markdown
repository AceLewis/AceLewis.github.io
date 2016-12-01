---
layout: post
title:  "When will the Bitcoin blockchain reach 1TB?"
url-title: "When will the Bitcoin blockchain reach 1TB?"
date:   2016-12-01 21:01:00
author:
published: true
categories:
- blog

tags:
- bitcoin
- p2p
- blockchain


img: /thumbs/bitcoin.svg
thumb: bitcoin.svg
---
Bitcoin's blockchain is the centre of the cryptocurrency and contains every transaction that as ever happened in Bitcoins history. The file size of the blockchain is increasing, it is currently over 80 GB however when will it be over 1TB.
<!--more-->

## Sections
So I have broken this post into a few sections

 * What is the blockchain?
 * How to estimate the blockchain size in the future
 * What does this all mean
 * Not all doom and gloom

## What is the blockchain?
I will explain briefly how Bitcoin works but I will not go into any of the maths/algorithms used as to understand this you only need to understand how Bitcoin works in a broad context and not too much in detail.

So first, Bitcoins are not physical possessions. You don't have a file that contains a Bitcoin, all you have is basically an account number in this case your public key. When you want to give some Bitcoins to someone else you don't send them anything but you sign the amount that you want to give them with your private key (look into public [private key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography){:target="_blank"}{{_}}, it is cool and not only at the centre of Bitcoin but is instrumental to HTTPS/SSL). When you sign the transaction you post it on "the Bitcoin network" the many people that mine Bitcoins then look at the transaction to verify it.

The verification process evolves looking to see if you have the Bitcoins in your account, the miners do this by looking at every transaction that has ever happened in the history of Bitcoin to see if you have the Bitcoins you claim you do. Once the miners have verified that you have the coins you say you do then they verify that you have not tried to send the bitcoins to someone else at the same time (double spending) once all the checks have passed it is verified and added to the Bitcoin blockchain, after 6 verifications you can say with out a shadow of a doubt that the Bitcoins were sent without any funny business going on (aka the person trying to spend the Bitcoins twice) this process takes about 1 hour however after 10-30 mins the money sent to you is probably legit and some places don't even wait for verification if they deal with amounts of money that are relatively small.

So in summary the blockchain stores every transaction that has ever happened in Bitcoins history and is needed for Bitcoin to work, as the total number of transactions is increasing so the file size of the blockchain is also increasing.

### How I estimated the future filesize of the blockchain
 So all you need to do is three steps 1. get the data, 2. fit the data to an equation, and 3. use this fitting to estimate the filesize in the future.

#### Getting the data
So first I needed the data on the historical filesize of the blockchain, I could have done this by downloading the blockchain but as it is over 80GB I just used [https://blockchain.info](https://blockchain.info){:target="_blank"}{{_}}. On this website you can do a simple request to get the historical filesize of each day since Bitcoin was created. The request can return a JSON object and that is super easy to work with in Python.

#### Fitting the data to an equation
Blockchain.info displays the graph of the blockchains size and it is clearly an exponential so that was the fitting used.

The data was then fit to an exponential equation with the "curve_fit" curve fitting tool in SciPy, to help this function converge on the correct answer the input data has to be modified slightly. First the time of each day was formatted in the unix timestamp (Just a number stating the number of seconds since midnight 1st January 1970) this means that the number starts very large to correct for this I just shifted the time so that the timestamp started on the 1st March 2009 the starting date of Bitcoin. The second thing I had to do was divide each fitting parameter by mean of that parameter so the numbers were small. After these steps were done the curve_fit tool converged to a correct fitting.

<img src="/assets/img/blog/bitcoin-blockchain-1tb/blockchain_size_fitting.svg" width="80%" class="center-image">

The data and fitting were then plotted to see how well the exponential fit the data, to plot the fitted data the reverse steps were taken that were done so the curvefit converged. As you can see below the fittting was good, this means that it can be used to estimate the blockchain size in the future.

## Estimating the future file size
As we already have the equation for the blockchain size and the fitting parameters for it we can simply extrapolate this to see when the equation is equal to 1TB.

### My Estimations
Ok, so I believe my fitting was pretty good however the vast difference between 80GB and 1TB is so big that it will not be that accurate however it will give a good indication of the timescale until this even takes place assuming the growth continues to be exponential. That being said I estimate that the Bitcoin blockchain will reach 1TB around October 2022, the graph of the fitting and the historical data so far is shown below.

<img src="/assets/img/blog/bitcoin-blockchain-1tb/blockchain_size_estimate.svg" width="80%" class="center-image">

I also have a table of my estimations for other key events;

| File Size  | Estimated Date    |
|------------|-------------------|
| 100 GB     | 22 January 2017   |
| 250 GB     | 21 December 2018  |
| 500 GB     | 18 September 2020 |
| 750 GB     | 15 November 2021  |
| 1000 GB    | 06 October 2022   |

<style>
table:nth-of-type(1) {
    display:table;
    width:80%;
    margin-left:15%;
}
table:nth-of-type(1) th:nth-of-type(2) {
    width:50%;
}
</style>

### Not all doom and gloom
First off this is an estimation that is biased on the blockchains file size continuing to grow exponentially, small errors in the fitting are also amplified in the extrapolation from 80GB to 1000GB so the estimation is not that accurate, although not accurate it does give a good indication of the timescale that it will take.

I want to clarify that the blockchain reaching 1TB is not disastrous for the users of Bitcoin. If you want to receive and spend Bitcoins you can just use a light/thin wallet whereby you don't need to download the blockchain you just use this client it will act like a client that does have the blockchain however it just sends the requests to a server run by the people that made the client and that server can tell you how much Bitcoins you own, it can tell you what adress' paid you and allows you to send Bitcoins to however you want. Thin clients do NOT know your private key so they can't steal or deny you access to your Bitcoins (unlike web services like CoinBase) however they can reduce anonymity. They also can increase your anonymity because you could combine Tor and a thin client to only ever do transactions using Tor, it would be unfeasible to do transactions in Tor without a think client because that would require downloading the blockchain and anyone who has used Tor will know it is too slow to download it in any reasonable amount of time.

You could also use a web-based service to send and receive Bitcoins for example CoinBase however I would heavily recommend using a thin client because they are as easy and simple to use but do not come with the massive drawbacks like your Bitcoins being stolen or you being denied access to your wallet and thus not allowing you to spend any Bitcoins you own (the digital equivalent to burning your money).

Also if you want to mine Bitcoins you don't need to download the whole blockchain you can join a mining pool for example [SlushPool](https://slushpool.com/home/){:target="_blank"}{{_}}, when you are in a mining pool everyone attempts to mine Bitcoins and when someone successfully mines a Bitcoin the profits are shared out between everyone. If you want to mine Bitcoins without being in a mining pool due to the small fees associated with them then you have to download the whole blockchain.

### The code
The code used to gather the data and to make the estimations was done in Python, it will be uploaded to [my GitHub](https://github.com/AceLewis){:target="_blank"}{{_}} soon.

I am going to be doing a few more blogs on topics like this so if you are interested then maybe you should bookmark me.
