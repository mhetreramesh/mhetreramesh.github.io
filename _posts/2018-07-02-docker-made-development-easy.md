---
layout: post
title: How Docker Made Development a More Fun
categories:
  - Development
tags:
  - Docker
  - Docker Containers
  - Docker Swarm
header:
  teaser: /images/docker.png
  og_image: /images/docker.png
last_modified_at: 2018-07-02T15:12:19-04:00  
---

If you work on the different projects at the same time, your environment floods with the different tools. These tools install other tools, create directories (hidden, and not only). After some usage they cache something eating your space on the drive & you loose your time fixing this. This eventually starts adding stress on you. Having separate virtual environment for every new project is not at all feasible. Trouble! Trouble! Trouble!

![Docker containers](/images/docker.png)

So, what to do? What can isolate these tools and make them available only when I need them and delete them, when I’m finished?

The first thing that came into my head was docker. <strong>Docker</strong> could be the solution to this problem. From that day, Docker changed how I work with tools during the day. Let’s explore, how you can almost completely dockerize your environment. This can apply to your development, test or both environments.

## Examples

For example you were asked to use Django(Python), Angular2 for your next big awesome project. Basic things that should be installed are:

- Python3
- pip
- node
- npm
- yarn (because we are cool and modern)

For me, installing all these things on my local system is not the best choice. What to do?

Thanks, we have Docker with us.

I’ll create a Dockerfile with the configurations & my reusable/throwable/deployable setup is ready in minutes.

The best thing is there are tones of resources available about it. So, learning docker isn’t a big deal today.

Once you get some basic idea, you can refer this [docker cheat sheet](https://github.com/gliterd/docker-cheat-sheet) which I have prepared exclusively.