+++
title = "Speed up your builds by 9.5% instantly!"
slug = "2009-10-27-speed-up-your-builds-by-9-5-instantly"
published = 2009-10-27T12:23:00.009000-05:00
author = "Matt Campbell"
tags = []
+++
Nope, despite the tone of the title, I'm not selling a product, even
though it does sound like a sales pitch. But I did just do this on the
builds on my team, and I thought I'd share. And though it's really not a
revolutionary process, I've removed a guaranteed 1 minute and 6 seconds
from every build cycle by deleting one line of code in one production
class, and refactoring a constant into an injectable property in
another.  
  
The deleted line was in a method that is invoked in 3 different test:  
  

    Thread.Sleep(12000);

  
  
And the line converted from constant to injectable property was:  
  

    Thread.Sleep(30000);

  
  
Since our average build time over the last week is around 11:36, and
these two edits save 66 seconds per build, I've achieved a time savings
of 9.47% virtually instantly.  
  
So the moral of the story is this: any time you feel a desire to include
Thread.Sleep in production code, you need to go stick your head in a
freezer until the feeling subsides.  
  
P.S. I think it may be important to note that at least one of those two
offending lines was written by me.
