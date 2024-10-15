---
layout: post
title: "1000 Days of Harvester for my Home Lab"
date: 2024-10-15
category: "Home Lab" 
tags: [ harvester, suse, kubernetes ]
---
On Monday 17th January 2022, I re-[installed SUSE Harvester 1.0.0 on two Intel NUCs to become my home lab](https://simonflood.info/blog/2021/12/31/nuc-nuc-whos-there). Little did I know then that 1,000 days later it would still be running!

![Harvester Dashboard](/assets/images/Harvester-1000-Dashboard.png)
![Harvester Hosts](/assets/images/Harvester-1000-Hosts.png)

During those 1,000 days I've upgraded Harvester to each next applicable version, usually soon after they've become available (bleeding edge!). Here are all the releases since version 1.0.0 with my path (in **bold**) to the current latest version 1.3.2.

![Harvester upgrade path](/assets/images/Harvester-1000-upgrade-path.png)

Now I won't pretend that it's all been straightforward and easy as there have been some moments, particularly with upgrades, where given this is a home lab I've thought about reinstalling but then where's the fun in that? Thanks to the Harvester team, particularly Kiefer and Zespre, any issues have been investigated and resolved plus we all learnt something ...

Which is one of the reasons for having a home lab, so that I could learn and develop skills. Having [changed jobs just over two years ago](https://simonflood.info/blog/2022/09/01/my-future-is-bright-my-future-is-green-white-and-orange) I've been able to try out some things in relation to that plus investigate technologies that I've become aware of. It has also provided a platform to help me prepare for various certifications, mostly SUSE ones (Linux and Kubernetes) but also the awareness of Harvester's underlying Kubernetes (you learn a lot troubleshooting a broken cluster!) helped with taking and passing Linux Foundation's [Certified Kubernetes Administrator (CKA)](https://training.linuxfoundation.org/certification/certified-kubernetes-administrator-cka/) exam.

During SUSECON Digital 2022 I also co-presented on [using Harvester for your home lab](https://www.youtube.com/watch?v=tYSsJmqKws4) to share some of things I'd learned up until that point.

So having reached this milestone what next for my little lab?

1. I've a third NUC which I had previously thought might have hardware issues which I'm going to recheck and hopefully add which would then introduce high availability and help balance resources across the cluster
2. I'm making some hardware changes to my home networking setup which would then allow me to create some additional networks
3. I'm still running Rancher as a Docker container on a VM within the cluster and whilst it works upgrades are a bit of a pain (disk space issues) so I will likely change to running Rancher in a single-node K3s or RKE2 cluster
  - Another option I'm considering is using the rancher-vcluster addon to run Rancher as a workload on the underlying Harvester cluster
4. Whilst my Harvester cluster has worked well for me I'm aware that I'm pushing it with the limited hardware, particularly CPU cores, so I'm considering new hardware
  - I'm looking to stick with the NUC form factor but may have to give up on the remote management though

Simon
