---
title: Deep Learning and AI from the Shallow End
layout: post
category: Learning
---
On February 27th, I will be presenting for the [Sarnia Tech Community](https://www.sarniatech.ca)
on a topic near-and-dear to my last thirteen months: Deep Learning for Good.

I'm hoping to take this presentation on tour, but it will undoubtedly take some
iterations and practice.

At [Link2Feed](https://www.link2feed.com), we are the market leader for food bank
client intake software. It's not a big market, but we've been able to help our
partners serve more than 3 million individuals in over 50 million hunger relief
transactions. I would like to discuss the story around our use case, around tech
for good, and how deep learning has helped us gain insights that help us
measurably improve the lives of our food-insecure neighbours.

<!--more-->

### The Link2Feed Story

<div class="right"><img src="/assets/images/Link2Feed_BCertified_Logo_Colour.png"></div>

Link2Feed is a certified [B Corporation](https://bcorporation.net/) that has
been on the [Best for the World list](https://bthechange.com/best-for-the-world-2018-all-honorees-f30a880f8ac0)
for two years in a row. In short, this means we are a social enterprise that not
only cares about doing good, but doing it well.

The company started as a spin-off of a local marketing firm: one of those side
projects that just gets its own set of legs and runs off. In 2010, one of the
local food banks came to the firm and said, "We'd like a better way to go
paperless." As of February of 2019, we have helped partners all across Canada and
the United States serve more than three million individuals and aided in over 50
million hunger relief transactions.

To give an example of where we help: Food Banks Canada produces a national report
called [The Hunger Count](https://www.foodbankscanada.ca/HungerCount-Archives.aspx).
Every March they ask food banks around the country to keep a little closer count
and answer a series of surveys about their usage rate for the month. These survey
responses are collated and used to drive discussion about how best to tackle food
insecurity. However, for the final result to be useful, there needs to be an audit
trail that goes all the way down. That's where Link2Feed comes in.

We provide the tools for food banks to gather information on the people that use
their services, and then to report on those metrics in a meaningful, validated
way. This helps fuel data-driven decision making both with our partners, and the
higher bodies that they report to, like Food Banks Canada and Feeding America.
Now, this is the kind of thing that could be done through Excel, or Access,
or even pen and paper, so what does Link2Feed really provide? We work with the
higher bodies to make sure that the important compliance and data-gathering
pieces are built right and able to be used consistently across the board, whether
that's asking the right questions for the Hunger Count in Canada, or ensuring
that civil rights processes are followed correctly by volunteers administering
TEFAP in the US. We help make the very specific jobs easier.

### Ethical Building Blocks for Client Profiles

At some point in that introduction, you may have had a lightbulb moment. Or your
skin might have crawled. We get both reactions.

    With great power comes great responsibility.

Link2Feed is, among many things, a database system of personal information for a
vulnerable sector of society. Our big hairy audacious goal is to help build that
metric for hunger in the developed world: to determine the causes and factors
that can either put a family on the road to the food bank, or help bring them
back to self-sufficiency.

To do that, we have begun enlisting the aid of modern data analysis tools:
artificial intelligence, machine learning, and deep learning. These are three
increasingly specific tools in computer-aided analysis. Where **artificial
intelligence** is the generic term for any decision-making that is created without
a living organism, **machine learning** is a very specific tool.

Machine learning is an umbrella term for all the tools we use to teach a computer
how to solve problems on its own even if it's never seen them before. The process
is very similar to teaching a human being, but is often very specific and very
limited in scope. For example it is conceptually easy to teach a computer to
recognize handwritten characters: you show it a million labelled handwritten
characters, and then show it one it's never seen before and ask, "What do you
think this is?" However, if you show that same model the letter A, it will surely
try to decide whether it's a 4, an 8, or some other number.

This process has several codified steps and variations, but ultimately it focuses
around identifying connections between similar data points. The common steps are:

1. Establish an interesting data set (eg- 1 million handwritten characters)
2. Break the set up randomly into a training set and a validation set (eg- 800k
   to train with, and 200k to hold for later)
3. Feed the tagged training set through a learning algorithm of some kind to
   produce a model (eg- "This is a 7", "This is a 6", etc.)
4. Feed the tagged validation set through the trained model to make sure that
   the model agrees (eg- "This is a 7, do you think this is a 7?")
5. Tweak the hyperparameters from step 3 and repeat steps 3 and 4 to maximize
   the number of "correct" answers in the validation step.

The overall training method has been super successful at building computer models
that can predict and discern patterns that might not be obvious to the human eye.
This is being used in medical imaging to find anomalies at their earliest stage,
when they can be most easily treated. Trained machine learning models are also
being used in natural language processing and audio processing so that Google and
Siri can turn up your music, or turn down your lights.

Trained machine learning is a subset of machine learning, and it's possible to
have untrained models, or naturally growing models. These are great in theory,
and have led to some amazing experimental effects, but did not fit the need for
our specific problem.

At Link2Feed, we are using machine learning to build a model that maps hungry
people on their struggle through food insecurity, in the aim of breaking the cycle
of poverty. By using this apples-to-apples comparison system, we're able to
train a model that recognizes households based on a number of meta-factors
including size, income, composition, and other less-obvious factors that crop up.
So in the same way that Google teaches a model to know "What number is this?" we
are teaching a model to know "What kind of household is this?" and "What can we
do to help them break the cycle of poverty?"

Unfortunately, the real world is vastly more complex than a few anecdotes in a
presentation.

If you've been watching the news, you've probably seen the stories: a Fortune 500
company fed their existing HR database into an algorithm to suggest people that
would be good cultural fit with their company. It included names and genders. So
at the end of the day, the model learned that the highest performers at this
particular company were men named Michael, so it suggested a disproportionate
amount of Michaels.

There's a new story like this every week. And the last thing we want is for
Link2Feed to be the funny headline next week.

So we have taken serious consideration into a few key factors:

1. What information do we want to use to train our system? What is relevant for
   finding out the causes of poverty? What is not? For example: is street address
   relevant? Or age? Or ethnicity?
2. What real-world biases will our data have that might sway the model one way
   or another? For example: if we train it with information based on Toronto,
   but then deploy the model in Detroit, the issues will be subtly different.
3. What will we DO with this comparison? Will the food banks use this information
   to provide more service to some and not to others? Is that fair? For example:
   if this categorization leads to some families receiving more food, will others
   feel left out? Will they try to game the system?

It is not an easy set of challenges, and we are actively working through the
implications of using this technology in the food security space. At the end of
the day, it may turn out that the tools aren't mature enough to capture the
complex needs of society. Even finding out if we're doing the right thing is a
part of the challenge.

### Measuring Success

One of the biggest difficulties when dealing with food-insecure neighbours is
measuring "success". The typical measurement in a relief scenario is "How many
people stopped attending?" However, there are a lot of reasons that a user may
lapse, for example they might move out of the service area, or pass away.

Knowing whether or not someone is succeeding can help us identify a spectrum of
preferable states for households to be in. While some metrics are harder to
change, the food banks have the ability to change a few of them, like frequency
of service, or the amount of food provided, or what other services a client
is directed towards, like rent and utility assistance.

In social services, we frequently refer to success tracking as "closing the loop."
For example, if we suggest that a family sign up for financial literacy programs,
and then we never see them again, one of two things happened: 1) it worked!, or
2) it didn't, and we lost track of them. Being able to close that loop where we
hear from them again is a huge part of Link2Feed's strategy going forward.

But even more important is to track the little steps that make all the difference.

For example, we work with our partners to track income and employment status. A
good employment opportunity is the single biggest step out of poverty. However,
many full-time employees are still struggling to make ends meet, so there are
more factors at play than just steady income. In addition to tracking quantifiable
data points, we're also working with our partners to get more tools in the hands
of volunteers to track perception of success.

Working with our clients to help measure both the success of their internal
programs as well as external referrals will help them make better informed
decisions about their time and effort, but will also help our deep learning
tool better grade for successful interactions.

### Demonstration

At this stage, the Link2Feed prediction system is buried inside the guts of the
beast, and not super useful or visible on the outside. Give me six months and
we'll have a better demo for you.

So instead, I'd like to show two cool projects that are completely unrelated,
and walk through a toolset that data scientists around the world use every day.

#### [Google Translate](https://play.google.com/store/apps/details?id=com.google.android.apps.translate&hl=en)

<div class="right" style="margin: 1em"><img src="/assets/images/google_translate_l2f.png" /></div>

This has been around for a few years, but it's still magic if you've never seen
it before. Google uses your smartphone camera to detect text and live translate
it to another language.

Where does the AI come in? The text detection: being able to intelligently
determine text at any angle, even handwritten? That takes some smarts. And it
even works offline.

Offline? Yes, offline. The trick with an AI model is that, once it's trained, it
only takes up a few kilobytes, maybe a megabyte or two. It's the training process
that is tricky.

#### [Magenta](https://magenta.tensorflow.org/)

Magenta is an expansion of the [Tensorflow](https://tensorflow.org) project that
focuses on creating art and music using AI tools.

Check out the [demos](https://magenta.tensorflow.org/demos/web/) to learn more,
like about Sornting (Sort + Song) and the Piano Scribe tool that transcribes
piano playing based on audio recognition.

#### [Jupyter Notebooks](https://jupyter.org/)

Data Science is still very much a science, and as such spawns many research
papers. More and more, reproducibility is key to peer reviewed research, so
data scientists needed a toolset that allowed them to share their experiments.

Thus, the Jupyter Notebook was born: "an open-source web application that allows
you to create and share documents that contain live code, equations,
visualizations and narrative text."

These, specifically, are used to help teach the [Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/)
by Google.

### Follow-Up

Thanks for reading this far. If you're curious about anything I wrote here, hit
me up on Mastodon [@LenPayne@Cybre.Space](https://cybre.space/@LenPayne), or join
us in the [Sarnia Tech Community](https://sarniatech.ca).
