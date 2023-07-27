---
title: Open Source in Business
layout: post
category: Learning
---
On July 25th, I will be presenting for the [Canadian Undergraduate Computer Science Conference (CUCSC)](https://www.cucsc.ca)
at one of my alma maters, the University of Windsor. The presentation will be on
a topic I think is valuable to current students, namely the implications of using
open source technology in business, both pros and cons, and how to manage the
balance.

This article is mostly a brain-dump of all the things I think I might talk about.

I will include this link in my presentation, and I will [attach the slides](/LenPayne-CUCSC-2019.pdf) on my
site for people to download. To dig into the meat of the matter, keep reading.

<!--more-->

### What is Open Source?

Better people than I have spoken at length about open source. So here's their
words:

* [The Open Source Initiative](https://opensource.org/)
* [Wikipedia: Open Source](https://en.wikipedia.org/wiki/Open_source)
* [The Free Software Foundation](https://www.fsf.org/about/)
* [Red Hat's Stance on Open Source](https://www.redhat.com/en/about/open-source)

Without getting too historical, the basic distinctions are open and closed source.
With open source technology, a member of the general public can somehow gain
access to see and modify the original source material of a piece of technology.
With closed source technology, the general public does not have these rights.

#### So how does a piece of technology become open source?

It is released publicly, and explicit permission is given for people to use, re-use
and modify the technology under certain conditions. Basically: someone shares it.

This concept flies stark in the face of many ideas around intellectual property,
valuation and profit that many people and organizations hold dear. If something
is valuable, the theory goes that it should not be given away freely.

To avoid a lengthy philosophical debate, let's just agree that different camps
will disagree. I will get into the pros and cons a bit more after some definitions.

### Types of Open Source Licenses

The "explicit permission [...] under certain conditions" that I mentioned above
is what's called the "License" for the technology. It usually starts something like:

    Redistribution and use in source and binary forms, with or without
    modification, are permitted provided that the following conditions
    are met...

    - Preamble for the BSD 3-Clause license

When [choosing how to license](https://choosealicense.com/) a new project as an
open source initiative, it's entirely possible to write your own license, but
most projects share common licenses. These broadly fall into two camps:

#### 1. Permissive Licensing

The basic idea of a permissive open source license is to allow people to use it
without requiring much extra from them. The low bar to entry may be as simple
as providing credit where due, and frequently does not even require that unless
the modified project is redistributed.

Some of the common licenses in this category are:

* [Apache 2.0 License](https://opensource.org/licenses/Apache-2.0)
* [BSD 3-Clause License](https://opensource.org/licenses/BSD-3-Clause)
* [BSD 2-Clause License](https://opensource.org/licenses/BSD-2-Clause)
* [MIT License](https://opensource.org/licenses/MIT)
* [The Unlicense](https://unlicense.org/)
* [The WTFPL](http://www.wtfpl.net/)

If I build a piece of technology and share it with any of these licenses, you
can pretty well do whatever you want with it, and in only a few of them would
you be required to tell people I was involved at all. That's free and open source.

And... some feel it's not fair. So there's also:

#### 2. Restrictive Licensing

The basic idea of a restrictive open source license is to require anyone who uses
the original technology to share any changes they make. This varies, depending
on the license, and the exact terms. This basic concept is called ["copyleft"](https://en.wikipedia.org/wiki/Copyleft).

The most common restrictive, copyleft licenses are:

* [GNU General Public License (GPL)](https://opensource.org/licenses/GPL-3.0)
* [GNU Library/Lesser GPL (LGPL)](https://opensource.org/licenses/LGPL-3.0)
* [GNU Affero General Public License (AGPL)](https://www.gnu.org/licenses/agpl-3.0.en.html)
* [Mozilla Public License](https://opensource.org/licenses/MPL-2.0)

These vary in their specifics, but broadly require the same basic protections for
freedom:

1. If the software is changed and distributed, those changes are shared publicly.
2. The publicly shared material is shared under the same or similar licenses.
3. Any breach of the agreement is punishable through clear legal recourse.

### But Len, You Said This Was About Open Source in Business!?!

So here's the trick. Every business is different. There is only one [Red Hat](https://www.redhat.com).
There's only one [Facebook](https://opensource.facebook.com/) and only one [Microsoft](https://opensource.microsoft.com/).

And there's only one [Link2Feed](https://www.link2feed.com), and only one [Redis](https://redis.io/) too.

I'm going to try a scatter-shot approach to discuss some pitfalls and some big
wins from open source in business. We'll start with the big dogs.

#### Red Hat - Preferring Reciprocal Sharing

"The Open Source Company" was recently purchased by IBM. They have operated for
over 20 years, have peaked over $1b in revenue, and all of their IP is open source.

So what are they selling, to get that $1b? Services. The software is important,
but it is a means to an end. Red Hat exists as a professional services company
with a unique ethical bent. They build and support open source technology, but
their primary goal is to provide stable technology for enterprise clients.

Many Red Hat technologies are licensed using restrictive licenses, like the GPL,
because they believe strongly in the share-and-share-alike mentality.

#### Facebook - Profiting from Permissive

When Mark Zuckerberg and his team built the initial Facebook platform, they did
not go about re-inventing wheels. They built on top of freely available tools
like Linux, Apache, MySQL and PHP (the LAMP stack).

While the core Facebook platform has remained behind closed doors, the team at
Facebook have been actively contributing back to those open source tools that
they use (ie- the LAMP stack, and others.)

In recent years, Facebook has even taken a strong step to license and make
available some of their internal tools, like [React](https://reactjs.org/).

As a counterpoint to the mandated-sharing above, Facebook prefers the MIT
license, which is about as permissive as you can get short of the WTFPL. The
main reason that Facebook prefers the permissive license is because it does not
require them to share other tools, as a GPL license might.

#### Redis - Open Source for the Little Guy

As a counterpoint to the big dogs, I'd like to take a look at a smaller project:
Redis, which is a fast caching system and key-value store. Basically, a simple database.

Redis, as a project, has been [open source since day one](https://github.com/antirez/redis),
and is offered under a BSD 3-Clause license.

However, as it quickly gained popularity, the original authors realized they could
potentially add premium and enterprise features on top as paid bonuses. The
flexibility of the BSD license allowed them to build on top without sharing. This
business model became [Redis (the company)](https://redis.com/).

For a time, Redis enjoyed their status as a growing tech company, but the
truth of the matter was that their core service (Redis) was free. So some of
the big tech companies, [like Amazon](https://aws.amazon.com/elasticache/), were
undercutting Redis on their own product.

In response to this, [Redis changed their licenses... a couple times](https://redis.com/blog/redis-labs-modules-license-changes/).

As I mentioned above, there's only one Red Hat. Only one company has taken a fully
open sourced technology and made a billion dollars off of building a support
system around that free technology. Most companies that choose to share their IP
as open source too early will get squashed by the big dogs.

Redis is holding on, and fighting the good fight, but they are definitely
reeling from a fight with Amazon that Jeff Bezos probably doesn't even know is
happening.

### Bringing it Back Home

Link2Feed is a small company. We use open source software every day. However,
we have to be very careful about which open source software we use. Why?

1. If we use the wrong OSS, it may require us to share our private code.
2. If we use abandoned/dying projects, we may be left with a security mess.
3. If everything goes right today, we may still be stuck down the road as the sole supporter of a 3rd party project just to keep our systems afloat.

Like Facebook, we prefer to use products with MIT or Apache licenses. This avoids
triggering any reciprocal licensing clauses, and helps us keep the value of our
own IP.

### Wrapping Up

During the presentation, I plan to give a quick demo/hands-on exercise of
contributing to an open source project, and talk about [#hacktoberfest](https://hacktoberfest.digitalocean.com/).

There are several lists of [beginner-friendly projects](https://github.com/MunGell/awesome-for-beginners)
for a person to peruse, for example [this newbie label on phpMyAdmin](https://github.com/phpmyadmin/phpmyadmin/labels/newbie).

Time permitting, I will walk through an easy issue with the group. Otherwise,
I will highlight the story of how I tried to log into [the Changelog](https://changelog.com/)
and wound up [contributing to the page's source code](https://github.com/thechangelog/changelog.com/commits?author=LenPayne)
and [the upstream tool that caused the initial issue](https://github.com/ueberauth/ueberauth_github/commits?author=LenPayne).

* Get [the slides](/LenPayne-CUCSC-2019.pdf).
