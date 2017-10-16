
## [Flexible Systems: The Power of Generic Operations](https://www.youtube.com/watch?v=cblhgNUoX9M)  
by Gerald Jay Sussman  
given at [LispNYC meeting](https://www.meetup.com/LispNYC/events/227620989/?_cookie-check=8KI918CyErqAITjD)  

### Abstract

Most systems we build work well for the application that they were designed for, but they are brittle in that adapting to even small changes in the problem requires large changes in the code.  Can we optimize for flexibility, trading off other virtues like proofs of correctness or efficient execution?  I think this is often the right path.

Indeed, Postel's Law, "Be conservative in what you do, be liberal in what you accept from others," is strong advice for enhancing robustness in open systems.

In the spring term I teach an advanced programming class, where the goal is to learn how to avoid programming oneself into a corner.  One of the most powerful (and dangerous) techniques for enhancing flexibility is the use of extensible generic operations.

I will show where it is to our advantage to make systems with extensible generic operations, and how to control such systems. 

### Introduction

I have been programming computers for ridiculously long time, since 1962, when the then undergraduate, eventually my provost, Joel Moses, was an undergraduate at Columbia and taught a class in computer programming for high school students. I learned how to program on 650 data processing system which had 2000 decimal words of 10 decimal digits represented in bi-quinary on a drum which took 12.5 ms to turn around. There was an assembly language which involved 2 addresses, one of which was next instruction location so you could optimize you program so that next instruction will be just after you've done this one. That was my original experience with programming. I programmed in almost everything since then and as a consequence I learned more ways to screw yourself with the computer than almost anybody I know. That is certainly what I want to talk about today, because it seems to be that one of the biggest problems people have with programs, is writing programs that are dead ends. What I mean by dead end is, you have written this big complicated piece of software and the world changes, and something else is needed to be done, and then you have to rewrite big chunk of it. There is something really wrong with that. It just should not be that way. By contrast, consider the human genome. Here we've got a GB of code. Maybe it is the same size as GNU/Linux. You got a GB of code. So you have a GB of code, instructions for making you (a very complex machine) out of a single cell, operating that machine for approx. 70 years reasonably well, fending off attackers desperately trying to eat you, and things like that. Eventually it fails, that is true, but the bottom line is ... better than that, it does not have a version skew, that is, suppose I took half of Ubuntu 14.04 and complementary half of Red Hat 23, and put them together. You think it would work? That is how you make more people. Something is very wrong the way we program, and I am worried about that a lot. That is one of the things I am thinking about today. But the other thing is, I do want to contrast that with biological systems more interestingly, but fundamental thing is flexibility. Flexibility is the key thing that is very different, that I want to concentrate on. I am not going to care about provability of correctness. It does not mean that that is not a good idea. If I have a garbage collector, it better be correct. You want red blood cells to work too. There is few things that have to work, but on the other hand, most of the time, correctness is not the issue. Security is maybe somewhat an issue, but maybe the way you do that has nothing to do with proving little theorems about cryptography. After all, any good locksman will tell you that if you have really good locks on your door, the easiest way to get into your house is to break the window. So that does not work either. 

### [Robustness](slides/01-robust-systems.png)

Here is what I am really worried about. I am worried about acceptable behavior over much larger classes of situations then it was anticipated by the designer. That's what I really care about here. I want things with the property that if you got something it works, it does the job you want, and all of a sudden problem changes, I want it to not be too hard to make it work on the next thing. 

## [Frog examaple](02-frog-example.png)

Consider this character. This is a relative of mine, and yours. It is a vertebrate, so it has the same body plan as we have. 5:13
