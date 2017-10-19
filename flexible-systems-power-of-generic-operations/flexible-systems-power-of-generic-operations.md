
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

Audience: This sound marvelous.  
GJS: I am not done. You will get more marvelous.  
Audience: In a situation in which you will write big flight-control system or avionics package.  
GJS: Lets get back to avoionics, because that is safety-critical, even more interesting.  
Audience: Or some medical software. In the real world Raytheons, Lockhee Martins, etc. will look at you and go, there is no way I am going to put Lisp on an aircraft.  
GJS: That is exactly right.  
Audience: But they will inherit methodology that give them mobility, robustness, etc., but field programmers will stick to their C or assembly, and they are going to take their decades old methodology to develop these things ... we really do not want to kill all those people on the plane.  
GJS: I agree. I will point out something very different though. I think that people who think that the avionics software, for example autopilot should be perfect are wrong. I will explain what I mean by that. That does not mean I can convince them, that is a different thing, because they also have liability problems. A lot of what is going on in the world is determined by lawyers. That is a real problem. Shakespeare had an idea about that ... Henry IV, part 2 ... I do not remember ... he said, first kill the lawyers. Lets get the autopilot as an example. It is designed perfectly when everything is going well. Few years ago, Air France plane got inconsistent information about the air speed. This caused an autopilot to basically turn itself off. Now, there was plenty of information, but it's job was do nothing unless it knew exactly what to do. Unfortunatelly pilots did not understand what happened and they crashed the plane in the middle of the Atlantic ocean. That's what happened. The right answer as far as I am concerned is that the autopilot should not turn itself off. It should've done something reasonable. It should've tried to fly the plance at constant altitude and heading which it was perfectly capable of doing. It had enought information to do that, and inform the pilot that something was wrong, that it is getting inconsistent data. That seems to me to be the right thing, and the fact that it should try rather than erroring out and crashing seems to me to be the wrong response. And a lot of the stuff we build is built basically to turn itself off, so it is not responsible for causing the problem, so that somebody's lawyer does not get to sue this guy.  
Audience: Have you contrasted this methodology with ...  
GJS: I did not look into that, but I will tell you that recently I have been looking into stuff that has to do with automobiles. The insides of automobile's software is disastrous. A lot of the problem is the world are due to the way legal system is structured. This idea that you have to blame someone. Engineers would do far reasonable things if they were not under those constraints.  

### [Let's go](slides/17-lets-go.png)
I am deliberately taking risks here, extreme ones. Code I am writing here is terribly risky, on purpose. I am showing you extreme end of it. Of course I would like to put there lots of tests, checks, etc., that things are sensible. That is a different problem. I want to show you what I can do so far. This is the beginning of course. I can still do what I did before. This is the original numerical history that I started with, first few values of sin. It also works symbolically, and it works in combination, meaning I can have part of the thing being numerical, and part being symbolic, and I can get the result with symbolic part being left unevaluated. Everything seems to be in a nicer state. In many ways this is the way I like to build software myself. I like to build it so that I can layer it on like this, and when I get a new problem, I am just going to add more stuff. I want to be additive. I do not want to screwing around with I already got. In the case of numerical stuff which is easy ... algebraic or numerical stuff ... it is true this is very structured, and that makes it a lot easier than something more complicated. I want to make sure that you understand that I understand that that is true. This is very simplified situation. Hardly anything is well understood as algebra. 

### [Arithmetic on functions](slides/18-arithmetic-on-functions-1.png)

Mathematicians like to invent funny notation. f(g(x)) = (f + g)(x). It just happens to be convention. We also get into some trouble with mathematical notation. You know that cos2(x) = cos(x) * cos(x), but cos-1(x) is not 1/cos(x). These people are not even consistent. We have to put up with the fact that traditional mathematics is a natural language. Suppose I want to put in functions. I make a function arithmetic over some arbitrary range arithmetic cause I am dealing with the values of functions that ought to be added together or multiplies or whatever. ... 

### [But (f + 1)(x) = f(x) + 1](slides/19-arithmetic-on-functions-2.png)

