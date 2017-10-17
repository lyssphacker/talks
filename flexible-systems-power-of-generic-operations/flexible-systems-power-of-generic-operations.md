
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

Here is what I am really worried about. I am worried about acceptable behavior over much larger classes of situations then it was anticipated by the designer. That's what I really care about here. I want things with the property that if you got something that works, it does the job you want, and all of a sudden problem changes, I want it to not be too hard to make it work on the next thing. 

## [Frog examaple](slides/02-frog-example.png)

Consider this character. This is a relative of mine, and yours. It is a vertebrate, so it has the same body plan as we have, meaning there is nose and a tail, he has spine going down it, same organs that we have. We are pretty much the same creature. In fact, it is not very much different from us. In a simpler case, you take a human genome, change a little bit of it, and you get a rabbit. So, it is very flexible. This is more than the rabbit change, but not much, to make one of these. 

### [Body plans](slides/03-body-plan.png)

We have body plans in engineering. Here is a very famous body plan every electrical engineer knows. This was invented by Edward Robert Armstrong in 1918. It is the standard radio receiver body plan. It is used for audio receivers the way it is written here, because this is a audio frequency amplifier, and that is a loud speaker. That could have been a video amplifier and a display. That could have been FM detector rather than AM detector. That could have been something that did something digital. I am not very worried about the details. The important thing is, that there is a plan. And of course [my friend](slides/02-frog-example.png) over here has the same body plan we have in a very deep way too. He has exactly the same hox gene sequence we have. Does anybody knows what the hox gene is? It is sequence of genes that almost every animal past spunge has. They are actually in a sequence of a chromosome. They represent regions from the nose to the tail. They divide creature into regions. They do not say anything what goes on in those regions. They are the coordinate sequence. 

### [Combinators](slides/04-combinators.png)

Here is a composition operator. That is a little piece of a body plan. You can have complicated ones like tensors. We understand a little bit, as engineers, what the body plan is. It means that we specify the outline of something without specifiying the inside. That is very important. 

### [Worm example](slides/06-worm-example.png)

Here is a guy that is quite different from us. He has the same hox sequence we have. However, his kidney is in his nose. Again, I am trying to explain idea there. That is kind of thing that I want to be able to talk about today and has to do with being able to diddle inside of something that is already laid out. That is a very dangerous kind of manipulation, but is the kind of thing which gives you tremendous kind of flexibility. I am willing to trade off almost everything for flexibility, do I want to be really nasty programmer today. 

### [Variations on an Arithmetic Theme](07-variations-on-arithmetic-theme.png)

This is the idea that Chris Hanson and I have been talking about for very long time. Chris is principal author of MIT Scheme. He now works at Google, although he worked for me for 26 years. We are writing a book on stuff like this, on flexibility. I want you to remember this idea: A diamond is very pretty, but it is very hard to add to a diamond. A ball od mud is not so pretty, but you can always add more mud to a ball of mud. I learned from Joel Moses or Paul Penfield, I do not know which, at APL 79 conference. 

### [Simple ODE integrator](slides/08-simple-ode-integrator.png)

I am going to start with an illustration of a particular numerical process. I do not know how many of you know much about numerical things, but I do a lot of that, because I like to push planets around, in orbits, etc. (celestial mechanics). But, I am going to show you simple one here. This is an ordinary differential equation. All I need to know is time and the position at this time to give how this is accelerating, whatever this object is. It is Newton's laws. All Newton's laws look like that and x can have gazillion dimensions for all I care, usually does. 3 dimensions for every particle or whetever you like. I might want to descritize this so that I can integrate that numerically, and one way to do that is to make discrete approximation of a 2nd derivative which you see there. h is a step size. Stormer's two-step method is a simple version of this. ... The reason I am bringing this up is because I want you to show some interesting things with this. 

### [Evolver](slides/09-evolver.png)

I can make a thing that evolves this thing. ...

### [Harmonic oscillator](slides/10-harmonic-oscillator.png)

Second derivative of x is minus x. That means the answer is sin. Sin is one possible answer. ... This is an example of a very simple process. Why am I showing you that? Because, suppose you built this thing. Ignore the fact that I am giving you trivial thing to integrate. I am doing something in Solar system I might have 12-step integrator, one step size of one day or something.

### [Symbolic arithmetic](slides/11-symbolic-arithmetic.png)

