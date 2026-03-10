---
layout: home
title: "Welcome to Unmet Tricks"
---
# Welcome 👋

Yes, another econometrics blog to crowd the net-world. As someone who completed Bachelors in Economics in Bangladesh and laters Masters and ongoing PhD in Sweden, I noticed there's a significant difference in the approach towards Economics. While in Bangladesh Economics is taught as more of a near philosophical social experiment based approach, in Europe Economics is deeply scientific. It is not just sprinkled with Mathematical reasoning, but taught in the language of Math. For students who are not used to this approach, the transition can be intimidating (as it was for me). Econometrics, in particular, can feel like a completely different language (Greek and Latin letters to be accurate).
While there are a plethora of resources out there to help in varying degrees of ease, I found very few that had examples that I could relate to, and almost none in my vernacular (Bangla). So this project is more of a way to meet that unmet gap. But beyond altruisic (!) reasons, it is also my way to revise and remember what I learn as I traverse across the often turbulent but forever exciting terrain of causal inferences and empirical analysis. Hope this endogeneity in purposes serves more than just me.


## Latest posts

<ul>
  {% for post in site.posts %}
    <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> - {{ post.date | date: "%b %d, %Y" }}</li>
  {% endfor %}
</ul>
