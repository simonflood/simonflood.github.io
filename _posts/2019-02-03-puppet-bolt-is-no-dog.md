---
layout: post
title: "Puppet Bolt is no dog"
date: 2019-02-03
category: "Configuration Management"
tags: [puppet, puppetbolt, ubuntu]
---
On 24 January I was fortunate enough to be able to attend a free
[Puppet Bolt](https://puppet.com/products/puppet-bolt) workshop at
[Puppet](https://puppet.com/)'s London office. Having not previously used
Puppet (although I have been asked to talk through a Puppet module during an
interview!) I thought it would be a good opportunity to find out more and about
Puppet Bolt particularly.

Note: I saw this event promoted on LinkedIn by one of my contacts who now works
at Puppet (thanks Tom!). I don't think it was widely advertised yet it still
attracted 30 attendees not including a number of employees from Puppet.

Puppet Bolt is open source and although the name might suggest that it is an
add-on (or bolt-on ... sorry!) for Puppet you don't actually need Puppet to use
Puppet Bolt, although unsurprisingly you can use Puppet Bolt with Puppet.
Puppet Bolt connects to remote systems via SSH and WinRM and can be used to run
commands, existing scripts (written in any language), Puppet tasks, or Puppet
plans.

~~~
bolt command run <command> --nodes ...
bolt script run <script> --nodes ...
bolt task run <task> --nodes ...
bolt plan run <plan> --nodes ...
~~~

Like Ansible (or Salt in agentless mode), Puppet Bolt is agentless and one of
the reasons for Puppet Bolt is because people were using Ansible with Puppet.
Unlike Ansible (and other configuration/infrastructure management tools such as
Salt), Puppet Bolt can be installed on Windows, macOS, and various Linux
distributions. During the workshop we each installed Bolt on our own laptop to
manage two assigned nodes in AWS, one running Windows and the other CentOS
(Linux). It was just as well I was running Ubuntu 18.04.1 LTS Desktop on my
laptop because for Ubuntu only LTS releases are supported for Puppet Bolt!

I've simplified their [Installing Bolt](http://pup.pt/installbolt) instructions
for Ubuntu to use the **lsb_release** command to retrieve the codename.
~~~
wget https://apt.puppet.com/puppet6-release-`lsb_release -cs`.deb
sudo dpkg -i puppet6-release-`lsb_release -cs`.deb
sudo apt-get update 
sudo apt-get install puppet-bolt
~~~

Whilst you can specify authentication options when using the **bolt** command
it's easier to create **bolt.yaml** and **inventory.yaml** files. You can
create these within a directory called **Boltdir** but as I discovered during
the workshop don't create an empty Boltdir otherwise that will cause the
configuration files in your current working directory to be ignored! Oh and
Puppet Bolt will only look for inventory.yaml if bolt.yaml exists!!

During the workshop we worked through a simple task of setting up time
synchronisation on both our Windows and Linux AWS instances, ending up with a
Puppet plan which Puppet Bolt could run on both at the same time.

~~~
bolt plan run tools::timesync_code --nodes windows,linux
~~~ 

We then used Puppet Bolt to make pre-installed Puppet Agents on our AWS
instances register with Puppet Enterprise and used our Puppet Bolt tasks within
it. You can also use PCP (Puppet Communications Protocol) to use Puppet Bolt
directly against nodes managed by Puppet Enterprise which means you don't need
SSH/WinRM credentials and everything is automatically tracked and logged in
Puppet Enterprise.

Not previously knowing Puppet this was an interesting workshop. I can see that
if you're already using Puppet (or not using any configuration management
solution) then you should definitely take a look at Puppet Bolt. If you are
already using Ansible or Salt (or some other solution) then you're probably
already covered although it doesn't hurt to be aware of other solutions.

Simon

----
Updated 05 Feb 2019:
* removed reference to Puppet Bolt being multi-platform since Ansible, etc. can
  manage multiple platforms (even though they can only be installed on Linux)
* removed reference to SLES since Puppet Bolt package is only available for
  SLES12
* changed SaltStack to Salt
* added reference to Salt in agentless mode
