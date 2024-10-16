---
layout: post
title: "Introducing AutoRAND: A New Paradigm for Computational Science"
date: 2024-10-13
categories: blog
author: Kori Rogers
tags: none
---
**The design**
Ok, so I forked bolt.new in order to make the front end for AutoRAND. A couple notable points to make here: first, that I'm quite impressed by StackBlitz’s WebContainers, it basically allows you to embed an IDE (including filesystem, terminal & ability to install dependencies) into a website; second, that though forking bolt makes our product look like a co-pilot for now, it's fine as an MVP and I think the end-goal for it looks closer to a code editor. 

This is a 1 month sprint, but I've maybe gotten to 80% of what the front-end will be in basically half a day- thank you bolt & open-source!

**An AI-reasoning product, not an AI product**
We're focussed on making this an o1 product vs a GPT product, meaning roughly that we trade-off cost & speed for extremely high reasoning. The reason why we've done this is xxxx. What this means in the UX is that we'd like our user's queries to be as well-specified as possible, making the input bar closer to a word editor than a search bar. We instruct users: "Think of AutoRAND as a really smart friend you're going to send a DM to solve a problem. Plan your prompt & specify well." 

The first query will likely answered by o1, and follow-up queries by Claude 3.5 Sonnet. 

**The core technical challenge**
*Starting from a very low bar*
So, the core technical challenge of our sprint is to get our science code generation to a place where it beats benchmarks in a notably meaningful way- Claude 3.5 Sonnet currently scores 4.6%.

Here I list some of our hypotheses on how to meaningfully improve this score, roughly in descending order of my guess on how impactful I think they'll be. 

(1) Really good RAG to use scientific tools, packages, and functions. 
- Basically, this models off of MATLAB's toolboxes & in-built functions. Can we give our model toolboxes & in-built functions to solve computational problems rather than asking it to re-invent the wheel?

- As an example, defaulting to Convex Optimization solvers like [CVXGEN](CVXGEN) exist and are said to be used in SpaceX rockets, rather than 

- Check out [MATLAB's documentation](https://www.mathworks.com/help/index.html?s_tid=CRUX_lftnav) there is something to be learned here.

(2) Really good RAG to encourage adding adding scientific context to queries. 
- An obvious point, but this is promising because SciCode showed that adding scientific context to queries improvred results significantly. 
![SciCode Background](/assets/img/sci-code-background.png)

(3) Tricks? Does getting the model to code in MATLAB then convert that to Python help?


**Defining our problem-choice**
*Fields & Sub-fields*
SciCode has listed 5 fields (Math, Physics, Chemistry, Biology, Material Science) and 16 sub-fields (Condensed Matter Physics, Quantum Chemistry, Semiconductor Materials etc.). 

*Problem structuring*
SciCode roughly categorises problems into main-problems and sub-problems, where sub-problems have dependencies on each other, and must collectively be solved in order to solve the main-problem. The logic in mapping this out is itself a fascinating challenge, but not where we are starting with.  

*Categories of computational scientific work*
So SciCode defines three meta-categories of computational scientific work:(1) numerical methods, (2) simulation of systems, (3) scientific calculations.

For example, a climate scientist might use numerical methods to solve differential equations (category 1), create a simulation of global weather patterns (category 2), and then perform statistical analyses and create visualizations of the results (category 3).

We will work on scientific calculations & on sub-problems that are as close to biophysics as possible. 

**Why this matters and what could be the impact?**
MATLAB as an incumbent- why can we disrupt them? They are a fantastic platform, but they are married to their programming language (MATLAB).


**Tasks today:**
- This essay, roughly outlining the key design decisions & core technical challenge as we sprint through the next month. 
- Set up the SciCode Github and examine the problems. 
- Write an essay that justifies our existence. 
- Compulsory books for our company

(Note: it will be worth doing a much deeper dive into the repo- including the problems and sub-problems.)

**Random:**
Thoughts about outputting in this way: https://www.mathworks.com/help/simbio/ug/simulating-the-glucose-insulin-response.html

Not just raw code


**Future work:**
- Dealing with main-problem & sub-problem dependencies; work related to Rasched's hypothesis-testing graph. 

[back]({{ site.url }})