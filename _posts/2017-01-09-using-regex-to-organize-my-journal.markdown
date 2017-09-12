---
layout: post
title: "Using Regex to Organize My Journal"
date: 2017-01-09T10:11:19+03:00
image: 
summary: For the past four years I’ve been keeping a daily journal in an app called Simplenote, but because of the way I write, they're all out of order. Regex to the rescue!
category: "Side Projects"
---

I just finished another project I assigned myself over my winter break from classes. Like [the one]({{ site.baseurl }}{% post_url 2016-12-20-quirk %}) I completed in December, this was written in C++, but rather than a proof of concept, this had real utility for me. First, some background.

For the past four years I've been keeping a daily journal in an app called [Simplenote](http://app.simplenote.com). Rather than keeping one document and adding a new line for each day, I actually have a separate plain text document for each day of the year. So when January 9 rolls around, I open that document and enter in new paragraph for that year. It looks like this:

*Done: January 9*  
*Monday, 2017: This is a fake journal entry for Monday, January 9, 2017.*

*Saturday, 2016: This is a fake journal entry for Saturday, January 9, 2016.*

*Friday, 2015: This is a fake journal entry for Friday, January 9, 2015.*

I think this is a great way of keep a journal because when I write in it every day I get to see what I've been doing a year ago, and two years ago, and so on. The major downside is that there's not much continuity from day to day. That's what I was trying to solve with my C++ program, [JournalSort](https://github.com/alxmjo/JournalSort).

Completing the project required learning a few new things. I'd never used Regex before, but I since my problem involved reading and filtering strings of text, I knew that I'd have to. I used these websites to get a basic understanding of Regex:

- [RegExr](http://regexr.com/)
- [YouTube video by Bo Qian](https://www.youtube.com/watch?v=_79j_-2xMrQ)
- [RegexOne](https://regexone.com/)

Here are the two capture strings I came up with. This one captures the month and day at the top of each plain text file:

````Done: (January|February|March|April|May|June|July|August
|September|October|November|December) ([0-9]{1,2})\\n````

And this one captures the year and the entry itself:

````(?:Monday|Tuesday|Wednesday|Thursday|Friday|Saturday
|Sunday), ([0-9]{1,4}): (.*)````

Thankfully, Regex is supported in C++11, so there was no need to install any other libraries to use it. 

I also had never worked with C++ maps before, but my use wasn't too complicated so it didn't take long to get them to do what I needed.

The program starts by reading through a folder of plain text documents and parsing them with Regex. 

Once I had the year, month, and day captured, I converted the month to an int and saved the date (in the form YYYYMMDD) and the entry into a map container, with the date as the key and the entry as the value. 

The point of the program was to sort the entries by date, which the map container did automatically. I still needed to convert the date from YYYYMMDD to a long-form format, so I used `strptime()` and `mktime()` to create a `tm` object which I then printed with the C++11 function `put_time()`. 

Now that I had the date how I wanted it and the entry, I simply used a for-loop to print the contents of the `map` container to a single plain text file.

I'd never assembled all of my journal entries into a single file before, so completing this project gave me an opportunity to see that over the past four years I've written about 180,000 words in my journal. That's [the length](http://lotrproject.com/statistics/books/wordscount) of Tolkien's The Fellow of the Ring. Of course, that book is done, but I'm only getting started.