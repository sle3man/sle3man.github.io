---
layout: post
title: MEGA Breach!
date: 2019-06-29 19:10
---

Earlier this week, I went to a cottage with some friends- we did kayaking, barbequing, peddleboating, the works! 

It was a great deal of fun.

What wasn't fun was when I decided to use [MEGA](https://www.mega.nz) to upload the photos I took in full resolution to my friends.

Ok you might be wondering about the title- No, MEGA was not breached. My account was, though.

It all happened when I noticed a strange "cryptocurrencies.zip" folder in the file listing- I don't recall uploading it or even using MEGA in the past year before last week.


![Strange file](/assets/mega_compromise/dropped.png)

Curious, I downloaded the file and there was an executible inside. Tempted to blow it up in my malware sandbox, my suspicions were confirmed when uploading to VT gave me a bunch of hits for a TROJAN HORSE ([VT link](https://www.virustotal.com/gui/file/615e3fc9b983cd5697f0e6e1496d5b3266695a39a26f897c8619fb562136817a/detection)).

Hahaha, nice try black hats!


MEGA also has a convenient session history section and as you can see here-

![Session history](/assets/mega_compromise/session.png)


I can confirm I was nowhere in any of the countries listed in a 24-hour timespan when the file was uploaded- that an external party compromised my account and likely uploaded "cryptocurrencies.zip" to my account.

![Date the file was uploaded](/assets/mega_compromise/session2.PNG)



<h2> How did it happen? <h2>

The most likely scenario: since the email I was using was seen in HIBP, attacker(s) got a hold of my password from a database dump. Of course, this should indicate to you that password reuse is *very bad* and that *you should never do it* but hey, this was a while ago and these days I use a password manager now with randomly generated passwords and multifactor authentication (MFA)!

With the password from the database dump, I can imagine the attacker utilized a combination of a [credential stuffing](https://www.owasp.org/index.php/Credential_stuffing) and [password spraying attack](https://www.triaxiomsecurity.com/2018/11/08/password-spraying-attack/), sort of a hail mary approach with leaked credentials from various sources to try every email in the database they've extracted with the associated password in the dump to see if access is granted.

So I can imagine that once the attacker was successful with the email and password pair, they uploaded a file in the hopes that the victim will open it up. 


The whole ordeal gave me a brief spook but there's nothing to worry about, to be honest. I don't think the files I had on there were accessed as it feels like the compromise was automated. 

Moral of the story? Use a password manager and multifactor authentication when possible!

If you'd like some recommendations for password managers (I'd go with paid ones since free services might not actually be free, where *you* are the product) check out this [PCWorld link](https://www.pcmag.com/roundup/300318/the-best-password-managers)! Granted, password managers [have their own issues/vulnerabilities](https://devd.me/papers/pwdmgr-usenix14.pdf) (PDF) but the costs outweigh the benefits- using strong passwords is the first step towards better online security.
