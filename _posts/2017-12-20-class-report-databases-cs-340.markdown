---
layout: post
title: "Class Report: Databases (CS 340)"
date: 2017-12-20T06:53:41-08:00
image: /images/cs340-notesheet.jpg
summary: "This fall I took two courses: Web Development and Databases. This post summarizes my experiences with the latter, and offers some advice for people taking the class in the future."
permalink: osu-cs340-class-report
category: "Oregon State University"
tags: newsletter class-report
---

![sheet](/images/cs340-notesheet.jpg)
*Part of the note sheet that I used for the final.*

This fall I took two courses: Web Development and Databases. This post summarizes my experiences with the latter, and offers some advice for people taking the class in the future. 

### Instructor

Samarendra Hedaoo

### Topics

- Entity-Relationship Models
- Schemas
- Database Normalization
- Object-Relational Mapping
- MySQL
- Keys (Primary and Foreign)
- Joins
- Aggregate Functions
- phpMyAdmin
- Node.js

### Preparation

I had some downtime after summer term so I used it to prepare for the classes I took over fall term: databases and web development. For databases, I took this excellent [Udemy course](https://www.udemy.com/the-ultimate-mysql-bootcamp-go-from-sql-beginner-to-expert/learn/v4/overview) by Colt Steele. While it won't prepare you for the conceptual side of CS 340, it'll go a long way in getting you comfortable with creating, reading, updating, and deleting data with MySQL. Just make sure you don't pay full price for it — it goes on sale a lot.

### Programming Environment

With the exception of the final project, this course didn't involve much programming. When I did need to code, I spent most of my time in [Sublime Text 3](https://www.sublimetext.com/3). Occasionally I'd use [Cloud9](https://c9.io) because I found the interface simpler than phpMyAdmin (to use MySQL, create a new HTML5 workspace and then from the terminal type `mysql-ctl cli` – this sets up a command-line interface for MySQL through which you can create and use databases). 

When I needed files from FLIP I'd download them with Cyberduck. This was especially useful for the final project, when I was constantly downloading files, changing them, and then re-uploading.

It was easy enough to run my Node apps on Oregon State's FLIP server, so I never ran them locally, although I did install Node so that I could run simple JavaScript apps from my command-line. 

Here are some commands I found to be helpful when setting up and running Node servers on FLIP.

Install [forever](https://github.com/foreverjs/forever) to run Node servers continuously:  

`npm install forever`

Start a forever process to run a Node server continuously:  

`./node_modules/forever/bin/forever start [file.js] [port]`

Show currently running Node servers (must run from whichever folder contains your node_modules folder):  

`./node_modules/forever/bin/forever list`

### Assignments

None of the assignments were particularly difficult, though the final project did take up a fair bit of time. Here are a few examples of tasks we had to complete for assignments: 

- Get a Node server running and connect it to a MySQL database
- Create a plan for the final project
- Create schemas and ER diagrams
- Select certain entities from a given database
- Convert MySQL queries to relational algebra statements and vice versa

The final project required creating a database that modeled something with a variety of tables. The database was required to have C.R.U.D. functionality: it had to be possible to create, read, update, and delete data. My groupmate and I chose to model the Game of Thrones universe, with tables representing characters, houses, appearances, locations, and episodes. Styling wasn't necessary, but I had gained some experience with the [Bulma CSS library](https://bulma.io/) in my web development class and so we used it to make our website a bit prettier. You can see the final product [here](http://flip3.engr.oregonstate.edu:6765/) (after connecting to Oregon State's network via VPN), at least until they delete it.

![got database website](/images/adofai-screencap.png)
*A screen-capture of my final project.*

### Quizzes

There were six quizzes, but they were unproctored, open-note, and could be taken as many times as necessary, so it's probably more accurate to describe these as assignments. 

### Exam

This class had a final and no midterms. The final was somewhat difficult but I had done well on all of my assignments so I wasn't too worried about acing it. We were allowed a hand-written sheet of notes, which was useful. 

Another thing that helped on the exam was creating a few flashcards for each week of the course and reviewing them every day. It only takes a few minutes but goes a long way in helping me remember things. I use an app called [Anki](https://apps.ankiweb.net/). 

### Extra Resources

In addition to the resources I've already mentioned (Udemy, Cloud9), I used [LeetCode](https://leetcode.com/problemset/database/) to practice MySQL queries. 

### Difficulty and Time Commitment

This course was straightforward and not particularly difficult. I spent 86 hours on the course over the entire semester, including the Udemy course I took at the beginning of the term. That works out to a little under nine hours per week. If I had decided against doing the Udemy course and had done the bare minimum for my final project, I probably could've gotten this down to about 60 hours or so. 

### Enjoyment

You won't find me creating and maintaining databases in my spare time, but one thing that I came to enjoy about this course is that it's specifically oriented toward solving problems. I don't mean problems in the general sense, I mean small, discrete problems like "Given a database which represents a video rental store, find the most and least popular dramas." That's not the whole class, obviously, but it's still fun. 

I also enjoyed completing the final project, in large part because I had a good working relationship with my partner. I felt like we created a good product together.

The course wasn't quite as well-organized as others I've taken from Oregon State (CS 271, CS 290) but it wasn't the worst, either.

### Final Grade: A