I does not take to much to turn this into symbolic machine. In fact, it is trivial. Assume for the moment that I have arranged my system so that all numerical operations in my numerical library are in the package, where package is a mapping of names to the procedural values. It is some kind of mapping which tells me what each name means. So, + means the thing that adds, but that is for me to decide. I can make another arithmetic package which is "symbolic" package. It starts as being built atop of numerical arithmetic, whatever that means, we are going to talk about that in a second, such that for every procedure in the numeric package there is procedure of any number of arguments which conses the name onto the arguments. It is not abvious what this does. It basically builds parse tree of some expression. I am going to modify all bindings, so numerical procedures are now symbolic ones. That is dangerous. I understand this is dangerous. I assure you that I believe that sometimes the danger is worth it. We do this all the time anyway. We have generic operations in most of our languages where we have mixed floating and integer arithmetic - that is terrible. I can have a thing that works just great for integer arithmetic, and if I try to use floating point, it is going to do the wrong thing sometimes. How many of you know that the average of 2 numbers in floating point might not be necessarily between them? 9.96 * 10^0 (imagine 3 digit precision), plus 9.98 * 10^0 is 19.94 * 10^0. Correctly rounded that is 1.94 * 10^1, divided by 2, is 9.95 * 10^0. Watch out. I would not get into the airplain unless test pilot has tested it out. Floating point does not impress me. In any case, we do this all the time, but we do not realize that it is dangerous. Of course, if I have a numerical process that depends on commutation of multiplication, and I put matrices, it won't work, so I have to be careful when I do these things. Sometimes you have to live dangerously. I am installing that, and now I say, what is the value of x(0) of the result of evolving the Stormer thing one step from the initial history which is entierly symbolic? I get the symbolic result. It is not simplified - you can run it through the simplifier, that is a different problem. 

### [Sticky notes to control applicability](slides/12-sticky-notes-on-applicability.png)

I have given something up. We will fix that in a second. In particular, the symbolic operators cannot do numbers. I am going to start elaborating this process for you. We have numeric arithmetic when appropriate and symbolic arithmetic when appropriate. What we really want to do is to attach to every operation applicability predicate which says whether or not it does the job. And I can make sticky notes very easily. Most people think that the right thing to do is to make careful record structures that have all the right slots in them, etc. That is nice when you know what you are doing. 99% of the time you do not know what you are doing. My view of the world ... again, I am being very extreme today ... what I do to make sure that everything is really flexible, is to do it with property lists, i.e., I have some double-entry hash table, and I am attaching to every object the thing that is eq, property, and now I have a sticky note that I stick to the thing. So I can find what things are, what things are not, that they have this applicability property, and so on. We make a new arithmetic-maker that has in-domain predicate I am going to pass in. So, to make numerical arithmetic I obviously want to say, test for number. If it is symbolic arithmetic, let test be symbolic, and we are going to see in the second what that means. 

### [Numeric arithmetic](slides/13-numeric-arithmetic.png)

And then I can write down my numeric arithmetic. It is arithmetic starting with the name "numeric", a debugging name when I chasing around inside the machine I can find out what I've got. It is built on raw scheme arithmetic structure, it has applicability prediate number?. It is replacing every operation of name "name" with the thing which has appropriate base operation of that name. I am not saying how I am going to build this, it might be that I am building numeric arithmetic over something else. I pick up that base operation, and return a new object which annotated version of the procedure that applies baes operation to the arguments with an applicability that says, every one of the arguments for base operation whatever it's arity is, is going to be one of the things that is in the domain predicate. I am leaving a lot of space for things I am going to add. 

### [Symbolic arithmetic](slides/14-symbolic-arithmetic.png)

I can make symbolic arithmetic parametric over base arithmetic. What you see here is that symbolic arithmetic ... I am calling it symbolic over base arithmetic ... right now my head is numeric arithmetic, but it might be something else. It might be matrix arithmetic, for all I know. For every name pick up the base operation ... 

### [Some combinators](slides/15-add-2-arithmetic.png)

Now I can make some combinators, like we had compose originally. Compose was a very simple one. Here is the one that adds two arithmetics together. I start with 2 arithmetics, a1 and a2 ... 

### [A bit more setup](slides/16-a-bit-more-setup.png)

So far, I am building little more structure here, and now I can build a little bit more setup ... Now you will see what is going to happen. This btw something I teach classes in. Every spring term I teach a class on games like this, and the reason I do that is because I am in opposition to the standard belief structure of computer scientists, who think you should not do things like this. And the reason why I am worried about that is because I think they are worried about the wrong things, most of the time. What I want to make sure is, that it is not the case that I am going to spend the rest of my life ... everybody who is a programmer spends most of his life fixing code that is already built, that somebody else had built, which in fact it should not be a problem. It should be easy to do that. The hard stuff should be coming up with the ideas and organizations that do not have this problem. Inspiration for that is Emacs. Emacs is a gorgeous program explicitly because of the fact that 10000 people had written parts of it, and it still works, it is reliable.  

Audience: 27:19
