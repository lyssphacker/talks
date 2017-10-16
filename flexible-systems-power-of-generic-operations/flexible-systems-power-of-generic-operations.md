
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

## [Frog examaple](slides/02-frog-example.png)

Consider this character. This is a relative of mine, and yours. It is a vertebrate, so it has the same body plan as we have, meaning there is nose and a tail, he has spine going down it, same organs that we have. We are pretty much the same creature. In fact, it is not very much different from us. In a simpler case, you take a human genome, change a little bit of it, and you get a rabbit. So, it is very flexible. This is more than the rabbit change, but not much, to make one of these. 

## [Body plans](slides/03-body-plan.png)

We have body plans in engineering. Here is a very famous body plan every electrical engineer knows. This was invented by Edward Robert Armstrong in 1918. It is the standard radio receiver body plan. It is used for audio receivers the way it is written here, because this is a audio frequency amplifier, and that is a loud speaker. That could have been a video amplifier and a display. That could have been FM detector rather than AM detector. That could have been something that did something digital. I am not very worried about the details. The important thing is, that there is a plan. And of course [my friend](slides/02-frog-example.png) over here has the same body plan we have in a very deep way too. He has exactly the same hox gene sequence we have. Does anybody knows what the hox gene is? It is sequence of genes that almost every animal past spunge has. They are actually in a sequence of a chromosome. They represent regions from the nose to the tail. They divide creature into regions. They do not say anything what goes on in those regions. They are the coordinate sequence. 

[Combinators](slides/04-combinators.png)

Here is a composition operator. That is a little piece of a body plan. You can have complicated ones like tensors. We understand a little bit, as engineers, what the body plan is. It means that we specify the outline of something without specifiying the inside. That is very important. 

[Worm example](slides/06-worm-example.png)

Here is a guy that is quite different from us. He has the same hox sequence we have. However, his kidney is in his nose. Again, I am trying to explain idea there. That is kind of thing that I want to be able to talk about today and has to do with being able to diddle inside of something that is already laid out. That is a very dangerous kind of manipulation, but is the kind of thing which gives you tremendous kind of flexibility. I am willing to trade off almost everything for flexibility, do I want to be really nasty programmer today. 8:43
