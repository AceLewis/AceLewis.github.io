---
layout: post
title:  "Coding Challenge: HipsterPy"
url-title: "Coding Challenge: HipsterPy"
date:   2017-03-27 12:00:00
author:
published: true
categories:
- post
category: post

tags:
- python
- regex
- coding
- coding challenge


img: thumbs/coding-icon.svg
thumb: coding-icon.svg
---
The coding challenge here is to "Hipsterfy" a sentence by removing the last vowel in the word as long as is is not also the first letter of a word.
<!--more-->

## Sections
 * HipsterPy
 * Solution
 * Conclusion


## HipsterPy
In HipsterPy I will "Hipsterfy" words or sentences in Python. The challenge is eaily done in Regex so can be re-created in any language that has Regex, which is most languages. All that needs to be done is to remove the last vowel in every word in a sentence, the vowel  e.g: "A Hipster follows the latest trends and fashions." goes to "A Hipstr follws th latst trnds and fashins.".

## Solutions

The solution to this problem is in Regex, the solution can be found on [my GitHub](https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/HipsterPy/Hipster.py){:target="_blank"}{{_}} and is also shown below.

<script src="http://gist-it.appspot.com/https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/HipsterPy/Hipster.py?footer=minimal"></script>

It is basically just Regex, I will break down the Regex to explain the steps.

`r"(?i)([^\s])[aeiou]([^aeiou]*)\b"`

The first part `(?i)` means case insensitive for the whole Regex. The `([^\s])` means group 1 will be any single character that is not whitespace, `[aeiou]` is simply match any vowel. `([^aeiou]*)` is get all characters that are not vowels (including no letters at all) after the matched vowel and they will be in group 2, and finally `\b` is a word bondary.

For example in `"HipsterPy"` you match `"terPy"` with `"t"` being in group 1 and `"rPy"` being in group 2. You then substitute the whole match `"terPy"` with group 1 and 2 added together `"trPy"`, this substitution gives you `"HipstrPy"`.

## Conclusion

I have shown how Regex can easily solve a problem with a solution that is easy to understand (so long as you know Regex) and is much shorter than other methods that could be used. I do like Regex as it is very powerful for matching strings in text however it does have its limits and can easily become hard to read for more complex problems.
