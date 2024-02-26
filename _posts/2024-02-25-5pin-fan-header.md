---
layout: post
title:  "Fixing Dell's Weird 5-pin Fan Header"
date:   2024-02-2 20:30:00 -0600
categories: [Homelab, Janky]
---

# Fixing Dell's Weird 5-pin Fan Header
#### 25 February 2024

## Introduction

I had a casualty in my homelab last night. The bearings in one of the front fans of the Dell Precision T3500 finally gave out, and while the fan _worked_, it was not pleasant to listen to at all. Since I have all of my hypervisor's clustered together, I was able to live-migrate any running VMs onto another machine for the time being while I replaced the fan.
<br>
Which was where I hit my first road block. The fan I had planned to replace the broken one with was a standard 4-pin PWM fan. However, Dell uses this weird 5pin header for their T3500 towers. I wasn't keen on having to spend money on either an adapter or a new fan assembly. I do not have another fan that will fit, and I wanted to use this as an opprotunity to try somthing. I have a strong suspicion that those connectors are just pin to pin connections.

## Background
When I was initially taking out the broken fan, I noticed two things. The first thing I noticed was that the fan header was five pins instead of the standard four. The second thing I noticed that the fith pin was completely unused.

![The fan header in question, with the fifth pin not used.]("../asstes/_5pin-fan-header/broken-fan-header.jpg"){: .responsive}

Putting that in the back of my mind, I went out to do some research to find a replacemnet. It wasn't hard to do so. There's an abundance of of adapters on eBay and Amazon. And most of them do not have any kind of shroud to protect the individual wires.

![One of the fan header adapters in question.]("https://m.media-amazon.com/images/I/418pwbCqw+L._AC_SX679_.jpg"){: .responsive}

After seeing this, my suspicions were validated.

## The Plan
I have several buck converters, jumper wires, and breadboards from when I used to tinker with Arduinos. So. I'm going to use these to put something together that will let me put that four pin fan in the case and have it plugged into the motherboard. It wasn't hard to find out what wires go where.

![The wires in question.]("https://www.techpowerup.com/forums/attachments/dell-5-pin-fan-png.250470/"){: .responsive}
