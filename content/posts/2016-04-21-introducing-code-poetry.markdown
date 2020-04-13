---
title:  "Introduction to Code Poetry"
date:   2016-04-21 19:37:01
description: "A presenation of the niche poetry genre of code poetry"
tags: [
    "poetry",
    "development",
    "code"
]
categories: [
    "Education",
]

---

Today I saw a seemingly randomly hanging little poster on a wall in my university. A poster for a code poetry slam. Say what?

<!-- more --> 

I was quite familiar with the concept of poetry slams. They got quite well known in German speaking regions after the excellent poem by [Julia Engelmann][1] went crazy viral in 2013 in all major medias (which you should check out if you know German. Yes, it is full of post-teenage-angst, insecurity, everything bothering about millenials and being one, but it is technically flawless and definitely leaves an impression on everyone listening). Afterwards, there was a hype about those slams, a revival was declared on the art of writing poems, long thought dead, the performance bit made it fresher than just "poetry", events and competitions took place everywhere. The hype existed in the States way longer, on Youtube you can find tons of inspiring, angry, moving, thoughtful, poignant or just plain funny slam poems ([this poem][2] by George Watsky is one of my favourites, such a good blend of technique, message and spit-take). Now they seemed to gain too much popularity for their own good sake, angry and fast-spoken rants were now also declared "slam poems". But it's all in good fun.

But code poetry? That was something really new I have never heard of. My first mental images of how this would look like ranged from the very awkward to the very awesome. Avid programmers regard coding beautiful algorithms poetry in itself, but of course this was not gonna be only about nice, efficient lines of code. It seems that the first event of this kind was organized [at Stanford in 2013][3], with a spiritual predecessor being the [code{poems} project by Ishac Bertran in 2012][4] (unfortunately the contents are not freely accessible). Looking through some of the examples, I am either extremely delighted by the completely genius of some of these or extremely lost by the lack of getting-it.

Check out these lovely examples from the first Standford Code Poem Slam:
```java {linenos=table}
//"That Girl" by Ian Holmes

import java.Object.*

public class ThatGirl {
  public SomethingBetter main() {
    return whatYouFound;
  }
}
```
or

```java {linenos=table}
///"Expect_Delays" by Dylan Moore

private Boolean she_smiles_for_me() {
  //heart:
  while(true) {
    System.out.println("beat.");
    try {
      Thread.sleep(86400000);
    } catch (InterruptedException e) {}
  }
  return true;
}
```

The programmer's love, expressed. How cute! Actually, one could combine the two poems, which would add a nice fatalistic Goethian touch. So poetic!

Some poems are harder to get. The high entry barrier of some of these poems is the only thing that can block someone from enjoying code poetry to the fullest.

It seems that almost all of the code poem examples that I found can be classified in one of these two categories:

1. They are actual poems themselves, either written in real, machine executable code or typed in some form of pseudo code inspired by some programming language. For example, the two poems posted above!

2. They are not actual poems, but more executable poem generators, most of the times spitting out different results each time they are run. One brilliant example is [21st Century Prophecies by Hunter Bacot][7], which is a tongue-in-cheek statement about the ideological leaders of nowadays. Another one is [Ross Goodwin's Poetizer][6], which will spit out lots of more or less sensible rhymes according to the parameters you specify (of which there are lots to choose from).

Anyway, I just found out that my Uni actually hosts one slam like this in May for the second time, so I will check it out. The results from last year were kinda mind blowing (especially for some that were in a german-english mix), so I can recommend [looking through the site][5].


[1]: https://www.youtube.com/watch?v=DoxqZWvt7g8 "Bielefelder Hörsaal-Slam 2016 Julia Engelmann"
[2]: https://www.youtube.com/watch?v=6GvTLfV8fls "George Watsky Lisp Slam Poem"
[3]: http://stanford.edu/~mkagen/codepoetryslam/ "Stanford Code Poetry Slam Homepage"
[4]: http://code-poems.com/ "Code{poems}"
[5]: https://codepoetry.at/ "Code Poetry Slam at Technical University of Vienna 2016"
[6]: https://github.com/rossgoodwin/poetizer "Ross Goodwin's Poetizer"
[7]: http://stanford.edu/~mkagen/codepoetryslam/#1.1_bacot "Hunter Bacot's 21st Century Prophecies"
