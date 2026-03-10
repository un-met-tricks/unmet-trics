---
layout: post
title: "The Idea of Justice - fair estimations and fairly well-done framework"
date: 2026-03-10
---

** A Much-Needed Statutory Warning **
Although, in keeping with the essence of basic metrics, the first posts should really be about basic statistics, I hope at some point I have the energy (and enthusiasm) to write everything out from the very foundations. But for now, we stick with randomness of what I want to write about. 
Super important note: the posts are not meant as a replacement of amazing source books already out there, not even as a replacement of truly enlightening blogs and posts that draw beautiful analysis from analogies. Think of this more as a journey on my train of thoughts if you will, as a try to navigate my own understanding of metrics. 

## The Idea of Justice - fair estimations and fairly well-done framework

---
Quotes from good book quoted in another good book always feels like a fortuitous bonus. In his book - *The Idea of Justice* - one of his many seminal works, Amartya Sen quotes Pip from *Great Expectations* - saying 

*"In the little world in which children have their existence, whosoever brings them up, there is nothing so finely perceived and so finely felt as injustice"*

Truly when we look back at the comparisons we make in our day-to-day lives, one of the key things we consider is how fair is the comparison. Is it truly fair to say that if some style of education worked in one place, it would work everywhere else? or if having ice-cream cured your post-break up depression, it would help your friend too in the same way? May be education system needs more interactive approach for certain student? May be your friend prefers to rather have a a whole new glow up routine to get over? May be what worked in one place, may not work elsewhere? How do we know when it will?  

At the end of the day, in everything we do, in the hope of finding the why's and how's of the bigger and smaller questions - of life, of policy formulation, of human behavioural changes, of technological changes, of macroeconomic changes - from what may cause these changes to happen, or exploring the effectiveness of these, we know we need some fair way to compare what is, what was, and/or what would have been. And so we try - by asking first some simple questions..

## Day-to-day pondering over state of the world:

How come whenever there is rain, auto/CNG/Uber fares see a spike?

Why do lemon prices surge during Ramadan?

Does giving away water-filtering alum (i.e. *fitkari*) actually reduce cholera epidemics?

For those of the readers in South Asia, these are typical problems/questions our minds have wondered at some point or another (I know for a fact the lemon price this year have been giving panic attacks to people in Dhaka). But before we attempt to discuss how to answer these, lets reframe these questions to bring them to their bare bones:

- Does **rain cause fares to rise?**
- Does **Ramadan cause lemon prices to increase?**
- Does **alum actually reduce cholera?**

The first one sounds a bit odd when we say it out loud. It is unlikely that rain directly causes fuel prices to rise every single time. Imagine if prices were directly linked with how bad the rain was — slight drizzle versus full thunderstorm. 

The second question is also a bit strange. It would be odd if just the arrival of Ramadan magically made lemons pricier.

And the third? Maybe giving alum reduces cholera. But maybe it’s not the alum. Maybe the areas where fitkari is distributed also happen to have more doctors or better sanitation.

What we are really asking in all of the examples above is this:

> To what extent is something **actually causing** something else, rather than just being correlated with it?

Maybe when we measured prices we simply happened to compare at a time when there were a lot of lemons available to a time when there weren’t.

Maybe rain makes people want to go home early, and so they are willing to pay higher fares.

Maybe areas distributing alum also received other public health interventions.

