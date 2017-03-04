---
layout: post
title:  "Coding Challenge: Rotate your vowels"
url-title: "Coding Challenge: Rotate your vowels"
date:   2017-03-04 11:43:00
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
This is the first coding challenge snippet that I am going to share on my website.

The coding challenge here is to rotate the vowels in a given string multiple times and then print the rotated strings.
<!--more-->

## Sections
 * What are coding challenges?
 * Rotate your vowels
 * Solutions
 * Table of performance
 * Conclusion

## What are coding challenges?
Coding challenges are little challenges that I am going to use to highlight features of programming languages. The main language I will start these challenges in will be Python however in the future I may also use other languages. I will in some cases show multiple ways of doing each coding challenge.

## Rotate your vowels
First off the challenge name is a joke based of a silly old music video [Rotate Your Owl](https://www.youtube.com/watch?v=9hBpF_Zj4OA){:target="_blank"}{{_}} which in turn is based off [a video showing the head stability of owls](https://www.youtube.com/watch?v=k6M-h5g3PwI){:target="_blank"}{{_}}. So the challenge I found is from [Writing Impositions in Matlab](http://www.debipattnaik.com/writing-impositions-in-matlab/){:target="_blank"}{{_}}. The challenge is simple for any input string change all a's to e's, e's to i's and so on, effectively rotating the vowels in the string. Also you should apply this rotation multiple times printing it out each time.

## Solutions

The code for all solutions can be found [here on my GitHub](https://github.com/AceLewis/AceLewis-Miscellaneous-Code/tree/master/Rotate-your-vowels){:target="_blank"}{{_}}. I have broken down each solution here.

### regex
So we want to be able to swap only the vowels, we can use regex to only select vowels then input the vowel matched into a lambda function to find the corresponding substituted vowel.

The pros of this method is it shows regex a good way to match strings and it shows that functions can be used in regex in Python. Functions in regex are very useful in certain circumstances. It also shows lambda functions in Python, although the `def` style functions are in most cases preferred. The con is that using regex is overkill on such a simple problem. [Code here.](https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/Rotate-your-vowels/regex_solution.py){:target="_blank"}{{_}}

<script src="http://gist-it.appspot.com/https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/Rotate-your-vowels/regex_solution.py?footer=minimal"></script>

### The indexing method

This method relies on the `.find` method returning `-1` if the string is not found. `-1` is also the way to index the last thing in an string, so by putting the character on the end of the string means that if the character is not found by `.find` it will default to the character. [Code here.](https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/Rotate-your-vowels/positional_solution.py){:target="_blank"}{{_}}

<script src="http://gist-it.appspot.com/https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/Rotate-your-vowels/positional_solution.py?footer=minimal"></script>

### The dictionary method

This is solution relies on using the vowels as key, values. The dictionary is built via using `zip` to pair up the characters in the two strings. Also the `.get` on the dictionary uses a default value if the key is not found. [Code here.](https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/Rotate-your-vowels/dictionary_solution.py){:target="_blank"}{{_}}

<script src="http://gist-it.appspot.com/https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/Rotate-your-vowels/dictionary_solution.py?footer=minimal"></script>

### The string translate method

The last method is using the string translate function, this function is built to do these translations so is the fastest. [Code here.](https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/Rotate-your-vowels/str_translate_solution_min.py){:target="_blank"}{{_}}

<script src="http://gist-it.appspot.com/https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/Rotate-your-vowels/str_translate_solution_min.py?footer=minimal"></script>

I also made code that can be used to easily do this translation on other letters and by different amounts of shift. [Code here.](https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/Rotate-your-vowels/str_translate_solution.py){:target="_blank"}{{_}}

<script src="http://gist-it.appspot.com/https://github.com/AceLewis/AceLewis-Miscellaneous-Code/blob/master/Rotate-your-vowels/str_translate_solution.py?footer=minimal"></script>

## Table of performance

Performance is not everything, readability counts however I have also compared the execution time of these pieces of code to translate the string 100,000 times (without printing to the console).

| Method           | Time   |
|------------------|--------|
| regex            | 1.07 s |
| indexing         | 2.22 s |
| dictionary       | 1.10 s |
| string translate | 0.39 s |

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

I knew the string translate method would be fastest however I am surprised that the regex solution was that fast, I thought it would be slower than the other methods. I also thought that the indexing method would be the second fastest as it only used basic inbuilts however it was twice as slow as the other methods, however looking in hindsight it makes sense because the dictionary method builds the dictionary once whilst in the indexing method the string used for indexing is built on repeatedly.

## Conclusion

To conclude I have shown multiple ways to solve the problem and have showcased many features of Python.
