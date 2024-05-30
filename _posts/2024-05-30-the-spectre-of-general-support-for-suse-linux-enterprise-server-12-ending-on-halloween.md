---
layout: post
title: "The spectre of General Support for SUSE Linux Enterprise Server 12 ending on Halloween"
date: 2024-05-30
category: Linux
tags: [ linux, opensource, suse, sles ]
---
Disclaimer: Please note that I don’t work for SUSE but do work for a SUSE Diamond Partner, Securelinx. However this article was written by me in a personal capacity in the absence of an official blog article by SUSE.

Whilst the attention of the Linux community (including SUSE with Liberty Linux) has been on [support ending for CentOS Linux 7 on 30 June 2024](https://blog.centos.org/2023/04/end-dates-are-coming-for-centos-stream-8-and-centos-linux-7/) (in line with the [end of Maintenance Support for Red Hat Enterprise Linux 7](https://access.redhat.com/support/policy/updates/errata#Life_Cycle_Dates)), SUSE has their own deadline approaching for the end of General Support for SUSE Linux Enterprise Server (SLES) 12.

![Screenshot of SUSE Product Support Lifecycle for SUSE Linux Enterprise Server](/assets/images/SLES12-end-of-General-Support-1.png)

From SUSE's [Product Support Lifecycle](https://suse.com/lifecycle) page you can see that General Support for SLES 12 ends on 31 October 2024. This also includes the SUSE Linux Enterprise (SLE) HPC, SLE Real Time, and SLES for SAP Applications products plus the High Availability and Workstation Extensions. General Support for SUSE Linux Enterprise Desktop (SLED) 12 already ended on 31 December 2019.

So what does this mean in reality? Exactly the same as it does for CentOS and RHEL 7 – no further updates will be available for SLES 12 unless you purchase Long Term Service Support (LTSS).

What are your options?

Whilst doing nothing is always an option it’s not a good one if you are using SLES12 for anything other than development work in an isolated environment. The end of General Support will mean no further security updates so you don’t want SLES12 connected in any user- and/or internet-facing roles.

If doing nothing is not an option then what can you do?

1. Buy yourself time by purchasing [Long Term Service Support (LTSS)](https://www.suse.com/support/policy-products/#ltss). This is available for up to three years (with a minimum of one year) and is bought on a per server basis. Depending on the number of servers  this could be costly plus if you’re not already running SLES12 SP5 you’ll need to upgrade all those servers to be covered.

   If you are running SLES 12 or SLES for SAP Applications 12 and purchasing SUSE subscriptions via a public cloud provider please see this [SUSE blog article by Stephen Mogg on adding LTSS to SLES 12 in the Public Cloud](https://www.suse.com/c/adding-ltss-to-sle-12-on-the-public-cloud-for-payg-on-demand-workloads/).

2. Upgrade SLES 12 servers to SLES 15. It sounds simple written down but this all depends on the SLES versions and number of servers.

   ![Screenshot of supported upgrade and migration paths to SLES15 SP5](/assets/images/SLES12-end-of-General-Support-2.png)

   As you can see from the [SLES15 SP5 Upgrade Guide](https://documentation.suse.com/sles/15-SP5/html/SLES-all/cha-upgrade-paths.html#sec-upgrade-paths-supported) depending on your starting point there are multiple routes to the (currently) latest version of SLES15, SLES15 SP5. In my role at Securelinx I’ve successfully upgraded a lot of servers from SLES for SAP Applications 12 SP3 and SP5 to 15 SP4 (with some of those also having first been upgraded from 11 SP4).

   Each upgrade will require testing and may involve others, particularly if you are upgrading SLES for SAP Applications as there will likely be upgrades required at each stage to the SAP components.

3. Migrate services from SLES12 servers to new SLES15 servers. Depending on the SLES versions and types of services this could be quicker than multiple upgrades but will require good documentation and might require more testing.

As you can tell from the above options, this will take time whether you choose to upgrade or migrate, particularly if you have a large number of servers. With a continuously improving upgrade procedure I estimate 1-2 hours per off-line upgrade using (virtual) media.

If you are using Subscription Management Tool (SMT) on SLES 12 you should also be aware that after upgrading your SMT server to SLES 15 you will need to migrate SMT to Repository Mirroring Tool (RMT). As the name suggests, RMT is not a complete replacement for SMT and you will lose some functionality.

As a final takeaway, whatever you do (or don’t) decide to do the one thing I would strongly recommend is to download all the required media for your current and later versions of SLES from the [SUSE Products](https://www.suse.com/products/) pages and keep those somewhere safe. You should only require DVD1/Media1 for the architecture(s) you are using and note all SLES15-related products for the same Service Pack share the same media.

Simon
