---
layout: post
date: 2018-07-11T07:47:40-07:00
permalink: jekyll-microblog

title: "Untitled Posts in Jekyll"
image:                  # /images/filename.jpg
summary:                # A sentence or two about the post.
category: Jekyll              # "Oregon State University" (only one)
tags: writing jekyll
sharing:                # Text to be shared on each network.
  twitter: A simple way to make writing easier - drop the title.
  facebook: I don't usually share my coding-focused blog posts on here, but I think I'll change that. This one is about how dropping titles can make writing easier.
  linkedin: A simple way to make writing easier - drop the title.
---

A couple weeks ago I read a thought-provoking [post](http://fionavoss.blog/2018/06/24/untitled-blog-posts) by Fiona Voss, a fellow C.S. student at Oregon State. The crux of the post was this: writing blog posts without titles reduces friction and makes writing easier. So how could I put it to use in my own writing?

<!--more-->

### Reducing Friction

I'm always thinking about ways to make writing easier. I don't have too much trouble with the writing itself, mostly because I always try to remember a line from William Stafford, one of Oregon's poet laurreates: 

> "There is no such thing as writer's block for writers whose standards are low enough."

When I say easier and with less friction, what I mean is that I want to spend more time writing and less time worrying about the setup. Twitter is a good example. They give you a box, you type some stuff in, press tweet, and you're done. 

I'd like to be able to open up my editor ([Visual Studio Code](https://code.visualstudio.com/), which is *excellent*), create a new post (with [Octopress](https://github.com/octopress/octopress)), commit it, and push it to GitHub (where this blog is hosted) in under a minute (minus any time I spend writing, of course). 

In order to accomplish this goal, I made a few small modifications to my blog. Or if you just want to see what all of this amounts to, take a look at [this example](/example-short/). 

### Modifing Jekyll

Jekyll already has pretty good support for writing untitled posts, depending on your setup. The only thing you need is an explicitly empty title, like so:

```yaml
title: ""
```

If you leave the title out all together, then Jekyll will pull the title from the name at the end of your markdown file. (This post's filename is `2018-07-11-jekyll-microblog.markdown`, so the title would be "Jekyll Microblog.") But I found that a few other modifications were necessary in order to make untitled posts play well with the rest of my site.

#### _templates/post

This is the template that new posts are made from. I updated it so that no values had to be filled in explicitly. The important stuff is added automatically, and then everything else can be left blank.

{% raw %}
```yaml
---
layout: {{ layout }}
date: {{ date }}
permalink: {{ title | downcase}}

title: ""               # Empty quotes if this is a short.
image:                  # /images/filename.jpg
summary:                # A sentence or two about the post.
category:               # "Oregon State University" (only one)
tags:                   # newsletter
sharing:                # Text to be shared on each network.
  twitter: 
  facebook: 
  linkedin: 
---
```
{% endraw %}

Everything above the break (layout, date, and permalink) is filled automatically, and everything below I can fill out if I want to. If I don't, then everything will still work just fine.

#### index.html

This is my [homepage](/index.html). You may not need to modify yours, depending on how you manage excerpts and summaries. 

[Here's the code](https://github.com/alxmjo/code/blob/gh-pages/index.html). I basically display a summary or an excerpt if those exist (which they always do for my longer posts), or the whole post otherwise. 

These untitled posts are meant to be short and won't have a summary or an excerpt (or a title, for that matter), so the entire post will show up on my homepage. It looks a bit like a tweet.

One thing I still have to decide is whether (and how) someone should be able to click through from the homepage to the untitled post itself. Right now the only way to get to the post itself is via the [Posts](/posts) page

#### posts.html

This [page](/posts) shows a list of all my posts, first by category and then by date. The important part of modifying it is to figure out what to display, since there's no title. This is what I settled on:

```html
{% raw %}
{% if post.title == "" %}
  {{ post.content | strip_html | truncatewords: 5 }}
{% else %}
  {{ post.title }}
{% endif %}
{% endraw %}
```

An if statement checks whether the post is untitled. If so, it takes the content of the post, strips any html (like an `img`, for example)and displays the first 5 words. [Here's the code](https://github.com/alxmjo/code/blob/gh-pages/posts.html).

#### _includes/head.html

On my site, the title of the post is displayed as part of the title of the page (which shows up in the browser tab). If the post is untitled, I simply leave it blank. Here's what it looks like:

```html
{% raw %}
<title>
  {% if page.title and page.title != "" %}
    {{ page.title | strip_html }} &#8211; 
  {% endif %}
  {{ site.title | strip_html }}
</title>
{% endraw %}
```

### Going Forward

I'm hoping to take advantage of this newfound capability by posting more, posting more often, and getting less hung up on the idea that every post has to be a fully-formed, perfect essay. 
