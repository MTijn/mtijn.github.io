---
layout: post
title:  "Spotify stopped working after upgrading from Kubuntu 14.10 to 15.04"
date:   2015-04-24 17:34 +0200
categories: [KDE, Spotify, Plasma]
author: Martijn Klene
---

Whilst the new KDE with Plasma 5 is a treat to work with, I really do like the new interface they have created, and I must admin, when I tried the alpha releases I was not impressed at all. Good thing they have made a stable environment.
<!--more-->

This morning when I had updated the Kubuntu version on my laptop I got a nasty surprise when starting Spotify, it kept telling me libgcrypt11.so was not installed on my system. That was a bit strange since the app worked just fine the day before. I started investigating the issue and found out the libgcrypt version on Ubuntu 15.04 was upgraded to libgcrypt20, and the older version removed.

After some searching I headed for the Utopic release where the version still is at 1.5 and working for Spotify, so I grabbed the download link (http://security.ubuntu.com/ubuntu/pool/main/libg/libgcrypt11/libgcrypt11_1.5.4-2ubuntu1.1_amd64.deb), and installed it by doing a dpkg -i libgcrypt11_1.5.4-2ubuntu1.1_amd64.deb.

And presto Spotify started working again, and I could go on developing with my music on.
