---
title: Annual is "Regularly Scheduled", Right? 
layout: post
category: Learning
---
I was not very good at continuing to post in the last year.

I wrote a draft around late November when I got into Mastodon (before the Tumblr
Exodus) about setting up Mastodon on the RHEL 8 beta. It... didn't go well.

You can find some of my musings on Mastodon [@LenPayne@Cybre.Space](https://cybre.space/@LenPayne)

When I have occasion to wax on things, I am often waxing there. I do not have
occasion very often, though.

If you're interested, follow through for a more full update. But the Coles'
Notes version is:

- I officially resigned from the College in mid-2018
- I have been the full-time CTO of Link2Feed for 13 months now
- I have not posted since last Family Day -- it is again Family Day
- The Sarnia Tech Community and Sarnia-Lambton Linux Users Group 
  are going strong
- I am still running a DragonflyBSD VM here at home
- I tried to run some production loads on the RHEL 8 beta and 
  realized how many non-standard tools we use

<!--more-->

### Greener Pastures

Yes, I did it. I jumped out of the fishbowl into the wide open ocean.
I loved my time at the College, and miss it in many ways, but I am very
excited for the opportunities and challenges that I am able to face out
in the field. The opportunity to step in as technical leadership in a
business whose mission I genuinely believe is worth taking part in? It's
a dream come true, and it's a 10min commute.

Our team has grown, both through the grace of good business, but also
through the tight integration with Lambton College's Applied Research
department. We have been able to train and retain four great students
for various time frames. We also picked up a new Senior Developer
through dumb luck and good timing. The size of our technical team has
doubled in the time since my last post here.

### Community Living

The [Sarnia Tech Community](https://www.sarniatech.ca) and the 
[Sarnia-Lambton Linux Users Group](https://www.sllug.ca) have
managed to weather their first full calendar year and are still going
strong, each in their own way. There has been a bit of a merging of
bodies, as there was a leadership vaccuum in the Sarnia Tech Community.
However, the community has become stronger through adversity, and we
are getting closer to sustainability.

We're having our second annual InstallFest coming up for the SLLUG.
It's going to be a good time, and I'm looking forward to it. It's
always fun watching the community come together.

We also have a "Controls Village" event tentatively planned. We have
access to some esoteric controls systems that our group can play
around with and learn on. It's not a beginner-friendly exercise (yet)
but the wizened vets are looking forward to it.

### Technical Front

My DragonflyBSD VM is still running strong. It's still a VM, though
and doesn't have any bare metal to muck about on. I'd like to get
some new metal in, but I have both cash-flow issues and space issues.
(And "What the hell is that noise?!" issues.) I don't know how long
I'll run the VM. It's cool, but right now it's basically just a ZNC
bounce box and an outdated mirror of my website.

I tried to run some production workloads on the RHEL 8 beta. We run
primarily CentOS boxes in production, so I wanted to get an idea of 
how rocky that change is going to be.

Turns out: rocky.

I took for granted how much extra side-channel things we have in
our deployments. Both simple things like Ruby, and more complex
things like Passenger on top of Nginx. So while I can stand up a
bog-standard LAMP or LEMP server pretty easily, getting our unique
workload working is going to be a little post-release while the
tooling around us catches up.

Another cool weekend project I tried out (partly as a lark) was
to run some production workloads on AWS' new ARM-based a1 units.
It was remarkably easy to setup a Mastodon instance: no different
than on an x86 box. I'm sure it wouldn't be hard to find the
limits of what those boxes can do, but it was nice not to hit them
while I was setting up a relatively robust app like that.

### Trying to Be More Engaged

I'm really trying to be more engaged with the community. Both the
actual in-my-life community of Sarnia-Lambton, but also to
interact with the larger world of development outside my walled
garden. We do some amazing things here, and I know that a lot
of the reason I do them is because I stay involved by listening
to the world outside. But I think we're starting to generate
some stories worth telling.

So I hope to do that again soon.

See you next Family Day, but hopefully sooner.
