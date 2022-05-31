+++
title = "A Unit Testing Dilemma"
slug = "2009-09-10-a-unit-testing-dilemma"
published = 2009-09-10T19:26:00.003000-05:00
author = "Matt Campbell"
tags = [ "TDD",]
+++
After returning to blogging after a really long hiatus with some [really
heavy and emotional
stuff]({{< ref "2009-08-15-a-long-overdue-reality-check-wundarous.md" >}}),
I think I'm way the hell overdue for a development-related post.  
  
I've long been a believer that one of the most important and most
overlooked aspects of TDD is *making sure the test fails first*. To put
it another way, here's "Gandalf's First Law of Unit Testing":  

> **You shall not pass!**
>
> — <cite>Gandalf the Grey, in his first (and last) TDD seminar</cite>

  
  
This step is *crucial* due to the extreme and surprising ease of writing
utterly **useless** tests. If you're looking at a unit test and you
suspect that it might be useless, here's one way to confirm your
suspicions:  

-   Comment out the entire body of the method under test
-   If needed, uncomment (or stub in) just enough code to make the class
    compile
-   Run the suspicious unit test again - if it passes when run against
    an empty method, then it's utterly useless

  
This isn't a contrived story; it's actually happened a couple times
where I work. Granted, there may be an easier way to tell the
uselessness, if the test in question performs neither assertions nor
verification against fakes (mocks, stubs, test-doubles, whatever) and if
that ain't a test smell, I don't know what is. But while that is an
admittedly extreme (though real-world) example, there are a plethora of
variations on the unit test that, once everything is inlined, boil down
to "Assert.That(true)". And the risk of writing a useless test rises
significantly if you're (mis)using a mocking framework that supports
non-verifying fakes.  
  
In any case, I'm also a philosophical believer that with a certain
amount of elbow-grease and prestidigitation, it's possible to wrap
legacy code (in the Michael Feathers sense of the phrase) in tests. I
say that I'm a *philosophical* believer of this, since I've yet to
actually make it work. It certainly doesn't seem to be a trivial
undertaking.  
  
And herein lies the dilemma to which I allude in the post title. When
writing a new unit test against a piece of previously-existing and
previously-untested code, how can you write the test so that it fails
first? Is there a sane way? Should you comment out the method's code,
like in my earlier example, and write the test bit by bit, uncommenting
code to make the test pass each time?