Here is a thing that mathematicians do, they have coersions. In this context 1 is interpreted as a constant function which always produces 1 no matter what it's arguments are. I can do that pretty easily by changing function arithmetic slightly. ... 

### [So](slides/20-arithmetic-on-functions-3.png)

If I install that arithmetic, then I can say things like this. I have very large system built on this stuff that I use for teaching advanced classical mechanics in fall term of every year with my friend Jack Wisdom. It is very simple and students get to use it. ...

### [Have we found heaven?](slides/21-have-we-found-heaven.png)

I can have algebraic simplifier which is itself a complicated problem, probably far more complicated ... I am not going to tell you to write one of those. Sometimes algebraic simplifier is a complicater. What you mean by simple depens on what are you going to use result for. But imagine that I have something call simplifier ... then I get this fairly horrible object. If I were debugging a numerical program it is very important for me to do this, to be able to symbolically evaluate it and examine it. Indeed, a lot of good compiler technology is in fact simplifying symbolic evaluation of a program. I do not thing we should consider a compiler other than fairly complicated simplifier of such a thing with maybe a translation phase to some other language, and maybe simplification of that language too. 

### [Another frog example](slides/22-frog-example.png)

Now I am going to get back to this biological metaphor. What I have shown you so far looks pretty daring but it is not. It was very simple. And it was simple in a way that was constraining me a lot. I did know what are all the algebraic operators going to be ahead of time. I had to have that library into a package. That is already too much for my point of view. I want to loosen this up. I am inspired by this character. This is a particular frog, quite different from the one you saw before, but it looks the same. Frogs all look the same. It has been known since 1913 or something ... the big deal is that different embrionic tissues combine to make organs in this frog than in the standard frog. So, there is more than one way to make a frog.  

Audience: This is argument for intelligent design.  
GJS: I am not going to fight with you over that one. I think this is the ability to tweak things under the table. Evolution has had nice feature that makes it more powerful then what we do, and it is that you do not have to figure out ahead of time. You build this thing called frog and you can tweak it by changing the order in which things happen in the development for example. That is pretty wild. So, you make the same frog, but different way. I want to be more like that. I want to have that kind of freedom.  

### [My mantra for today](slides/23-diamond-ball-of-mud.png)

### [Arithmetic is not everything - sequences](slides/24-arithmetic-is-not-everything-1.png)

Here is my ball of mud. First, lets say why I am worried about this. Not everything is arithmetic. Arithmetic is very, very simple. But I can start to deal with things like sequences which is much more complicated, because I have infinite sequence ... I see some Clojure over there ... infinite sequence are strong component of the Clojure world, and they should be. They should be the same as lists. That is the mistake I made long ago in Scheme before I understood that, that stream and a list should be the same, and they should have the same operators that apply to them. And I have vectors, which have different properties of course. Vectors are O(1) access. There are character string, there are various procedures appropriate for those. Diversity there is much more complicated than you find in algebra. 

### [Arithmetic is not everything - sets and multisets](slides/22-arithmetic-is-not-everything-2.png)

But it is worse than that. We have things like sets. And that can drive you nuts too. You have things as distinct as linear lists and hash tables. They have to be merged together to have one idea how to deal with sets. So when you start dealing with really complicated systems, the more like we deal in computation, you really do not want to be constrained by the feeling you are going to know all of the operators you are going to deal with ahead of time. The package I am interested in is the package of everything. I want everything to be generic and modifiable. 

### [Extensible generics - my ball of mud](slides/26-extensible-generics.png)

So, as a consequence, here is my ball of mud. I want to be able to say things like this. I am going to make a generic operation and give it name "foo" for purposes of debugging. It is generic operation of arity 2. If all 2 arguments are numbers then I am going to add them. If any of them is symbolic, I want to cons a plus onto the arguments. That is a much more flexible way cause I am not assuming ahead of time what all the parts are. 

### [How to play](slides/27-how-to-play.png)

Now I am going to tell you how I make this. ... There is some details on how to make this very efficient. It has to be efficient. That takes clever Chris Hanson type work. Basically, how to get a compiler turn this into 10 instructions. But that is separate issue. 

