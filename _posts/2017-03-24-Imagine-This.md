---
layout: post
tab_title: Claire's Cybersecurity Blog
title: Claire's Cybersecurity Blog
post_title: "Imagine This"
date: 2017-03-24 15:44
---

Following up on: [Galaxy Note 7s being prone to explosions](http://www.inquisitr.com/3803471/samsung-galaxy-note-7-explosions-reasons-found/)


Imagine this: A strain of mobile malware that masquerades itself as a totally non-suspicious application, 
like a game or a utility that supposedly scans your device for malware (there was an instance where the "antivirus app"
had a simple timer loop that made it seem like it was doing something, but wasn't).

It would be an app that targets the social engineering aspect of vulnerability.
What would this hypothetical application do?


For starters, the app is a response to the following: [http://www.bbc.com/news/technology-38404711](http://www.bbc.com/news/technology-38404711)

It would...
<ol>
<li> *Silently* access your WiFi hotspot settings (if applicable)</li>

<li> Set the hotspot to utilize the highest-strength encryption</li>

<li> Use a strong password (so it is hard to access the network, and subsequently, the phone)</li>

<li> Set the SSID to **Samsung Galaxy Note 7**</li>
</ol>
...*All* in an automated fashion!

Of course, I would never implement something like this (or even create a proof of concept).

I think it'd be pretty diabolical and a testament to how even some of the most clever people out there could get tricked by this social engineering attack.
