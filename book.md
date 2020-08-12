# The Generic Guide for Software Developers

## Preface 

### We, the people

Everyone is biased, I am and so are you. The bias in the role of a software engineer is stirred by a plenty of factors, for every individual: 

* The initial motive in life that eventually brought you here,
* the degree of formal education of this topic,
* your previous fields of engineering and products,
* your colleagues, [bosses](https://getlighthouse.com/blog/people-leave-managers-not-companies/), clients.

Ever discussed the absurdly prominent example of _tabs vs. spaces_? Given the [financial correlation](https://stackoverflow.blog/2017/06/15/developers-use-spaces-make-money-use-tabs/), you better do &ndash; yet it is just one of the sheer amount of things that ask for a common ground among you and the people around you.

Looking at the list above, you and me probably need to have subjects of discussions settled. Let me draw a few contexts first, because this turns out to make a significant difference in certain aspects. The most important one: On what basis do we justify a guide like this one?

When we are in the **economic** context, this is about selling products and services, scalability and reducing costs, and dealing with risks.

If you have been part of some **academic** institution, you know that software development is different: It serves your research for scientific significance, rendering publications and &ndash; hopefully &ndash; universally useful insights.

The ultimate fun factor finally: **personal** matters. The website, the game, the [demo](https://www.shadertoy.com/events), the [hack](http://labs.domipheus.com/blog/raspberry-pi-4-pci-express-it-actually-works-usb-sata-gpu/), the [operating](https://en.wikipedia.org/wiki/History_of_Linux#The_creation_of_Linux) [system](https://en.wikipedia.org/wiki/TempleOS), and [countless](https://www.theverge.com/tldr/2019/6/30/19102430/amazon-engineer-ai-powered-catflap-prey-ben-hamm) [other](https://bellard.org/jslinux/) [things](https://renderdoc.org/renderdoc-history.html). (There is no affiliation to the items here, just a collection of awesome things people demonstrate that I had in memory.) Enjoy your curiosity, preferences, desires at will.

This guide is about _economical_ software engineering for the individual developer, as portable as possible across domains and not bound to particular technology &ndash; unless stated otherwise. This guide will justify all its recommendations over the following factors:

* Saving time and costs while also
* managing risks.

This guide is designed for everyone inside the sphere of hands-on software engineering, regardless of the years of experience and performance of different roles. _I'm a successful developer for over 20 years, why yet another basic guide?_, if you agreed on the very first paragraph of the guide &ndash; the list of factors that form the individual &ndash;, while probably knowing most of the topics of this guide well and not missing a single aspect, you may re-evaluate the degree of feeling capable to plead your attitude and practices towards others.

Indeed, you may abort here if you are familiar with highly regulated software engineering, may it be by legal framework, or by throwing ISO auditor parties, or by [working at NASA](https://swehb.nasa.gov/). If so, there is a big chance of knowing all the aspects of this guide in all its bureaucratic depth.

I am not sure how many people will at least go once through a burning home in life, most of us hopefully never will. But why so little? Fire prevention. Smoke detectors, hardly inflammable materials, insulation, extinguishers. The overall risk of fire is unlikely if you follow best-practices, like not smoking a cigarette while lying in bed, falling asleep. Anyway, there may be factors you cannot fully account on yourself alone. So if your home catches fire, do you have a plan? What will you do, where will you try to escape?

_So, you are a prepper or something? Waiting for the zombie apocalypse to come, smiling 'told you so' at people?_ While I cannot deny the sweetness of _told you so_, no, I am not. But I'll probably had the scenario in mind and voted against buying realty for digging a hole somewhere.

This a about economical moves and calculating risks to the degree a software developer should be able to reason about on a daily basis, and here comes the checklist. After sampling from fellow students, coworkers, managers, team leads and online-only collaborators in open source development for more than ten years, I noticed a very big discrepancy in what I expected from people in either direction, given that somebody claims to already/only have X years experience doing just &ndash; or tons of other things alongside of Y. This concerns the following questions:

* What is the person's very individual capability of organizing the own time of work day, week, sprint, milestone, ...?
* What is the person's ability to express, visualize, defend and preserve ideas?
* What is the person's degree of basic software engineering knowledge &ndash; or what is still present, years after education/university?
* How is somebody approaching a new problem?
* What is the person's ability to step back, take a breathe and re-evaluate some idea? With and without external impulses?
* How is somebody keeping up to date with technological advancements and legal requirements? If any, what is the range of view beyond the own zone of comfort, and specialization?
* What is the attitude towards doing mistakes? How is quality being evaluated when not being asked for protocols?

When not aligned or guided properly, a team of software engineers may easily face misunderstandings, conflicts, delays, frustration. This, in turn, translates straight into time-to-market, or worse, disaster recovery and bad press. Unless it is _Cyberpunk 2077_, then delay is probably good.

### How to read, what to read

Let us write some software. Let us be done in time. Let us save resources, economically and &ndash; where possible &ndash; ecologically. Let us just not be guys that appear in press for failing miserably over beginner's mistakes. And here, I want to make sure we just get there well &ndash; on one or another way.

I have assembled a collection of technical topics and organizational guidelines, I will go into details or put a link to a useful and comprehensive reference. There will be inline examples or examples of implementations or products. **None** of these are meant to be as an advertisement in a sense that I get any affiliation link money or alike, they are a product of hands-on experience, knowledge, neutral (i. e. using Google) research and browsing news aggregators. Over time, of course, they may also lapse and be superseded by other standards, products, practices.

You may argue of missing some in-depth or more comprehensive information on very closely related fields here, such as security, networks, team leadership. This is true and I strongly recommend to have designated literature on these topics for both broader and deeper insights, as some simply go beyond this scope. Again, literature choice is based purely on personal recommendation.

You may find hints hilariously obvious, maybe even offending to read. That is good then, nonetheless for the reasons mentioned, you better carefully transfer such assumptions onto others and both the absolute beginners as well as longstanding software developers sometimes have a need for completing their knowledge.

## The Globals and Universals

_Schei� Encoding_, some guy at my undergrad university had a shirt writing that. It translates to _working with encoding is mildly frustrating_. No objection, if you have every tried making software work on _Windows 9x_ while trying to put people all around the globe together &ndash; in front of your software.

But then, what is beyond the mundane problems of language, time and location? Laws of thermodynamics and system equilibrium, and the human mind, of course.

### Laws, Principles and Models

In the United States, you may be particularly familiar with the concept of [post turtles](https://en.wikipedia.org/wiki/Post_turtle). And more than identifying one &ndash; that is easy &ndash; it may help you anticipating the next one, given that we found a name or symbol for such cases, and that we start to evaluate against them. And so there is a plenty of concepts, laws, principles and models out there, so I picked a couple of them because I consider them fundamental for software engineering, both for generally thinking about solutions, as well as for implementing them:

* [Murphy's Law](https://en.wikipedia.org/wiki/Murphy%27s_law) &ndash; The most prominent one, yet I probably found most of the managers working away from domains of potentially deadly problems keeping it low to a worrisome degree. _Anything that can go wrong, will go wrong._ Modifications include: _... to the worst extent/time possible._ or _... in the worst chain of combinations._ If you see something that is about to go wrong at some time, it will, and earlier than pessimistically estimated. Publicly raging against _4chan_ is like sending an invitation to Murphy, for example.
* _At scale, there is no edge case_ &ndash; A slightly more neutral form of Murphy. If you observed that edge case X happens about every few Y, scale up Y, and read the law of Murphy again. The economist wants to have costs and likelihoods here, so really spend some time modeling your nasty edge case's impact.
* [Gall's law](https://en.wikipedia.org/wiki/John_Gall_%28author%29%23Gall%27s_law) &amp; [KISS](https://en.wikipedia.org/wiki/KISS_principle) &ndash; In a way to put it short: Do not enter the stage of over-engineering, i. e. designing for features you are not sure about to ever see their requirement at the horizon when it comes to your task. 
* [Hofstadter's Law](https://en.wikipedia.org/wiki/Hofstadter%27s_law) &ndash; Hey, somebody made a cool and recursive law out of estimation meetings. The more important point I found is that you think twice to estimate more closely to what looks feasible, not by what appeals to the guys with money. There lies no profit in underestimation, but everyone is happy when you actually over-perform the estimations.
* [Hanlon's razor](https://en.wikipedia.org/wiki/Hanlon%27s_razor) as an instance of [Occam's razor](https://en.wikipedia.org/wiki/Occam%27s_razor) &ndash; While this is nowhere limited to the domain of software engineering, it frequently helped soothing the own nerves: Nobody probably ever wrote a _historically grown_ dump of code and processes from hell to deliberately cause anger to you. Instead, _they_ likely did not knew better, did not care so much, did not understand somewhere in between (Hanlon) or just made a reasonable economic decision not to touch a running mess of a system for the need of extension (Occam). Feeling angry about what you face is OK, but please refrain from doing so over what is likely the wrong reason.
* _Not invented here (NIH)_ &ndash; In any remotely mature software development environment, there is probably at least one actively maintained, well-tested, sufficiently documented, StackOverflow'd software product for every common problem since the day ALGOL60 went to see the light. The same holds for best-practices of human and/or technological processes. Google is one of your friends, and your advocate when an NIH-susceptible guy fantasizes on inventing unseen security measurements.
* [Sutton's law](https://en.wikipedia.org/wiki/Sutton%27s_law) &ndash; More on debugging at another time. Yet it helps well in a certain kind of situation: There is a bug or failure, and you are strongly biased before doing the obvious tests first as there is some assumption regarding the cause in your mind already. In the case when it is not confirmed, think of this law instead of digging around close to your analysis, chances are good to have something more obvious then instead.
* _All input is evil_ &ndash; No exception. Everywhere. Always assume that beyond the border of your software unit, every input is about stealing your computational resources or taking you down, about setting up intrusion vectors, about circumventing access rules. More on security later, but this is security rule #1 to always have in mind.
