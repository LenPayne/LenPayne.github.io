---
title: DragonFly BSD - First Impressions
layout: post
category: DragonFly BSD
---
As part of [SLLUG](https://www.sllug.ca), we have monthly chats about open source
software. One of the places I've had a significant blind spot in my FLOSS knowledge
is with the BSD ecosystem. Our March conversation is about enterprise technologies.
I tasked our members with some homework: go learn something new, and tell us
about it!

So I'm diving in a very specific direction: I'm going to learn about [DragonFly BSD](https://www.dragonflybsd.org).

#### History Lesson

[<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/77/Unix_history-simple.svg/1200px-Unix_history-simple.svg.png" alt="Unix history-simple.svg" align="right" style="width: 30%">](https://commons.wikimedia.org/wiki/File:Unix_history-simple.svg#/media/File:Unix_history-simple.svg)

I was introduced to DragonFly BSD through [Lobsters](https://lobste.rs/) some time
ago. For those (like me) unfamiliar with the BSD world, I want to get into [a
brief history lesson](https://en.wikipedia.org/wiki/History_of_Unix#/media/File:Unix_history-simple.svg)
before I get more specifically into DragonFly BSD.

- Jan 1st, 1970 - The UNIX Epoch. The effective start of time (and UNIXes)
- 1977 - UC Berkeley produced an academic UNIX-derivative called the [Berkeley Software Distribution](https://en.wikipedia.org/wiki/Berkeley_Software_Distribution)
- The 80s - BSD development was largely done in academic circles, on mainframes
- 1991 - Linus Torvalds launches [Linux](https://en.wikipedia.org/wiki/Linux), to bring a UNIX-like kernel to his Intel 80386 PC at home
- 1992 - Not to be outdone, two Berkeley alumni ported BSD 4.2 and BSD Net/2 to the Intel 80386 and dubbed it [386BSD](https://en.wikipedia.org/wiki/386BSD)
- 1993 - Two forks of 386BSD appeared: [FreeBSD](https://en.wikipedia.org/wiki/FreeBSD) and [NetBSD](https://en.wikipedia.org/wiki/NetBSD)
- 1995 - Berkeley stopped supporting BSD, and 4.4BSD-Lite Release 2 was released to the world. BSD did not die, it merely shifted to governance in forks (FreeBSD, NetBSD, Mac OS X, etc)
- 1996 - Conflict in the NetBSD project brought rise to a third fork: [OpenBSD](https://en.wikipedia.org/wiki/OpenBSD)
- 2003 - This is where our story begins, with the launch of [DragonFly BSD](https://en.wikipedia.org/wiki/DragonFly_BSD)

#### What is DragonFly BSD?

<!--more-->

In 2003, one of the core FreeBSD developers, Matthew Dillon, disagreed fundamentally
with the direction that FreeBSD was taking with the rise of threading and symmetric
multiprocessing (SMP). He tried to bring change within the FreeBSD project, but
the disagreement was fundamental enough that Matthew decided to fork the FreeBSD
project and begin a new BSD system of his own.

It's now been 15 years, so the [key features](https://www.dragonflybsd.org/features/)
that differentiate DragonFly BSD from other operating systems are:

- Significant Kernel changes designed to deal with threading and SMP differently
- "Extreme Scaling" modifications made to resource autoscaling methods
- The HAMMER filesystem is a ZFS-like filesystem providing snapshotting and history
- Various improvements to loopback systems, in-memory filesystems, NTP, and SMTP

Over time, though, DragonFly BSD has worked tightly with the other BSD systems
to move forward together. So good changes that make sense to port into DragonFly
BSD from FreeBSD, NetBSD or OpenBSD do get incorporated into DragonFly BSD.

#### DragonFly BSD's Use Cases

DragonFly BSD is a fully-featured OS, and can operate in either traditional
server or desktop roles. Its major feature development, though, is primarily
focused on bare-metal installs. Where much of the world is pushing to the cloud,
this DragonFly seems content to fly closer to the ground.

As a test, I installed a basic web stack on my DragonFly BSD VM: Nginx, PHP, and
PostgreSQL.

It was pretty straightforward. The usage of `rc.conf` brought me back to fond old
days of using [Gentoo](https://gentoo.org/) and [Arch Linux](https://www.archlinux.org/)
(before `systemd`).

#### One Challenge - `vim` without X11

There is one thing I wish had been more clear early on. I wanted to install `vim`
but it had massive X11 dependencies, and I wasn't planning on running graphical.

So the suggestions I found had me installing from `dports` (the DragonFly BSD
version of `ports`). But no one mentioned `vim-lite` as an option.

So here it is: if you want `vim` without the X11 dependencies on FreeBSD or DragonFly
BSD, install `vim-lite`. It appears on the FreeBSD side this has been [renamed as `vim-console` as of Jan 11th, 2018](https://www.freshports.org/editors/vim-console/),
and I expect that change to rollover to DragonFly BSD sooner or later.

This little excursion helped me better understand the relationship between FreeBSD
and DragonFly BSD, though. Most common software available for FreeBSD will be
already available for DragonFly BSD as they share a lot of things on the `ports`
side. Much of it was even built-in, so a lot of suggestions/fixes for FreeBSD
worked just great on the DragonFly BSD side.

#### First Impressions

I'm happy with my decision to explore. For the time being, I'm going to use this
server to experiment and play around with. It was really easy to install the
base software for my web stack. And `rvm` actually installed seamlessly.

There are significant limitations with DragonFly BSD. It's only available on x64
hardware. It has a small developer base (smaller than FreeBSD even.) The driver
availability is thus reduced due to the small dev base.

However, it's a lean, focused machine that gets the job done.

I don't know if I'll be pushing production workloads onto DragonFly BSD, but I
think my next physical server will be running this on the bare metal, and that's
pretty cool.

I'm looking forward to using DragonFly to learn how to use `jails`, and learning
to segment servers the BSD-way. So perhaps that will be my next post.

##### Notes:

1. The [Simple Unix History Diagram](https://commons.wikimedia.org/wiki/File:Unix_history-simple.svg#/media/File:Unix_history-simple.svg)
is by Eraserhead1, Infinity0, Sav_vas [[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0) or [GFDL](http://www.gnu.org/copyleft/fdl.html)], via Wikimedia Commons
