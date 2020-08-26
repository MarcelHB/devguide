# The Generic Guide for Software Developers

This guide is subject to the [Creative Commons License v4.0 BY, unported](https://creativecommons.org/licenses/by/4.0/).

## Preface 

### We, the people

Everyone is biased, I am and so are you. The bias in the role of a software engineer is stirred by a plenty of factors, for every individual: 

* The initial motive in life that eventually brought you here,
* the degree of formal education of this topic,
* your previous fields of engineering and products,
* your colleagues, [bosses](https://getlighthouse.com/blog/people-leave-managers-not-companies/), clients.

Ever discussed the absurdly prominent example of _tabs vs. spaces_? Given the [financial correlation](https://stackoverflow.blog/2017/06/15/developers-use-spaces-make-money-use-tabs/), you better do &ndash; yet it is just one of the sheer amount of things that ask for a common ground among you and the people around you.

Looking at the list above, you and me probably need to have subjects of discussion settled, now or later. Let me draw a few contexts first, because this turns out to make a significant difference in certain aspects. The most important one: On what basis do we justify a guide like this one?

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

I expect you to know something about software development, hands-on. This is not some guide for replacing some fundamental education, there is [literature](https://bigmachine.io/products/the-imposters-handbook/) for that. This for filling all the dirty little stuff you may have ignored so far, you may not be aware of, and that is mostly taught by experience and failure.

I have assembled a collection of technical topics and organizational guidelines, I will go into details or put a link to a useful and comprehensive reference. There will be inline examples or examples of implementations or products. **None** of these are meant to be as an advertisement in a sense that I get any affiliation link money or alike, they are a product of hands-on experience, knowledge, neutral (i. e. using Google) research and browsing news aggregators. Over time, of course, they may also lapse and be superseded by other standards, products, practices.

You may argue of missing some in-depth or more comprehensive information on very closely related fields here, such as security, networks, team leadership. This is true and I strongly recommend to have designated literature on these topics for both broader and deeper insights, as some simply go beyond this scope. Again, literature choice is based purely on personal recommendation.

You may find hints hilariously obvious, maybe even offending to read. That is good then, nonetheless for the reasons mentioned, you better carefully transfer such assumptions onto others and both the absolute beginners as well as longstanding software developers sometimes have a need for completing their knowledge.

## The Globals and Universals

_Schei� Encoding_, some guy at my undergrad university had a shirt writing that. It translates to _working with encoding is mildly frustrating_. No objection, if you have every tried making software work on _Windows 9x_ while trying to put people all around the globe together &ndash; in front of your software.

But then, what is beyond the mundane problems of language, time and location? Laws of thermodynamics, system equilibrium, information content, and the human mind, of course.

### Laws, Principles and Models

In the United States, you may be particularly familiar with the concept of [post turtles](https://en.wikipedia.org/wiki/Post_turtle). And more than identifying one &ndash; that is easy &ndash; it may help you anticipating the next one, given that we found a name or symbol for such cases, and that we start to evaluate against them. And so there is a plenty of concepts, laws, principles and models out there, so I picked a couple of them because I consider them fundamental for software engineering, both for generally thinking about solutions, as well as for implementing them:

* [Murphy's Law](https://en.wikipedia.org/wiki/Murphy%27s_law) &ndash; The most prominent one, yet I probably found most of the managers working away from domains of potentially deadly problems keeping it low to a worrisome degree. _Anything that can go wrong, will go wrong._ Modifications include: _... to the worst extent/time possible._ or _... in the worst chain of combinations._ If you see something that is about to go wrong at some time, it will, and earlier than pessimistically estimated. Leaving a password for user `root` set to `root` is an invitation to Murphy, for example.
* _At scale, there is no edge case_ &ndash; A slightly more neutral form of Murphy. If you observed that edge case X happens about every few Y, scale up Y, and read the law of Murphy again. The economist wants to have costs and likelihoods here, so really spend some time modeling your nasty edge case's impact.
* [Gall's law](https://en.wikipedia.org/wiki/John_Gall_%28author%29%23Gall%27s_law) &amp; [KISS](https://en.wikipedia.org/wiki/KISS_principle) &ndash; In a way to put it short: Do not enter the stage of over-engineering, i. e. designing for features you are not sure about to ever see their requirement at the horizon when it comes to your task. 
* [Hofstadter's Law](https://en.wikipedia.org/wiki/Hofstadter%27s_law) &ndash; Hey, somebody made a cool and recursive law out of estimation meetings. The more important point I found is that you think twice to estimate more closely to what looks feasible, not by what appeals to the guys with money. There lies no profit in underestimation, but everyone is happy when you actually over-perform the estimations.
* [Hanlon's razor](https://en.wikipedia.org/wiki/Hanlon%27s_razor) as an instance of [Occam's razor](https://en.wikipedia.org/wiki/Occam%27s_razor) &ndash; While this is nowhere limited to the domain of software engineering, it frequently helped soothing the own nerves: Nobody probably ever wrote a _historically grown_ dump of code and processes from hell to deliberately cause anger to you. Instead, _they_ likely did not knew better, did not care so much, did not understand somewhere in between (Hanlon) or just made a reasonable economic decision not to touch a running mess of a system for the need of extension (Occam). Feeling angry about what you face is OK, but please refrain from doing so over what is likely the wrong reason.
* _Not invented here (NIH)_ &ndash; In any remotely mature software development environment, there is probably at least one actively maintained, well-tested, sufficiently documented, StackOverflow'd software product for every common problem since the day ALGOL60 went to see the light. The same holds for best-practices of human and/or technological processes. Google is one of your friends, and your advocate when an NIH-susceptible guy fantasizes on inventing unseen security measurements.
* [Sutton's law](https://en.wikipedia.org/wiki/Sutton%27s_law), also close to Occam &ndash; More on debugging and error handling at another time. Yet it helps well in a certain kind of situation: There is a bug or failure, and you are strongly biased before doing the obvious tests first as there is some assumption regarding the cause in your mind already. In the case when it is not confirmed, think of this law instead of digging around close to your first point of entry, chances are good to have something more obvious then instead.
* _Everyone makes mistakes_ &ndash; Somebody rejecting the claim is to be considered suspicious. We all make them, some of them go unnoticed and some of them cost lives. The reasons include wrong assumptions, missing knowledge, misunderstandings, the wrong calculation of risk and a lack of focus. And similar to fire, collapsing bridges and crashing planes, we need to learn and establish mechanisms to catch them as broadly and as early as possible. In the European Union, every country needs to maintain an agency to perform investigations in accidents regarding naval vessels, trains and air planes, with their reports mostly being published online (examples for [Germany](https://www.eisenbahn-unfalluntersuchung.de/SiteGlobals/Forms/Suche/Untersuchungsberichtesuche/Untersuchungsberichtesuche_Formular.html), [UK](https://www.gov.uk/raib-reports?report_type%5B%5D=investigation-report)). Read some of such reports by example, and see how and why mistakes are presumed to have been made &ndash; including human interaction and technical negligence &ndash;, and what measurements were ignored or newly established as a consequence, with [shisa kanko](shisa kanko) being an impressive yet a very simple one.
* _All input is evil_ &ndash; No exception. Everywhere. Always assume that beyond the border of your software unit, every input is about stealing your computational resources or taking you down, about setting up intrusion vectors, about circumventing access rules. More on security later, but this is security rule #1 to always have in mind.

With some special relevance for this guide: _Premature optimization is the root of all evil_, by _Donald Knuth_ I suppose. I do not disagree. Remember _Adobe Flash Player_? It had or has [tons and tons](https://www.cvedetails.com/vulnerability-list/vendor_id-53/product_id-6761/Adobe-Flash-Player.html) of severe bugs in it. Unfortunately, I do not find the article any more but I told that Macromedia, later Adobe, tried to build up the Flash Player over an insane amount of techniques to save space, like leaving no bit unused. Assuming some truth in these claims, if you think of the fun programming with bit operations at a larger scale, nobody will make a face of surprise. Yet, it is even way easier to screw up some basics. If you think something will be your pain the back forever, it probably will &ndash; Murphy. Think of a distinction between optimization, like squeezing numbers over advanced calculations and strategies, and trying not to openly run into a knife by looking ahead for a bit.

### Time &amp; Space

Let us start with time, since we never have enough of it and we cannot go back in that:

* There is the [Coordinated Universal Time](https://en.wikipedia.org/wiki/Coordinated_Universal_Time), or _UTC_ &ndash; for the love between France and the UK, it did not turn into _CUT_. UTC knows no summer time, or _daylight saving time_, and is not geographically relocatable. Time zones effectively help humans to establish a global agreement of what numbers belong to the morning, midday and evening. And in some jurisdictions, we are expected to change our perception about that abruptly twice a year. Thanks to timezones, everybody knows that 4am is some strange time somewhere between dusk and dawn, and most of the time, you probably want to go awake through it anyway.
* If you write down a time without any closely locatable time zone information (like `+0200`), do it in UTC &ndash; and nothing else, ever. If you don't, you will mess up once year over one hour of summer time reset, you will probably not remember if your computer installation was configured correctly at that time any maybe not even its actual location to guess, you will likely never be able to ever fix this later. This may have legal implications.
* Time zones may change over time for political reasons, as well as summer time may be introduced or not. Do not use geogrphical identifiers as a time zone identifier. Instead, an identifier like _Europe/Berlin_ will help your clock adjusting the display &ndash; the one for human reasoning &ndash; of time into _Central European Time_ and _Central European Summer Time_ by some calendar that is applicable to inhabitants of Berlin. On computer systems, this information is often managed by the operating system and is frequently updated for upcoming changes and historical fixes.
* If you have to record time with a time zone information, do not use the symbolical names (`CEST`) but only numerical displacements (`+0200` or `+02:00`). The abbreviations and names are not standardized and even ambiguous. Go identify _CST_.
* Time zones are not bound to full hours, Nepal uses `UTC+05:45`.
* When you encounter UNIX timestamps, they are always supposed to be relative in the amount of seconds since the beginning of 1970 at UTC, though I've seen a FAANG company to really mess this up in one of their subsystems. Never adjust them for time zone by convention. There may be negative values, for the same reasons we have years _B. C._.
* When you encounter UNIX timestamps, make sure sure you have more than 4 bytes of storage available to write them down. At some point in 2038, the number of seconds will not fit into the positive half of 4 bytes anymore. If you read this guide between 2020 and 2037 and face this problem, act! 2038 is close and maybe nobody else is going to rewrite your software any time soon.
* Remember that February sometimes has 29 days &ndash; I say that because I had to fix that unawareness once already. Be aware that this is [not always in a cycle of 4 years](https://en.wikipedia.org/wiki/February_29).
* Mind the [leap seconds](https://en.wikipedia.org/wiki/Leap_second#Insertion_of_leap_seconds). They are rare, but they disrupt your `0-59` assumption.
* Be aware that [some calendars](https://linux.die.net/man/3/localtime) refer to months numerically by `0-11`, not `1-12` and that some libraries may be built on top of this mechanism.
* Remember that some cultures have a different convention of the first day of a week, like Sunday vs. Monday.
* The last week of the year mostly is shared by two different years.
* Do not invent time formats, follow [ISO 8601 principles](https://en.wikipedia.org/wiki/ISO_8601#General_principles).
* Time problems have been solved mostly since forever, heh, that's the good point. The more challenging one is that [some environments](https://docs.oracle.com/javase/8/docs/api/java/time/package-summary.html) use plenty of types for precision, relation, time zone affinity and backward compatibility. Familiarize yourself with what you need before picking `Date`, just because date.
* As a side note, setting the system's time-zone explicitly may be a [good idea anyway](https://blog.packagecloud.io/eng/2017/02/21/set-environment-variable-save-thousands-of-system-calls/).

Let us head over to the issue of textual representations:

* Know what [Unicode](https://en.wikipedia.org/wiki/Unicode) is made for. Image Unicode being _the_ atlas of all the symbols, letters, emojis and runes of all actually used scripts of the world, even some archaeological ones, like some old nordic rune: ᛈ. This rune is located under position (decimal) 5832. At the time of writing, Unicode was standardized at version 13 in early 2020, comprising more than 143,000 symbols, including new emojis like 🩱 (if you see � instead, I tried to show you a _one-piece swimsuit_, to be found at no. 129649). On top, it is not only symbols: Unicode lists [control entities](https://en.wikipedia.org/wiki/Unicode_control_characters) as well that are supposed to aid in various cultural aspects.
* Unicode is _not_ an encoding. [UTF-8](https://en.wikipedia.org/wiki/UTF-8#Description) is one example of an encoding to implement Unicode, and everything of it at once. Looking at the number of items in Unicode, you require at least three bytes per symbol to address anything from the atlas. Given that, historically, computer systems had less space than today and were centered on Latin languages, of which the English alphabet is composed of less than 128 symbols &ndash; including uppercase letters, downcase letters, digits, symbols &ndash; one byte was sufficient to even have some control bytes in the lower 128 items (see [ASCII](https://en.wikipedia.org/wiki/ASCII)), and to have some other Latin symbols in the upper 128 slots. Not all at once, but enough to put some things together, like [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1) for German and Roman scripts, or [ISO-8859-5](https://en.wikipedia.org/wiki/ISO/IEC_8859-5) for Cyrillic scripts. Depending on the computer's settings, it will then display `Ø` or `и` for byte `0xD8`. For a North-American computer system, one byte per symbol is usually enough, but the user may occasionally visit a [CJK](https://en.wikipedia.org/wiki/CJK_characters) website. In order not to break compatibility to ASCII and to have some space saved, UTF-8 makes use of bit patterns per byte that allows scaling up the use of one to four bytes per symbol, depending on what is in use while also preventing ambiguity, that is why it needs four bytes for modern emojis, not just three.
* There is also [UTF-16](https://de.wikipedia.org/wiki/UTF-16), requiring two to four bytes. It requires less magic to bit patterns but also requires more space. _Be careful_, there may be a byte-order marker of 2 bytes in use at the beginning of the text. It tells you which one of the two bytes is supposed to be the _lower_ one. Microsoft made Windows use UTF-16 for a very long time, requiring developers to constantly convert on touch points with UTF-8 data.
* For [UTF-32](https://de.wikipedia.org/wiki/UTF-32), there are no reserved bits, since every element is using exactly four bytes, thus wasting a lot of space for `0x00`s in Latin languages, but simplifying all related string operations.
* Make use of UTF-8 unless there is a very specific requirement.
* Do not step back to codepage-based encodings, i. e. needing the correct interpretation context as mentioned above, unless there are even more constraints to work with.
* Make sure to have all your tools configured correctly.
* Make sure you know your technology stack well to know how strings are handled internally, of what kind of string types you actively need to [choose from](https://de.cppreference.com/w/cpp/string/basic_string). The wrong call of e.g. a _split_-method, or an index based access, will tear apart your valid bytes or will return the wrong element, usually causing severe trouble.
* Know when to ask for bytes of a string, and when for characters (or _code-points_). Know what types there are available for bytes, individual characters and strings.
* Know what operations may depend on the platform they are executed on. Influencing factors include [operating system environment variables](https://www.gnu.org/software/gettext/manual/html_node/Locale-Environment-Variables.html) or [runtime configuration](https://www.oracle.com/technical-resources/articles/javase/locale.html).
* Depending on the culture you need to serve, obey that some languages write right-to-left (Semitic languages), or top-down (Mongolian) and may ask for a whole set of further considerations.
* Some widely available library to spare yourself from ever converting bytes on your own is [libiconv](http://www.gnu.org/software/libiconv/). Higher level environments surely ship wrapper libraries or other utilities without further setup.

### Primitive types

Primitive types usually refer to what can be used straight by the processor, without going through runtime indirections first, such as _run-time type information_ (RTTI) or memory offsetting. A language may expose them as such &ndash; or at least pretend to so &ndash; (C, Java, Rust, Go), it may need some special workaround (Javascript _asm.js_ and _typed arrays_) or restricts the user to its boxing mechanisms (Ruby).

* There are integer types, their bit patterns reflect the binary representation of some integer. They may be considered _signed_ or _unsigned_, sacrificing one bit in the first case. Depending on their size, they are referred to as 
    * _bytes_ or _chars_ (1 byte), 
    * _shorts_ or _words_ (2 bytes), 
    * _ints_ or _double-words_ (4 bytes) and
    * _longs_ or _quad-words_ (8 bytes).
* If the language requires you to think about that, do so and pick what is available and appropriate, for every single occurrence. Do you need a sign? Do you need 8 byte integers when some other restriction renders everything beyond one byte into a waste of space? 
* If primitive types are defined to have some soft constraints, such as _X is at least 4 bytes wide, depending on the target platform_, do stick to the fixed-sizes alternatives when available unless there is a very good reason not to do so (mostly: old compilers for very old platforms).
* For counters, use the largest integer unless there is really no need to do so.
* There may exist a _size_ type. It refers to an integer that with as many bytes as the target-platform uses for its memory addressing. On most modern desktop and server processors it is 64 bits (8 bytes), and some mobile and older processors its 32 bits. Size types are usually meant to be used in the context of contiguous memory span calculations.
* When it comes to non-integer numbers, [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754) is the de-facto standard on working with [real number approximations](https://en.wikipedia.org/wiki/Real_number). What? We are short of space and need a mechanism to somehow represent both the integer before the radix point, and the fractional part after. We cannot have large integers and an arbitrarily precise fraction at once, so smart people came up with a genius but also very unintuitive system that appears like magic. The most common references are _float_ or _single precision_ (4 byte) and _double precision_ (8 byte). You may also encounter _half precision_ (2 bytes) and _quadruple precision_ (16 bytes), but they are far less common and may not even be backed natively by the processor. So some things to know about floats:
    * Values are mostly approximations. If they do not appear as such in the first moment, increase the output precision, some printing defaults discard the tail of the fractional value.
    * They can represent much higher fraction-less integers than simple integers at the cost of losing some of the less significant positions.
    * When close to zero, there is even more magic involved.
    * There are reserved bit patterns, representing signed _infinity_ and _not a number_ (NaN).
    * There are different rounding modes, but stay away from messing with them unless you are a professional in numerical analysis.

  I really recommend to play around with an [IEEE 754 calculator](https://www.h-schmidt.net/FloatConverter/IEEE754.html) to just _get an idea_.
* When operating with values of different types, like floats and integers, or even integers of different size or signs, rules apply with respect to type extensions, precision and results. Look for _implicit conversion_ or _promotion_ rules for your language, see the non-trivial rule set by example for [C](https://en.cppreference.com/w/c/language/conversion) or [Java](https://docs.oracle.com/javase/specs/jls/se8/html/jls-5.html).
* If you have at least one user-controlled or user-influenced value in an arithmetic operation &ndash; and the nature of writing a software makes this quite the rule, not the exception &ndash;, let your alarm bells ring. There is a whole bunch of [security incident reports](http://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=Integer+Overflow) dedicated to this kind of problem, and also the blockchainists have been [repeatedly hit hard](https://blockchain-projects.readthedocs.io/overflow.html) by overly smart contracts, there is even a [good list](https://github.com/ethereum/solidity/issues/796#issuecomment-253578925) of vulnerable code to look for. Common arithmetic pitfalls include the following:
    * An addition or multiplication will overflow, possibly wrongly ending up in smaller value range, being accepted for the wrong reasons.
    * A subtraction will underflow, with two unsigned values yielding a larger one as a result.
    * A division by zero. Since this universally fails, you may have a problem when it did not or got swallowed unnoticedly because of improper exception handling.

  There are [different approaches](https://en.wikipedia.org/wiki/Integer_overflow#Detection) of avoidance and handling these cases across languages, make sure you know the appropriate one.
* If there is really a requirement to go beyond the value of range of the largest integers, you should look up _big number libraries_. They are often technically limited by the amount of memory available only, at the cost of doing more operations in software, not being primitives any more.
* Do not ever use floating point types for financial applications. Calculations on money regularly involve checking for thresholds, checking settlements. Looking at the details of IEEE 754 mentioned above, this is doomed to fail: Try to add the approximation of `0.1` to the approximation of `0.2`, end check whether it is equal to the hard-coded, or independently calculated, approximation of `0.3`. No, it may not, [try it out](http://weitz.de/ieee/). Two better ideas:
    * The preferred one: use decimal types. Most of the higher level languages come shipped with such a type, as well as databases do. They use calculations at the base of 10 at tolerant scales. As an instance of _big number library_, it may experience a drawback in performance, but that reduces the risk of somebody getting ripped off moneywise, and probably illegally.
    * The fallback solution, just that you have considered it: Calculate in milli-cents (or even more precise) using integers, and do what you did in middle school math to apply 15% VAT, or a 6% discount. [Integer division](https://en.wikipedia.org/wiki/Division_\(mathematics\)#Of_integers) is well defined and your friend, just mind the available space and obey the rules above.
* There are calculation rules that appear the same analytically, but [not when done in floating point](https://gcc.gnu.org/wiki/FloatingPointMath) arithmetic. Doing it either way will sacrifice precision or performance. In a video game, you will probably pick the performance style or auto-optimization, for precise calculations the other one.
* You must be aware that primitives are sometimes not ordered internally as they are supposed to be on a platform. When reading fixed-size values from certain file formats or network protocols, historical reasons lead to the order of bytes not matching the one of your platform, this the [endianess problem](https://en.wikipedia.org/wiki/Endianness). Most of the times, the host processor is subject to little endianness nowadays, with some exceptions being smaller or uncommon architectures.

### The O thing

In pre-COVID19 times, shaking hands was the etiquette in social gatherings. Now, let us think of some kind of party with the host having some kind of self-imposed shaking-hands policy. Now let us sum the number of hand-shakes of all participants individually, including the host:

* He shakes hands with only the very first guest arriving. No matter how many others will come, the total number will remain _constant_ at 1.
* He likes to spend more time with other activities that need more attention the more guests arrive, so after each handshake, he skips some people, and the number of skips doubles every time. The number of handshakes grows _logarithmically_ to the number of guests.
* He patiently waits at the entrance and leaves out no single guest. So the number of handshake grows _linearly_ to the number of guests.
* On the arrival of a new guest, he better walks through the whole location again and greets everyone, as his memory is bad and he did not notice who exactly entered the door. We calculate `1 + 2 + 3 + 4 + ...`. With `N` guests in total, [this sum](https://en.wikipedia.org/wiki/1_%2B_2_%2B_3_%2B_4_%2B_%E2%8B%AF) can be expressed as `N * (N + 1)` with factor `1/2`, a square of `N`. With this policy, in the end there will be a number _quadratically_ grown to the number of guests.
* Every guest has a seat at some table, and sometimes the guest gets up to a walk for buffet and returns later. For each change at the table configuration, the host starts to shake hands with people at the table from the beginning, and over the day, every possible combination of seats being taken occurs at least once. Phew. That is what an _exponential_ growth of hand-shakes, depending of the number of guests, looks like.

Now a plot twist: The party is more like a honey pot. The host set up the event to pick-pocket the guests. Now, the effectiveness of the plan improves over having more time to sneak around the guests, while the guests who feel unwelcome leave again soon. Saying hello to everyone as the host is the cheapest, non-speculative approach. The speculative approach is to hope for the guests to socialize so well to have everyone of them find another one to hang out with while trying to stay just at the half of required handshakes from the host's perspective. Make an A/B test out of that, maybe.

This is what the Os help you express, very shortly spoken. [Big-O or Landau notation](https://en.wikipedia.org/wiki/Big_O_notation) come up with some more handy things to know:

* Writing Os, usually constant offsets and factors are left out. They have a huge practical relevance but are not required for classifying the cost growing nature.
* In a sum of components that contribute to the cost, often only the dominating one presented, e. g. `O(N^2 + N)` is to be seen as `O(N^2)`.
* When there are more elements involved, like a problem referring to `N` guests arriving in `M` cars, they may co-dominate the cost and the O looks like `O(growth(M) * growth(N))` then.
* There is more than just _the_ O. O means: your problem grows not more expensively than what is described inside; but also Θ (the same), Ω (more or equally expensive), ω (definitely more expensive), o (definitely less expensive). Most of the time, we are happy with an O and something giving an idea, without the need for academic precision.  
But there are other relevant considerations that sometimes require more than just a single O.

Looking at our thievish party host, we change the pick-pocketing difficulty a bit: There is only one guest carrying a valuable thing. In the best case, the worst case, and the random case, how many guests does the thief need to _treat_ until finding what he is looking for?

* Best case: The first one is a hit,  
* Worst case: The last one of all the guests is a hit, so I takes `N` actions.
* Random case: By the [law of large numbers](https://en.wikipedia.org/wiki/Law_of_large_numbers) (I'm sure I'm getting this wrong, I never got statistics much), the expected success is around of doing half of the guests &ndash; and this depends on `N` again.

So finding our item is as expensive as `O(1)` in the best case, and `O(N)` for the average and worst. Practically, best cases can be seen as the base-line cost, something that you cannot beat this way. Average cost is the most common way to think of a problem, and worst-case cost is what calls Murphy if it does not match the average case.

A nice thing about logarithmic operations is that they can be considered constant-with-an-offset, virtually. If you plot the curve of some `log_b(x)`, it looks like a flat, hovering line at some point, and that is nice.

Quadratic operations often follow intuitive ideas on seemingly trivial tasks but also hit you hard after they are forgotten and eventually face some scale. Someone even made a [blog](https://accidentallyquadratic.tumblr.com/) of it collecting this kind of problem in the wild, and also providing better ideas sometimes.

Say you have a set of 100 items, and you want to check whether all of them appear in another list of 100 items. Your pseudo-oneliner for this task: `list.matchAll(i -> biggerList.contains(i))`. Euh, 100 x 100 = 10_000 match operations in the worst case. Scale the numbers, boom: quadratic growth cost for the average and worst case. What if we sort them first, and then go through line by line in parallel? Good idea: Sorting is `O(N * log(N))` using [MergeSort](https://de.wikipedia.org/wiki/Mergesort), but we need that twice, so plug in the numbers: `2 * (100 * 7)` (rounding up the result of `log_2`), that is 1400 match operations only! Now, take the sorted lists and go through them item by item to find a match: tiny little 200 operations more of them in the worst case.

Do not start to sort all the things all the time now, this may kill all gains again, instead, also think of the right data structures to use.

###  Data structures

Data structures are our air to breathe, but using the fanciest ones out there may do no good without some technical awareness. Some general rules for working with data:

* Asking for memory costs, not so much by the amount you ask for (that may simply fail), but the number of times. Depending on the level that your environment works on, you have a more or less deterministic view of what actually happens. In the lower levels, you ask your operating system for a memory allocation (`malloc`) of some size, and you better release that when no longer needed. Libraries or higher level runtimes hide that in various degrees, probably doing at least one large initial allocation, or by over-allocating a bit in advance. Requesting and releasing memory via the operation system usually invokes a _mode switch_ and a search for a sufficiently large memory chunk. Details vary by the actual allocator in use. In short: The less you need to do, the better.
* Copying memory costs. Copying data is not free, the processor needs to read one cell and write the bytes into another one, over and over again until all your bytes are copied. While you may not be aware of ongoing copying, working with certain data structures will do more than what is good, and you need to know these cases. When you hear of a new _zero-copy_ feature somewhere, be excited.
* If you can model a problem into working with a fixed amount of memory size easily, like streaming fixed-sized chunks of data, involving just one allocation &ndash; or maybe even none at all &ndash; do it like this. Application-side memory concerns have then reduced to `O(1)` overhead here, congratulations.
* Whenever you know the amount of bytes you need, or the number of your typed items, make the data structure initialize with that information (_capacity_). Chances are good to avoid a huge overhead footprint while using.
* Never let a user value go unchecked into the amount of items or bytes you need. In the easy case, reject anything beyond some limit, or consider a remodeling of the problem into some streaming pattern (continue reading to the later sections). Otherwise somebody will happily borrow some gigabytes from you.
* Try to think about some statistics, or gather them at some later point in use:
    * Quantity: How many items do I have to face for my case?

      Data that is bound by some internal frame will probably not justify the same attention as user inputs that may be arbitrarily many or large.
    * Access: Is the structure built up once, and then just being read? Is it constantly changing, or maybe just a few times?

      A read-only structure allows some optimizations, an ever-changing one requires considerations.
    * Position: Do we talk about use on a _hot path_?

      Does the pressure justify sacrificing convenience over performance? A dynamic, key-based lookup is nice and flexible but a static, index-based one saves more time, and hard-wired accesses even more.
* [Principle of locality](https://en.wikipedia.org/wiki/Locality_of_reference): If you need data together and fast, make it neighbours. This holds true for both a single computer as well as network architectures. The more related data fits into the different layers of a CPU (core) cache at once, the less cache-misses occur on subsequent uses, reducing the overall wait time for data to be loaded from main memory. It may also reduce the risk for intra-process paging towards a comparably slow hard disk. Thinking of an unoptimized, ordinary network, the constant need to ask for data from _far away_ involves round trip times of milliseconds and bandwidths that are lower than what your disk controller offers.
  
These are fundamentals when thinking of data structures and computer memory for most of the known data structures being an instance of either one, or allowing to be built on top of both of them, depending on the constraints:

* _Contiguous memory_: One item is supposed to be located right after the previous one, physically. There may be a disinction between static arrays, the ones that have a fixed size at compile time, and dynamic arrays (also _vectors_) that can shrink and grow. Actually, this may not be case: If the subsequent memory is reserved already, moving the memory is required first, so requesting a new memory location and moving the items. While its read and write access is constant, growing size modifications should be kept low or made upfront. Best suits: index based read and write accesses on largely stable sizes. Consider a deletion of items inbetween as unsetting of items, as it may otherwise lead to more expensive contraction operations.
* _Lists_: For every item, there is an address attached stating where to find the next item, or none when being the last one. Memory locations are scattered, and the whole struct requires additional memory _per item_. The good thing: a list never needs to be moved as a whole since we can just break it up and change a successor's address. Other than that, most other operations are `O(n)` at worst case since an operation around some index `i` needs `i` jumps around the memory (the last one is cached sometimes) to get there first. Best suits: A need for insertion and deletion operations at arbitrary positions. If you can model a use case using a dynamic array, always follow that approach instead.

So always know what types or classes of your language represent the following data structures (spare yourself from searching them in C, there you are on your own):

* _Stack_: How to push, how to pop items from the top.
* _Unordered Map_: Also _hash_ or _hash map_. How to associate keys to values under a constant lookup costs. Can a deterministic iteration order be achived anyway?
* _Ordered Map_: How to associate keys to values under stable insertion costs.
* _Set_: How to make sure to have a collection of unique items. When not available, consider a map while ignoring the values. Is there a way to have a multi-set?
* _First-in-first-out queue_: How to enqueue, how to dequeue items.
* _Custom queue_: How to enqueue, how to dequeue items, how to specify a queue criteria. What is the backing data structure?

Some further remarks on working with data structures:
* Know the difference when a _map_ or _dictionary_ &ndash; everything that requires a _dynamic_ lookup in general &ndash; is better using a tree or a hash-based backend. Trees are stable with respect to their average vs. worst case costs (not _trees_ in general, but the ones used in practice, like _self-balancing trees_) but hashes usually outperform at read-intensive tasks. Yet, there is no such thing as free beer, and so there are traps, and they need a [consideration or two](https://www.data-structures-in-practice.com/hash-tables/).
* Do not blindly transfer data structures into domains. For very common problems, people came up with good setups or specialized data structures (like graphs, sparse matrices, mutable strings), so never skip some research first.
* Some languages put a strong focus on a narrow set of dynamic data structures or remarkable features, such as lists in Lisp-and-family and Haskell, or immutable data structures in Clojure. Look around what your language of choice advocates &ndash; maybe it leaves you little choice or keeps its internals occluded.
* If you have a hard-coded, static data array with a need of dynamic lookups, think of a way to meaningfully sort it at the time of writing. It not only makes resolution easier when merging conflicting changes, it may qualify for [binary search](https://en.wikipedia.org/wiki/Binary_search_algorithm) lookups without asking for additional costs for setup at runtime.
* When working with multiple, concurrent modifiers on an instance of a data structure, an easy approach to prevent corruption is locking. Sometimes, environments already ship _synchronized_ data structures or even _lock free_ structures (like queues, since they matter a lot in such a scenario). Make use of them for both saving code, and maybe even benefiting from increased performance.
* If you feel that managing your application's _local_ data gets out of hand by data dimension, look up techniques, update patterns, lack of flexibility and persistence questions, consider [SQLite](https://www.sqlite.org/index.html), it does [not even need](https://www.sqlite.org/inmemorydb.html) a file on a disk and is also available on mobile operating systems. When working inside of a browser, _WebSQL_ is currently a restricted option among [some other ones](https://www.html5rocks.com/en/features/storage).

### Algorithms

Technically, every program is an instance of an _algorithm_, and even the ones that acquired a publicly known name fill books and books for all kinds of topics when it comes to writing them as code. Anyway, there are a bunch of helpful essentials to know:

* Keep the invariant calculations out of the loops, always. If some calculation does not depend on the iteration turn, put it outside. In `for (var i = 0; i < asMuchAsWeNeed(); ...)`, `asMuchAsWeNeed()` is evaluated right before re-entering the loop, so if it is invariant, just ask for it once.
* Compile your static regular expressions upfront, as they are invariant. A regular expression usually encodes code you don't see. The implementation is creating a state machine, and sometimes even hardware-accelerated code. If you do this over and over, you probably got yourself a handbrake in your code.
* Very close to optimization, but if a language supports [compile-time calculations](https://en.wikipedia.org/wiki/Compile_time_function_execution), think of what you can put there while just having code. Think of _runtime invariant_ aspects.
* Be aware how to properly use intra-process locks, both _shared_ and _exclusive_ ones, and how do synchronization and semaphores. More granularity means less blocking and thus more performance, but usually comes at the cost of more code and higher risk for dead locks when doing an error here.
* Do not parse or validate any non-trivial user input by regular expressions, make use of grammars and validate. Regular expressions become hard to read for humans at some point (see [email addresses](https://emailregex.com/)), and start to get flawed both semantically and technically &ndash; this is where grammars come into play. [Programming languages](https://www.nongnu.org/hcb/) specify them, [SQL does](https://sqlite.org/lang_select.html), so why not your input as well?
* The difference between [MergeSort](https://en.wikipedia.org/wiki/Merge_sort) and [QuickSort](https://en.wikipedia.org/wiki/Quicksort) matters. One is stable in costs and maintaining the relative order of equal items but requires more space, the other one is complementary to that.
* The pipeline of [map and reduce](https://en.wikipedia.org/wiki/MapReduce) is also a useful mental modeling tool for disassembling an approach into many smaller steps that can be implemented at different scales easily.
* If you can model your problem as a [graph](https://en.wikipedia.org/wiki/Graph_(discrete_mathematics)), there is probably a simple, sound and stable-cost solution for [the most obvious kinds of question](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/) you like to answer. Also: A tree can be seen as a graph.
* A graph can be seen as a [matrix](https://en.wikipedia.org/wiki/Adjacency_matrix).
* When calculating with arrays (vectors) and multi-dimensional arrays (matrices), refrain from implementing high school math on your own. There are libraries that help you doing so even better and numerically safer while exploiting hardware-accelerated SIMD concepts. It is even such a big topic that major CPU vendors provide such libraries working best on their platform ([Intel](https://software.intel.com/content/www/us/en/develop/tools/math-kernel-library.html), [AMD](https://developer.amd.com/amd-aocl/), [Apple](https://developer.apple.com/documentation/accelerate)), of course. But this is optimization, help yourself with generic ones first (best research keyword: _LAPACK_ + your language).

### Doing X is hard

For reasons of NIH, underestimation, skipping research or lack of awareness, people sometimes tend to solve problems on their own when they better should not. Even with being smart in algorithms and data, reality sometimes hits hard and makes you question the time you spend on certain topics. What we have recognized already:

* Doing dates and calendars and times is hard,
* Doing encoding and languages is hard,
* Doing email addresses is hard and
* Doing math is hard, and not by what people go through at school.

A list of other real-world examples that look somewhat easy at a first glance, but are not:

* Doing CSV is [hard](http://thomasburette.com/blog/2014/05/25/so-you-want-to-write-your-own-CSV-code/) 
* Doing JSON is [hard](http://seriot.ch/parsing_json.php)
* Doing HTTP cookies is [hard](https://tools.ietf.org/html/rfc2109) and got [harder](https://tools.ietf.org/html/rfc6265) (with updates pending)

For reasons of compatibility, performance and security &ndash; this cannot be stressed enough &ndash; always look for established solutions first. I had considered _doing XML is hard_ to be obvious for all my developer life, but even that did not stop a surprising amount of people from considering and even trying it on their own &ndash; and not as a private side-project.

## Inputs, outputs and throughputs

Without input and output operations, there was only little practical software. These operations often depend on devices that are magnitude slower in throughput and latency than CPU caches and memory. Doing such operations without some consideration will easily make your software wait, for a significant amount of its runtime.

* Similar to memory allocation requests, the less you need to do I/O operations, the better for performance. Even if we assume a comparably fast device, such as an M.2 SSD, look at an [interesting visualization](https://www.thomas-krenn.com/en/wiki/Linux_Storage_Stack_Diagram) of the I/O stack on Linux, for example.
* Always buffer your read operations when doing lots of small reads, a buffer size usually is equivalent to a file system page size, and that usually is 4096 bytes wide.
* Buffer your write operations by the same amount in the analogous case unless you need atomic operations. Do not forget to explicitly flush the buffer, otherwise data may indefintely hang in memory.
* When having a wild random access pattern without a need for appending to files, consider _memory-mapped I/O_ for its enormous potential of speeding up read and write operations. Again, because of _no free beer_ it comes at the cost of limited portability (but every platform has its API for this), and some need for caution in large files or [network storage](https://news.ycombinator.com/item?id=19806349).
* For reasons, never forget to set the binary (or `"b"`) flag when opening files. If the software ever touches Windows ground, not having this set on data that is not strictly human text to be displayed, it will implicity convert bytes related to line-endings.
* For reasons of convenience in times that nobody remembers, there are _readers_ in some environments that use implicit, i. e. system-dependent encoding when reading files. Stay away from them or always specifiy encodings explicitly (e.g. binary, UTF-8), as they are not portable otherwise.
* For doing I/O operations, there is sometimes a bunch of (system-dependent) types you can choose from: Synchronous (POSIX, mostly default), asynchronous (POSIX AIO, Node.JS) or batch/vector operations. Stick to the defaults of your environment unless you can identify needs for other patterns, and especially do not mix them uncautiously.
* When touching lots of files all the time, there is [room for tuning](https://opensource.com/article/20/6/linux-noatime) on some platforms: Not touching the `atime` attribute.
* In fact, I/O operations become a bottleneck so easily that I strongly recommend to have profiling tools at hand to identify the ratio of I/O waiting when looking for reasons of slowness around file operations.
* Have a timeout whereever you do not want to wait forever, and also think of a proper handling when elapsed. Socket-based I/O often suffers from hanging indefinitely, blocking allocations, when done improperly in exceptional circumstances. Sometimes, foreign code has biting default settings. Do a proper research first, especially when talking to endpoints outside of your domain.
* Remember: the slower the I/O channel, the bigger the advantage of a CPU compressing and decompressing data. This is [why we use compression](https://www.pingdom.com/blog/can-gzip-compression-really-improve-web-performance/) in HTTP servers, also for dynamic responses.
* Close all the handles when done, and mind the exceptions or error cases. Handles usually represent operating system allocations that are otherwise exhausted eventually while the process continues running.

### Streaming

Data on disks is easily larger than what fits into RAM. And since there is usually more than one process working on a host, constraints are not getting any easier. These are examples of tasks you will encounter at large:

* Reading a full set of records from a database into memory.
* Parsing the whole XML file into a DOM representation.
* Reading the whole file without checking its size first.
* Reading the whole data from a network connection to parse it in a 2nd step.

Some languages have tools that make it fairly easy to fall for these cases, the punishment they await: _out of memory_. It is not an optimization and I would not even call it a pattern anymore but a sheer necessity: _streaming_. It is not primarily about performance but about keeping the required amount of resources constant while facing virtually any kind of worklooad, and it starts by tasks as simple as reading data from a file which can be as big as the file system allows it to be.

While reading from and writing to I/O channels usually are first-class streaming citizen of any serious environment, your product requirements may ask for more thinking or sophistication, maybe even rethinking your view of the problem &ndash; like streaming between local views of something larger and using hierarchies of resolution. But the general rules include:

* Have a fixed number of allocation calls.
* Have a fixed size of memory to be used for buffering between reading from a source and writing into the next sink.
* Reuse allocations, even if your environment includes a Garbage Collector.
* Know your libraries and how they support streaming.
* Reality is often disappointing when facing closed source software and remote services, so maybe consider secondary solutions as well.

When done well, memory problems will disappear forever &ndash; locally, of course.

## Security

* Rule #1: _All input is evil_. Some DNA sequencer device engineers probably never considered malcrafted DNA sequences remotely to be an actual threat to their software. Well, [they were wrong](https://www.schneier.com/blog/archives/2017/08/hacking_a_gene_.html), and so will you.
* Rule #2: _Do not invent or implement cryptography yourself_. Leave that to mathematicians and cryptographers, like _Daniel J. Bernstein_ or the inventors of _AES_, just to name some of the very few.
* Rule #3: _Security by obsecurity is taboo_. If somebody argues that reveleaing its security mechanisms is a security risk, it _is_, so go away.

Ok, people have come up with more formal concepts and established resources on IT security than this list.

* The [CIA principle](https://en.wikipedia.org/wiki/Information_security#Key_concepts) &ndash;
    * _Confidentiality_: Nobody can read who is not supposed to read it.
    * _Integerity_: Nobody can temper a message unnoticedly.
    * _Availablility_: Do not be disruptible.
    * _Non-repudiation_: Prevent false or ambiguous impersonation of participants.
* [OWASP Top-10](https://owasp.org/www-project-top-ten/): A list of common security violation types in the domain of websites.
* [ISO/IEC 27002](https://www.iso.org/obp/ui/#iso:std:iso-iec:27002:ed-2:v1:en) (excerpt): Probably everything you need to formally know about IT security.
* [CVE](https://cve.mitre.org/cve/search_cve_list.html) (Common Vulnerabilities and Exposures): A database to refer to disclosed security incidents by some _CVE number_. It is one such database among others (_security advisory databases_) but it is likely the most common one to use when looking for vulnerabilities in IT products.

There are many concepts a software engineer needs to know when remotly touching topics subject to security.

* _Cryptographic hash functions_: While a _hash function_ maps data into a fixed range of values, _cryptographic hash functions_ do the same while matching some security requirements:
  * There is no known way to produce collisions, and finding some is infeasibly expensive by brute force.
  * There is no known way to infer its input just by looking at some hashed value.
  * Depending on the context in use
      * they are fast to also work on large data, often backed by hardware implementations, for example [SHA](https://en.wikipedia.org/wiki/Intel_SHA_extensions),
      * they are deliberatly slow to make brute force approaches take even longer, e. g. to slow down guessing of passwords. _bcrypt_ is an example of such a hash function.
* _Salting_: Imagine two or more users using the same password. If an attacker obtains password (e. g. by social engineering), the attacker can identify all the other users just by looking at their identical hash values. _Salting_ the input by some unique or sufficiently random input makes this kind of weakness difficult again. Look at [bcrypt](https://en.wikipedia.org/wiki/Bcrypt) for an implementation example.
* _Message Authentication Code_ (MAC): How to make sure that something has not been modified illegally? One easy and common approach includes _hashed MACs_ (HMAC), i. e. `hmac(message + secret)`. The secret needs to be known to all authorized parties, of course. Make sure not to use ordinary cryptographic hash functions but only its HMAC-derivatives, for example `HMAC_SHA256`, this is imperative ([details](https://security.stackexchange.com/questions/79577/whats-the-difference-between-hmac-sha256key-data-and-sha256key-data)).
* _Symmetric cryptography_: The _same key_ is used for both encryption and decryption. Examples include _AES_ or _Twofish_.
* _Asymmetric cryptography_ or _public key crypthography_: There is one key to be used for encryption (or verifying) &ndash; also known as _public key_, and another one for decryption (or signing), the _private key_. The keys are coupled mathematically by requirements similar to cryptograhpic hash functions, and as the names suggest, one is supposed to be shared and other is to be kept secret _at all times and under all conditions_. Mathematical concepts behind this include _integer factorization_, _discrete logarithms_ and _elliptic curves_. Known implementations of different feature sets include _RSA_ or _ECDH_. If the private key is leaked, everything related must be considered compromised.
* _Signatures_: First: Do not set _digital signatures_ equivalent to _signatures_ as you use to confirm an intent with legal binding by writing something at the of a letter; the only commonality is the aspect of _there is something at the end of the message_. The digital signature is an output of a procedure taking the input and the _private key_, and that can be matched by using the corresponding _public key_, i. e. verified. This way, we know that the holder of the private key of the given public key has _signed_ the data. This signature is _free_ of semantics, it can indicate authorship, ownership, authorization, integrity &ndash; look at the use case.
* _Certificates_: How do we know that a given public key truly belongs to the one who claims it? Like _I'm truly your bank's online portal now_. Because you really know that other party and got the public key in a way that is subject to little risk of tampering. Or because somebody we trust for doing proper identity checks in a hopefully clean environment tells us: _yup_. A certificate is a signature of a trusted entity over somebody's public key. And mostly, there are middlemen who need to be trusted, who need to be trusted ... and eventually, your operating system or browser ships a bunch of _root certificates_ that are accepted to be at the top of the _chain of trust_. In the real world, things go wrong of course. So if some _certificate authority_ (the middlemen or root-men) make a mistake, this usually results in some kind of _security fallout_ scenario, as everyone affected of the chain suddenly needs to act fast. Read stories of [DigiNotar](https://en.wikipedia.org/wiki/DigiNotar) or [Symantec](https://security.googleblog.com/2015/10/sustaining-digital-certificate-security.html). Google has [undergone approaches](http://www.certificate-transparency.org/) to spot illegally issued certificates, and there are [mechanism](https://en.wikipedia.org/wiki/Online_Certificate_Status_Protocol) to structurally publish revocations of compromised keys.

## Databases

## Modeling

## Testing

## The Project

## The Running Project

## Legals and Lawfuls

Laws and legal aspects touch everyone, everywhere. When being employed, every employee will likely get a training in applicable laws and compliance rules in every mid-sized company. Yet the software engineer quickly turns into the technician to overview the technical implementation details of software with respect to legal requirements. For example, the EU _General Data Protection Regulation_ (GDPR) contains articles like _personal data must be protected technically by up-to-date best-practices_. Guess who is closest to know what _up-to-date best-practices_ actually means, especially if there is no dedicated software security crew available. Here is a list of legal topics that every software engineer should have heard of:

### Laws

* The omni-present _privacy laws_, like GDPR, especially if you remotely touch European internet ground. While its general applicability is more an issue of your business drivers, you should know what your job is technically. The compliance person may or may not know what a _hashed password_ means in contrast to an _encrypted password_ &ndash; _non-plaintext passwords_ sounds good, but all your work should back this by _up-to-date best-practices_ (see the topic about security).
* _Authorship laws_ &ndash; Either by law or by contract, there is some ruling on what your employer, or contract partner, acquires as rights on the work you create in your work time or project. Know the implicit and explicit practices and rules. This is especially a topic when developing software on your own, even when fully in your off-work time, that is closely connected to what you do for work, and when it ends up in use there.
* _Criminal code_ &ndash; Learn your jurisdiction's subtle limits between software engineering, hacking and cracking. Reverse-engineering some badly documented second- or third-party API and spotting some unsecured parameters making you see things you were not supposed to see means STOP. Google for _responsible disclosure_ practices to know how to continue, and immediately take actions if some discovery threatens you or your data as well.
* Laws on business secrets: Know what you better forget &ndash; and technically erase &ndash; when changing the employer or client. When leaving a client or an organisation, exploiting any knowledge beyond what is publicly visible easily puts you at risk for civil and criminal charges. And: Taking away an unauthorized copy of some software project &ndash; because you contributed much to it, or find it useful &ndash; is a very stupid idea.
* When in doubt about facing financial, civil or penal consequences: Ask a lawyer or compliance coworker first before taking any action.

### Licenses

As a software engineer, you will have to pick fitting tools and libraries, and they always come with a license you have to obey without risking of being sued, even if [open source](https://gpl-violations.org/). Fortunately, a whole bunch of software is subject to [some well-known licenses](https://opensource.org/licenses/alphabetical) that simplify decision-making.

* When you encounter a 3rd party software without a clear license, consider it taboo. Just because it is found on GitHub, it doesn't mean you can simply make any use of it.
* When contributing to an open source software project while at work, even a minor bugfix, and it requires the contribution to be subject to a certain license for being accepted, make sure you got an OK by your employer first.
* At an early point, ask your employer what libraries and programs are actively being shipped to the world, what is exclusively part of internal services and tools. Ask for license policies, like cleared and [banned ones](https://opensource.google/docs/using/agpl-policy/). If nobody has a clue what you actually want by that, you probably got yourself a new job: A client or compliance person will eventually have questions.
* If there are specialized people in your organization for contracts, laws and licenses, it may be the best &ndash; or only &ndash; option to get a clearance from them per license type or individual software. But this should not stop you from reading this section at all.
* Open source software matters, and so do the license models. [Have some statistics](https://resources.whitesourcesoftware.com/blog-whitesource/top-open-source-licenses-trends-and-predictions) and [some synposis](https://choosealicense.com/appendix/). 
* Know the distinction between licenses that cover software (for its dual form of source and binary state, warranties, liabilities, patents) and _asset licenses_ that addresses non-software creative work, data and documentation.
* To mention the major OSS licenses &ndash; and **just to outline them roughly** (this is not legal counselling, I must make this explicit):
    * [1](https://opensource.org/licenses/BSD-1-Clause), [2](https://choosealicense.com/licenses/bsd-2-clause/), [3](https://choosealicense.com/licenses/bsd-3-clause/)-clause BSD, [MIT](https://choosealicense.com/licenses/mit/), [ISC](https://choosealicense.com/licenses/isc/): Use how you like to do, but obey where the authors want to see their copyright notice in distributions. No patent grant, warranties, liabilities.
    * GPL [v2](https://choosealicense.com/licenses/gpl-2.0/), [v3](https://choosealicense.com/licenses/gpl-3.0/): Source code must be made available, modifications must be outlined and subject to the same license, and that also holds for most cases of making use of GPL software by another software (but not when be used over command line interaction or network). Obey previous copyright (or -left) notices and user rights. No warranties, liabilities.
    * [AGPL](https://choosealicense.com/licenses/agpl-3.0/): An even stronger focus on copyleft than GPL, as it considers the use over network as distribution, so you must make the source code of some server available if its components are subject to AGPL.
    * LGPL [v2.1](https://choosealicense.com/licenses/lgpl-2.1/), [v3](https://choosealicense.com/licenses/lgpl-3.0/): A weaker focus on copyleft than GPL, as it does not consider the use of dynamically linked code, i. e. it is still usable when stand-alone, as subject of falling under the same license. This is why some libraries subject to LGPL can be found in projects with incompatible licenses.
    * [Apache License v2.0](https://choosealicense.com/licenses/apache-2.0/): Grants a permissive use while requesting copyright notices and outline of changes to the source code. Grants patent use, but not warranties and liabilities.
    * [Mozilla Public License v2.0](https://choosealicense.com/licenses/mpl-2.0/): Grants a permissive use while requesting a file-based copyleft, i. e. disclosing changes to source code files that are subject to MPL. Grants patent use, but not warranties and liabilities.
    * _Public domain_ &ndash; Publicly floating software, or so. A difficult topic since there is such thing in some jurisdictions. It is probably OK if the author(s) explicit state a public domain release or an equivalent one, but if there is no such credible statement, consider it taboo. A better alternative for software is the [CC0](https://choosealicense.com/licenses/cc0-1.0/) or [WTFPL](https://choosealicense.com/licenses/wtfpl/) for addressing the possible lack of _public domain_ regulations in an internationally acceptable way.
    * Everything else: There are lots of less common ones, so read the available texts or comments, at least. For any custom ones, well, read through.
* Generally assume that the use of trademarks and patents is not granted unless explicitly stated. So do not use them until then.
* For asset licenses, there are also some to know about &ndash; since you as a software engineer will also choose an icon or data set, or presentation banner from time to time:
    * [Creative Commons Licenses](https://creativecommons.org/) (CC) &ndash; An organization that helps artists of all kind to pick a well-defined license with global acceptance for their work, also used by Wikipedia. There are some identifiers that easily allow you what fits:
        * _BY_: mention the author(s)
        * _SA_: _share alike_, modifications are legal only when subject to the same conditions of the CC license
        * _NC_: not allowed to be used in commercial contexts
        * _ND_: do not modify
    * [GNU FDL](https://www.gnu.org/licenses/#FDL): The concept of a copyleft in the context of books and documentation. The old default of Wikipedia articles.
    * [Open Database License](https://opendatacommons.org/licenses/odbl/1-0/): Think of CC-BY-SA for collections of data, like _OpenStreetMap_ does.
    * _Fair use_: The concept of fair use is known to some countries such as the US. It allows a fairly limited use of some otherwise protected work but you should not assume a right to claim _fair use_ under general conditions, and outside of these countries.
* If you are generally interested in picking an open source model for you, let tools help you guiding through, for [software](https://creativecommons.org/choose/) and for [assets](https://choosealicense.com/non-software/) ([CC](https://creativecommons.org/choose/)).
* Mention your license situation in some well-known locations like the Readme, a package meta-data file, and the whole texts and 3rd parties in well-known files to look for, such as a `LICENSE`, `COPYING` file or around an _About ..._ section.
* Consider using [SPDX headers](https://spdx.github.io/spdx-spec/appendix-V-using-SPDX-short-identifiers-in-source-files/) in your source code when making it available. This allows simplified identification and parsing while also saving a lot of copyright-related comments to be found in the header otherwise.
* Depending on the view, the most interesting, or most painful aspect, is what commercial legal texts looks like. Well, we cannot generalize, it may be individual agreements and general terms of services and end-user license agreements (EULA). But depending on your background, this can be Pandora's box when facing to work with such:
   * Something on-premise is bound to natural persons by name, with no option of transfer.
   * Something on-premise is bound to serial numbers of hardware.
   * Something on-premise makes you pay for the number of CPUs, or CPU cores that you like to use.
   * You may not have the permission to take unauthorized screenshots, or [publish benchmarks](https://www.brentozar.com/archive/2018/05/the-dewitt-clause-why-you-rarely-see-database-benchmarks/).
   * Its obedience is enforced by all kinds of digital rights management (DRM) tools.
   * It is OK when you have something running on your personal computer, but [it is bad when it enters the guest Wifi of a corporation](https://www.linkedin.com/pulse/being-radicalized-oracle-license-drone-martin-zetterlund).
   * ... (insert the absurdest things to think of that actually drive people towards OSS as far as they need to do serious work) ...
