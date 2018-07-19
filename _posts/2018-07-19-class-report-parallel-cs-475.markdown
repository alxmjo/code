---
layout: post
date: 2018-07-19T06:20:46-07:00
permalink: class-report-parallel-cs-475

title: "Class Report: Parallel Programming (CS 475)"
image: 
summary: I took parallel programming this spring. It focused on a variety of parallel programming libraries and the hardware that they depend on.
category: "Oregon State University"
tags: 
sharing:                # Text to be shared on each network.
  twitter: 
  facebook: 
  linkedin:
---

### Instructor
Mike Bailey and Paris Kalathas

### Topics
Here's a general overview of the topics we covered:

- OpenMP
- Amdahl's Law and Moore's Law
- Caching
- Prefetching
- Parallel design patterns
- SIMD (single instruction multiple data) processing
- Xeon Phi processors
- GPUs
- OpenCL
- MPI
- OpenGL

### Preparation
I didn't do any advanced preparation for this course.

### Programming Environment
I did all of my programming on my MacBook Pro using CLion and Sublime. It takes a little bit of work to get some of the libraries (OpenGL in particular) installed.

Most of the assignments can be run on Oregon State's flip server, but then you're sharing the processors with other students, many of whom might be trying to finish an assignment at the same time as you.

### Assignments
This class is based on weekly programming assignments, each of which are centered around the application of a particular parallel programming library. Professor Bailey provides some snippets of code and then it's up to you to figure out how they fit together and what needs to be filled in. 

The assignments generally focus on solving a problem, like modeling animal populations, or calculating the volume between two Bézier surfaces. We'd then compile data about the performance of that modeling in the form of calculations per second. Needless to say, as more parallelism is employed, you generally expect to see number of calculations per second increase.  

That data is then imported into a graphing application like Excel in order to show how calculations per second are affected by, say, the number of threads being used. This data can be very noisy, though, so it was usually necessary to run the program 10 or more times to get good averages.

One very valuable tool I took away from this course was Bash scripting. While it's possible to compile those averages within the program executables themselves, I found it much easier to run them from Bash scripts and then capture and average the output. This is also good abstraction: let the C++ executable focus on the programming task and let the Bash script focus on the data compilation. Here's the [Bash script](https://gist.github.com/alxmjo/50ee37c1bd6dc4d0e42fbafa9efcc0cb) which I adapted for most of the assignments.

### Quizzes
Each week finishes with a short quiz. I saved the questions and answers in a flashcard program called [Anki](https://apps.ankiweb.net/) and then used them to study for the exams.

### Exams
A midterm and a final. They were quick and easy, though I felt like a few questions were overly subjective.

### Extra Resources
Besides an occasional search on Stack Overflow and the OpenMP/OpenGL/OpenCL/MPI docs, I didn't use any outside resources for this course.

### Difficulty and Time Commitment
The workload for this class was relatively light. I spent about 60 hours on it total. The subject matter is mostly straightforward and Professor Bailey's lectures do a good job of explaining it. The only thing that makes it *seem* difficult is that the cutoff for an A was 97 percent, so if you're gunning for an A, it might take a little bit more work.

For what it's worth, I took two other courses this term (Computer Networks at Oregon State and Calculus IV at Portland Community College). I also take care of my daughter (along with my wife and in-laws).

### Enjoyment
I chose this class mostly because I'd heard good things about the class (mostly from Huff, a fellow student who I've met a few times in Portland) and because I'd heard good things about the instructor (from pretty much everyone on Slack). 

But this turned out to be a strange class. During the second week we heard from the department head that because of some unexpected event (I seem to remember that it was health-related), Professor Bailey would not be finishing the term and would be replaced by someone else. 

We found out shortly thereafter that his replacement would be an Oregon State graduate student named Paris Kalathas. I thought Paris did an excellent job, considering the circumstances. He kept the class running smoothly and was always easy to get in touch with. I still wish I'd had a chance to take the entire course from Professor Bailey, though, since he was one of the main reasons I'd signed up for the course.

The main things I liked were the focus on how things work at the lowest levels of abstraction, that each assignment was centered around compiling and analyzing data, and that we had an opportunity to see what different types of hardware were really capable of. 

The only thing I wish would've been different was that most of the code was provided in advance. This was a survey course that sacrificed depth for breadth, which is fine, but I think it still would've been possible to at least write one novel program in OpenMP. 

### Final Grade: A