### [Back to arithmetic](slides/28-back-to-arithmetic-1.png)

Now I go back to arithmetic. ... This is very flexible, yet there are lot of constraints here.

### [Back to arithmetic - examples](slides/29-back-to-arithmetic-2.png)

I am going to give you some examples. ... I have done something nasty. I have introduced some order dependencies, that are worst than the ones I had before. It depends on the order which I build things. That is the cost of being flexible this way. An alternate way to thing, which I did not implement, which will be fun to do, and which I will next time I have all nighter to pull off, which I like to spend whole night programming. What I am going to do then is to make machine try all possible orders and see if there is any that converge (that is the right one) unless there are 2 that converge in which case they have to be equal. That is the way real things ought to work. It is the same way biological systems work, sort of. There is degeneracy in biological systems, meaning ... in physics we talk about degenerate eigenvalues, in quantum mechanics there are many ways to get that eigenvalue. From biological point of view, if I fail to eat sugar anymore, for example I lose the ability to process glucose, I can still get energy by eating proteins. It turns out there are different pathways ... I might not be able to survive for long that way, but certainly there are many things like that. E.g. if I hurt my right arm, I can do use my left arm, including write badly. Degneracy means there are many ways to do it. It is not the same as redundancy. Our kidney is redundant. It has gazillion copies of the same machine. If you have many machines each of which does approximately the same thing, that is called degeneracy. That is a very powerful thing to build into programs. We do not do that very often. Graceful degradation by having more than one way of solving the same problem, so that if any of the ways fails, there are maybe other ways to do it.  

### [Closure](slides/30-closure.png)

... I can use generic arithmetic and build things over that. ... That is the best situation when things work when you do not expect them to. 

### [Order dependency - Sigh!](slides/31-order-dependency.png)

### [Unambiguous rules](slides/32-unambiguous-rules.png)

Now I have something that works for every case I have shown you before and is much cleaner and easier to work with because I can add things without knowing about them ahead of time. 

### [A Literal Force Law](slides/33-literal-force-law.png)

Now, going back to where we started, we are going to look at some literal force law. 

### [Two steps with symbolic simplification](slides/34-two-steps-withs-symbolic-simplification.png)

I am beginning to see things that I want to fix. As a good programmer I do not like this because I am evaluating this guy several times, and that is the most expensive process in doing integration. So what I want to do here is common subexpression elimination. 

### [Removing common subexpressions](slides/35-removing-common-subexpressions.png)

That looks pretty good. I am about to converge and summarize. What I have been showing you are some very dangerous games I play. I believe that careful but dangerous programming is actually a very good strategy, and the reason why it is good is because it allows you to try things very fast and get them to work. Many of the mutations in biological systems are fatal. But what you end up with is very robust mechanism when it works. There are lots of cases where that can be improved. I am not trying to say that this is the right way to do everything. As I said at the very beginning, if I have garbage collector, yes, that is the case where I am going to prove it correct. I have to make the effort to make sure that garbage collector is not going to screw things up because that is very hard to debug. That is the reason. It is not because I care it is right, I care that it is very hard to debug. It is very hard to debug a program when garbage collector fails. I want to make sure that things are debuggable. Easily modifiable and debuggable, very fast, with very little effort. 

### [Programming Organizational Theories](slides/36-programming-organizational-theories.png)

There are all these things that people believe are the right thing to do things is. I have lots of friends who will tell me you whip the programmer until he does it right. This is the Dijkstra theory. Then there are people who say that object-oriented programming is clearly right way to do everything, or functional programming - maybe, I like it, I enjoy programming that way. I tried all things things (listed on the slide). They are all good. Each of them is good for the thing it is good for. A really good engineer has a pretty big toolkit. What really matter is to use the right tool for the right purpose. Tools better have to work together. Go to the machine shop (which I do a lot), and it better be the case that the coloth? which I pull of the shelf go into the mill at the right place and the appropriate taper, and if it does not I have the wrong machine shop, somebody has done something wrong. 55:41
