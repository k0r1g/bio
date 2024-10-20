<!-- Home page -->
# About me 
I'm Kori and I really care about advancing science. 

Previously, I was a Founder-in-Residence at Entrepreneur First, and before that I co-founded a startup that raised $8.3M and sent a human to space via Blue Origin.

I completed a BA & MEng in Engineering Science at Oxford University with a focus on Clinical AI, where I was supervised by Prof. David Clifton, and built models that enable clinical alarms to predict if patients would be admitted to ICUs before a medical emergency occurs.

# Writing
{% for post in site.posts %}
[{{ post.title }}]({{ post.url | relative_url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}

<!-- # Blog posts I will wirte
- ClickSolve AI
- Once I move to SF, I wish to write a blog post about the multi-year journey it took me to get there. 
- BIG POST: Building a startup in a post-AGI world. 
- LessWrong POST: Write a post about interpretability for chain-of-thought models
- Write a post about SONAR models (which I believe is how Perplexity does their autocomplete) and how Cursor likely does auto-complete and their tab feature. Could also look at open-source versions like Continue to figure this out.  -->
