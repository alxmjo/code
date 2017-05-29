---
layout: post
title: "How to Schedule Jekyll Posts on Github Pages"
date: 2017-05-30T05:00:00+03:00
image: 
summary: Scheduling posts on Github Pages is actually pretty easy. I'll show you how.
tags: newsletter
---

### Background

One of the drawbacks of using a static site generator like Jekyll on Github Pages is that you can't schedule posts to be published in the future. The reason for this is simple: because the site is only generated when a commit is added to the repository, any future-dated posts won't show up. Github Pages doesn't know to go back and build<sup>[1](#myfootnote1)</sup> your site on its own, so those future-dated posts remain hidden until you add a commit and force the site to build. 

While it would be convenient if you could check a box in Github and force your site to build on a regular basis, this isn't currently possible. An internet search pulls up a variety of overly-involved solutions, among them:

- Serverless and AWS to [merge branches](https://serverless.com/blog/static-site-post-scheduler/) with "scheduling" comments
- Zapier to [schedule posts](http://www.east5th.co/blog/2014/12/29/scheduling-posts-with-jekyll-github-pages-and-zapier/) based on Google Calendar events
- Cron jobs [pushing "empty" commits](https://stackoverflow.com/questions/4923867/is-it-possible-to-schedule-posts-with-jekyll) to force the site to build

All of these seemed too cumbersome except the last one, and even that one is bad because it would litter your repo with tons of worthless commits. Not good. Thankfully there's a better way.

### How To

Github allows site building through the [Github Pages API](https://developer.github.com/v3/repos/pages/). We'll schedule a [cron job](https://en.wikipedia.org/wiki/Cron) to make that API call on a regular basis allowing scheduled posts to be published automatically. Here's how to set it up:

##### Set up Jekyll site for future posting
1. In your site's `_config.yml` file, set the future tag to false:
 ```future: false```
2. Create a test post and set its date a day or so into the future (via the [YAML frontmatter](https://jekyllrb.com/docs/frontmatter/)).<sup>[2](#myfootnote2)</sup>

##### Setup up Github API access
1. Log in to Github and navigate to [Settings → Personal access tokens](https://github.com/settings/tokens/)
2. Select **Generate new token** in the upper right-hand corner
3. Under **Select scopes**, check the boxes next to **repo** and **user** and then click **Generate token**
4. Copy the generated token somewhere safe – you won't be able to see it again

##### Schedule a cron job<sup>[2](#myfootnote2)</sup>
1. Before adding the cron job, do a test build via the command-line (replace USERNAME, REPO, and THE-TOKEN, which you saved earlier, with your values):

   ```bash
   curl "https://api.github.com/repos/USERNAME/REPO/pages/builds" \
   -X POST \
   -H 'Authorization: token THE-TOKEN' \
   -H "Accept: application/vnd.github.mister-fantastic-preview"
   ```
2. The response should be something along the lines of ```"status": "queued"```, but just to make sure, wait a minute and then run the same command with ```GET``` instead of ```POST```:

   ```bash
   curl "https://api.github.com/repos/USERNAME/REPO/pages/builds" \
   -X GET \
   -H 'Authorization: token THE-TOKEN' \
   -H "Accept: application/vnd.github.mister-fantastic-preview"
   ```
3. This should return a list of your site's most recent builds, with the newest ones at the top.
4. Once you're confident that it's working through the command-line, you should be able to set your ```POST``` command as a cron job on your hosting service (on Dreamhost, it's as simple as copying and pasting). I set mine to run every hour, which is well within the API limits set by Github. 

### That's it!

You should now see your blog updating every hour or day or however often you set it to update. Please [let me know](/about) if this worked for you or if you have a suggestion of how I can make the guide clearer or more simple. 

For the record, this post was scheduled using the same steps I've outlined above, so if you can read this, it worked!

***

<sub><a name="myfootnote1">1</a>: By "build," I mean take the posts, pages, and images and assemble them into a proper HTML website.</sub>
<sub><a name="myfootnote2">2</a>: When you build your site locally you'll need to add the ```--future``` tag to be able to see future-dated posts.</sub>
<sub><a name="myfootnote3">3</a>: This will depend on your hosting provider, but this method works for me on [Dreamhost](https://www.dreamhost.com/).</sub>
