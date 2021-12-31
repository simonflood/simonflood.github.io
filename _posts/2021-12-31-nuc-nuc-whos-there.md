---
layout: post
title: "NUC, NUC, Who's There?"
date: 2021-12-31
category: "Home Lab"
tags: [ nuc, harvester, suse ]
---
As I'm sure for so many people, 2021 didn't quite go according to plan but then
neither did 2020!

Although not published here, I did manage to write one article for the
[SUSE Community site](https://community.suse.com/) on
[how to manage SUSE Harvester 0.3.0 with Rancher 2.6.1 running in a VM within Harvester](https://community.suse.com/posts/how-to-manage-harvester-030-with-rancher-261-running-in-a-vm-within-harvester)
which kind of links back to the subject of this post.

As of today I'm now all in on using
[Intel NUC](https://www.intel.co.uk/content/www/uk/en/products/details/nuc.html)s
for my home lab servers having
sold my last tower server to someone who will hopefully get more use out of it
than me. Despite working from home for most of the past 21 months (time flies!)
I found that I was not using my servers (two HP ProLiant ML110 G6, each with an
Intel Xeon X3430 quad core CPU, one with 16GB RAM and another with 32GB, plus
an Intel S5520HC/SC5650BRP "beast" with two Intel Xeon E5645 hex core CPUs and
96GB RAM!) as much as I expected to due to the noise they made and heat
generated. I also discovered how much floor space they took up.

Having known of the popularity of Intel NUCs for use in home labs, particularly
by those running VMware vSphere/ESXi, these were my first thought when I
started thinking about replacing my servers. However it was only when I bought
my first NUC, a
[NUC7i7DNHE](https://www.intel.co.uk/content/www/uk/en/products/sku/130393/intel-nuc-kit-nuc7i7dnhe/specifications.html),
in August that I realised how small they were! Thanks to William Lam and the
VMware community I already knew it should take
[64GB RAM](https://williamlam.com/2019/03/64gb-memory-on-the-intel-nucs.html)
but it's always good when it works!

Before buying this NUC I looked at the various models and specifications
available and wanting at least a quad core CPU I knew it had to have an 8th
generation i5 or i7 (or i9!) CPU. The advantage of this particular model is
that it has Intel AMT so I can remotely manage it.

A driver for updating my home lab was the development of a SUSE project called
[Harvester](https://harvesterhci.io) which I've been playing with since version
0.2.0. Essentially this allows you to host VMs and containers on the same
server and manage them all through a single interface. SUSE have a
[great video on YouTube](https://infl.tv/knFc) which explains Harvester far
better than I can!

I've since bought another two NUCs, a
[NUC7i7DNKE](https://www.intel.co.uk/content/www/uk/en/products/sku/130392/intel-nuc-kit-nuc7i7dnke/specifications.html)
(same as NUC7i7DNHE but M.2 SSD only) and a
[NUC8i5BEH](https://www.intel.co.uk/content/www/uk/en/products/sku/126148/intel-nuc-kit-nuc8i5beh/specifications.html).
The second NUC has joined the first to run
[Harvester 1.0.0](https://github.com/harvester/harvester/releases/tag/v1.0.0)
in a cluster and the third will become a management machine hosting
[Rancher](https://rancher.com/products/rancher) (amongst other things).

You've probably heard of Elf on a Shelf, well here are my NUCs (plus a SUSE
cowmeleon) on a shelf!

![NUCs on a shelf](/assets/images/NUCs-on-a-shelf.png)

This was definitely not possible with any of my tower servers (although I did
have one HP server on top of a bookcase before I acquired the other two
servers)!

Here's to a happier, healthier, and safer new year for everyone!
