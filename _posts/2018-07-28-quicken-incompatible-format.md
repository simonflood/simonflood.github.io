---
layout: post
title: "Quicken Incompatible Format"
date: 2018-07-28
tags: [quicken, qif, homebank]
---
When I moved from a Windows desktop at home to Linux the only thing I missed
was Quicken, or more specifically a personal accounting application that could
handle Quicken files.

Before you rightly say that there are accounting packages that can import
Quicken files I found that the ones I tried, HomeBank and GnuCash, created two
accounts for each imported QIF file (I was using Quicken 6 so had to export
each account to a separate QIF file). When you have a lot of accounts to
import, including closed ones I was keeping for historic purposes, trying to
fix this post-import is a nightmare so having seen this with more than one
package I focused on the source files.

Even though Intuit came up with the
[Quicken Interchange Format](https://en.wikipedia.org/wiki/Quicken_Interchange_Format)
(QIF) it seems that from reading up about QIF files their own software doesn't
fully follow the format, or at least Quicken 6 doesn't! Checking the exported
QIF files I saw that each was missing an !Account header section at the
beginning of the file.

~~~
!Type:Bank 
D7/28/18
T1,000.00
CX
POpening Balance
L[SMF Current Account]
^
~~~

By writing a little Perl script I was quickly able to add an appropriate
!Account header section to each file and could then import all my accounts into
HomeBank, my chosen application, without creating secondary accounts.

~~~
!Account
NSMF Current Account
TBank
^
!Type:Bank
D7/28/18
T1,000.00
CX
POpening Balance
L[SMF Current Account]
^
~~~

Whilst I've now happily been using HomeBank for some time I'm posting this in
the hope that it helps someone else moving from Quicken.

Simon
