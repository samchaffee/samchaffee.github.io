---
layout: post
title: My Vagrant setup for Jekyll/Github Pages
description: Blog entry about setting up Jekyll/Github Pages in a VirtualBox VM using Vagrant and Puppet.
tags:
- Jekyll
- VirtualBox
- Vagrant
- Puppet
- Github Pages
- Windows
status: publish
type: post
---
I recently started futzing around with this blog again and ran into problems with differences between my local [Jekyll](https://jekyllrb.com/) setup and Github Pages (where this is generated and hosted). My home computer runs Windows 10 so nice things like Homebrew and Macports weren't available to me. Because of that I decided to "redesign" my local setup to use Vagrant, Puppet (just to learn something new) and the Github Pages gem.

The result can be found in this Github [repo](https://github.com/samchaffee/cautious-memory). It depends on two PuppetLabs modules: [stdlib](https://forge.puppetlabs.com/puppetlabs/stdlib) and [ruby](https://forge.puppetlabs.com/puppetlabs/ruby), which for now are committed to the repo. I may make them Git submodules or something else later, but this was good enough to get me up and running in the meantime.

Check it out and if you have any suggestions or questions, please leave a comment below.
