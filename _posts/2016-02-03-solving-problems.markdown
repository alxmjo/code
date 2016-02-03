---
layout: post
title: "Solving Problems"
date: 2016-02-03T08:46:56+01:00
image: 
summary:
---

Whenever I feel like I'm focusing too much on Android and forgetting how to solve actual problems, I go to Project Euler. There are a few hundred math- and programming-related puzzles there which users are encouraged to solve by writing code. I'm on [Problem 15](https://projecteuler.net/problem=15), which asks for the number of paths through a 20 by 20 grid.

I started by getting out a piece of paper and sketching the number of paths through a 2 by 2 grid (I'm trying to start more of my writing and programming on paper before moving to a computer - fewer distractions). Before long, I realized that every route involved two horizontal movements and two vertical movements which could be represented like so: &rarr; &darr; &rarr; &darr;. In order to find all of the routes through the grid all you'd have to do is find all the ways of arranging two horizontal and two vertical arrows. It's easy enough on pen and paper (since there are only six routes), but to solve the puzzle with its 20 by 20 grid would require something more.

![Paths on scratch paper](/images/paths.jpg)

It didn't take me long to realize that the horizontal and vertical movement could be represented in binary, with 0s for one direction and 1s for the other. So, all I'd need to do to solve the puzzle is find all of the combinations of twenty 0s and twenty 1s (since moving through the grid along any path would require exactly twenty horizontal movements and twenty vertical movements).

Keeping in mind that every integer has a binary equivalent, I wrote a short program that loops up to the greatest 40 digit binary string possible (equal to 2^40 in decimal) and iterates a counter each time it comes upo one with exactly twenty 0s and twenty 1s. Here's what it looks like: 

{% highlight java %}
public class pe15 {
  public static void main(String[] args) {
    
    int gridWidth = 20;
    long max = (long) Math.pow(2, gridWidth * 2);
    long ways = 0L;
    
    System.out.println(max);
    for (long l = 0; l < max; l++) {
      if (Long.bitCount(l) == 20) {
        ways++;
      }
    }
    System.out.println("Answer: " + ways);  
  }
}
{% endhighlight %}

While the program was reasonably quick to compute correct answers for smaller grids, finding the correct answer for a 20 by 20 grid took over four hours. Confident that there had to be a better way, I turned to Google.

Turns out that finding the number of paths through a grid is a common enough problem in mathematics that people have written blog posts about it. Following a similar train of though to my own, the author of [this post](http://betterexplained.com/articles/navigate-a-grid-using-combinations-and-permutations/) showed that factorials can be used to quickly compute the number of combinations of 0s and 1s in a binary string. Follow the link for the detailed description, but basically it comes down to this formula, which is so simple it can be solved with a calculator, and faster to boot:

{% highlight java %}
((stepsInPath)!/(gridWidth)!)/(gridHeight)!
{% endhighlight %}

Now I'm back to Android, at least until I hear Euler calling my name.