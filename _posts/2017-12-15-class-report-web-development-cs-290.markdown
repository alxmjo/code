---
layout: post
title: "Class Report: Web Development (CS 290)"
date: 2017-12-15T11:55:16-08:00
image: /images/cs290-notesheet.jpg
summary: This course, which I completed in Fall 2017, covered HTML, CSS, JavaScript, Node, and MySQL.
permalink: osu-cs290-class-report
category: "Oregon State University"
tags: newsletter class-report
---

![sheet](/images/cs290-notesheet.jpg)
*Part of the note sheet that I used for the final.*

This fall I took two courses: Web Development and Databases. This post summarizes my experiences with the latter, and offers some advice for people taking the course in the future. 

### Instructor

Luyao Zhang

### Topics

- HTML
- CSS
- JavaScript
- TCP/IP
- DOM
- Ajax
- Node.js
- Express
- Handlebars
- MySQL

### Programming Environment

In comparison to my introductory courses (CS 161 and 162), data structures (CS 261), and assembly (CS 271), this course did not involve a lot of coding. As such, I spent most of my time coding in [Sublime Text 3](https://www.sublimetext.com/3). 

It was easy enough to run my Node apps on Oregon State's FLIP server, so I never ran them locally, although I did install Node so that I could run simple JavaScript apps from my command-line. 

Here are some commands I found to be helpful when setting up and running Node servers on FLIP.

Install [forever](https://github.com/foreverjs/forever) to run Node servers continuously:  

`npm install forever`

Start a forever process to run a Node server continuously:  

`./node_modules/forever/bin/forever start [file.js] [port]`

Show currently running Node servers (must run from whichever folder contains your node_modules folder):  

`./node_modules/forever/bin/forever list`

### Assignments

None of the assignments, save for the last, were particularly difficult. Here are a few examples of tasks we had to complete for assignments: 

- Create and style an webpage with HTML and CSS
- Complete [challenges](http://eloquentjavascript.net/04_data.html#h_IJBU+aXOIC) laid out in the book [Eloquent JavaScript](http://eloquentjavascript.net/)
- Create comparison operators for custom objects
- Handle events and manipulate the DOM
- Send GET and POST requests
- Interact with a MySQL database (the most challenging of the bunch)

The final project for the course was easy (though it was open-ended so could be made more difficult depending on what the person decided to do). It didn't require much JavaScript (only enough for a slideshow) and didn't require database interaction at all. I got really NASA's Mars Photos API and so for my project I built an Instagram-like site based on it. You can see it [here](http://projects.alexmontjohn.com/rovergram/).

![rovergram website](/images/rovergram-screencap.png)
*A screen-capture of my final project.*

### Exam

There was no midterm and no quizzes, just a final. The final was difficult but I had earned perfect scores on all of my assignments so I wasn't too worried about doing well. We were allowed a hand-written sheet of notes, which was very useful. I wrote down lots of code snippets, especially for JavaScript and Express.

Another thing that helped on the exam was creating a few flashcards for each week of the course and reviewing them every day. It only takes a few minutes but goes a long way in helping me remember things. I use an app called [Anki](https://apps.ankiweb.net/). 

### Extra Resources

A couple weeks before the course started I began an Udemy course by Colt Steele called the [Web Developer Bootcamp](https://www.udemy.com/the-web-developer-bootcamp/). Colt is a natural instructor and so I highly recommend taking his course if you want to get a leg up on the material. Just don't pay full-price for the course, it goes on sale all the time so you should be able to find it for $15 or less.

One note about Colt's course: The instruction is so good that it often made Oregon State's web development course very, very boring. If you want to get a head start, great, but just know that it's not necessary. 

At the beginning of the term I checked out a bunch of JavaScript books from the library. JavaScript is known for being strange in parts, but aside from [closures](https://stackoverflow.com/questions/111102/how-do-javascript-closures-work), the course doesn't cover anything too complicated. If I were going to dig further into JavaScript I'm sure I'd find books like [JavaScript: The Good Parts](http://shop.oreilly.com/product/9780596517748.do) helpful, but they were unnecessary for this course.

### Difficulty and Time Commitment

This course was straightforward and not particularly difficult. I spent 87 hours on the course over the entire semester, including the Udemy course I took at the beginning of the term. That works out to a little under nine hours per week. If I had decided against doing the Udemy course and had done the bare minimum for my final project, I probably could've gotten this down to about 65 hours or so. 

My 

### Enjoyment

This course was fine. Web development is not my number one interest in the world of programming, but I feel like the course designer, Justin Wolford, did a good job of covering an extraordinarily broad subject in a short period of time. If I decided to make a web app tomorrow, I think I'd have a reasonably good idea where to start. The only thing we never really touched on was how to handle users: accounts, passwords, etc.

Another thing to credit to Justin Wolford and Luyao Zhang is that the course was well-organized. Course content, expectations, and deadlines were very clear.

### Final Grade: A