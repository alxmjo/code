---
layout: post
title: "Class Report: Algorithms (CS 325)"
date: 2018-03-31T19:00:17-07:00
image: /images/cs325-notesheet.jpg
summary: "This term I took two courses: Algorithms and Software Development I. This post summarizes my experiences with the former, and offers some advice for people taking the class in the future."
permalink: osu-cs325-class-report
category: "Oregon State University"
tags: newsletter
---

![sheet](/images/cs325-notesheet.jpg)
*Part of the cheat sheet that I used for the final, with room to spare!*

This term I took two courses: Algorithms and Software Engineering I. This post summarizes my experiences with the former, and offers some advice for people taking the class in the future.

### Instructor 
Julianne Schutfort

### Topics
Each week of the course (excepting those preceding exams) focused on a particular topic or problem. Here they are, in order:
- Asymptotic Analysis
- Recurrences
- Dynamic Programming
- Greedy Algorithms
- Linear Programming
- P and NP Problems
- Graph Algorithms
- The Traveling Salesman Problem

### Preparation
I spent so much time preparing for [Web Development](/osu-cs290-class-report) and [Databases](/osu-cs340-class-report) last term that it made the courses themselves a bit boring. This term I didn't spend much time preparing for Algorithms or Software Engineering I. That said, here are a couple of things I did that I'd recommend to others: buy a paper copy of [Grokking Algorithms](https://www.manning.com/books/grokking-algorithms) (so that you can take a break from looking at your computer) and familiarize yourself with data structures and file I/O in the language you'll be using for the class. I chose C++, so this meant reviewing the Standard Template Library (vectors, specifically) and making sure I knew how to read and write to a plain text document.  

You may also find, as I did, that a few of the things you were exposed to in [Data Structures](/osu-cs261-class-report) are helpful for this course. Namely, big-O analysis and how stacks, queues, and graphs work. I didn't review any notes from Data Structures, but I did find myself returning to the same resources I used during that course, like the [Dictionary of Algorithms and Data Structures](https://xlinux.nist.gov/dads/).

### Programming Environment
I try to maintain as much consistency as possible between courses, so I did all of my homework in C++ with the CLion IDE. I used git and GitHub for version control, and tested all of my programs on Oregon State's FLIP server. I also occasionally used [Repl.it](Repl.ithttp://repl.it), which is a great resource if you just need to write or test a snippet of code without creating an entire project in an IDE.

### Assignments
One thing I really appreciated about this course is that each assignment followed essentially the same format from week to week. This reduces the overhead for getting started on an assignment because you can reuse code snippets and text documents from previous assignments. This allows you to dive straight into the material, which should always be the goal.

Speaking of reusing code, having good functions for reading from and writing to plain text files saved me a ton of extra work. For reading, I used nested vectors wherein each string on a line was read into a vector, and then each of those vectors was stored in a parent vector. Writing followed the same process in reverse. The code smelled a bit, but it was fast and portable, and certainly beat devising a completely new I/O strategy for every assignment.

When it comes time to start the final project, try to choose your group members yourself. Obviously it's best if you know the person and their habits and abilities well, but even if you don't, I swear there's a psychological benefit that comes with having chosen your lot instead of having been randomly assigned.

### Exams
The course has a midterm and a final. I found the midterm more difficult than the final, but I also scored higher on it (I earned a 90 percent on the midterm and an 85 percent on the final).

When I first attempted the midterm practice test, I could barely answer a single question. This freaked me out a bit, but thankfully I'd taken the practice test over a week before the midterm was due, so I had a lot of time to sort myself out. This was my basic study strategy:

1. Attempt practice problem with pen and paper
2. Fail
3. Understand why my idea didn't work and why the correct strategy does
4. Copy the correct strategy's name, running-time, and pseudo-code, and description of the correct strategy onto my cheat sheet
5. Find similar problems (in [Algorithms, Etc.](http://jeffe.cs.illinois.edu/teaching/algorithms/) or elsewhere) and figure out how to adapt the strategy or algorithm on my cheat sheet to solve that particular problem
6. Repeat

That last part, adapting the algorithm on your cheat sheet to the problem in front of you, is key. That's because the exams aren't really testing you on whether you can, for example,  devise a dynamic programming algorithm from scratch that correctly determines the most advantageous way to rent canoes along a river. Instead, it's testing you on whether or not you can identify the "bones" of the problem and adapt something you've already seen to solve that problem.

I'll always make a cheat sheet if I have the opportunity, but most of the time I barely look at it during the test. That was not the case for this course: **the cheat sheet was a critical resource for both the midterm and the final**. I found myself looking at it for almost every question.

[This](/files/CS325-Midterm-CheatSheet.pdf) is the cheat sheet I used for the midterm and [this](/files/CS325-Final-CheatSheet.pdf) is the cheat sheet I used for the final. Both served me well. However, if I had just found them instead of making them myself, I doubt they would've held much utility. Hopefully this isn't news to anyone, but don't just print out and use someone else's cheat sheet! At the very least, copy it over by hand so you know what information is on it and where that information is located. 

Based on what I saw on Slack, it seems like most people type out their cheat sheets so that they can fit more information on the page. I understand that desire, but if you have halfway decent handwriting and can write small, do it by hand. It'll force you to slow down and prevent you from copying code from elsewhere without actually thinking about what the code does or how it works. Both of those things will result in better understanding and better retention.

Both the midterm and final had questions wherein you're asked to compare the runtimes of different functions. If you're having a hard time figuring out which function grows faster, or if you simply want to check your work, use a graphing calculator. Substitute x for n and type it in and then use the TABLE function to see how the y values change as x increases. Usually starting the comparison at x = 100 was enough to see a pattern.

### Extra Resources
- [Dynamic programming demonstrations by Tushar Roy](https://www.youtube.com/channel/UCZLJf_R2sWyUtXSKiKlyvAw)
- [Lectures by Erik Demaine](http://erikdemaine.org/classes/)
- [Dictionary of Algorithms and Data Structures](https://xlinux.nist.gov/dads/)

### General Strategy
As with all of my classes, I always try to start as early in the week as possible. Even just writing down the week's tasks on Sunday night makes for a much less stressful week. I'd make a comment or two in the discussion board by Monday. This often started a conversation that led to the rest of my posts for that week. Before I watched the lectures for the week I would try to find a simple summary of the topic (via Grokking Algorithms, YouTube, Wikipedia, etc.). Then came the lectures. I rarely found them helpful, so I ended up watching them on 2x speed just to make sure that I wasn't missing anything. Then onto the reading. I found CLRS boring and dense, so I often just skimmed these chapters to make sure that I wasn't missing anything important. [Algorithms, Etc.](http://jeffe.cs.illinois.edu/teaching/algorithms/) was much more interesting, so I'd usually read these chapters in full. At this point I'd try to focus on another class for a few hours or a day so that everything I'd learned could settle in. Then, before I started the homework, I'd try to fill in the gaps in my knowledge by watching more videos online. I often ended up watching Erik Demaine's lectures via [MIT OpenCourseWare](https://ocw.mit.edu/index.htm). He's great.

A note on extra credit: I went into the final with over 100 percent in the course, thanks in part to intermittent opportunities to earn extra credit. Take advantage of these! If subsequent terms are graded like this term, you'll receive an extra point in each discussion for posting early and often (I usually ended up with about 15 posts per week, which is not challenging if you're actively asking and answering questions). In addition, the extra credit offered in the assignments themselves didn't take much extra time to complete. Just make sure to do it when it's offered, since only a few assignments offer extra credit opportunities.

### Difficulty and Time Commitment
The first few weeks of this course are quite difficult, but I didn't find them any more challenging or overwhelming than Data Structures or Assembly. Some of the concepts covered in later weeks (like P and NP) were more *conceptually* challenging than everything else we'd covered in the program, but not impossibly so. The key is to accept that most of the things you study in this course are not immediately intuitive (at least for me), and so it takes some time to understand them. And when I say time, I literally mean the passage of time. Do the reading and then come back to it after an hour or a day. I think you'll find that while you were away your subconscious has sorted and clarified things for you. If you're curious about this concept (and you should be!), check out [this book](http://www.powells.com/book/mind-for-numbers-how-to-excel-at-math-science-even-if-you-flunked-algebra-9780399165245) by Barbara Oakley, or the [Coursera course](https://www.coursera.org/learn/learning-how-to-learn) on the same subject.

I spent about 120 hours on this course, which works out to about 12 hours per week. To put that in perspective, I spent about 8 hours per week on Software Engineering I (which I also took this term), 9 hours per week on Databases, and 9 hours per week on Web Development. Unfortunately I don't have accurate data for the courses I took before that. Note that this is focused, "nose-in-the-book" study time. I didn't count the time I spent getting up and going to the bathroom, eating lunch, daydreaming, etc.

For what it's worth, I took two other courses this term (Software Engineering I at Oregon State and Calculus III at Portland Community College). I also take care of my one-year-old daughter (along with my wife and in-laws) and volunteer one afternoon per week at a local high school teaching computer science.

### Enjoyment
The only thing I didn't like about this course was the lectures. They're long, unfocused, and poorly produced. This was the only criticism I offered in the course evaluation, and it's definitely the lowest hanging fruit for improvement. As a teacher myself, I can appreciate that making good lecture videos is difficult and time-consuming, but it's also every online student's primary point of contact with their instructor, program, and school. There's really no excuse for them to be anything other than great. 

### Final Grade: A