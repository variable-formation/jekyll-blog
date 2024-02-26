---
layout: post
title:  "Replacing Dell's Weird 5-pin Fan Header"
date:   2024-02-2 20:30:00 -0600
categories: [Homelab, Janky]
---

# Introduction

I had a casualty in my homelab last night. The bearings in one of the front fans of the Dell Precision T3500 finally gave out, and while the fan _worked_, it was not pleasant to listen to at all. Since I have all of my hypervisor's clustered together, I was able to live-migrate any running VMs onto another machine for the time being while I replaced the fan.
<br>
Which was where I hit my first road block. The fan I had planned to replace the broken one with was a standard 4-pin PWM fan. However, Dell uses this weird 5pin header for their T3500 towers. I wasn't keen on having to spend money on