In short, there simply isn't enough information (at least in the stories we told above) to say that one thing **causes** the other. This is what most econometrics books on causal inference will begin with - understanding that just because two things appear to move together doesn't mean one causes the other. Sometimes there might be a different mechanism moving them both (in which case that's also interesting to observe in itself) and sometimes it's completely a coincidence (like the lack of sun in Scandinavia and my general morose mood). 

---

## The Basic Idea of Causality

But now suppose we really wanted to figure out whether something is causal or just correlation.

The idea seems simple.

First we define:

- a **treatment** -- This is something that we change 
- an **outcome** -- This is the effect of the change we made.

For example:

Treatment:  
Rain or no rain.

Outcome:  
Ride fares.

Then we simply measure the **difference in the average outcome**.

For example:

Compare average cholera incidence **before alum distribution** and **after alum distribution**.

This seems intuitive.

And in fact, this is often the first thing people try to do. For those involved in field research, something called *baseline survey* and *endline survey* tries to capture that - measure the incidences before doing the project, measure the incidences after the project, and compare to find if there has been any changes. 

---

## The Problem

Now think about households that started using fitkari. This is where we start considering each households as not just arbitrary all-are-the-same units but rather as ones made of humans  with differences - in attitudes, in choices, in actions. And we ask, can we really fairly equate all as the same?  

One household might already be extremely clean. Another might have too many children who love mud. Another might simply have stronger immunity genetically.

In all three cases, we never really observe **what would have happened if they had not used the alum**.

To be more concrete in our choice of differences, lets say, different households have different immunity levels.

Some are more immune, some less.

So it is possible that:

- giving alum to a low-immunity household has a **large effect**
- giving alum to a high-immunity household has **almost no effect**

So how do we take these differences into account? 
---

## Potential Outcomes

This idea leads to what is called the **potential outcome framework**.

Each household has two possible outcomes:

Outcome if the household **uses fitkari**

$$
Y_i(1)
$$

Outcome if the household **does not use fitkari**

$$
Y_i(0)
$$

The **true treatment effect** for household \(i\) would therefore be

$$
\tau_i = Y_i(1) - Y_i(0)
$$

---

## The Fundamental Problem

Here comes the real difficulty.

We **never observe both for the same household at the same time!** 

We either observe

$$
Y_i(1)
$$

or

$$
Y_i(0)
$$

For example, if a household uses alum, we observe the cholera outcome **with alum**. But we never observe what would have happened to that exact same household **without alum**.

That counterfactual world simply does not exist for us (whatever happened is factual, whatever didn't happen is countering that - I wonder if the opposite should just have been 'fictional', but let's not get into semantics).

This is often referred to as the **fundamental problem of causal inference**.

---

## So What Do We Do?

Since we cannot observe both outcomes for the same household, we try to approximate the missing one.

How?

We look at **other households that are similar**.

If one household of people used alum, we compare it with other households **that did not use alum**. To be even more accurate, if we think immunity is a factor in deciding how much of a response the household will have to fitkari usage, we comapre households with similar level of immunity (say, compare among households with vaccinated members). 

In other words, we use the **average outcome among untreated households** as an estimate of what would have happened to the treated household without the treatment.

---

## Great Expectations

Now a real math-based nod to Dickens' work. 

As mentioend in the statutory warning, I do expect the reader to know what **expectation** is (by now, I won't even apologize for the barrage of puns). But I will still ramble a bit and explain it in the way that helped it stick in my rather slippery mind.

Suppose we want to know the typical cholera incidence among households that used alum.

One way to approximate this is to take the **average outcome** among those households.

Formally, the mean of an outcome \(Y\) across \(n\) households is -

$$
\bar{Y} = \frac{1}{n}\sum_{i=1}^{n} Y_i
$$
which gives us the average outcome from all the houses which used alum. 

In probability terms, we often talk about the **expectation**

$$
E[Y]
$$

Expectation is a probability-weighted average of a random variable. What is random variable - a variable has no fixed value. How is expectation different from mean? Not much, but there's a very subtle one. Mean is what we use when we have a fixed dataset. Calling this an expectation says that we may have different datasets, taken from the same populations, that will lead to our variable changing.  The mean we calculate from data is often used as an **estimate of that expectation**. Strictly speaking, expectation belongs to probability theory while the mean is a sample statistic, but we will happily leave that philosophical rabbit hole for another day. 

---

## Average Treatment Effect

Using expectations, we can write the **average treatment effect (ATE)** as

$$
ATE = E[Y(1)] - E[Y(0)]
$$

Meaning:

Average outcome **with treatment**

minus

Average outcome **without treatment**.

---

## The Observation Rule

Now back to contextualization rather than average. This is where we bring what is known as Rubin’s causal framework. 

For our example, in each household we only observe **one realized outcome**.

Formally:

$$
Y_i = D_iY_i(1) + (1-D_i)Y_i(0)
$$

where

$$
D_i =
\begin{cases}
1 & \text{if household } i \text{ receives treatment} \\
0 & \text{otherwise}
\end{cases}
$$

This is called the **observation rule** for obvious reason as one can guess. It simply formalizes what we discussed earlier about potential outcomes. If a household receives treatment, we observe the treated outcome. If it does not receive treatment, we observe the untreated outcome. For each household, there are thus two possiblities - what we observe (treated/untreated) and what we don't observe (untreated/treated). So now, the rule is, to use the outcome that we do observe as replacement for outcomes we don't observe, for each households. 

This let's us say *yep, what we observe in cholera rate in household which used alum, applies for cholera rate in household that didn't use alum - had those actually used it IRL** . 

But this is math we are discussing, not Trump's general orders that defy logic or laws, and still get implemented. Stating that two outcomes in two different households are substitutable doesn't make them substitutable. When are they truly proper substitute? What needs to be ensured for such substitution to stay in place?

---
## In Assumptions, We trust

For the substitution logic above to hold, we need a few assumptions. It might be better to call them as requirements than assumptions though since without those, the model doesn't hold.

The first is what Rubin calls the **Stable Unit Treatment Value Assumption**, mercifully abbreviated as **SUTVA**. It sounds intimidating but really says two fairly intuitive things. First, one household's treatment should not affect another household's outcome. If the neighboring household receives alum and that somehow changes cholera risk in my household — say because the water source is shared — then my outcome is no longer purely my own potential outcome. Second, the treatment itself must be well defined. “Using fitkari” cannot secretly mean ten slightly different things across households — different dosages, different water sources, different instructions. If the treatment varies wildly, then \(Y_i(1)\) stops being a single coherent object. In short: treatments/changes should not spill over across units, and the treatment itself should mean the same thing everywhere. Why? because we want to be able to isolate the effect and the treatment for each unit - not look at how multiple units share their effects across each other (there are some cool models that look into things like social network affect and use spillovers as treatments). 

The second assumption is usually called **independence**, **random assignment**, or in observational settings **unconfoundedness**. In spirit, it simply says that treatment assignment should not be systematically related to the potential outcomes. Formally we write this as

$$
(Y_i(1), Y_i(0)) \perp D_i
$$

which says that the pair of potential outcomes is independent of whether a household actually receives treatment. Translating back to human language: households that receive alum should not be systematically different, in terms of cholera risk, from those that do not. If the dirtiest households are precisely the ones more likely to receive alum, then comparing treated and untreated households will mix the treatment effect with the pre-existing differences between them.

When these assumptions hold, something very convenient happens. The average outcome among treated households becomes a valid stand-in for \(E[Y(1)]\), and the average outcome among untreated households becomes a stand-in for \(E[Y(0)]\). In other words, the substitution we casually performed earlier — replacing the unobserved counterfactual with outcomes from other households — actually becomes justified. Without these assumptions, that substitution is not fair in principle. 

## When Things Work — and When They Don't

Now we can finally return to the simple comparison we started with: the difference in average outcomes between treated and untreated households.

Suppose we simply calculate

$$
E[Y \mid D=1] - E[Y \mid D=0]
$$

that is, the average cholera incidence among households that used fitkari to filter water minus the average among households that did not.

Using the observation rule we discussed earlier, we can rewrite this expression in terms of potential outcomes:

$$
E[Y(1) \mid D=1] - E[Y(0) \mid D=0]
$$

But notice something subtle here. The first term tells us the average treated outcome for households that actually received treatment. The second term tells us the untreated outcome for households that did not receive treatment.

What we *really* want, however, is

$$
E[Y(1)] - E[Y(0)]
$$

which is the **Average Treatment Effect (ATE)** for all households. As in next time when we say something caused something, we don't have to state "oh it happened only to the ones that received the treatment", although logically, that's how we draw it. But because we don't want to leave anything to leap of logic, we go through the long route of explicitly showing how observational rule helps us connect what we observe with what we could have observed and state the effect with pride and (sometimes) confidence.

To see how this all connects, we look at the difference, and then we add and subtract the missing counterfactual term \(E[Y(0) \mid D=1]\). Why? Because it let's us talk about another important thing - selection bias:  

$$
E[Y(1) \mid D=1] - E[Y(0) \mid D=0]
=
\underbrace{E[Y(1) - Y(0)]}_{ATE}
+
\underbrace{\left(E[Y(0) \mid D=1] - E[Y(0) \mid D=0]\right)}_{Selection\ Bias}
$$

This decomposition is the heart of Rubin's framework. The first term is exactly what we care about: the **average treatment effect**. The second term is what we call **selection bias**. It captures the possibility that treated and untreated households were already different even before treatment occurred.  So for our case, suppose the households that chose to use alum were precisely those with worse water sources to begin with. Then their baseline cholera risk, even without treatment, would already be higher. In that case

$$
E[Y(0) \mid D=1] \neq E[Y(0) \mid D=0]
$$

and our simple comparison would mix up two things: the true effect of alum and the pre-existing differences between households.

But if the independence assumption holds — meaning treatment assignment is unrelated to potential outcomes — then something nice happens:

$$
E[Y(0) \mid D=1] = E[Y(0) \mid D=0]
$$

and the selection bias term disappears. This basically means what we don't observe as outcome in treated household equals what we do observe as outcome in untreated households - thus, it's simply the subsititution we talked about earlier that lets us equate the seen with the unseen.

In such a world of perfect presumptions and perceptions,

$$
E[Y \mid D=1] - E[Y \mid D=0] = ATE
$$

which means the simple difference in means actually recovers the causal effect.

Of course, most of empirical econometrics is really about one question:

**How do we get ourselves as close as possible to that perfect world?**

Randomized experiments do it by design. For anyone who ever held an econometrics book for more than 60 seconds, these four words *..treatment was randomly assigned* must have jumped out at one point or another. This is the experimental ideal - what we strive for. It lets us utilize Rubin's causal model by simply plugging in the means. Why does it do that? because it allows for the independence assumption to hold. 

But why is randomizing the ideal? I find the best way to explain that would be to imagine providing the alum to each housheold while wearing a blindfold. This means, as an experimenter, you have no idea what kind of household actually received it or didn't - you can't see how they differ. So chances are on average, you would just hand out those alums to any and every type of households. This brings us back to fairness - the blindfold of the lady of justice. Being random allows us to uncover the true treatment effect as we are not selecting based on any bias (thus no selection bias if I may). 

Of course, this brings the *what if* question. What if even though we were blindfolded, we still end up with a sample where certain characteristics are more in the units which have been treated compared to the ones which haven't been treated. It is possible, afterall perfect randomization is utopian. In such cases, we first do something called balancing test (yep, a nod to the balance held by above mentioned lady if you will) - which is just to see if the sample is balanced in terms of characteristics between the groups which got treated and didn't get treated. And even if they aren't, we next have another tool called conditional independence - which lets us take the difference into account and still extract the effect of the treatment. But it might be wise to leave that for later. 

## In conclusion, it's only the beginning 

Rubin's causal framework provides the most basic way to analyze treatment effects. It's clean, simple and at its core, provides the most concrete way to compare outcomes. It underlies almost every causal inference approach we use now and everything that we do onwards, at the crux of it all, is the aim to reach this exact idea of just comparison and appropriate contextualization.

