---
layout: post
title: A 100-year-old website
date: 2026-04-10
categories: inkhaven
image: /assets/metropolis.jpg
---
Fifteen years ago, a [conference talk](https://web.archive.org/web/20130818232029mp_/http://aneventapart.com/event/austin-2013) planted an idea in my brain that I haven't been able to uproot since. What things would we do differently if one of the success criteria of a web project was that it should be readable 100 years from now? It's strange that this question feels as radical as it does. We can easily read 100-year-old books, watch 100-year-old movies, and listen to 100-year-old songs. Isn't it interesting that the idea of people browsing 100-year-old websites in 2126 seems so wild in comparison?

The web is already designed to be radically backwards compatible. You can visit [a website that was last edited in the 1900s](https://wayback.archive-it.org/763/19970220034057/http://www.umn.edu/tc/) and interact with it basically the same way you would have back then. Even wilder, you can start up [a computer that was built in the 1900s](https://en.wikipedia.org/wiki/IMac_G3), insert a Netscape Navigator disk image of appropriate vintage, and point it at a contemporary website, and watch it mostly kind of work. Countless engineer-hours have been dedicated to maintain these unsung miracles. So what's the problem? Can't we just trust our collectively galaxy-brained engineers and archivists to find a way to preserve as much of this moment in amber as we can, so that future generations of historians can have all the background context they need to debate the literary merits of Homestuck?

When put in those terms, my problem sounds like more of a personal problem. I bet the likes of Substack and YouTube will be fully archived, indexed, and preserved in their original formats for historians willing to brave the brainrot. If I *only* cared about being legible to gen-delta historians, I'd just stick to the major platforms and stop expending mental energy on this ridiculous problem.

But I *also* bet we can do better. I've spent an entire career understanding how computers work from resistors to css. Shouldn't I be able to use this hard-won knowledge to figure out how to construct something all my own that might [stand the test of time](https://en.wikipedia.org/wiki/Ozymandias)? Furthermore, shouldn't I share the results of my quixotic quest so that people have a chance to collectively improve on my half-baked ideas?

So here they are. By far my biggest self-imposed restriction is: all of my artistic work to date is entirely client-side. That means that there is no database, and therefore no persistent storage across computers. This sounds like a huge limitation, and it is! But you can do a lot more than you might expect without an internet database. For example, you can do everything that a computer could do in 1995, but seamlessly accessible from any device anywhere, as long as it has a web browser. You can use local storage to let people save their place and preferences, despite the lack of a central server.

If your work is entirely client-side, that then means you can distribute it as bare files. You don't have to figure out how to bundle an executable, restart a server when it hangs, or figure out how to get a server to page you when it hangs. You can just spin up an FTP server, or a modern equivalent with a nicer UI — I currently use GitHub Pages — and put the files there, then point a URL at that bare directory. For local testing, you can spin up a minimal web server pointed at the directory with `python3 -m http.server` and test on that. 

I believe the tech stack most likely to work in 100 years is the smallest possible tech stack. For simple projects, I tend to stick with vanilla JavaScript or TypeScript, which are far nicer to work in than they were just five years ago. [Here's an example.](https://github.com/jessechen/trefall) For more complex projects, I like the balance of simplicity, convenience, and portability that a Svelte app compiled down to a static site offers. [Here's an example of that](https://github.com/jessechen/subpar/tree/trunk/src/routes).

One outcome of this process I can proudly point to now is [this art project](https://github.com/jessechen/polypile). It has now been publicly available and functional for eight years. In that entire time, I have spent zero (0) hours of maintenance on it. I've spent enough time around tech art spaces and their graveyards of dead project links to appreciate just how rare this actually is.

I do have to admit that, even with all of that accounted for, 100 years is probably not realistic. Hosting providers will go out of business, domain renewals cost money, and there's a new norm around automatically deactivating your accounts when you die. So I mentally target 50 years. Far enough in the future that I expect to be dead, but for a short enough time that my infrastructure providers might not also have died. And I willingly choose to relinquish my agency, and trust in the archivists to handle the next 50 years after that.

To whom it may concern in 2076, I hope this ~~email~~ blog post finds you well...
