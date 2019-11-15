---
layout: post
title: MEGA Breach!
date: 2019-06-29 19:10
---

Earlier this week, I went to a cottage with some friends- we did kayaking, barbequing, peddleboating, the works! 

It was a great deal of fun.

What wasn't fun was when I decided to use [MEGA](https://www.mega.nz) and upload the photos I took in full resolution to my friends.

Ok you might be wondering about the title- No, MEGA was not breached. My account was, though.

It all happened when I noticed a strange "cryptocurrencies.zip" folder in the file listing- I don't recall uploading it or even using MEGA in the past year before last week.

Curious, I downloaded the file and there was an executible inside. Tempted to blow it up in my malware sandbox, my suspicions were confirmed when uploading to VT

gave me a bunch of hits for a TROJAN HORSE ([VT link](https://www.virustotal.com/gui/file/615e3fc9b983cd5697f0e6e1496d5b3266695a39a26f897c8619fb562136817a/detection)).

Hahaha, nice try!


MEGA also has a convenient session history section and as you can see here- and I can confirm I was nowhere in any of the countries listed in a 24-hour timespan- that

an external party compromised my account and likely uploaded "cryptocurrencies.zip" to my account.



<h2> How did it happen? <h2>

The most likely scenario: since the email I was using was seen in HIBP, attacker(s) got a hold of my password from a database dump. Of course, this should indicate to you

that password reuse is *very bad* and that *you should never do it* but hey, this was a long time ago and these days I use a password manager now with randomly generated passwords and

multifactor authentication (MFA).

With the password from the database dump, I can imagine the attacker utilized a password spraying attack, sort of a hail mary approach to try every email in the database they've extracted

with the associated password in the dump to see if access is granted.

So I can imagine that once the attacker was successful with the email and password pair, they uploaded a file in the hopes that the victim will open it up. 


Moral of the story? Use a password manager and multifactor authentication when possible!

