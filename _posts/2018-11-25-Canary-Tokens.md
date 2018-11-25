---
layout: post
title: "Tracking with Canary Tokens, Bugs, and PDFs"
date: 2018-11-25 16:15
---

Yesterday night while going through [cybersecurity Black Friday deals](https://pastebin.com/aLBfQT6H) I stumbled upon something really interesting called [Canary Tokens](https://canarytokens.org/generate) by Thinkst. 
According to the deal on the Pastebin paste, you can get "Unlimited canary tokens free till heat death of Universe". I'm a bit fan of having free things until the *heat death of the universe* so I decided to check it out.

When you access the Canary token generator, you are greeted with a fairly non-descript page to generate a token.
![Canary token generator](/assets/canary1.PNG)

"What is a Canary token", you may ask? [This link explains it fairly well](https://blog.thinkst.com/p/canarytokensorg-quick-free-detection.html) but essentially a Canary token
is like a piece of code placed inside of a file or document that communicates back to the creator of the token when the file/document is accessed, kind of like a honeypot.

I first tried the token out by creating a web bug or web beacon. The form asks for an email address to notify when the bug is accessed or viewed- usually it's a 1x1 pixel that is 
usually unnoticeable to a regular user, but contains a bit of code that will reach out to a domain associated with the associated Canary and its token.

In the case of the web bug token I created, the image is actually a full-sized image and when someone accesses a page with the image, I'd get an email alert with some information
of the user that accessed the page. Think of it like an IDS that warns you of an event being triggered or a silent alarm being tripped.

![Canary token web bug](/assets/canary2.png)

The same thing applies to the case of a PDF document- an unscrupulous user or someone snooping around for information like credentials or private financial data might 
stumble upon a seemingly content-rich in a folder on someone's computer. It's located in the "documents" folder and doesn't have any indication it'd be bugged. In this case 
we have something called a "honeypot document" or "honeydoc" that entices the user into accessing the delicious contents inside. 

![Canary token PDF doc](/assets/canary4.png)

The interesting thing is that the document by default is blank. I'm sure it's possible to edit the document with content to make it more convincing, but I didn't try to edit with 
a PDF editor, however, I did try to edit the document using Word and then exported it to a PDF- whatever the conversion did, the token no longer was in the document as I didn't 
get any email alerts regarding document access.

It should also be mentioned that the PDF honeydoc should be opened in Adobe Reader- I tried to open it with my PDF reader of choice, Sumatra PDF, but no email alerts were sent.
I then went to download Adobe Reader and tried to open the PDF... and received a warning asking the following:

![Canary token PDF doc](/assets/canary5.png)

In the Thinkst blog article I linked above, they mention that "the PDF document will trigger a notification by Adobe Reader regardless of whether the user allows network communications!"
and it was true- I clicked on "block" and still got an email alert about it. Very nifty!

The blog article also describes other uses for the tokens.

In the words of Bill Buchanan of *Art Attack*- ***try it yaself!***
