# The Guide to the Dirty Little Things in Software Development

This guide is subject to the [Creative Commons License v4.0 BY, unported](https://creativecommons.org/licenses/by/4.0/), started in 2020.

## Preface

### We, the people

Everyone is biased, I am and so are you. The bias in the role of a software engineer is shaped by a wide range of factors:

* The initial motive in life that eventually brought you here,
* the degree of formal education of this topic,
* your previous fields of engineering and products,
* your colleagues, [bosses](https://getlighthouse.com/blog/people-leave-managers-not-companies/), clients.

Have you ever discussed the absurdly prominent example of _tabs vs. spaces_? Given the [financial correlation](https://stackoverflow.blog/2017/06/15/developers-use-spaces-make-money-use-tabs/), you better do &ndash; yet it is just one of the sheer amount of things that ask for a common ground among you and the people around you.

Looking at the list above, you and me probably need to have subjects of discussion settled, and better early than late. Let me draw a few contexts first, because this turns out to make a significant difference in certain aspects. The most important one: On what basis do we justify a guide like this one?

When we are in the **economic** context, this is about selling products and services, scalability and reducing costs, and dealing with risks.

If you have been part of some **academic** institution, you know that software development is different: It serves your research for scientific significance, rendering publications and &ndash; hopefully &ndash; universally useful insights.

The ultimate fun factor finally: **personal** matters. The website, the game, the [demo](https://www.shadertoy.com/events), the [hack](http://labs.domipheus.com/blog/raspberry-pi-4-pci-express-it-actually-works-usb-sata-gpu/), the [operating](https://en.wikipedia.org/wiki/History_of_Linux#The_creation_of_Linux) [system](https://en.wikipedia.org/wiki/TempleOS), and [countless](https://www.theverge.com/tldr/2019/6/30/19102430/amazon-engineer-ai-powered-catflap-prey-ben-hamm) [other](https://bellard.org/jslinux/) [things](https://renderdoc.org/renderdoc-history.html). (There is no affiliation to the items here, just a collection of awesome things people demonstrate that I had in memory.) Enjoy your curiosity, preferences, desires at will.

This guide is about _economical_ software engineering for the individual developer, as portable as possible across domains and not bound to particular technology &ndash; unless stated otherwise. This guide will justify all its recommendations over the following factors:

* Saving time and costs while also
* managing risks.

This guide is designed for everyone inside the sphere of hands-on software engineering, regardless of the years of experience and performance of different roles. _I'm a successful developer for over 20 years, so why reading?_, if you agreed on the very first paragraph of the guide &ndash; the list of factors that form the individual &ndash;, while probably knowing most of the topics of this guide well and not missing a single aspect, you may re-evaluate the degree of feeling capable to plead your attitude and practices towards others.

Indeed, you may abort here if you are familiar with highly regulated software engineering, may it be by legal framework, or by throwing ISO auditor parties, or by [working at NASA](https://swehb.nasa.gov/). If so, there is a big chance of knowing all the aspects of this guide in all its bureaucratic depth.

I am not sure how many people will at least go once through a burning home in life, most of us hopefully never will. But why so little? Fire prevention. Smoke detectors, hardly inflammable materials, insulation, extinguishers. The overall risk of fire is unlikely if you follow best-practices, like not smoking a cigarette while lying in bed and falling asleep. Anyway, there may be factors you cannot fully account on yourself alone. So if your home catches fire, do you have a plan? What will you do, where will you try to escape?

This a about economical moves and calculating risks to the degree a software developer should be able to reason about on a daily basis, and here comes the checklist. After sampling from fellow students, coworkers, managers, team leads and online-only collaborators in open source development for more than ten years, I noticed a very big discrepancy in what I expected from people in either direction, given that somebody claims to already/only have X years experience doing just &ndash; or tons of other things alongside of Y. This concerns the following questions:

* What is the person's very individual capability of organizing the own time of work day, week, sprint, milestone, ...?
* What is the person's ability to express, visualize, defend and preserve ideas?
* What is the person's degree of basic software engineering knowledge &ndash; or what is still present, years after education/university?
* How is somebody approaching a new problem?
* What is the person's ability to step back, take a breathe and re-evaluate some idea? With and without external impulses?
* How is somebody keeping up to date with technological advancements and legal requirements? If any, what is the range of view beyond the own zone of comfort, and specialization?
* What is the attitude towards doing mistakes? How is quality being evaluated when not being asked for protocols?

When not aligned or guided properly, a team of software engineers may easily face misunderstandings, conflicts, delays, frustration &ndash; that is subsumed in an [article](https://neverworkintheory.org/2021/08/29/software-development-waste.html) called _Software Development Waste_. This, in turn, translates straight into time-to-market, or worse, disaster recovery and bad press. Unless it is _Cyberpunk 2077_, then delay is probably good [update as of 2021: _Well, ..._].

### How to read, what to read

Let us write some software. Let us be done in time. Let us save resources, economically and &ndash; where possible &ndash; ecologically. Let us just not be guys that appear in press for failing miserably over beginner's mistakes. And here, I want to make sure we just get there well &ndash; on one or another way.

I expect you to know something about software development, hands-on. This is not some guide for replacing some fundamental education, there is [literature](https://bigmachine.io/products/the-imposters-handbook/) for that. This one is for filling all the dirty little stuff you may have ignored so far, you may not be aware of, and that is mostly taught by experience and failure.

In 2020, I have started assembling a collection of technical topics and organizational guidelines, I will go into details or put a link to a useful and comprehensive reference. There will be inline examples or examples of implementations or products. **None** of these are meant to be as an advertisement in a sense that I get any affiliation link money or alike, they are a product of hands-on experience, knowledge, neutral (i. e. using Google) research and browsing news aggregators. Over time, of course, they may also lapse and be superseded by other standards, products, practices.

You may argue of missing some in-depth or more comprehensive information on very closely related fields here, such as security, networks, team leadership. This is true and I strongly recommend to have designated literature on these topics for both broader and deeper insights, as some simply go beyond this scope. Again, literature choice is based purely on personal recommendation.

You may find hints hilariously obvious, maybe even offending to read. That is good then, nonetheless for the reasons mentioned, you better carefully transfer such assumptions onto others and both the absolute beginners as well as longstanding software developers sometimes have a need for completing their knowledge basement.

## The Globals and Universals

_Schei� Encoding_, some guy at my undergrad university had a shirt writing that. It translates to _working with encoding is mildly frustrating_. No objection, if you have every tried making software work on _Windows 9x_ while trying to put people all around the globe together &ndash; in front of your software.

But then, what is beyond the mundane problems of language, time and location? Laws of thermodynamics, system equilibrium, information content, and the human mind, of course.

### Laws, Principles and Models

In the United States, you may be particularly familiar with the concept of [post turtles](https://en.wikipedia.org/wiki/Post_turtle). And more than identifying one &ndash; that is easy &ndash; it may help you anticipating the next one, given that we found a name or symbol for such cases, and that we start to evaluate against them. And so there is a plenty of concepts, laws, principles and models out there, so I picked a couple of them because I consider them fundamental for software engineering, both for generally thinking about solutions, as well as for implementing them:

* [Murphy's Law](https://en.wikipedia.org/wiki/Murphy%27s_law) &ndash; The most prominent one, yet I probably found most of the managers working far away from domains of potentially deadly problems keeping it low to a worrisome degree. _Anything that can go wrong, will go wrong._ Modifications include: _... to the worst extent/time possible._ or _... in the worst chain of combinations._ If you see something that is about to go wrong at some time, it will, and earlier than pessimistically estimated. Leaving a password for user `root` set to `root` is an invitation to Murphy, for example.
* _At scale, there is no edge case_ &ndash; A slightly more neutral form of Murphy. If you observed that edge case X happens about every few Y, scale up Y, and read the law of Murphy again. The economist wants to have costs and likelihoods here, so really spend some time modeling your nasty edge case's impact.
* [Gall's law](https://en.wikipedia.org/wiki/John_Gall_%28author%29%23Gall%27s_law) &amp; [KISS](https://en.wikipedia.org/wiki/KISS_principle) &ndash; In a way to put it short: Do not enter the stage of over-engineering, i. e. designing for features you are not sure about to ever see their requirement at the horizon when it comes to your task.
* [Hofstadter's Law](https://en.wikipedia.org/wiki/Hofstadter%27s_law) &ndash; Hey, somebody made a cool and recursive law out of estimation meetings. The more important point I found is that you think twice to estimate more closely to what looks feasible, not by what appeals to the guys with money. There lies no profit in underestimation, but everyone is happy when you actually over-perform the estimations.
* [Hanlon's razor](https://en.wikipedia.org/wiki/Hanlon%27s_razor) as an instance of [Occam's razor](https://en.wikipedia.org/wiki/Occam%27s_razor) &ndash; While this is nowhere limited to the domain of software engineering, it frequently helped soothing the own nerves: Nobody probably ever wrote a _historically grown_ dump of code and processes from hell to deliberately cause anger to _you_. Instead, _they_ likely did not knew better, did not care so much, did not understand somewhere in between (Hanlon) or just made a reasonable economic decision not to touch a running mess of a system for the need of extension (Occam). Feeling angry about what you face is OK, but please refrain from doing so over what is likely the wrong reason.
* _Not invented here (NIH)_ &ndash; In any remotely mature software development environment, there is probably at least one actively maintained, well-tested, sufficiently documented, StackOverflow'd software product for every common problem since the day ALGOL60 went to see the light. The same holds for best-practices of human and/or technological processes. Google is one of your friends, and your advocate when an NIH-susceptible guy fantasizes on inventing unseen security measurements. Of course, the inverse of NIH also found its name: _proudly found elsewhere_.
* _Everyone makes mistakes_ &ndash; Somebody rejecting the claim is to be considered suspicious. We all make them, some of them go unnoticed and some of them cost lives. The reasons include wrong assumptions, missing knowledge, misunderstandings, the wrong calculation of risk and a lack of focus. And similar to fire, collapsing bridges and crashing planes, we need to learn and establish mechanisms to catch them as broadly and as early as possible. In the European Union, every country needs to maintain an agency to perform investigations in accidents regarding naval vessels, trains and air planes, with their reports mostly being published online (examples for [Germany](https://www.eisenbahn-unfalluntersuchung.de/SiteGlobals/Forms/Suche/Untersuchungsberichtesuche/Untersuchungsberichtesuche_Formular.html), [UK](https://www.gov.uk/raib-reports?report_type%5B%5D=investigation-report)). Read some of such reports by example, and see how and why mistakes are presumed to have been made &ndash; including human interaction and technical negligence &ndash;, and what measurements were ignored or newly established as a consequence, with [shisa kanko](https://en.wikipedia.org/wiki/Pointing_and_calling) being an impressive yet a very simple one.
* _All input is evil_ &ndash; No exception. Everywhere. Always assume that beyond the border of your software unit, every input is about stealing your computational resources or taking you down, about setting up intrusion vectors, about circumventing access rules. More on security later, but this is security rule #1 to always have in mind.
* [Principles of chaos engineering](https://principlesofchaos.org/): Become the Murphy. Instead of _solely_ spending work on _doing it right_, make every _what if..._ question an action. Your disks will eventually fail, your security lines will eventually break, somebody will trip over an important network cable. Instead of hoping for the best in this case, try it out, test your low-hanging countermeasures, evaluate them, improve them, repeat. AWS even does so called _people attacks_: _What if Neuralgic-Joe gets hit by a bus?_ (This is simulated by ordering Joe to stay at home for a day or another).

With some special relevance for this guide: _Premature optimization is the root of all evil_, by _Donald Knuth_ I suppose. I do not disagree. Remember _Adobe Flash Player_? It had or has [tons and tons](https://www.cvedetails.com/vulnerability-list/vendor_id-53/product_id-6761/Adobe-Flash-Player.html) of severe bugs in it. Unfortunately, I do not find the article any more but I was told that _Macromedia_, later acquired by _Adobe_, tried to build up the Flash Player over an insane amount of techniques to save space, like leaving no bit unused. Assuming some truth in these claims, if you think of the fun programming with bit operations at a larger scale, nobody will make a face of surprise. Yet, it is even way easier to screw up some basics. If you think something will be your pain the back forever, it probably will &ndash; Murphy. Think of a distinction between optimization, like squeezing numbers over advanced calculations and strategies, and trying not to openly run into a knife by looking ahead for a bit.

### Time &amp; Space

Let us start with time, since we never have enough of it and we cannot go back in that:

* There is the [Coordinated Universal Time](https://en.wikipedia.org/wiki/Coordinated_Universal_Time), or _UTC_ &ndash; for the love between France and the UK, it did not turn into _CUT_. UTC knows no summer time, or _daylight saving time_, and is not geographically relocatable. Time zones effectively help humans to establish a global agreement of what numbers belong to the morning, midday and evening. And in some jurisdictions, we are expected to change our perception about that abruptly twice a year. Thanks to timezones, everybody knows that 4am is some strange time somewhere between dusk and dawn, and most of the time, you probably want to go awake through it anyway.
* If you write down a time without any closely locatable time zone information (like `+0200`), do it in UTC &ndash; and nothing else, ever. If you don't, you will mess up once year over one hour of summer time reset, you will probably not remember if your computer installation was configured correctly at that time any maybe not even its actual location to guess, you will likely never be able to ever fix this later. This may have legal implications.
* Time zones may change over time for political reasons, as well as summer time may be introduced or not. Do not use geographical identifiers as a time zone identifier. Instead, an identifier like _Europe/Berlin_ (one example of a name in the _TZ database_) will help your clock adjusting the display &ndash; the one for human reasoning &ndash; of time into _Central European Time_ and _Central European Summer Time_ by some calendar that is applicable to inhabitants of Berlin. On computer systems, this information is often managed by the operating system and is frequently updated for upcoming changes and historical fixes.
* If you have to record time with a time zone information, do not use the symbolical names (`CEST`) but only numerical displacements (`+0200` or `+02:00`). The abbreviations and names are not standardized and even ambiguous. Go identify _CST_.
* Time zones are not bound to full hours, Nepal uses `UTC+05:45`.
* When you encounter UNIX timestamps, they are always supposed to be relative in the amount of seconds since the beginning of 1970 at UTC, though I've seen a FAANG company to really mess this up in one of their subsystems. Never adjust them for time zone by convention. There may be negative values, for the same reasons we have years _B. C._
* When you encounter UNIX timestamps, make sure sure you have more than 4 bytes of storage available to write them down. At some point in 2038, the number of seconds will not fit into the positive half of 4 bytes anymore. If you read this guide between 2020 and 2037 and face this problem, act! 2038 is close and maybe nobody else is going to rewrite your software any time soon.
* Remember that February sometimes has 29 days &ndash; I say that because I had to fix that unawareness once already. Be aware that this is [not always in a cycle of 4 years](https://en.wikipedia.org/wiki/February_29).
* Mind the [leap seconds](https://en.wikipedia.org/wiki/Leap_second#Insertion_of_leap_seconds). They are rare, but they disrupt your `0-59` assumption. And they may even [go negative in the future](https://fanf.dreamwidth.org/133823.html).
* Be aware that [some calendars](https://linux.die.net/man/3/localtime) refer to months numerically by `0-11`, not `1-12` and that some libraries may be built on top of this mechanism.
* Remember that some cultures have a different convention of the first day of a week, like Sunday vs. Monday.
* The last week of the year is usually shared by two different years.
* Do not invent time formats, follow [ISO 8601 principles](https://en.wikipedia.org/wiki/ISO_8601#General_principles).
* Time problems have been solved mostly since forever, heh, that's the good point. The more challenging one is that [some environments](https://docs.oracle.com/javase/8/docs/api/java/time/package-summary.html) use plenty of types for precision, relation, time zone affinity and backward compatibility. Familiarize yourself with what you need before picking `Date`, just because date.
* As a side note, setting the system's time-zone explicitly may be a [good idea anyway](https://blog.packagecloud.io/eng/2017/02/21/set-environment-variable-save-thousands-of-system-calls/).

Let us head over to the issue of textual representations:

* Know what [Unicode](https://en.wikipedia.org/wiki/Unicode) is made for. Image Unicode being _the_ atlas of all the symbols, letters, emojis and runes of all actually used scripts of the world, even some archaeological ones, like some old nordic rune: ᛈ. This rune is located under position (decimal) 5832. At the time of writing, Unicode was standardized at version 13 in early 2020, comprising more than 143,000 symbols, including new emojis like 🩱 (if you see � instead, I tried to show you a _one-piece swimsuit_, to be found at no. 129649). On top, it is not only symbols: Unicode lists [control entities](https://en.wikipedia.org/wiki/Unicode_control_characters) as well that are supposed to aid in various cultural aspects.
* Unicode is _not_ an encoding. [UTF-8](https://en.wikipedia.org/wiki/UTF-8#Description) is one example of an encoding to implement Unicode, and everything of it at once. Looking at the number of items in Unicode, you require at least three bytes per symbol to address anything from the atlas. Given that, historically, computer systems had less space than today and were centered on Latin languages, of which the English alphabet is composed of less than 128 symbols &ndash; including uppercase letters, downcase letters, digits, symbols &ndash; one byte was sufficient to even have some control bytes in the lower 128 items (see [ASCII](https://en.wikipedia.org/wiki/ASCII)), and to have some other Latin symbols in the upper 128 slots. Not all at once, but enough to put some things together, like [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1) for German and Roman scripts, or [ISO-8859-5](https://en.wikipedia.org/wiki/ISO/IEC_8859-5) for Cyrillic scripts. Depending on the computer's settings, it will then display `Ø` or `и` for byte `0xD8`. For a North-American computer system, one byte per symbol is usually enough, but the user may occasionally visit a [CJK](https://en.wikipedia.org/wiki/CJK_characters) website. In order not to break compatibility to ASCII and to have some space saved, UTF-8 makes use of bit patterns per byte that allows scaling up the use of one to four bytes per symbol, depending on what is in use while also preventing ambiguity, that is why it needs four bytes for modern emojis, not just three.
* There is also [UTF-16](https://de.wikipedia.org/wiki/UTF-16), requiring two to four bytes. It requires less magic to bit patterns but also requires more space. _Be careful_, there may be a _byte-order marker_ of 2 bytes in use at the beginning of the text. It tells you which one of the two bytes is supposed to be the _lower_ one. Microsoft made Windows use UTF-16 for a very long time, requiring developers to constantly convert on touch points with UTF-8 data.
* For [UTF-32](https://de.wikipedia.org/wiki/UTF-32), there are no reserved bits, since every element is using exactly four bytes, thus wasting a lot of space for `0x00`s in Latin languages, but simplifying all related string operations.
* Make use of UTF-8 unless there is a very specific requirement.
* Do not step back to codepage-based encodings, i. e. needing the correct interpretation context as mentioned above, unless there are even more constraints to work with.
* Make sure to have all your tools configured correctly, starting at the text editor.
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

In pre-COVID19 times, shaking hands was the etiquette in social gatherings. Now, let us think of some kind of party with the host having some kind of self-imposed shaking-hands policy. Let us sum the number of hand-shakes of all participants individually, including the host:

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

* Asking for memory costs, not so much by the amount you ask for (that may simply fail; [or maybe not](https://www.kernel.org/doc/html/latest/vm/overcommit-accounting.html)), but the number of times, as [demonstrated](https://sploitfun.wordpress.com/2015/02/10/understanding-glibc-malloc/) for one such memory manager. Depending on the level that your environment works on, you have a more or less deterministic view of what actually happens. In the lower levels, you ask your operating system for a memory allocation (`malloc`) of some size, and you better release that when no longer needed. Libraries or higher level runtimes hide that in various degrees, probably doing at least one large initial allocation, or by over-allocating a bit in advance. Requesting and releasing memory via the operation system usually invokes a _mode switch_ and a search for a sufficiently large memory chunk. Details vary by the actual allocator in use. In short: The less you need to do, the better. [Actual footage](https://www.forrestthewoods.com/blog/benchmarking-malloc-with-doom3/) how these numbers add up in practice.
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
* A [Bloom filter](https://en.wikipedia.org/wiki/Bloom_filter) is a nice thing that is often guarding other data structures (sets and maps): Every item that goes in touches its bits according to some hash function. Now, when checking for some item for its presence, the bloom bits tell us: _Yeah, maybe_ or _definitely not_. Latter case helps preventing exhausting lookups.

### Algorithms

Technically, every program is an instance of an _algorithm_, and even the ones that acquired a publicly known name fill books and books for all kinds of topics when it comes to writing them as code. Anyway, there are a bunch of helpful essentials to know:

* Keep the invariant calculations out of the loops, always. If some calculation does not depend on the iteration turn, put it outside. In `for (var i = 0; i < asMuchAsWeNeed(); ...)`, `asMuchAsWeNeed()` is evaluated right before re-entering the loop, so if it is invariant, just ask for it once.
* Compile your static regular expressions upfront, as they are invariant. A regular expression usually encodes code you don't see. The implementation is creating a state machine, and sometimes even hardware-accelerated code. If you do this over and over, you probably got yourself a handbrake in your code.
* Very close to optimization, but if a language supports [compile-time calculations](https://en.wikipedia.org/wiki/Compile_time_function_execution) (examples include C++, up-to-date Rust), think of what you can put there while just having code. Think of _runtime invariant_ aspects.
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
* doing encoding and languages is hard,
* doing email addresses is hard and
* doing math is hard, and not by what people go through at school.

A list of other real-world examples that look somewhat easy at a first glance, but are not:

* Doing CSV is [hard](http://thomasburette.com/blog/2014/05/25/so-you-want-to-write-your-own-CSV-code/),
* doing JSON is [hard](http://seriot.ch/parsing_json.php),
* doing HTTP cookies is [hard](https://tools.ietf.org/html/rfc2109) and got [even harder](https://tools.ietf.org/html/rfc6265) (with updates pending),
* doing IP address parsing is [hard](https://blog.dave.tf/post/ip-addr-parsing/),
* doing emojis is [hard](https://www.unicode.org/reports/tr51/) and
* doing language identifiers is also [more than you'd wish for](https://www.rfc-editor.org/rfc/rfc5646.html).

For reasons of compatibility, performance and security &ndash; this cannot be stressed enough &ndash; always look for established solutions first. I had considered _doing XML is hard_ to be obvious for all my developer life, but even that did not stop a surprising amount of people from considering and even trying it on their own &ndash; and not as a private side-project.

## Inputs, outputs and throughputs

Without input and output operations, there was only little practical software. These operations often depend on devices that are magnitude slower in throughput and latency than CPU caches and memory. Doing such operations without some consideration will easily make your software wait, for a significant amount of its runtime.

* Similar to memory allocation requests, the less you need to do I/O operations, the better for performance. Even if we assume a comparably fast device, such as an M.2 SSD, look at an [interesting visualization](https://www.thomas-krenn.com/en/wiki/Linux_Storage_Stack_Diagram) of the I/O stack on Linux, for example.
* Always buffer your read operations when doing lots of small reads, a buffer size usually is equivalent to a file system page size, and that usually is 4096 bytes wide.
* Buffer your write operations by the same amount in the analogous case unless you need atomic operations. Do not forget to explicitly flush the buffer, otherwise data may hang in memory indefintely.
* When having a wild random access pattern without a need for appending to files, consider _memory-mapped I/O_ for its enormous potential of speeding up read and write operations. Again, because of _no free beer_ it comes at the cost of limited portability (but every platform has its API for this), and some need for caution in large files or [network storage](https://news.ycombinator.com/item?id=19806349).
* For reasons, never forget to set the binary (or `"b"`) flag when opening files. If the software ever touches Windows ground, not having this set on data that is not strictly human text to be displayed, it will implicity convert bytes related to line-endings.
* For reasons of convenience in times that nobody remembers, there are _readers_ in some environments that use implicit, i. e. system-dependent encoding when reading files. Stay away from them or always specifiy encodings explicitly (e.g. binary, UTF-8), as they are not portable otherwise.
* For doing I/O operations, there is sometimes a bunch of (system-dependent) types you can choose from: Synchronous (POSIX, mostly default), asynchronous (POSIX AIO, Node.JS) or batch/vector operations. Stick to the defaults of your environment unless you can identify needs for other patterns, and especially do not mix them uncautiously.
* When touching lots of files all the time, there is [room for tuning](https://opensource.com/article/20/6/linux-noatime) on some platforms: Not touching the `atime` attribute.
* In fact, I/O operations become a bottleneck so easily that I strongly recommend to have profiling tools at hand to identify the ratio of I/O waiting when looking for reasons of slowness around file operations.
* Logging is I/O &ndash; a side-effect. When logging a lot, the application may actually lose plenty of time flushing `stdout`, doing filesystem operations, or sending bytes across the network.
* Have a timeout whereever you do not want to wait forever, and also think of a proper handling when elapsed. Socket-based I/O often suffers from hanging indefinitely, blocking allocations, when done improperly in exceptional circumstances. Sometimes, foreign code has biting default settings. Do a proper research first, especially when talking to endpoints outside of your domain.
* Remember: the slower the I/O channel, the bigger the advantage of a CPU compressing and decompressing data. This is [why we use compression](https://www.pingdom.com/blog/can-gzip-compression-really-improve-web-performance/) in HTTP servers, also for dynamic responses.
* Close all the handles when done, and mind the exceptions or error cases. Handles usually represent operating system allocations that are otherwise exhausted eventually while the process continues running.
* On some systems, it is easy to test _no space left on device_ behavior as they expose a dummy device for this purpose. On Linux, there is not only `/dev/null` for redirecting data into the void, there is also `/dev/full` to simulate a disk without space.

### Streaming

Data on disks is easily larger than what fits into RAM. And since there is usually more than one process working on a host, constraints are not getting any easier. These are examples of tasks you will encounter at large:

* Reading a full set of records from a database into memory.
* Parsing the whole XML file into a DOM representation.
* Reading the whole file without checking its size first.
* Reading the whole data from a network connection to parse it in a 2nd step.

Some languages have tools that make it fairly easy to fall for these cases, the punishment they await: _out of memory_. It is not an optimization and I would not even call it a pattern anymore but a sheer necessity: _streaming_. It is not primarily about performance but about keeping the required amount of resources constant while facing virtually any kind of workload, and it starts by tasks as simple as reading data from a file which can be as big as the file system allows it to be.

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

There are many concepts a software engineer needs to know when remotly touching topics subject to security ([here is a guide](https://joyofcryptography.com/) for discussions and details on the math behind the following):

* _Cryptographic hash functions_: While a _hash function_ maps data into a fixed range of values, _cryptographic hash functions_ do the same while matching some security requirements:
  * There is no known way to produce collisions, and finding some is infeasibly expensive by brute force.
  * There is no known way to infer its input just by looking at some hashed value.
  * Depending on the context in use
      * they are fast to also work on large data, often backed by hardware implementations, for example [SHA](https://en.wikipedia.org/wiki/Intel_SHA_extensions),
      * they are deliberatly slow to make brute force approaches take even longer, e. g. to slow down guessing of passwords. _bcrypt_ is an example of such a hash function.
* _Salting_: Imagine two or more users using the same password. If an attacker obtains a password (e. g. by social engineering) next to a list of leaked password hashes, the attacker can identify all the other password's users just by looking at their identical hash values. _Salting_ the input by some unique or sufficiently random input makes this kind of weakness difficult again. Look at [bcrypt](https://en.wikipedia.org/wiki/Bcrypt) for an implementation example.
* _Message Authentication Code_ (MAC): How to make sure that something has not been modified illegally? One easy and common approach includes _hashed MACs_ (HMAC), i. e. `hmac(message + secret)`. The secret needs to be known to all authorized parties, of course. Make sure not to use ordinary cryptographic hash functions but only its HMAC-derivative where requried, for example `HMAC_SHA256`; this is imperative ([details](https://security.stackexchange.com/questions/79577/whats-the-difference-between-hmac-sha256key-data-and-sha256key-data)).
* _Symmetric cryptography_: The _same key_ is used for both encryption and decryption. Examples include _AES_ or _Twofish_. AES is [widely hardware-accelerated](https://en.wikipedia.org/wiki/AES_instruction_set) nowadays. Your cipher setup may require additional awareness towards correctly setting up [initialization values](https://en.wikipedia.org/wiki/Initialization_vector): Since data is mostly divided into smaller blocks (like 128 bits for AES) &ndash; what would happen if we encoded the same value with the same key over and over again? We get the same result, so an attack can infer that certain sections of data are identical, or even worse: discover patterns. See the visual demonstration in the provided Wikipedia article.
* _Asymmetric cryptography_ or _public key crypthography_: There is one key to be used for encryption (or verifying) &ndash; also known as _public key_, and another one for decryption (or signing), the _private key_. The keys are coupled mathematically by requirements similar to cryptograhpic hash functions, and as the names suggest, one is supposed to be shared and other is to be kept secret _at all times and under all conditions_. Mathematical concepts behind this include _integer factorization_, _discrete logarithms_ and _elliptic curves_. Known implementations of different feature sets include _RSA_ or _ECDH_. If the private key is leaked, everything related must be considered compromised.
* _Signatures_: First: Do not set _digital signatures_ equivalent to _signatures_ as you use to confirm an intent with legal binding by writing something at the of a letter; the only commonality is the aspect of _there is something attached to the message_. The digital signature is an output of a procedure taking the input and the _private key_, and that can be matched by using the corresponding _public key_, i. e. verified. This way, we know that the holder of the private key of the given public key has _signed_ the data. This signature is _free_ of semantics, it can indicate authorship, ownership, authorization, integrity &ndash; look at the use case.
* _Certificates_: How do we know that a given public key truly belongs to the one who claims it? Like _I'm truly your bank's online portal now_. Because you really know that other party and got the public key in a way that is subject to little risk of tampering. Or because somebody we trust for doing proper identity checks in a hopefully clean environment tells us: _yup_. A certificate is a signature of a trusted entity over somebody's public key. And mostly, there are middlemen who need to be trusted, who need to be trusted ... and eventually, your operating system or browser ships a bunch of _root certificates_ that are accepted to be at the top of the _chain of trust_. In the real world, things go wrong of course. So if some _certificate authority_ (the middlemen or root-men) makes a mistake, this usually results in some kind of _security fallout_ scenario, as everyone affected of the chain suddenly needs to act fast. Read stories of [DigiNotar](https://en.wikipedia.org/wiki/DigiNotar) or [Symantec](https://security.googleblog.com/2015/10/sustaining-digital-certificate-security.html). Google has [undergone approaches](http://www.certificate-transparency.org/) to spot illegally issued certificates, and there are [mechanisms](https://en.wikipedia.org/wiki/Online_Certificate_Status_Protocol) to structurally publish revocations of compromised keys.
* _Random number generators_: When _inventing_ keys, computers rely on random number generators. It is actually quite hard to think of a way to create randomness on a computer by just having plain old chips on it. There are plenty of ways that _look_ like randomness but [are actually deterministic](http://www.jbox.dk/sanos/source/lib/stdlib.c.html) (look for `rand` in there), given some seed value. And what do we use as seed? A constant, some timestamp of now? By reverse engineering or looking at the source code, an attacker could obtain a series of random values, try to find the correct seed for their replay, and predict the next ones, for example when used for secrecy for upcoming users. Operating systems try to gain entropy, and over time, lots of non-deterministic events take place to update its RNG state (like I/O operations, sensor values), but what if we need that early, very early after boot? [It may wait until entropy](https://wiki.debian.org/BoottimeEntropyStarvation). Systems that really depend on randomness for security are mostly equipped with hardware RNGs &ndash; and they may rely on radioactivity. Read a story of [Debian](https://freedom-to-tinker.com/2013/09/20/software-transparency-debian-openssl-bug/) that once failed to set up its RNG in a security system.

For reasons, asymmetric encryption is slow. Symmetric encryption and hashing, in contrast, are fast &ndash; see their hardware acceleration above. So real life examples combine almost everything above, see a short summary of HTTPS with [TLS v1.2](https://tls.ulfheim.net/):

1. Client and server exchange some meta data and _inventend_ random data on first encountering of each other.
1. Server presents a certificate for its public key to be verified by the client: _Integrity OK? Domain matches? Not expired? Not revoked? Signature chain leads to known root CA?_ ...
1. Client and server _invent_ ephemeral public/private-key pairs (server one's is signed, public key of the certificate to be used for verification), exchange their public keys.
1. Given the own private key, the other parties' public key and the random data at the beginning, both sides can now calculate a symmetric key to use for the payload using hash functions.
1. The payload is transmitted using symmetric keys.

Also signing involves notable actions:

1. The payload to sign is being hashed by a cryptographically secure hash function.
1. The resulting hash is being signed by the signer's private key.
1. The viewer calculates the hash value, and tests whether the public key, when applied to the signature, results in that hash value.

If someone was able to create a payload with a hash collision, the signature would still be correct!

* So when designing certain security related processes, stick to the established ones:
    * Communication: use TLS v1.2, implemented by libraries such as _GnuTLS, OpenSSL, Microsoft SChannel_
    * (A)symmetric data encryption, signatures: [choose](https://en.wikipedia.org/wiki/Comparison_of_cryptography_libraries) from a fitting library or consult your environment's manual
    * Hashing: _SHA3_ or _BLAKE3_
    * Hashing of passwords: _bcrypt_ or _scrypt_
    * Randomness: look what library supports _pseudorandom number generators_
* Regardless, keep an eye on what cryptography got into press for being cracked, flawed or considered too weak for near-future hardware. [SSL](https://en.wikipedia.org/wiki/Transport_Layer_Security#SSL_1.0,_2.0,_and_3.0) and [WEP](https://en.wikipedia.org/wiki/Wired_Equivalent_Privacy#Weak_security) broke many, many years ago already. MD5 and SHA1 hashes are [considered weak](https://en.wikipedia.org/wiki/Secure_Hash_Algorithms). And [MD4 is an example](https://en.wikipedia.org/wiki/MD4#MD4_collision_example) of a broken hash mechanism.
* You may, of course, use weaker hash functions or RNGs (such as `Math.random` in JavaScript, or `rand` in C) but do not when security and money are at stake.

Let us do not forget _all input is evil_:

* Whitelists are better than blacklists.
* Escape right before presentation or application time: This takes away all the questions and bad assumptions of _has it been sanitized already?_ Make sure you always do and right before it matters. And to prevent bad and ugly multi-escaping: just there.
* User input [always ends up somewhere](https://samcurry.net/cracking-my-windshield-and-earning-10000-on-the-tesla-bug-bounty-program/), but the most common cases to strictly apply escaping are (and there are libraries for that!):
    * rendering it within HTML (XSS attack),
    * putting it into SQL statements (injection attack),
    * creating regular expressions from it (denial of service attack, see below),
    * using it in shell arguments (injection attack),
    * using it in the evaluation of interpreted languages (injection attack),
    * using it in file names and paths (directory traversal and [denial of service](https://tldp.org/HOWTO/Secure-Programs-HOWTO/file-names.html) attack).
* Regular expressions are the first (but not the ulimate) choice of input validation for many cases. That is OK, but do not forget to properly address upcase and downcase, start and end of string, single and global application, EOL handling and encoding. Poor bugs have resulted from failures here.
* _Fuzzing tests_ are your best friend when trying to stress your counter-measures.
* Inserting an emoji icon is the second best test to check your input handling.
* Both the application of poorly-written regular expressions as well as input-based ones can take your system down, as it [did at Cloudflare once](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/). Be sure not to write ping-ponging greedy matchers following each other. Again, consider a grammar over regular expressions also for security concerns.
* Do not use C at the front line unless you really, really know how to do right. Microsoft estimates security vulnerabilities caused by improper use of memory to have a [share of about 70%](https://github.com/Microsoft/MSRC-Security-Research/blob/master/presentations/2019_02_BlueHatIL/2019_01%20-%20BlueHatIL%20-%20Trends%2C%20challenge%2C%20and%20shifts%20in%20software%20vulnerability%20mitigation.pdf) of all vulnerabilities listed in CVE. And it is probably not only because of so many newcomers to C. It is still technically possible to do this kind of bad &ndash; in a more or less easy way &ndash; in other languages as well (C++, Rust).

Aside from injection attacks or DoS attacks, there are other kinds of attacks you should generally be aware of:

* _Side-channel attacks_: Does guessing pieces of a secret lead to differences in the response time, or the power consumption? Is there any kind of leftover afterwards, like cache contents? Intel had this kind of bug [in hardware in recent years](https://meltdownattack.com/), other CPU manufacturers probably as well. It also holds for software, like algorithms terminating early or late, depending how much of the input is guessed correctly. Even comparing an input hash with a stored password hash (again, use something like _bcyrpt_ here!) naively &ndash; byte per byte until the end or the first difference &ndash; may beat blind brute-force attacks, [even over a noisy channel](https://www.blackhat.com/docs/us-15/materials/us-15-Morgan-Web-Timing-Attacks-Made-Practical-wp.pdf) like the internet!
* _Enumeration attacks_: Allowing somebody to systematically obtain data, secrets and statistics by just counting. Think of counting new users per day over some URL containing an incrementing ID, or obtaining rebate codes or digital vouchers by just increasing the "confidential" code number by one. And while a monotone growth is easily spottable, better enumeration attacks may look organic/random but are actually not (using [Feistel networks](https://en.wikipedia.org/wiki/Feistel_cipher) and just knowing the upper bound).
* _Filter attacks_: While statistics is supposed to abstract the individual data contribution, generously allowing setting of filters may reduce the sample size to a degree that you can infer data ththat you were supposed to protect.
* _Human factor_: The most frustrating part. Default passwords, shared passwords, bad passwords, written-down passwords, update fatigue, bad configurations, ignorance, gullibility, bribery. There is a whole discipline of _threat modeling_, going beyond the world of software.

For the human factor, there is a wide range of solutions of differenct convenience and cost. Embrace the _Principle of Least Privilege_ (POLP) all around your software. Funnily, there is not much difference between a human user and a deployed process when it comes to security factors:

1. If something is not your task, restrict to what is yours. There is authentication, permissions, a whitelist of actions (even system calls towards the OS, like [Seccomp](https://en.wikipedia.org/wiki/Seccomp)).
1. If something is your task now, it is no longer after you are done. Make your actors ask for a temporarily federated set of permission for the time they need it, protected by a second authentication factor. This way, higher privilege tokens do not stay alive for too long, or indefinetely.
1. Even if it is your task, it must not be carried out by somebody else. An injection attack will happily make it look like yours from a system setup perspective.
1. Something can go rogue, simply for bad use or configuration.

So even if you fully trust somebody, there is a stack of threats involved that do not care for your mutual trust. Limiting the potential damage, the _blast radius_, must be done regardless. The range of implementations of protection is too large to mention them here, so I strongly recommend to obtain designated literature.

As a closing word: Consider every topic before and after this one as a subject to security as well: Any way to externally provoke a system to leave its functional state, causing a denial of service, is a matter of risk, thus a security concern. For a large overview and deeper insights of domain-specific attacks and security engineering, I recommend the book [Security Engineering](https://www.cl.cam.ac.uk/~rja14/book.html) by Anderson.

Just another random collection of security issues that are part of every-day work, or somewhat good to have heard of:

1. Generally do not pass or request plain credentials via command line arguments. On Linux, a call to `ps -aux` reveals that you can see processes and arguments across users, and you may not always know who exactly is sharing the OS with you. File paths into restricted folders are OK.
1. A common alternative, passing credentials to processes by environment variables, does not suffer from this problem. But since it's so common, [malware can make a simple guess](https://www.bleepingcomputer.com/news/security/javascript-packages-caught-stealing-environment-variables/) where to hit-and-run. To reduce such a risk and raising the need for more individual exploits, using indirections (e. g. putting a file path into the environment variable instead) or using a designated credentials management API may be a suitable alternative.
1. Do not put or load credentials for building steps (e. g. downloading stuff from a package hub) into a `Dockerfile`. Even when deleted afterwards, it remains in the previous layer image and may end up in the wrong hands. Use `build --secret` instead.
1. This one is tricky: Even if you review source code thoroughly, it [may not be doing](https://www.lightbluetouchpaper.org/2021/11/01/trojan-source-invisible-vulnerabilities/) what it claims to do ([examples](https://github.com/nickboucher/trojan-source)). Invisible code obfuscation. Anyway, a very comprehensive guide to review source code with respect to security is [given by OWASP](https://owasp.org/www-project-code-review-guide/assets/OWASP_Code_Review_Guide_v2.pdf).
1. When setting up an SSH daemon in an environment that is new to you, or that you don't fully recall, _always_ check its [authentication settings](https://www.howtoforge.com/set-up-ssh-with-public-key-authentication-debian-etch) first. And when exposed to the web, people from all over the world will try to get in by using weak or default credentials. On Linux, [fail2ban](https://github.com/fail2ban/fail2ban) is happy to help on a small-to-medium scale.
1. If you are interested how an application is affected by AV interferences, you can experiment safely with an [EICAR test file](https://www.eicar.org/?page_id=3950).

## Databases

They are omnipresent, or what a friend once said: _Damn, you always end up with a database._ Whether it be you transactional ground, your large scale analytics, or just maintaining some local meta data, why write this on your own if there is probably a convenient solution available already?

But really know what kind of databases fits your needs _generally best_. While _data is data_ often allows multiple ways to store and query, a bad choice comes with drawbacks in terms of scalability, managability and tooling, connectors, or simply because of KISS.

Most software that labels itself as database-related falls into the range between the following two concepts:

* [ACID](https://en.wikipedia.org/wiki/ACID#Characteristics) &ndash; a strong focus on safety:
    * _Atomicity_: Operations are _all or nothing_, nothing results in a state of being half-way done.
    * _Consistency_: No operation violates contraints, and nothing ever slips through. Any attempts will be rejected.
    * _Isolation_: To some (configurable) degree, two concurrent operations do or do not mutually interfere with their changes.
    * _Durability_: Once an operation has been confirmed, its effects have manifested. Unless all your disks get nuked, it is visible even after an immediate shutdown.

  One or multiple operations in conjunction that meet all the ACID criteria are known as _transaction_.
* [BASE](https://en.wikipedia.org/wiki/Eventual_consistency) &ndash; A concept that just states: _Eventually, your operation's effects will reach full visibility_. Until then, the old state may return. And if there are two conflicting updates floating around for convergence, a resolution strategy is required.
* [CAP](https://www.ibm.com/cloud/learn/cap-theorem), since we are about to list uppercase database theorems &ndash; When having a distributed setup of database nodes, you may choose _just two_ of the following three properties:
    * _Consistency_: All nodes exhibit the same state.
    * _Availability_: The cluster is fully available.
    * _Partition tolerance_: The lines between the nodes can be cut so that the cluster splits into partitions.

  This is fun to think about by going through every combination: When promising consistency, no node must lose update connectivity (C+A), or otherwise I have to close the service while waiting for it (C+P). In another scenario, if somebody gets cut off, the node simply goes out of synchronization (A+P).

For everything that is not content by ephemeral, local state representations, we usually skew towards ACID satisfaction. So when in doubt, go ACID. Depending on the requirements, various databases make different promises with respect to properties of ACID. I strongly recommend to browse some [in-depth analyses by Jepsen](https://jepsen.io/analyses) on such promises, and how to get them cracked in some cases. Not sure if [this hillarious sticker](https://pbs.twimg.com/media/CWhO2jIUYAAbuiK.png) is related ...

That only answered how our database treats data operations. Let us summarize what is out there in order to save and query data:

* _Relational databases_ &ndash; Good old entity-relation (ER) model persistence with hard-wired relations and typed fields. A (mostly) uniform set of instances of an entity, normally to be seen as a table per entity, with one row representing an instance. Chances are good we operate by SQL here.
* _Graph databases_ &ndash; In contrast to ER, graph databases focus on instances, or _nodes_, &ndash; typed or tagged ones &ndash; and their individual relation among each other, the _edges_: _You (node) know (edge) me (node) since 2020 (edge property), but I do not know you (so unidirectional edge) but I visited (edge) Canada (node) in 2004 (edge property), so you know somebody who once visited Canada no earlier than 2004 (transitional edge to Canada)._ A lot of nodes and edges can actually be modeled as entities and relations, yet graph databases provide queries that vastly simplify working with a dynamic degrees of node-hops and relation directions. Imagine modeling ER and writing SQL for _Show me every known person to me that visited Canada after me and who also knows somebody directly who once visited the US_ &ndash; sounds edgy, huh? _Neo4j_ is a nice and widely-used example of a graph database.
* _Key-value databases_ &ndash; Nothing as simple as putting something somewhere giving it a name, well.
    * _Hash-based ones_: You use a key, and you better do not lose it. They are fast because of hashing, and anything but the whole key will not get you anywhere fast. Keys may be stored secondarily in plaintext as well. Famous candidates include _Redis_ or _Memcached_.
    * _Lexical ones_: The keys are stored lexically, mostly as you would read byte sequences from left to right in the same way as (some of) you did in the telephone book by alphabet. This allows reading by key prefixes, or scan ranges as well. _HBase_ works like that.
    * _Hierarchical ones_: Imagine folders and files as in a file system, using paths. Unlike lexical KV stores, there is an intrinsic hierarchy in a way that you must know some parent's path to query all its children, and their path as a key to some value. Examples include _etcd_ or _ZooKeeper_.
* _Document-based databases_ &ndash; In contrast to KV databases, these databases are not agnostic towards their values, the _documents_. In contrast to relational databases, they are usually less strict with respect to schemas, i. e. allowing documents to look different while operating over all of them at the same time. This often comes at the cost of sacrificing features that conventiently work on relations between instances. Examples include _ElasticSearch_, _MongoDB_ or _CouchDB_.
* _Time-series databases_ &ndash; A database with a strong focus on appending or logging instances over the axis of time, physically representing data associated to some timestamp. There are often retention policies and features including downsampling for compressing older data. Thus it makes this kind of database the first choice for a steady flow of events to be caputured, for a wide range of purposes (including monitoring and alerting, logging and billing). Open source examples include _InfluxDB_ and _Prometheus_.

Representatives of these classes often come with core and side features of related aspects (geo-spatial data, full-text search, analytics), and some systems promote themselves as _multi-model database_ (_ArrangoDB_, _Oracle database_).

Among these, databases may have a flavor, or should be configured to primarily serve one purpose:

* _Transactional_, or _OLTP_ &ndash; While not strictly referring to transactions as above, it refers to _writing to it_. If there are frequent changes taking place, both in schema and data, databases organize their persistance for flexibility and safety: updates to keyed values, introduction of new columns, deletions of instances, logs.
* _Analytical_, or _OLAP_ &ndash; When configured to serve the need to do analytics, like creating reports and doing data mining, databases will organize data for being fast under segmented aggregations, while being inserted or updated mostly by large batch operations, in a less frequent manner. A _column-based_ database will densely store one field of many instances, followed by the next block or field. If we had a _row-based_ (so OLTP) setup, we had to wait for much I/O striding time (on spinning disks) between fetching one particular value from every individual row. In a column-based setup, this data can be streamed contiguously, and calculated under constant operations.
* _Search_: I put it here since it actually requires to look at both aspects in parallel, having a little-to-zero-delay to the OLTP state while needing to act like an OLAP system. For this topic and everything to take into account there, I found a [valuable guide](https://scribe.rip/p/what-every-software-engineer-should-know-about-search-27d1df99f80d) ([archive](https://web.archive.org/web/20211018081413/https://scribe.rip/p/what-every-software-engineer-should-know-about-search-27d1df99f80d)) that is similar to this one, focussing on _searching_.

While all these _NoSQL_ databases are difficult to generalize &ndash; again, I recommend to individually check the Jepsen analyses mentioned at the beginning of this chapter &ndash; there is hell to get straight on SQL, i. e. the relational ones. Before all, the [rules of normalization](https://en.wikipedia.org/wiki/Database_normalization#Normal_forms), because everything that has not been designed that way is doomed to fail at light speed. I never thought to see violations at large scale in production for reasons of common sense, yet here I am:

* _1NF_ &ndash; Never compact data that is relevant for _relational_ purposes in the same column, have it atomic: Not a string of seperated IDs, _just one ID_. Storing a JSON string is OK if it could have been an opaque, binary large object (BLOB) instead, from the perspective of the relation.
* _2NF_ &ndash; Do not manage more than one logical, related entities inside of the same table as if they were subject to an inner join. Split them up.
* _3NF_ &ndash; Do not have stuff lying around in a table that does not contribute information to the primary key but something else. Put it away.
* _BCNF_ &ndash; There is one superkey, i. e. a minimal set of values that defines the rest of the row. If there is no such combination, it smells like your table lacks some relevant information.
* _4NF_ &ndash; If you have two 1:n relations, let us say `A -> B` and `A -> C`, do not have them stored in one table by columns `A, B, C`. Split them up.
* _5NF_ &ndash; You have taken the overall decomposition of tables to the maximum extent possible.
* One rule always implies all preceding ones.
* There are more rules, but the ones missing here are not part of the classic set of rules.

A _surrogate key_ is a key that takes away a lof of burden of finding or constructing unique identifiers out of your data. There are reasons _to always have one_:

* It is managed by the database at no additional application logic &ndash; except from being configured in the DDL.
* It is decoupled from your business data, thus immutable.
* No headaches with respect to being used as a foreign key somewhere. No need for cascades, no need for schema changes because of multi-column keys, simple to be used for extension at any time.
* It is the easiest way to externally address one row.
* Given that it usually is a sequence number, you can use modulo operations as one simple fallback for partitioning the data.
* You should even consider the use of a surrogate key for tables that were simply meant as a cross relation table, given the reasons above.

Reasons to optionally have some secondary, unique, immutable and atomic key for public use instead of the surrogate key (like a UUID):

* It prevents enumeration attacks.
* It remains publicly stable even under migration or arcane disaster recovery strategies.
* A primary key may be implemented by a tree exclusively ([PostgreSQL](https://www.postgresql.org/docs/9.4/indexes-unique.html)), whereas a secondary key may be configured to be subject to a hash.
* It is still easily addressable and can be backed by the underlying database by different means at little to no cost (uniqueness check, native UUID types and generations).

While some people consider the following topic as expert-grade stuff, I consider this essential to know when working with databases: isolation levels, the _I_ of ACID. Setting the isolation level may happen at different places: by a server default setting, by a session default setting, or as an individual transaction property. So what are they:

* _Read uncommitted_ &ndash; Transactions may see data that has not been committed or reverted by its originating transaction. So we see half-a-thing and broken promises.
* _Read committed_ &ndash; Transactions only see what has been committed, and so two subsequent `SELECT`s can return different results, both for committed changes and new records.
* _Repeatable read_ &ndash; When opening a transaction, two subsequent `SELECT`s may still read different results but only because it could not have been locked earlier as something was not subject to the lock in the first run.
* _Serializable_ &ndash; Two transactions cannot interfere with each other since they are ordered and executed linearly by the database.

The intent is clear: Choose between levels of performance and safety, depending on your requirements. To implement these degrees of isolation, databases work with different types and levels of locks, and [versioning](https://en.wikipedia.org/wiki/Multiversion_concurrency_control). Consider every single query a transaction, even outside of `BEGIN ... COMMIT` command, and even a plain and simple `SELECT` query: While it is mostly abstracted away by the way applications make use of the query result (getting a full page fast and at once), technically the database will maintain a pointer to reach out to every single row of the result set &ndash; until it is exhausted. That means that under the highest isolation level, slowly reading a result set makes everyone else wait on the affected tables.

Reality may indeed be complicated: What if we do some `BEGIN; SELECT ... WHERE status = 0; ... (business logic) ... UPDATE ... WHERE status = 0; COMMIT;`? When not serialized, the `UPDATE` may touch rows that have not been known to the `SELECT` since they showed up later, and now we will assume that they were subject to business logic. The bitter truth: We must help by requesting an exclusive lock to the table. You can often find `SELECT ... FOR UPDATE;` in manuals. Consult them for what is available. Of course, working with locks means summoning dead locks.

Indexes. Use them, and use them correctly:

* An index helps reducing the need to do record scans. In a worst case, your `WHERE name = 'Joe'` query makes your database scan millions of rows individually until it has found all the Joes, doing a so called _full-table scan_. An index will tell the database where to find all the Joes because it keeps track of them, as well as for all the other names. But: Depending on statistics concerning the distribution of values and specificity of some indexed value, a database may decide to go another way getting your rows than simply using some index.
* As for every data structure, database indexes also split up into two major types: hash-based and tree-based ones. There are also other ones for specific cases (full-text search, geo-spatial data, big data, ...), but let us focus here:
    * _Tree-based indexes_: Your primary key is probably one, and I guess it is the default type on most systems. As it is a tree, you can use more operations on these indexes (like `=, <, <=, =>, >`, and maybe also begins-with-tests on strings and null checks). For multiple columns of an index, the order matters: This way, you can make use of parts of the index, i. e. using criteria from left to right of the definition order. Rule of thumb: Set the order from left to right by descending use across your queries. Example: We set an index on `a, b, c`, we now accelerate many queries on criteria containing columns `a` and `a, b` as well, but not `b`, `c` and `b, c`. `a, c` will benefit as much as `a`. Also, tree indexes may drop the need for a sort-pass when using them in an `ORDER BY`.
    * _Hash-based indexs_: All column data is being used for hashing, thus only `=` criteria on _all_ involved columns make the index activate.
* Set indexes the way you need to support queries, by what you use in `WHERE`, `JOIN` and `GROUP BY` as columns and criteria.
* Do not simply index all the things. Indexes involve storage and need to be updated on any relevant change to the table. Even for sane use-cases, this may cause trouble at some point: See what Uber [once claimed](https://eng.uber.com/postgres-to-mysql-migration/) on such a scenario, and [some interesting](https://use-the-index-luke.com/blog/2016-07-29/on-ubers-choice-of-databases) thoughts about that.
* Indexes may have a total maximum length. So you cannot extend them infinitely, use any arbitrary type, or always convert string columns into wide-string encodings afterwards.
* Assume that only one index at a time can be used per table scan.
* Foreign-key constraints do not set up indexes automatically.
* Materialized views can also benefit from indexes.
* Most important: Know to read the `EXPLAIN` result of your query. Depending on your database, it shows the query execution plan, including key candidates, chosen keys, join types or hints for doing expensive operations, such as a full-table scan or file sorting. Use some offline schema to experiment.
* Some databases allow picking the index manually on a per-query basis, overriding the query planner. Be careful to do so, i. e. do an evaluation first, and do not expect portability.

Some general remarks on database use:

* Read the manuals. They are huge, but you should defintely not skip general best practices (or discouraged practices, see [PostgreSQL](https://wiki.postgresql.org/wiki/Don%27t_Do_This)) and optimization chapters (see [MariaDB](https://mariadb.com/kb/en/query-optimizations/)).
* Consider the use of _prepared statements_ in your client code when using the same queries over and over again, both for performance and security (escaping).
* Collation: The rule to sort strings. Depending on your culture, you may expect an `Ö` to be equal to `O`, or appear deliberately somewhere at the end, past `Z`.
* On MySQL, do not go `utf8` string encoding. It is `utf8mb4` you want to use, or watch your application suffer from exploding over [causing errors](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-utf8mb4.html) on attempts to insert emojis.
* Mind the rights. PostgreSQL for example does not allow granting `ALTER` statements. This might affect your ideas of having a limited user while also trying to do schema migrations under the same user. Changing an owner afterwards will not be easy as well, as you would have to touch all your backups, too.

In many cases, an _object-relational mapper_ (ORM) simplifies working with databases. While it saves large amount of time over interacting with a database, an ORM makes it fairly easy to fall into a bunch of pits that not everyone is always aware of. _Instance_ hereby refers to an individual table row as an object, some ORM environments also call them _records_ or _entities_.

* When not needing most of the columns of an instance, try to only load what you need. This especially holds for columns of type `BLOB` and `TEXT`.
* When having relations on entities, do not make _eager loading_ a default. The need for relations is a matter of view components, and penalizes you by loading much more from the database than required, and wastes your precious heap space. If your ORM makes that difficult to control, look for a better one.
* Avoid the use of 1:1 attribute tables (like `users`:`usernames`) for performance and code simplicity reasons unless there is a good reason to do so: hitting the limit of allowed columns per table, actually designing an 1:N relation, grouping permissions by table, or having a logically remote 1:1 attribute relation (`users`:`genome_codes`, `service_a_settings`, `service_b_settings`).
* If the range of entity attributes needs to be flexible, consider pitvoting the model instead of adding new columns: Using an 1:N key-value table, also known as [EVA modeling](https://en.wikipedia.org/wiki/Entity%E2%80%93attribute%E2%80%93value_model). It may require further approaches for efficiently searching entities matching different attributes then, like a document-based system.
* Know the strategy that is being used to load relations. Common strategies include joining, sub-selecting or 1:N loading. While there may be necessities to rely on one particular strategy, bad or incomplete configurations may cause 1:N loads when you could have done a simple join instead. Calculate the round trip time and execution time per query, multiply by N minus one: That is the time lost.
* ORMs may provide hooks that allow the invocation of code a certain points of an instance's lifetime. A common mistake is to start interacting with components far away in the world while there is a transaction pending. Depending on the isolation level and lock strategies, you start to stress the transaction management of your database because plenty of instances wait for a slow _substring-as-a-service.io_ response. This may be acceptable in circumstances, but I assume otherwise until proven. Know these points and prefer to model around such situations by introducing _pending_ states or similar.
* ORMs usually have at least two ways to interact with the database: One that is supposed to work on instances, and one that does not. One will create objects, invoke hooks, do validations. The other one skipps all that stuff. A simple _DELETE-BY-and-good-bye_-operation may not ask for instance lifetime cycles anymore. So chosing the wrong way will either cost you plenty of time, or makes you skip all your nice business code.
* Make sure your ORM application-side validations are not less strict than your database's.
* More than often, it makes sense to maintain an optimistic locking on a table by the ORM. This way, the ORM detects if somebody attempts to commit a stale object, i. e. somebody else did an unforeseen change in the meantime. Do not forget to pass that version token around, like over your HTTP interface, so that you can inform a user properly.
* Some generally cool features that are widely available across relational databases that are sometimes overseen:
    * _Common table expressions_ (CTEs): Predefining result sets by a `WITH` so that there is no need to rewrite them everywhere in a query (think of uses in different statements combined over a `UNION`).
    * Partitioning: Physically splitting row data by a partition criterion (like year of a date column). This way, data is located in different underlying files, allowing mixed read-only access and cold storage transfer.
    * _Window functions_: Ways to relate values of rows around to the current one, like calculating a rolling sum or a floating average.
    * Conflict resolution: When inserting batches of rows, violating constraints (like uniqueness) may abort the statement with an error. `ON CONFLICT`/`ON DUPLICATE KEY` modifiers may help skipping such attempts or doing a conflict resolution (overwriting values).

## Modeling

The less triviality, and the more people involved, the more I urge developers to spend a lot of time preparing ideas and models:

* To make sure everybody has understood the requirements: When people start arguing over something, at best, this rules out a divergence in the perception.
* To make sure as many constraints and impacts as possible have been put on the table, especially when working on some existing solution: Mostly, nobody has the same picture of some setup in mind, including gaps here and there. If somebody raises _Hold on, what about..._, you may have crossed out some difficulty at a very early stage, saving you lots of headache. Leave a lot of room to think about here.
* To have a basis for commiting plans: In a first step, identify what _logical_ units of your ideas ask for some in-depth thinking in a next step, so repeat the whole process at lower levels, thinking with interfaces. The more there is on the board, the more a project manager and you can design the first tasks &ndash; not necessarily implementation yet, but research, contacting the right people, asking for tools and budgets. Project managers love tasks, and in the best case, your very first tasks involve all elicitation steps to get things on the road afterwards, in the next iteration or sprint.

By the way:

* _Functional requirements_ &ndash; Requirements that refer to the purpose of the software, to the tasks to be fulfilled. This is what your customers are paying for, because they need it for doing their business better.
* _Non-functional requirements_ &ndash; Every other requirement, including: Supported platforms, service level agreements, user authentication, fancy UIs. To get the whole picture, I recommend to read the [headlines of ISO 25010](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010) whenever you need the whole catalogue to think about.

Depending on your organization, requirements will rain down in different forms: Less formal when discussing internal tools to boost some department's productivity, highly formal when working with a customer. _Requirements elicitation_ is a huge topic on its own, asking for a distinct group of people, requirement engineers. I assume that, in whatever way, we have somebody having done this for us here.

* It may not appear feasible for every software developer to read the (whole) requirement documents. Make sure to have at least two people reading these documents completely, synchronizing each other afterwards
* Make sure to present or refresh a customer, the business domain, the problem at large, systems you will depend on, 3rd party components, targetted milestones and schedules to every software developer as a whole.
* While developers often like to discuss and negotiate about the requirements imposed by some shareholder, it is sometimes just a waste of time. Something may sound stupid, and it maybe is, indeed. Yet you must focus on an _intrinsic_ test of the requirements:
    * Are there any obvious gaps?
    * Are there any evident contradictions?
    * Are there conflicts to some existing setup left unaddressed?
    * Is the shareholder fully aware of constraints that are imposed by some third party? Is some API not offering what the customer requests?
    * Is every topic of ISO 25010 (non-functional requirements) addressed?
One common misunderstanding that I have observed in agile teams: There is _always_ an initial set of requirements that somebody is going to pay for, or that is required to go into production, and failing to look at _that_ set completely, or simply ignoring (_backlogging_) parts of it as one tends to do in later stages, puts developers at risk to do decisions that do not pay off &ndash; while you must refrain from over-engineering (things you have no clue about if they ever come), do not start by shooting yourself in the feet if you know that a journey is longer than your body height.
In software management courses, [you are probably](https://www.researchgate.net/publication/221440391_Successful_software_project_and_products_An_empirical_investigation/link/0c96052d424d188171000000/download) told that software project success largely depends on clear and stable requirements, and having an understanding of the problem's domain. Act like you have been told that.

First, let us collect the things we are usually interested in visualizing around software:

* Requirements: Before even starting modeling software, try to model requirements out of the interviews, protocols or textual representations. This way, we have a first, presentable double-check for understanding what a client expects, as well as a nice introduction for every developer.
    * _Systems and actors_: What are the first (you), second (client) and third party players? What is their role, where are the boundaries of responsibility? Where do we find humans, where machines?
    * _Glossaries and domain models_: What are the elements the client sees from the functional perspective? What are they, what are they not, how are they related? What are fundamental constraints?
    * _Use cases, Interactions and Decisions_: What is supposed to be happening from the functional perspective?
* Implementations: Knowing the requirements, we can continue thinking about drafting technical solutions.
    * _Components_: How to logically design a setup of custom services, third party software, databases, storages, frontends, devices?
    * _Hosting and Provisioning_: How to physically place and wire components?
    * _Protocols_: How to communicate across individual components? From the logical perspective as in the [upper OSI layers](https://en.wikipedia.org/wiki/OSI_model#Layer_architecture) (5 to 7).
    * _Entities and Relations_: How to squeeze the domain model into something to work with as a software developer?
    * _Code_: How to actually encode all the stuff into your programming language without feeling ashamed?

Let us examine a bunch of ways to represent this:

* Requirements:
    * _System diagrams_:
        * Put in every second and third party component _logically_: Users, systems, devices.
        * Put in the first party components as blob(s) without going into any detail, they are the gaps to be filled later on.
        * Use names, icons, colors, provide a short description where possible: _ACME auth service_, _Google Translate_.
        * Draw lines that are supposed to indicate a general interaction.
        * Draw a different kind of lines (dashed, dotted), to group components.
        * _Do not_ paint use cases here, do not go into interaction details.
    * _E/R diagrams_:
        * Model entity and relations as seen from the functional requirements and constraints: _A user has an inventory_, _An inventory has many items, possibly none, and up to N_.
        * Model entity and relations when imposed by some second/third party, simply to find analogies and aim for mirroring (if applicable): _Google ads campaign_, _LLVM expression_.
        * _Do not_ model any interactions, just relations.
    * _Decision trees_: For any non-trivial way to acquire decisions &ndash; by the way, do you know [how Slack decides on bothering you](https://imgur.com/gallery/0p5bV) with notifications? Think of other ways to communicate this feature.
        * Make sure to label nodes by questions, atomically, i. e. one by one, represeting conjunctions (_and_) and disjunctions (_or_): _Value large enough?_, _Other value set to override?_
        * Make sure to label edges appropriately: by boolean values, by labels, by integers and probabilities.
        * _Do not_ model interactions here.
    * _Flow charts_:
        * Think of a start and all the ends of a _flow_, use bubbles: _Start_, _Success_, _Failure_, _Result A_.
        * Use a human-readable, logical description for every action, use squares: _Cancel subscription_, _Send invoice by mail_.
        * Use diamonds for decisions. They also represent loops: _Any item left in the queue?_
        * Put any non-trivial decision diamond into a seperate decision tree, use an abstracted question then. _User gave consent to data transmission?_
        * _Do not_ model actors here.
    * _Use case diagrams_: A flow chart to be enhanced for taking actors into account on individual actions.
    * [EARS](https://www.researchgate.net/publication/224079416_Easy_approach_to_requirements_syntax_EARS) and [Rupp's](https://francaballero.net/requirements_generator/): Methods to break down requirements into a human-consumable text structure that follows certain patterns, allowing data mining.
* Implementations:
    * _Components diagrams_:
        * In contrast to the _systems diagrams_, include _your_ components logically, and include their relations.
        * In the same fashion, include custom services, storages, databases, devices, third party software choices, general interaction, your all-winning ML models.
    * _Host and provisioning diagrams_:
        * In contrast to the _components diagrams_, focus on physical setups: hosts and their services, networks, devices, test setups.
        * When using provisioning systems, take a special consideration &ndash; or even a layer between these two &ndash;, for example modeling topologies of _Kubernetes_ and cloud providers.
    * _Sequence diagrams_:
        * Every logical component gets a vertical line, the time is on the Y axis and _flows down_.
        * Interaction is drawn by a line between some two lines, naming the interface: `--> GET /api/status`, `<-- 200 {...}`.
        * The focus lies on interface invocations, waiting, synchronization and local activity over time.
    * _E/R diagrams_:
        * Draft or model your representation towards a solution.
        * Be precise about soft and hard ownerships, cardinalities, hierarchies.
        * Borrow elements from _Class diagrams_, see more on this below.
        * Refrain from going deeper into language-specific aspects here.
* Fitting into both categories:
    * _State machine diagrams_: When there is a need to enforce a specific order or allowing a well-defined time for something to happen, _finite-state machines_ are your friend, both for thinking and representation.
        * [State machines](https://en.wikipedia.org/wiki/Finite-state_machine#Representations) should represent some closed state, i. e. one unit or system at a time.
        * State machines can be seen nested, so simply stick to the level of detail that is appropriate.
        * Think of all the states, think of one initial state.
        * Think of actions (transitions) that can change a state: This is the only legal interaction, reject everything else.
    * [Petri nets](https://en.wikipedia.org/wiki/Petri_net): Model an application in terms of _places_ that can hold _tokens_ (whatever number and kind you need), and those tokens advance through _transitions_. It combines modeling, interactivity, parallelism and visual representation in a cool way.
    * _Graphs_: Nothing beats drawing nodes and edges as you would do for the data structure mentioned earlier, when it comes to modeling relations and their weights, directions and ways.

The last bucket lists examples of representation models that have a huge background in computer science, and so they work as fundamentals in formal verification at different stages (_Can this use case reach a dead lock? What about the implementation?_) and exhibit all kind of interesting relations (_How to model some state machine as a Petri net?_). This is where some dry courses of theoretical computer science suddenly come in handy when trying to do something cool by combining modeling and theory, in order to make promises, testing ideas and finding efficient solutions.

### UML

I never encountered anybody for now who was remotely enthusiastic when talking about [UML](https://en.wikipedia.org/wiki/Unified_Modeling_Language). Or [WSDL](https://en.wikipedia.org/wiki/Web_Services_Description_Language), or some other incarnation of a [feature creep standard](https://xkcd.com/927/). I am no exception here, but I want to both prepare the section of tools below, and like to outline what use cases I found it really handy anyway.

Looking at the list of _diagrams_ of the previous section, UML provides a lot of them, maybe at a different name. Recommendations:

* Know the language-independent parts of [class diagrams](https://en.wikipedia.org/wiki/Class_diagram): Relations, compositions, hierarchies, generations. As the name _class_ indicates, it is closely related to object-oriented languages, seamlessly matching C++, Java, C#. Fortunately, the world is more than that, and some languages have different concepts, maybe not even classes: structs, traits, tables, tuples. Yet, let us take what is portable both across languages and diagram types (E/R diagrams) for general understandability.
* Know the [sequence diagrams](https://en.wikipedia.org/wiki/Sequence_diagram).
* Look at the remaining collection of diagrams if you are lacking creativity or need formalisms.
* Make use of more UML, and stick to all the conventions (instead of using custom formats), the less you know who is about to depend on interfaces and behaviors outside of your scope: interface users, your future but unknown coworkers, manual readers.

### Modelling toolsets

Sometimes, we need handy tools to model data procedurally. Fortunately, there are plenty of math functions or algorithms that help us. Here, we do not target precision, correctness or security, but performance and ease. Let's never forget the following (as usual, there is more than library readily available):

* Oscillation &ndash; having values that go back and forth periodically: _sine_ function.
* Smooth peaks: Using the _probability density function_ of a [Normal distribution](https://en.wikipedia.org/wiki/Normal_distribution) &ndash; generally, have a look at distributions for their variety.
* Software random values: [Mersenne Twister](https://en.wikipedia.org/wiki/Mersenne_Twister)
* Seemingly random values that go through a range without repetition: [Feistel permutation](https://medium.com/codezest/pseudorandom-permutation-using-a-feistel-network-48b617dd8c1)
* Smooth randomness in higher dimensions (e. g. for generating a terrain map): [Perlin noise](https://en.wikipedia.org/wiki/Perlin_noise) or [Simplex noise](https://catlikecoding.com/unity/tutorials/pseudorandom-noise/simplex-noise/)
* Hashing something quickly (e. g. for generating a key out of data): [MurmurHash](https://en.wikipedia.org/wiki/MurmurHash)
* Modelling and combining geometry: [Signed distance functions](https://www.alanzucconi.com/2016/07/01/signed-distance-functions/) ([some collection](https://www.youtube.com/@InigoQuilez/videos) to broad mathematical modelling)
* Predictably walking around on a surface or volume with the impression of locality: [Z-order curves](https://en.wikipedia.org/wiki/Z-order_curve)

### General ideas

After all those ideas and concepts, there are some things that are generally a good idea when working on designing solutions:

* Remember, it is all about sharing software engineer knowledge easily, validating requirements and picking up ideas at some later point.
* People like visuals (sorry, blind guys, I have no idea here), so make a consistent use of shapes, colors, positions, labels, images, interactivity.
* Do not mix representations into some super-blueprint, it will not work and fail for being indecipherable at every non-trivial scope. One aspect at a time, let UML be a guide.
* Do not mix scales. High-level models should remain high-level, and similar intermediate- and low-level models. Nobody ever looks at everything at once, but only at what is the required point of entry. Add information that is essential, but skip what better fits into some more detailed view. A normalized specification of these view levels can be found under the [C4 model](https://c4model.com/).
* If models stick close to the code, i. e. working with language specifics and actual code lines in parallel, make sure not to lose yourself in synchronising either part. Better abandon that idea or make sure your tooling perfectly fits into the environment.
* Have the tools available to continue working on it. ASCII art and some exported JPEG image file may look cool, but the next one doomed to work on it is likely to have the day ruined. See below for some ideas here.
* When sensible, combine your representations with what is appropriate: Pseudo code, illustrations, literature references, formulas, plain old text. Wiki articles often allow some full-scale environment for elaboration.
* Speaking of wikis, and evenly important: Manage all that stuff well! Know how to find it, how to search by related terms, how to quickly contribute to and update material. Have it available by hyperlinks in your articles, readmes, code file headers, task trackers.

As there are too many tools out there &ndash; generic, language and domain specific ones &ndash; here are just some generic tools to start with:

* Suitable drawing tools: [diagrams.net](https://app.diagrams.net/) (was _draw.io_, strong general recommendation), _Microsoft Visio_, [Inkscape](https://inkscape.org/).
* Sequence diagrams: [sequencediagram.org](https://sequencediagram.org/)
* For algorithmic sketching: [Processing](https://processing.org/)
* Wikis, we just named them: self-hosted (_Mediawiki_), as a service (_Confluence_), piggy-backed (_GitHub_ repository wikis).
* Visual Markdown editors with syntax support: [Typora](https://typora.io/)

Also, an ultimate fallback tool for rough visual sketching: _Microsoft Powerpoint_. For more tools, consider the Wikipedia collections: [diagrams](https://en.wikipedia.org/wiki/Category:Diagramming_software), [UML](https://en.wikipedia.org/wiki/Category:UML_tools).

Help yourself &ndash; even some technically cheap approaches may help storytelling your ideas a lot!

Since no topic on software modeling is complete without naming them, a bunch of principles that help (re)factoring a model, or just a high-level idea:

* [SOLID](https://en.wikipedia.org/wiki/SOLID): Focus on object-oriented environments, but somewhat portable:
  * S &ndash; _Single resposibility_: Do not do too much in your unit, preferably just one _thing_.
  * O &ndash; _Open-Closed principle_: _Open for extension, closed for modification_, design to leave a unit's (binary) code in peace while allowing to have an alteration slip in front of it.
  * L &ndash; _Liskov substitution principle_: Replacing something with its subtype should go unnoticed from the functional perspective.
  * I &ndash; _Interface segregation_: Single responsibility for interface designing.
  * D &ndash; _Dependency inversion_: Prefer the use of abstractions (interfaces, higher-level classes, abstract classes) over concretions. Like allowing a stupid test surrogate class to sneak in, not just its brother of production.
* [MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller): Most of us probably learn this from web frameworks or mobile applications, but its underlying concept is much broader:
  * M &ndash; _Model_: Logic and data that works _as is_, not aware of how somebody or something looks at it.
  * V &ndash; _View_: A representation of one or many models: a load into a UI component, a data serialization, a context-sensitive decoration.
  * C &ndash; _Controller_: Loads model(s) and view and wires them together, with flow-details depending on the context (also see _MVP_).

For many more _patterns_ and _anti-patterns_, pick your context and language of choice for more literature. Have you ever thought of _Hey, let's solve this by an 'abstract-factory pattern'?_ No? Me neither. So far, I have not seen anyone designing software by patterns from top to down _upfront_. Instead, we put ideas together and hopefully organize into some way that eventually ends up in some pattern, not in an anti-pattern. Otherwise, I really want to know the person that claims to have designed Spring's [AbstractSingletonProxyFactoryBean](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/aop/framework/AbstractSingletonProxyFactoryBean.html) before writing a single line of a web-service in Java, and not by facing some concern that brought us here.

A collection of random and portable _anti-patterns_ that I frequently encountered so far, and that does not fit into the other sections alone:

* Doing more, or something very different, than what the name of a method suggests. If your unsuspicious-looking class `BoringStruct` has an unsuspicious-looking method `setValue`, make sure it is _just_ doing that, not sending an email to the customer of that newly set value, not growing tomatoes by the amount of _value_, not doing anything _but_ setting the value. Despite some questionable modeling, having `setValue` and `setValueAndGrowTomatoes` in `BoringStruct` is Ok, `setValues(..., bool tomatoes = true)` is _not_.
* Doing too much method overloading. While it is nice to a certain, little degree, depending on your language, wildly adding methods that take abstractions _in addition_, or being subject to arcane type casting, may completely change where you end up from one minute to the next. On the tiniest bit of risk for this to happen, start distinguishing methods by name.
* Abusing private member fields for passing around values between invoking private functions. This introduces a potential or actual non-determinism when there is no synchronization: Two parallel accesses to some instance suddenly start to interfere for no obvious reasons. Have members represent the instance's state, not your laziness to store two lists of stuff between doing this and that, and use the local method stack instead, always. Or in other words: How to design classes with names ending on `Service`, `Client` or `Factory` wrong.
* Falling for _microservices_ for the wrong reasons (some article on _medium.com_?); and just maybe use the term _micro_ less, since most actually are not so micro anyway. Good and very good reasons to have a diverse range of _services_:
    * Different requirements towards the underlying platform (OS, hardware).
    * Scaling independently and meeting different constraints.
    * Reduction of blast radius risks over having logically unrelated stuff close together otherwise.
    * Having people or teams that use whatever tech they like and talking over interface is simply sufficient.

  Signs that some guys maybe went for that hype too early:
    * Having data partitioned across services that is frequently needed together, failing at performance or exploding in heap usage because of joining data.
    * Ending up using the the same filesystems, database and tables to overcome the previous issue with close code duplication.
    * Not knowing a way how to safely migrate services and schedule the hierarchy without taking everything down, i. e. sacrificing uptime and SLAs (suddlenly you understand the need for something like [istio](https://istio.io/) &ndash; damn, Kubernetes wasn't the end).
    * Not knowing how to trace behavior across services safely, fuzzy ways to correlate errors (have a look at [OpenTracing](https://opentracing.io/)).

  ~~Micro~~Services are not a per-sé solution to everything. Has XML been? Blockchain? Similar to that _AbstractSingletonEtcThing_ above: Start designing over the requirements, not by the patterns.
* Do not reinvent the wheel when thinking of external interfaces. There are plenty out there. Some guidelines to look at:
    * [CLI](https://clig.dev/)
    * [RESTful](https://restfulapi.net/) and [GraphQL](https://graphql.org/learn/)
    * [Signals](https://www.sharcnet.ca/help/index.php/Signal_Handling_and_Checkpointing) (mostly non-Windows)
    * SQL with [DIY backends](https://calcite.apache.org/docs/tutorial.html)
* If you design a library or SDK, users may want to mock components of it for testing. Depending on the language, do them a favor by:
    * Providing public abstractions and interfaces to customize for testing.
    * Allowing (optionally) injecting components that encapsulate otherwise unwanted side-effects.
    * Refraining from making use of language features to bar your public components from being mocked (like Java `final` classes and methods).
    * Allowing to configure non-production, custom-built mock server hosts, even with TLS verification disabled.

## Testing

Over the time, I found the the question _Is it designed well?_ equivalent to _Can you show me how to test it?_. Having the tests at hand helps us to understand the following:

* How to do little or minimal setup?
* How to actually use it? How does input look like?
* Interaction of components by isolating errors and regression errors vertically (it looks good up to _that_ layer of code) and horizontally (we have messed up working on _these_ inputs).

If something helps us understanding setup, use and blast radius more easily by looking at smaller, dedicated code snippets, we can judge the design for being good. Our holy abstract-factory pattern alone will not help much here, I have seen such things to be completely out of ease for testing.

Whatever we test, testing always challenges two design aspects:

* _Testbed-ability_ &ndash; The ability to only look at what we are interested in, keeping away all other side-effects that also steal our setup and run time.
* _Observability_ &ndash; The ability to unambiguously look at the detailed effects of our inputs. The less we are able to judge with confidence, the worse.

_Test-driven development/design_ (TDD) is a very good way to train people with little to no experience in writing tests for these two concepts from the very beginning of writing code. With some degree of experience, you probably think less in terms of TDD but going for better designing that makes it hard to distinguish how you actually spent your time writing the resulting code &ndash; everything else is more like a dogma.

Looking at tests, we have multiple dimensions of what to think about:

* logical layers (ranging from unit to end-to-end tests),
* specifications and assumptions (white and black box tests),
* non-functional aspects (performance, resilience).

Details of definition and layering slightly vary by context, language or framework, but these layers of testing are to be found almost everywhere:

* _Unit tests_ &ndash; The smallest pieces of executable code: methods, member methods, static portions. Expecting them to do what they are supposed to do locally.
* _Integration tests_ &ndash; The combination of suitable units under controlled playbooks, also using underlying systems in a test mode (databases, file system, mock servers). Expecting assumptions to hold across units.
* _System tests_ &ndash; The invocation of defined system interfaces, like invoking the executable and its parameters, opening network connections and doing HTTP requests or other interactions. Expecting well-defined specifications from the interaction level to be fulfilled.
* _Acceptance tests_ or _End-to-end tests_ &ndash; Combining real-world interactions with a system for fulfilling the business case. Executing tests on the highest level of interaction, having a full-scale test setup underneath: UI interaction, workflow views over heterogeneous components, interacting with remote services and hardware.

Regardless of what kind of test level we are looking at, we can write tests by either knowing its implementation, or just by specifiying its expectations from an outsider's perspective:

* _White-box tests_ &ndash; The implementation is known with respect to execution paths of the underlying code or programs, and in the knowledge of characteristics of the implementing system (like testing for/against a desired/unwanted configuration setting).
* _Black-box tests_ &ndash; Roughly, when having a certain input, a certain result is expected as an outcome, regardless if powered by a quantum machine or [The Mechanical Turk](https://en.wikipedia.org/wiki/Mechanical_Turk).
* _Gray-box tests_ &ndash; A blend of both ends, like expecting a particular use (white-box) of an injected dependency (black-box).

White-box testing is subject to some controversy, usually when it comes _... but the coverage! It just dropped._ Well:

* White-box tests do not focus to answer the question of doing the right thing (specification), but of doing things right &ndash; in terms of having written code that does not end up producing errors given some legal inputs.
* A very good reason to have a _suitable_ degree of white-box tests is working with languages that are highly dynamic, i. e. not allowing an inspection-time assertion whether a variable or method is defined on use or not. Such languages include JavaScript, Ruby and Python. Which is probably a strong motivation for having something like _TypeScript_.
* _Suitable_ in a way that code may exhibit an exponentially growing space of possible execution paths. Real-world _coverage_ is calculated in a simple way by measuring if _any_ test in your test suite ever touched that line. But what if just one of these paths leads to an error, and there are already lots of `if`-branches inside your code? Coverage number grins at you, manager is having a break-down.
* For their pessimistic stance of maintainability over growing code, people putting their hands at an implementation later will probably spend more time identifying existing test cases and strategies and think of ways not to make cases explode exponentially: _The happy-path™_, making testing economic since 1958.

So, skipping white-box tests for typed languages? Or altogether? Fortunately, there is nice way through called _mutation testing_.

_Mutation testing_ requires the help of some tool that knows how to read conditions of the underlying unit (thus a white-box): What if the tool simply mutates your code a bit (inverting conditions, exchanging operators or constants), and _none_ of your tests indicate an error afterwards? We have failed to write a test case that checks hitting an execution path for the wrong reason. That _mutant code_ is said to be _killed_ by adding such a test. If a mutation goes unnoticed, so a human error will.

_Black-box testing_ is usually more pleasant since we are testing whether we are doing _the right thing_: Adhering to interfaces, input specifications or standards, or simply testing whether some bug report of inputs or use cases can be reproduced, becomes fixed, and stays fixed (_regression test_). Hold on, a bug report? For my full suite of mutant-safe white-box tests and all my black box-tests? &ndash; What if we simply missed something completely? There is probably little help against missing a page or two of the spec document, but fortunately there are tools that help us go through much of the known stuff:

* _Fuzzing_ &ndash; Throwing random things at your system. Fuzzing refers to generating input values by some strategy, but also to permutating calls, like API calls and system calls. [syzkaller](https://github.com/google/syzkaller/blob/master/docs/internals.md) has found bugs in the Linux kernel over the recent years by fuzzing syscalls, [CSmith](https://embed.cs.utah.edu/csmith/) helped finding bugs in C compilers over legal source code. But how to do so without wasting a huge of amount of time over complete garbage? One way to do so is grammar-based fuzzing. A grammar specifiying legal input can be used for two things: 1.) Testing whether the system responds to some valid, random input following the grammar correctly and 2.) whether it rejects every random break-out from the grammar. Fuzzing is actually a very cool topic, helping in black-box tests, security and resilience. Research has found a broad scope for mining actual test-inputs (also from a white-box aspect). Please refer to something like [The Fuzzing Book](https://www.fuzzingbook.org/) for an overview, techniques and code.
* _QuickCheck_-ing &ndash; _QuickCheck_ is the name of the original Haskell library generating tests over property descriptions. I'm sure it is some kind of fuzzing but it is worth its own mentioning: Following the type signatures/hints, it generates an amount of inputs and tests for the specified properties to be fulfilled. If something breaks the property, the input is attempted to be reduced to the culprit (type). [ScalaCheck](https://www.scalacheck.org/) gives a nice impression of such an implementation, with other languages having [similar tools](https://en.wikipedia.org/wiki/QuickCheck#Software).
* _Boundary Value Analysis_ (BVA) &ndash; A very simple tool to do by hand, following the idea: _Many errors happen at handling boundary values_. `OutOfBoundsException` or `Uncaught TypeError: X is undefined` sound familiar? No matter what you need to test, _always_ test the boundary values, basically, and building up on:
    * Integers: legal maximum, `0`, legal minimum (signed types), maximum collection/string index, and +1 of that value
    * Floats: `Infinity`, `NaN`, `0.0`
    * Reference types: `null/nil/None/nullptr/NULL/undefined`
    * Strings: empty strings, blank strings, emojis
    * Collections: no element, one element, multiple elements

    Custom and composite types probably have analogies to test in the same matter.

Some further hints on testing:

* If you have to write a custom test runner and need to think of a way to output, consider [TAP](https://testanything.org/) for a simple pattern.
* Research for tools to replay a subset of remote host communication for running in an isolated system environment, examples include [Ruby VCR](https://github.com/vcr/vcr) or [Java WireMock](http://wiremock.org/).

## The Project

Hereby, we understand _project_ as the software-centered environment around a software product and its development, so the mentioned aspects should not be consued with _project_ as in _Project Management_ (the Gantt charts and stuff). Every non-private project, open or closed source, should be set up under the following assumptions:

* There will be more than one person involved, or another person after you.
* That somebody will start by little to no knowledge about the past, maybe also without any knowledge about the current state.
* That somebody will probably arrive by a blank setup, that is not what you likely need to get things running.
* That somebody is biased and maybe needs to be kept away from the idea to _just rewrite it_ or _doing my own thing_ because the entry into the project is just frustrating, and not because there is an otherwise good reason to do so.

### README &ndash; no really, read me, but also write me

When using GitHub, GitHub may show you projects that may be of your interest. Sometimes, I click one of them because of the name, the main technology, or maybe just for curiosity and boredom. _Sometimes_ as in _way too much for my expectation_, I end up in a project and have little to no idea what this is about. While there is a `README` file, it is not helpful to an outsider in terms of understanding, but also leaves nothing but a heuristic assumption of how to get into it.

A `README` is part of the much larger environment of documentation, yet it serves a very important idea. Let us call it the _Principle of first touch documentation_ (PoFTD): What is it what we see on the root level of the software project? And more generally: What is it that I have _here_, no matter where I am in the hierarchy exactly? But let's start by a top-level `README` file:

If we have a collection of loosely coupled things (let's say scripts or schema files):

* What do we collect here?
* What belongs in here, what does not?
* What tools and setups do I need to work with whatever here, and where to obtain them?
* What is imperative to know?

If we are on the root level of a logical unit or suite, please mention:

* A one-liner what this is.
* A _tl;dr_ (_too long; don't read_) paragraph or enumeration that describes a little more what this is.
* Links for further resources (Wiki, Homepage, `docs/` folder) and, if available, pre-built package downloads.
* If applicable, a short example demonstrating its use for a better understanding, maybe even a screenshot.
* The list of requirements (and exact version numbers where required) to build this project.
* The build and test instructions.
* The instructions to make it work and deploy (in simple circumstances).
* Unless asking for some large-scale documentation in a designated place, a description of configuration and parameters.
* If applicable, notes how to contact maintainers, ask for support and conditions for contribution.
* If applicable, a short mentioning of license concerns (with full terms to be put in a seperate file, like `LICENSE` or `COPYING`).
* Use some sane formatting, that does not require a reader (so no PDF and RTF; HTML only if accompanied by some other format): Plain text (maybe [RST](https://en.wikipedia.org/wiki/ReStructuredText)) and markdown are common ways to go.

If the project is of non-trivial size, apply PoFTD down the line, going more into detail where it makes sense:

* As a sub-`README` in a subfolder.
* As a comment block in a module or package root file.
* As a comment block in a source file.

In some projects, maintainers are pedantic about having correct license headers in source files but totally lack what this unit is about, and what's technically going on here, or just don't know anymore and that's equally bad. As a consequence, people are forced to reverse-engineer mechanisms, signatures, edge-cases &ndash; and chances are good that they are going to miss something, even after spending a lot of time there. So do not hestitate:

* To describe what a code unit is concerned about,
* to demonstrate how inputs may look like and what is going to happen to them.
* to mention the mechanisms that are implemented/used (_we are using a DFS/FFT/Kayutsu-Meinhorst decompsoition to ..._), and where exotic things are described in detail.

Close-code documentation (function signatures, classes, packages) profits from following some documentation notation that supports creating a nice looking (such as HTML) documentation of it, or to be used directly inside of an editor/IDE. Examples include _Doxygen_, _JavaDoc_, _PyDoc_, _RDoc_.

### Guides

Depending on what you are developing, consider providing example-driven guides. With only anecdotical justification, I find documentation that provides guides with examples of code of how to cover 50% of your primary questions when using your software or library much more helpful than being forced to read through 40 chapters first, and I doubt the ordinary developer is capable of ingesting that much quickly and with solid persistence.

Two good examples include: [Rails guides](https://guides.rubyonrails.org/getting_started.html) and [Jooq tutorials](https://www.jooq.org/doc/3.15/manual/getting-started/). Focusing on what matters first, brief and clear code snippets of how to do it, probably allowing the viewer to Ctrl+F to the sections for particular questions, maybe even just by buzzwords.

In contrast, look at how much _Spring_ [needs to tell you](https://docs.spring.io/spring-framework/docs/current/reference/html/) how little _you_ have to do for yourself (yes, there are dozens of _Getting Started_ [guides](https://spring.io/guides#getting-started-guides) taking 15-30 minutes _each_).

Help your users and developers to quickly adopt the project and to bring them on the right path. [Here](https://daniel.haxx.se/blog/2021/09/04/making-world-class-docs-takes-effort/) is another manifest and high-level guide towards _world-class docs_ by the dev of _cUrl_ that I do not object.

### Code contribution management

I closely stick to features that are well-known to be available and used with `git` version control. Every interesting, multi-collaborator project needs a bunch of policies to keep the degree of frustration low and management easy. For everything, of course, there is probably some kind of religion around it, but the core remains the same:

* _Commits_:
    * Title: What did I do where? (Good: `FS: support for async I/O`, bad: `bugfix`, also [xkcd](https://xkcd.com/1296/))
    * Body:
        * When non-trivial, a _change_ rationale. (Good: `This fixes a race condition when ...`)
        * _Trace links_, such as a requirement ticket number, bugtracker ticket number, GitHub issue number.
    * Convention examples: [Conventional commits](https://www.conventionalcommits.org/en/v1.0.0/), [Semantic commit messages](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716).
    * Generally good ideas:
        * No commit ever carries two unrelated changes, also known as _atomic_ commit.
        * A commit is &ndash; ideally &ndash; not breaking building and tests.
        * Cleaning up/fixing commits before going public. Get familiar with [interactive rebasing](https://git-rebase.io/).
    * Profit:
        * _Bisection_ &ndash; When looking for a subtle introduction of bugs, `git bisect` is a powerful tool to find a commit that introduced something. But if the amount and quality of commits is unnecessarily bad, it loses its power quickly ([usage tutorial](https://www.tutorialdocs.com/article/git-bisect-tutorial.html)).
        * _Tracing_ &ndash; When years pass, and people come and go, it may help to avoid mistakes of the past and recover the context and rationale of decisions. Maybe also somebody comes up with an idea for automatic ingestions, or simply for some later ISO requirement.
* _Branches_:
  * Naming: It's never wrong to have a name that helps recovery after forgetting a branch after a while. It's quite common to also include a trace link, such as `issue-123_mac_performance`.
  * Semantics: What branches do you need (version lines, customer lines), for what kind of development (milestones, features, bug fixes)?
  * Updating: How and when to pull updates from its origin into the branch?
  * Merging: _squashing_ (all commits collapse into one), _merging_ (makes the history look like tracks and switches) or _rebasing_ (linearizing the history)?
  * Convention examples: [Git flow](https://nvie.com/posts/a-successful-git-branching-model/), [GitLab flow](https://about.gitlab.com/blog/2014/09/29/gitlab-flow/), [Linux](https://www.kernel.org/doc/html/latest/process/2.Process.html).
  * Generally good ideas:
      * Do not mess up git concepts of merging and rebasing.
      * Avoid cross merging at all costs (if there is a good reason: cherry-picking), otherwise you probably end up in hell.
  * Profit:
      * As little merge conflicts as possible. Cross-merging and rebasing of different branches (look at [this ... impressive](http://justinhileman.info/article/changing-history/) network) at a certain point and dimension may lead to painful, hour-long conflict resolution. They will probably fail, and eventually, we have to start over. Simply stick to the rules!
* _Versioning_: Depending on the environment and needs, versions may be helpful or just ignored (e. g. by considering git revision hashes sufficient). _Tags_ are your friends. A common and simple to understand schema is [Semantic versioning](https://semver.org/).
* _Reviewing_:
    * What to obey? Agree on requirements for getting code reviewed for actual merging: code conventions and quality, availability of documentation and tests, the positive results of code scanners.
    * When to start? I have seen policies to publish branches, e. g. by a _GitHub pull request_ or _GitLab merge request_ only when they are considered _ready to review_. I considered WIP-publishing often as a useful place to publicly put discussions on development related to code, and for asking specific questions when people work across the globe. Help yourself with labels and state indicators.
    * Who to involve? Who are suitable reviewers, who is required to grant merge permission? Who executes merging?
    * Profit:
        * No losing or rotting of branches, getting the right people to review the code, saving time.

Also, if there is some broader or public interest in the project, consider maintaining manual changelogs that are structured, ordered and focused on what is new. It is never fun to dig through hundreds or thousands of (poorly) written commit and merge messages to get a general impression. Version guides with explanations, schemas or screenshots are even more appreciated by users and developers. If there are breaking changes, highlight them as such and provide migration instructions.

### General tooling

Periodically and/or right before accepting code, the following kind of tools should take their turn:

* Linter: Checking compliance over code conventions. Examples for such tools include _Checkstyle_, _Clang Format_, _Rubocop_ or _pep8_.
* Dependency scanner:
    * Vulnerabilities: Is there a package dependency in the project including discovered security vulnerabilities? This check can be carried out by code hosters (GitHub, GitLab) for any major package ecosystem, and also by some package managers alone (such as `npm`, or `mvn` with a plugin).
    * Licenses: Is there a new package dependency, or a sub-dependency, that includes a License that is banned? It should also print a list of all involved licenses on demand.
* Generic static code analysis (such as _SonarCube_, _go vet_ and _Clang Static Analyzer_):
    * Can we identify possible bugs and smells, bad practices?
    * Is there code that uses deprecatations or even insecure methods?
* Test runners:
    * Are all the tests still running, and running without errors?
* Packagers (if applicable):
    * Can we still produce running deployables?

Another checklist, primarily designed for Open Source Project best practices, is the _CII Best Practices_ initiative, that you can self-certify when adhering to the [criteria](https://bestpractices.coreinfrastructure.org/en/criteria/0).

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
* To mention the major OSS licenses &ndash; and _just to outline them roughly_ (this is not a replacement for legal counselling):
    * [1](https://opensource.org/licenses/BSD-1-Clause), [2](https://choosealicense.com/licenses/bsd-2-clause/), [3](https://choosealicense.com/licenses/bsd-3-clause/)-clause BSD, [MIT](https://choosealicense.com/licenses/mit/), [ISC](https://choosealicense.com/licenses/isc/): Use how you like to do, but obey where the authors want to see their copyright notice in distributions. No patent grant, warranties, liabilities.
    * GPL [v2](https://choosealicense.com/licenses/gpl-2.0/), [v3](https://choosealicense.com/licenses/gpl-3.0/): Source code must be made available, modifications must be outlined and subject to the same license, and that also holds for most cases of making use of GPL software by another software (but not when be used over command line interaction or network). Obey previous copyright (or -left) notices and user rights. No warranties, liabilities.
    * [AGPL](https://choosealicense.com/licenses/agpl-3.0/): An even stronger focus on copyleft than GPL, as it considers the use over network as distribution, so you must make the source code of some server available if its components are subject to AGPL.
    * LGPL [v2.1](https://choosealicense.com/licenses/lgpl-2.1/), [v3](https://choosealicense.com/licenses/lgpl-3.0/): A weaker focus on copyleft than GPL, as it does not consider the use of dynamically linked code, i. e. it is still usable when stand-alone, as subject of falling under the same license. This is why some libraries subject to LGPL can be found in projects with incompatible licenses.
    * [Apache License v2.0](https://choosealicense.com/licenses/apache-2.0/): Grants a permissive use while requesting copyright notices and outline of changes to the source code. Grants patent use, but not warranties and liabilities.
    * [Mozilla Public License v2.0](https://choosealicense.com/licenses/mpl-2.0/): Grants a permissive use while requesting a file-based copyleft, i. e. disclosing changes to source code files that are subject to MPL. Grants patent use, but not warranties and liabilities.
    * _Public domain_ &ndash; Publicly floating software, or so. A difficult topic since there is such thing in some jurisdictions. It is probably OK if the author(s) explicitly state a public domain release or an equivalent one, but if there is no such credible statement, consider it taboo. A better alternative for software is the [CC0](https://choosealicense.com/licenses/cc0-1.0/) or [WTFPL](https://choosealicense.com/licenses/wtfpl/) for addressing the possible lack of _public domain_ regulations in an internationally acceptable way.
    * Everything else: There are lots of less common ones, so read the available texts or comments, at least. For any custom ones, well, read through.
* Generally assume that the use of trademarks and patents is not granted unless explicitly stated. So do not use them until then.
* _Software patents_ generally have a hard time around the world. It is more likely to face restrictive copyright agreements or coupling of trademark use granting for advertising.
* For asset licenses, there are also some to know about &ndash; since you as a software engineer will also choose an icon or data set, or presentation banner from time to time:
    * [Creative Commons Licenses](https://creativecommons.org/) (CC) &ndash; An organization that helps artists of all kind to pick a well-defined license with global acceptance for their work, also used by Wikipedia. There are some identifiers that easily allow you what fits:
        * _BY_: mention the author(s)
        * _SA_: _share alike_, modifications are legal only when subject to the same conditions of the CC license
        * _NC_: not allowed to be used in commercial contexts
        * _ND_: do not modify
    * [GNU FDL](https://www.gnu.org/licenses/#FDL): The concept of a copyleft in the context of books and documentation. The old default of Wikipedia articles.
    * [Open Database License](https://opendatacommons.org/licenses/odbl/1-0/): Think of CC-BY-SA for collections of data, like _OpenStreetMap_ does.
    * _Fair use_: The concept of fair use is known to some countries such as the US. It allows a fairly limited use of some otherwise protected work but you should not assume a right to claim _fair use_ under general conditions, and outside of these countries.
* If you are generally interested in picking an open source model for you, let tools help you guiding through, for [software](https://choosealicense.com/) and for [assets](https://choosealicense.com/non-software/) ([CC](https://creativecommons.org/choose/)).
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

## Sales

_Excuse me? I thought we're at IT._ Chances are good that you will eventually, or again, by-sit a pitch, a sales talk, a brainstorming or workshop with someone willing to pay money for something _you_ are able to build or already have at hand. Let's try to make something out of it, and have some (more) food at the end of the month.

There are roughly two sides to approach _Sales_:

* Top-down: You are given something, and you have to sell it. You need to learn how to profitably sell ice in the Arctic, even to your family, without feeling bad about it.
* Bottom-up: You build something and and want to (need to &ndash; let's stick to reality) sell it. You know how to make ice in the desert, and you would like to know of how much to ask for it and if that justifies your effort.

The bottom-up approach is something than can be accessed easily even when you are not a sales person by any means. What follows is some key-takeaways from a book called [The Mom Test](https://www.momtestbook.com/).

### The Setting

You are a tech-related person or somebody responsible in IT. You have an idea, you are in a startup company, or you try to bring some loose strings together &ndash; predominantly B2B. You want to know two things now: _Is somebody worth the time?_ and _How much is it worth?_

We are not going the cover _cold calls_ since that's another topic (though mildly covered by this book), and _sales execution_ here since that will likely require additional legal work and signatures.

### The Questions

When asking questions towards a (potential) customer, do not ask what may give you a false positive for whatever reason. Ask questions that are hard to answer wrongly.

Bad examples are questions that pre-bias the answer, or that summon answers that are given for politeness, high degrees of abstraction and utopia and _Who wouldn't say Yes here?_:

* _You surely do/have/use ..., do you? Don't you think that ...?_
* _Wouldn't you like to have something that ...?_
* _We have this ... and that ... don't yout think that's great for you?_
* _What about ... wouldn't it a be a good idea to ...?_
* _How much would you pay for something that ...?_

Instead, let us try to harvest the truth:

* _Have you ever dealt with ...?_
* If yes: _What do you do/have right now?_ &ndash; Tools, services, people, ...?
* If yes: _What's your status quo here? Does that cover all your needs?_ &ndash; We are looking for signs of need, happiness or pain.
* If yes: _Did you ever look at alternatives? Which ones?_ &ndash; Willingness to try out something else?
* If no: _What did you try in the past? Why no longer?_ &ndash; Identifying things to address.
* _Is there any plan to introduce/change ... for this?_
* If yes: _What's the background behind this choice?_ &ndash; We are looking for things we cannot fight, like legal requirements, company mergers, ...
* _Who is requesting budget for this? Who is granting? How? When?_ &ndash; Can this person enter some commitment? How much? How much money is around?
* _If you face ... what are you doing then?_ &ndash; Is there a solution/handling, and is it feasible to attack? Is this a problem at all?
* _Can you demonstrate this?_, _How often does this occur?_ &ndash; Trying to get away from generalizations and distant memory.
* _So how much time does this take?_, _Who is involved?_ &ndash; This may give numbers for financial extrapolation.
* _Given there was some solution, how will this bring you closer to what?_ &ndash; Company goal vs. individual pain-point?
* _Is there somebody else who needs to be addressed here?_ &ndash; Is there somebody else who needs to like us? To give us more information?
* _Are there any other questions that need to asked?_ &ndash; Trying to identify what has been missed _by them_ so far.

The nice thing about this list: It's questions &ndash; no chatting, no theater, no suffering during lunch. We should have extracted business insights and can estimate the value of our solution a little better.

Also, try not to stop extraction after receiving compliements, and also always try to dig through statements of generalizations, the distant future or hypothetical statements.

Depending on the people, the answers, and the maturity of what you have, there may be just a narrow and brief moment &ndash; during a meeting! So have all involved people tuned &ndash; for the decision of how to proceed after all these questions:

* Is this something that is worth any more time at all? Is this someone from out target group? Any red flags?
* Is there something to show or to offer now or very soon? Does this match anything we came up with?
* If yes so far: Can we ask for any kind of commitment? See below.

If the person of interest turns around and comes up with ideas, also try to get something out of it (you are taking notes the whole time, do you?):

* _Why do you come up with this idea in particular?_
* _How does this help you?_
* _What problem will grow if you don't have that solution?_
* _Is this something you need from the very beginning?_ &ndash; Beware of the feature-creep! We want to know how much is enough to _buy_ it.

Let's say that somebody wants to connect Excel to that™: Is it a good idea to actually connect Excel to that, or to better think of something that can throw Excel away for good, given an understanding of the motions in play? Also, think of the amount of Excedrin you are about to need.

### The Follow-Ups

Idea: No meeting without commitment. Otherwise, focus elsewhere.

We'd like to see a commitment &ndash; a move towards us by the other party &ndash; or an advancement that will bring us closer to sale, or valuable insights at minimum that help us adjust. Signs of a commitment include:

* A follow-up meeting: discussing next steps, involving more people,
* a sign-up: committing to use a demo or trial, to board more people,
* a written agreement on helping in a case study or a promotion campaign,
* a project calculation.

In contrast, red flags include:

* No commitment, maybe just a compliment,
* they want to call back when the times are appropriate,
* they want to be notified when there is something to see.

These are polite ways of saying _No_ or _Not now and probably never_ or _I'm not gonna pay for this_.

So how does somebody from IT help sitting next to the sales people:

* Gathering business insights, understanding the idea behind functional requirements,
* estimating the problem and solution space, and estimating how much it takes to tackle it vs. what it's worth,
* questioning the pre-work on individual customers given the degree of business priority and commitment.
