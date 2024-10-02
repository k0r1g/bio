---
layout: post
title: "Mini Blog Post 2: Applying to MATS"
date: 2024-10-02
categories: blog
author: Kori Rogers
tags: none
---
<img src="{{ site.baseurl }}/assets/images/mini_blog_2_image.webp" alt="Mini Blog 2 Image" title="Mini Blog 2 Image">

Finished the interview- I'll give an update when I get news. Yesterday was also OpenAI's DevDay, and I'll set aside one pomodoro today to catch up on the details, but I'm definitely interested in the Realtime API and hacking a project with it- I've heard it's got latency and tonal issues, but it'd be a fun project to build. 

Today, I'll be applying to MATS, and that will involve: 

- Selecting a mentor
- Drafting a project proposal, in the form of a LessWrong post
- Coding a very simple MVP to demonstrate the idea 

I've also got to leave at 7.20pm to catch a train to London, so I've got to be efficient- aiming to finish everything at around 5pm, so I can spend some time with Lola before I leave. I didn't mention this in my other posts, but I'm currently in Brussels helping Lola settle in, she's starting a Blue Book traineeship with the European Commission- so proud of her!

Separately, by assigning a lot of weight to open communication, these mini-blogs have unintentionally turned into a diary of sorts. That's not inherently a bad thing, but I'll take note to dive deeper into topics of substance for future posts. 

Back to MATS. On the mentor-side, I've been leaning towards Nina Panickssery- who on paper seems smart but approachable. For the LessWrong post, I'd like to talk about applying sparse autoencoders to language models that have undergone reinforcement learning. So, quick brainstorm: 

I know that finetuning is a supervised learning approach, I think one can think of it as a form of transfer learning- you can think of it as applying supervised learning on top of a pre-trained model in order to specialise it in some domain. So finetuning adjusts the weight of the model, but in a way that keeps much of the learned knowledge intact, particularly in the earlier layers- mostly changing the weights in the later layers. 

I haven't done a deep dive into [OpenAI's o1 System Card](https://cdn.openai.com/o1-system-card-20240917.pdf), so that's the next step, but in paragraph 1, it says that "The o1 model series is trained with large-scale reinforcement learning to reason using chain of thought." So I'll assume that just like RLHF, it is a RL process applied to a pre-trained language model. ChatGPT tells me that while RLHF doesn't explicitly "freeze" earlier layers as in some forms of transfer learning, the earlier layers are less likely to change drastically, because earlier layers typically capture more general, foundational knowledge and the RLHF process mostly impacts the later layers, where task-specific decision-making happens. So, it makes sense to apply SAEs to the later layers of a language model that's undergone reinforcement learning to reason using chain of thought (let's call it RLCoT- not sure if that's a term of art). This would mean training an SAE on the activations of a model that's undergone RLCoT. At this point, I would think the research question of interest would be in understanding how the neurons in the later layers of an RLCoT model relate to reasoning in the model. 

 I'll apply to MATS and write a LessWrong post on applying SAEs to the later layers of RLCoT models. This seems like a huge task, as it requires training an SAE on the activations of an RLCoT model, so I cannot do it in a proposal. I'll have to think of the 'MVP' for this project. First, I'll try to see if there are already SAEs trained on the activations of RLCoT model, and if there are, I can do analysis of that SAE using the standard techniques. Otherwise, I'll just write a post about it, with minimal code- maybe I'll do one on an SAE trained on an RLHF'd model, and draw parallels.  

**tl;dr** The research end-goal is to apply SAEs to the later layers of RLCoT models & understand how a model reasons. 

An aside: Toying with the idea of applying to some jobs at Anthropic, there are some that seem like a fit but they are largely UK roles and I'm quite set on SF which constrains my options. 

Another aside: Cursor's tab/autocomplete feature has been amazing for writing these posts- since I've been thinking about an IDE for science, it's quite lovely to find that this format is fantastic for writing research as well as writing code. 

[back]({{ site.url }})