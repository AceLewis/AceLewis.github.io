---
layout: post
title:  "The Emoji that exists but is not real"
url-title: "The Emoji that exists but is not real"
date:   2017-05-06 20:00:00
author:
published: true
categories:
- blog

tags:
- emoji


img: thumbs/emoji-that-does-not-exist.svg
thumb: emoji-that-does-not-exist.svg
---

Everyone knows what emoji are, small pictures that are shared in text often faces or objects. Emoji work cross platform and are very common on phones and sites like Twitter. In this blog post I will tell you about this emoji <i class="twa twa-shibuya"></i> that exists but is not actually real.

<!--more-->

Before proving this weird claim I will need to overview the basics of emoji.

## Sections

 * The Unicode consortium
 * The problem with Unicode for Japan
 * The emoji in question
 * Weirdness of this emoji
 * Conclusion

## The Unicode Consortium
Computers only use binary 1's and 0's to save files/text, these are just numbers. When saving text every character is assigned a number (code point), you send these numbers to someone and when their computer needs to know what number corresponds to what character. This is where problems arose before Unicode existed. Communication between people in different countries (and even computers) was very difficult as they all had their own standards for how character characters should be encoded. The Unicode consortium aimed to allow international communication by having one big unified and agreed upon representation for all character code points by making a character encoding scheme that included all characters from all languages.



## The problem with Unicode for Japan
Japan like the rest of the world made its own character encodings, different mobile companies had their own encoding but it was generally the same. In English and other latin based languages their are not that many characters so you can represent all of them in under 255 numbers (one byte, this is 2^8). Japanese however has far more characters to be encoded, so they used two bytes to store their characters this gave them more than enough available code points (2^16 = 65536). So some Japanese phone carriers decided to make some of these unused code points for little images, these images became what we now know of as emoji.

This was a problem when the Unicode Consortium were trying to get Japan to use it because they wanted to keep their emoji but Unicode was intended for language not images. To allow for international communication the Unicode Consortium were forced to include emoji, that is why we have emoji today.

The fact that emoji's originated in Japan does influence the Emoji character set we have today, many Emoji's don't make much sense to the western world. For example the [love hotel](https://en.wikipedia.org/wiki/Love_hotel){:target="_blank"}{{_}} Emoji 🏩 a concept that is uncommon in the west. Also there is an over representation of trains for the types of trains in Japan, over time emojis for other cultures/foods ect have been included so this is not a problem.

## The emoji in question

The Emoji in question is the 109 (Shibuya), the emoji representation in Twitter is shown here <i class="twa twa-shibuya"></i> and below, if your device natively supports this Emoji then it's representation will be shown here  if not then it will be blank or be a box. This emoji will display on Apple iOS 5, Twitter and Chrome OS. It probably displays on more devices however I don't know how to easily test, I know it does not display on native Windows, native Android and modern iOS.

<div class="title-half">
    <div><b>Emoji on Twitter</b></div>
    <div><b>Emoji on iOS 5</b></div>
</div>

<div class="container-half">
  <img alt="Shibuya 109 Twitter" src="/assets/img/blog/thumbs/emoji-that-does-not-exist.svg"/>
  <img alt="Shibuya 109 IOS5" src="/assets/img/blog/emoji-that-does-not-exist/emoji-that-does-not-exist.png"/>
</div>

Shibuya 109 was included in SoftBank one of the original emoji sets in Japan but was not officially included in Unicode because 109 is a department store and the Unicode Consortium did not want to include emojis for companies. As it was not included in Unicode it is not a "real emoji", as I mentioned a code point should therefore not exist however one does exit and is used for this character  E50A (hex) or 58634 (dec). Technically it is a reserved character number but it was going to be included in Unicode so was used in old versions of iOS and continues to be used on Twitter. Although it is not a real emoji as it is not in Unicode it does exist as it can be used on some platforms and you are able to use it. Other original emojis failed to make be official however they are nowhere to be found.

## Weirdness of this emoji

So this emoji acts a bit weird.

A slightly weird thing I noticed was on the same version of Windows and using the same version of Telegram Desktop I can see the Emoji on one PC but not on the other, there must be other factors too but I can't easily find any.

Many search engines don't allow you to search for it, Bing, Yahoo, DuckDuckGo, Yandex and many other search engines just fail for the emoji, this makes sense as it is not a "real" emoji. DuckDuckGo however displays a weird behaviour, it shows an answer at the top as it usually does for emoji's but will not display any other results [(Search result here)](https://duckduckgo.com/?q=){:target="_blank"}{{_}}. Google does allow you to search for it and as expected other than a few sites that list Emoji all the other uses seem to be on Japanese sites. SearchX and Ask.com also are able to search for this emoji.

The weirdest behaviour of this emoji is when you search for it on Twitter, Twitter officially supports this Emoji and it is used in many tweets for example [one I made here](https://twitter.com/_AceLewis/status/861003749917163520){:target="_blank"}{{_}}. However when you search for the emoji Twitter fails and returns no results. Twitter is a place where this emoji should return something but it simply fails to do so, in the search result it shows the emoji too. 

![Emoji Search](/assets/img/blog/emoji-that-does-not-exist/twitter-search-fail.png){: .center-image }

## Conclusion

This 109 emoji used to exist on Japanese phones, when Unicode was created it included the emoji from Japanese phones. This emoji was excluded but does exist in some form and is supported by some websites e.g. Twitter. It is not a real emoji but it does exist as an emoji, and finally the Emoji has weird behaviour even on Twitter a platform you would expect to support it.
