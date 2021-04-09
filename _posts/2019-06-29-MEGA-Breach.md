---
layout: post
title: MEGA Breach!
date: 2019-06-29 19:10
---

Last updated: 9 April 2021

Earlier this week, I went to a cottage with some friends- we did kayaking, barbequing, peddleboating, the works! 

It was a great deal of fun.

What wasn't fun was when I decided to use [MEGA](https://www.mega.nz) to upload the photos I took in full resolution to my friends.

Ok you might be wondering about the title- No, MEGA was not breached. My account was, though.

It all happened when I noticed a strange "cryptocurrencies.zip" folder in the file listing- I don't recall uploading it or even using MEGA in the past year before last week.


![Strange file](/assets/mega_compromise/dropped.png)

Curious, I downloaded the file and there was an executable inside. There was a text file called "passphrases.txt" and "PasswordDecoder.exe" executable. Tempted to blow it up in my malware sandbox, my suspicions were confirmed when uploading to VT gave me a bunch of hits for a TROJAN HORSE stealer ([VT link](https://www.virustotal.com/gui/file/615e3fc9b983cd5697f0e6e1496d5b3266695a39a26f897c8619fb562136817a/detection)). Stealer malware typically has the aim of stealing credentials, currency, or the like. In this case, since the .zip file was titled "cryptocurrencies.zip", my guess is the executable is a cryptocurrency stealer.

I'm not the most proficient at malware analysis, but from what I see in VT, the malware connects to a Dynamic DNS service (DuckDNS) over port 10 and drops a couple files with Windows executable names as a way to masquerade as legitimate processes, e.g., runtimehelper.exe and dllhost.exe in %LOCALAPPDATA%\microsoft\. The text portion of the executable is also [packed](https://blog.malwarebytes.com/cybercrime/malware/2017/03/explained-packer-crypter-and-protector/) with a high amount of entropy (6.5). High entropy usually means that a malware author is trying to evade antimalware engines as high entropy [is typically found within malware](https://n10info.blogspot.com/2014/06/entropy-and-distinctive-signs-of-packed.html)

As for the text file, it has a single line of random text that I (or Cyberchef with the magic function) couldn't decipher. Shoot me an email if you're familiar [with this malware and know what the text means](https://gchq.github.io/CyberChef/#recipe=Magic(5,true,false,'')&input=MzJHQXRVMWRaZ3pNV2g5a2FlMzBtU0JTZTdDczBkSVJOTUh4YjIxODN5bDZzM2tVWWdET1VPblY3eXVGVjJ3b25tbFMwOTh5cXJqS2VuaWZkYXJSWk5tcFR6eG42bGR1MjlhVjd4ZjhGQ1hjREhIeDllZms1d3RwTFE5eVcyUWJHMnVSV2Jkd1lSWEpHVg). My best guess is it's an obfuscated crypto address of the threat actor.

Hahaha, nice try black hats!


MEGA also has a convenient session history section and as you can see here-

![Session history](/assets/mega_compromise/session.png)


I can confirm I was nowhere in any of the countries listed in a 24-hour timespan when the file was uploaded- that an external party compromised my account and likely uploaded "cryptocurrencies.zip" to my account.

![Date the file was uploaded](/assets/mega_compromise/session2.PNG)



<h2> How did it happen? </h2>

The most likely scenario: since the email I was using was seen in [HIBP](https://haveibeenpwned.com), attacker(s) got a hold of my password from a database dump. Of course, this should indicate to you that password reuse is *very bad* and that *you should never do it* but hey, this was a while ago and these days I use a password manager now with randomly generated passwords and multifactor authentication (MFA)!

With the password from the database dump, I can imagine the attacker utilized a combination of a [credential stuffing](https://www.owasp.org/index.php/Credential_stuffing) and [password spraying attack](https://www.triaxiomsecurity.com/2018/11/08/password-spraying-attack/), sort of a hail mary approach with leaked credentials from various sources to try every email in the database they've extracted with the associated password in the dump to see if access is granted.

So I can imagine that once the attacker was successful with the email and password pair, they uploaded a file in the hopes that the victim will open it up. 


The whole ordeal gave me a brief spook but there's nothing to worry about, to be honest. I don't think the files I had on there were accessed as it feels like the compromise was automated. 

Moral of the story? Use a password manager and multifactor authentication when possible!

If you'd like some recommendations for password managers (I'd go with paid ones since free services might not actually be free, where *you* are the product) check out this [PCMag link](https://www.pcmag.com/roundup/300318/the-best-password-managers)! Granted, password managers [have their own issues/vulnerabilities](https://devd.me/papers/pwdmgr-usenix14.pdf) (PDF) but the costs outweigh the benefits- using strong passwords is the first step towards better online security.
