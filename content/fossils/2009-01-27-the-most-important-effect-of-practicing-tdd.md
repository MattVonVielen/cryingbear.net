+++
title = "The most important effect of practicing TDD"
slug = "2009-01-27-the-most-important-effect-of-practicing-tdd"
published = 2009-01-27T23:00:00.003000-06:00
author = "Matt Campbell"
tags = [ "testing", "TDD", "design",]
+++
For the last couple weeks, I've been helping to interview candidates for
a vacancy on my company's development team. Experience with TDD is not a
prerequisite for our candidates (although openness to it certainly is),
but occasionally we'll get an applicant who claims to have some previous
TDD experience at a previous position. One of the questions I always
pose to a candidate in this category is "what would you say is the most
important effect of practicing TDD?" I have a very particular and narrow
set of expected / accepted answers in mind when I ask this, and I'm all
too frequently disappointed by the responses I get. (To be clear, this
isn't a "pass/fail" question in our interview process - very few of them
are - but it **is** one to which I attach an amount of weight
proportional to the claimed amount of TDD experience.)  
  
Just today I was listening to the Hanselminutes podcast episode with
Scott Bellware entitled "[Test Driven Development is Design - The Last
Word on TDD](http://www.hanselminutes.com/default.aspx?showID=164)".
Anybody who follows [@bellware](http://twitter.com/bellware) on Twitter
is almost certainly familiar with his strength of opinion and extreme
verbosity on many topics and there are probably some folks who are
inclined to take his positions with a proverbial grain of salt. This
show however should prove to be pretty easy to swallow even for those
folks, and I agreed with pretty much everything I heard there.  
  
That said, it's is a half-hour long interview / discussion on the topic.
Something far shorter is in order, especially for a response to an
interview question. And although the title - "TDD is Design" - is about
as terse as one can get, it's also unfortunately blunt and doesn't
really cover much in the "why / how" department.  
  
A little over a year ago, I came across [this 5-minute TDD Primer from
Microsoft's
ARCast.TV](http://channel9.msdn.com/shows/ARCast.TV/ARCastTV-Test-Driven-Development-Primer-with-Peter-Provost/)
featuring [Peter Provost](http://www.peterprovost.org/), which does a
fairly good job at peeling back the issue to the bare bones. I've
included the most relevant snippet here:

> It's something developers use to kind of enable emergent design. TDD
> is not about testing \[...\] and that the "T" is really a wrong choice
> of words in there. And then it's also not about development and so one
> of the "D"s is wrong too. We like to say that it's "Example Driven
> Design" - saying what you want before you do it, and then confirming
> that you got what you expected - and that leads to emergence of design
> in the small.
>
> — <cite>Peter Provost</cite>

Peter later mentions that TDD has "this amazing side-effect" of
producing "really high unit test coverage." Until then, I'd never
considered calling the test coverage a "side-effect" - it seemed almost
sacrilegious - but this was a major "Matrix Moment" for me.  

> Do not try to cover 100% of your code with tests, for that is
> impractical. Only try to realize the truth - the tests are a
> side-effect.
>
> — <cite>That annoying kid from The Matrix (slightly paraphrased)</cite>

Anyway, Peter's explanation is some pretty good stuff. But it's still
lacking a certain *je ne sais quoi*. Wouldn't it be really nice if we
had something that was sound-byte-sized and yet still contained the
distilled essence of this message? Well it turns out that we do. Also a
little over a year ago, I was at a meeting of the [St. Louis .NET User
Group](http://www.stlnet.org/) and the topic of "why do TDD" was raised.
[Brian Button](http://oneagilecoder.asolutions.com/) was in the room and
delivered what I still consider to be the end-all, be-all sound-byte-ish
answer to this question, and I love it so much that I'm making the text
annoyingly large to try to drive the point home:  
  
> The single most important effect of practicing TDD is that it forces
> you as the developer to be the first consumer of your own API.
>
> — <cite>Brian Button</cite>

It's my firm belief that nearly any developer with more than a little
experience knows an annoying or unfortunate API when he/she uses it. How
does TDD help you in this regard? Well, in the podcast I mentioned
above, Scott Bellware refers to "test friction" and Scott Hanselman
refers to "test smells." One example that was mentioned was the sort of
test that requires way too much setup just to exercise a single method
(or worse, constructor). If you're doing TDD, and you catch yourself
writing a metric butt-ton of setup or "Arrange" code for an otherwise
simple method call, then your instincts should kick in and start sending
tiny messages to your conscious mind saying "hey - this API is crap!"  
  
I will soon write a follow-up to this post with some more concrete
examples - there are plenty of products and frameworks out there that
make for easy targets, and I'm deliberately **not** going to discuss
[Oxite](http://visitmix.com/Lab/Oxite) since it's already been beaten to
death. Instead, I plan to discuss an open-source project near and dear
to my heart, one to which I am in fact a committer -
[FileHelpers](http://www.filehelpers.com/).
