---
layout: post
title: "Facebook: A Tale of Alternate Text"
date: 2017-03-29 12:53
---

Several moons ago, I would occasionally see my Facebook feed with broken images (i.e., not loading with empty boxes in place of where the images would go) like this:



![Example image](https://scontent.fybz1-1.fna.fbcdn.net/v/t39.2229-6/11057177_10153197137149210_361761597_n.jpg?oh=7a6e459126b526fac9081791ebd4cf5d&oe=59682F76)


Source: https://www.facebook.com/help/community/question/?id=10153197138404210

However, the "owner's photo" in place of the empty image wasn't what I saw. Instead, it was something to the tune of, "Image may contain: one person, standing". Odd, indeed.

Curious, I did some digging into what was displaying this text, so I pulled up the HTML inspector (F12 in Firefox) and searched for the string "may contain" and found what I was looking for:



![Neat, but a bit peculiar](/assets/alt%20text.png)

*I used a random image with a lot of detail/subjects shared by a friend on my Facebook feed earlier*

See how FB got all of it right, even though it says "may contain"? Neat, but a bit odd!

Generically, the HTML is in this format:

`<img class="*FB IMAGE TYPE*" src="*FB IMAGE LINK*" alt="Image may contain: *WHAT FB THINKS THE IMAGE CONTAINS*" height="*HEIGHT*" width="*WIDTH*">`


So why are they doing this?
I could imagine this kind of image analysis isn't being used for nefarious reasons (I do have my doubts, however) as it plainly shows up in the HTML. Indeed, I did further sleuthing and found that this 'feature' [is being used in tandem with text-to-speech for users with difficulties looking at images](https://www.theguardian.com/technology/shortcuts/2016/apr/10/image-may-contain-cat-now-facebook-can-talk-you-through-your-photos "The future is here").

The article states that: 
> "Facebook claims that it can identify at least one concept with 80% accuracy in more than half the photos it analyses."

No mention of what machine learning techniques are used, but I am sure whatever algorithms are employed, they have to be *scalable and very efficient*, due to the sheer amount of data that is processed by Facebook on a daily basis.

With this in mind, be weary of what you send to any social network or site as securing your privacy or information may not be a top priority for these parties. Doesn't it sound a bit scary that some of us send so much information to these sites, operating under the assumption that our personal information or memories would not be sold or traded to other parties? All under a subsection somewhere in the terms and conditions? Personally, I would not use Facebook at all if not for over three quarters of my friends and contacts using it.

I had a discussion with some coworkers during a lunch break about Google having access to so much data, and how our data could be for nefarious reasons. "The stakeholders wouldn't allow it", one colleague would mention. I told them, a company could do whatever it wants, be it against the wish of their stakeholders. They could do things covertly and their stakeholders would be unaware, continuing on with their lives and not think otherwise that such a big company would do such things.

What do you think? Is the trade-off of security for convenience worth it? Should we trust such companies with so much information, or would it be better to decentralize our information sharing? Or would it be better to restrict as much information sharing as we can, or even go as far as not share any information at all?


