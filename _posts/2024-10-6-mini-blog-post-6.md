---
layout: post
title: "Mini Blog Post 6: Hackathon Day 2"
date: 2024-10-06
categories: blog
author: Kori Rogers
tags: none
---
![Mini blog post 6 image](/assets/img/mini_blog_6_image.webp)

Hackathon complete! We did not win, but it doesn't matter- we came in to have fun and code. Below is a screenshot of our game. 

![Wiki Game image](/assets/img/wiki_game.png)

We faced some interesting challenges, for example, we wanted to have a score that told you how close you were to the target but we did not want to actually calculate the number of clicks away you were because we wanted to use Mistral's embedding model and this felt like an interesting use-case. So the approach we took was to calculate the distance between your current wikipedia page and the target wikipedia page in the embedding space, and use this as a proxy for 'click-distance'. Turns out distance in the embedding space isn't as cleanly correlated to 'click-distance' in the Wikipedia knowledge graph, so our progress bar wasn't as accurate a scoring as we would have liked. Another interesting bug was that our AI getting caught in 'click-loops', where it would repeatedly click on the same set of pages over and over again, and we solved that by keeping track of the pages the model already clicked on and not allowing it to click on them again. 

[back]({{ site.url }})