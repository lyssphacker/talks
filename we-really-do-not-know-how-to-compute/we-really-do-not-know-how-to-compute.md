
## [We Really Don't Know How to Compute!](https://www.youtube.com/watch?v=O3tVctB_VSU)
by Gerry Sussman
at [Strange Loop conference](https://www.thestrangeloop.com/about.html), 2011  

Note: This document includes edited transcript of Sussman's talk with associated slided plus my comments and questions. Document is organized in a way that each section contains Sussman's claims in bold, followed by associated slid and possibly my comments and questions.  

[All slides](slides/slides.pdf)  

Opening remark: We are in a real trouble and have not the foggiest idea how to compute very well. There might some glimmer of hope on the horizon, in number of different direction, some of which I might point out.  

[Opening slide](slides/page_1.pdf)

### Most things are obsolete

Most things we are talking about, even here are obsolete. As I said to somebody at the yesterday's Haskell sessions: this is the most advanced of the obsolete languages.

My comments/questions:
1. This is exactly what Alan Kay was saying for a long time, pointing out that top languages in use today haven't got passed Simula which was one of the great languages of the 60s.
2. Since almost all companies are writing millions of lines of mostly incomprehensible code, this is probably greatest confirmation that languages in general use today simply do not scale. It is also amazing to look back at the greatest artifacts of the 60s and 70s and see with how tiny amount of code they were implemented on machines with wastly less resources. For example, as we can hear from Alan Kay, personal computing as done by his group at PARC was done in only about 10k lines of code. Also Howard Shrobe wrote in one of his papers that OS on Lisp Machines (done by Symbolics) was implemented in only about 1 million LOC written in maybe Common Lisp/CLOS (or some other Lisp variant - Lisp Machine Lisp?). So, with better architecture (both hardware and software) one can do a lot with much less material, or as Alan Kay said so many times - architecture dominates material.

### [Kanizsa’s Triangle Illusion](slides/page_2.pdf)

You now see the triange that is not there. What did you do? I took only 100 or maybe 200 ms, or few tens of neuron times. I do not care how parallel the machine is. I do have the foggiest idea how to write a program that organizes complex process like that in the latency of about 30 or 40 steps. That is the example of something we do not understand how to do.  

### Human genome

And more serious than that, human genome is about a GB. That is instructions for making you from a cell. You are pretty complicated machine. A GB is the same size as the source code appropriate for making say Microsoft Windows. It is not much bigger or smaller, it is somethig like that. It has all the possible things it can do, all possible drivers which might be relevant. It is probably of that size. It is not much bigger, not 3 orders of magnitude bigger. A GB is not that big, but what is interesting is that with the small change you make a cowens? out of the person, so it is flexible too. So we have enourmously flexible language there that we do not have the foggiest idea what it is like. I am not talking about DNA. DNA is like gates, or something. What I am interested is the higher level language that is necessary to do things like that and we certainly do not know how to do that.

### Salamander example

Biologists do nasty experiments on animals. Suppose you took a salamander. Salamander can regrow it's limbs if you cut them off. So all these biologists do nasty experiments. They cut salamander's arm off between the shoulder and elbow, and between the elbow and the hand, flip around that segment and resow it back on. What do you think you get? You get 3 elbows. It grows for the fact that the wrong thing is connected to the wrong thing. That's pretty weird. But that is a clue to something that we should be thinking about. How do you talk about how to make a bazillion - human is 10^12 cells, salamander is probably 10^11 or 10^10 - but the fact is how do you make something big like that grow itself? Little neighbours talking to each other and they say: I am supposed to connect to something like this but it ain't there, so we will make some of that. That is sort of amazing kind of process that is going to be necessary if we want to approach the future in our computing because it is almost impossible to setup the situation in which we know everything that is going to happen in the future.

### [IBM 650](slides/page_3.pdf)

Let me go into the past a bit. When I started computing in 1961 I was computing on the IBM 650 at the Columbia State University. That machine costs half a million bucks. It had 2000 words of 10 decimal digits each of memory on a drum that rotated so that access time was 12.5 ms. 10 ms cycle time. Total amount of memory was probably about 10 KB. For the price of that machine now I can buy 50 thousand PCs each with a GB of RAM (that is 10^4 times as much) and million times faster. So one of the things that has been happening over the years (I am not trying to worry about Moore's law or anything like that). What I am worried about is that all our intuitions from being programmers have come from a time of assuming a kind of scarcity, a world in which computation is somehow expensive, where memory is somehow expensive, where we have to optimize it. Well, there some applications like that, but the answer is that most applications are not like that at all. Right now, memory is free, computing is free. It is our problem to figure out how to use computing like that. And if I have 50 thousand PCs in a network which will probably cost about million (modern) dollars, I can make a very serious computer out of that. It is no longer necesssary to minimize operations, to worry about how much memory we take up. It is very important to minimize latency. That is critical, you have to understand that.  

### [Quote from Huw Evans](slides/page_4.pdf)

The real cost of programming is a cost of programmers. Here is a quote from Mr. Evans made a while ago. It turns out that almost all cost of computing is you, and me. That's a different world. That's the real problem.

### Things people worry about

There is lots of things people worry about. People worry about correctness. That is a problem. Is it a real problem? Maybe, probably not. Most things do not have to work. Look at Google. If it makes a mistake, it does not matter, so long if the next time it gets the right answer, or maybe something close to the right answer, reasonable answer. People worry about security. Well they have no idea how to handle security. We will find out for example that humans manage to survive for about 70 years. We are continuously attacked by the parasites. It must be that there are some bad things we are doing. It is all in that GB of code. You have to think about that. We certainly have no any good ideas how to make things last for very long time by continuously being attacked by mutating parasites.

### Evolvability and modifiability of code 

The other thing that seems really important to me is that we spend all our time modifiying our existing code. The problem is that our code is not adequately evolvable and modifiable to fit the future. In fact, what we want is to make systems that have the property that they are good for things that the designer did not even think of or intend. That is a big problem. That is a real problem I want to after a little bit. The problem is that when we build systems we program ourselves into holes. I have done it a number of times. I have been programming since 1961, and found more ways to screw up that anybody I know. I learned a lot I hope but not an infinite amount. So here is this problem. How do we keep ourselves from programming ourselves into holes. What does that mean? It means that we make decisions early into some process that spread all over our system. The consequences of those decisions are such that the things we want to change later are difficult to change becaue we have to change very large amount of stuff. That is the problem. I want to figure out ways we can organize systems so that the consequences of the decisions we make are not expensive to change. We cannot avoid making decisions, but we can try to figure out ways to minimize the cost of changing decisions we made.

### [Traditional generic arithmetic in Scheme](slides/page_5.pdf)

Let me start with the simple example, one that is so familiar that we all do it these days, certainly in good dynamically typed langages like Lisp or Python or whatever, or good statically typed languages like Haskell or whatever. We always have generic operators, we call it operator overloading and things like that. Lets talk about that for a second because I am going to be very extreme about this. [Here](slides/page_5.pdf) is a traditional arithmetic you will find in Scheme. I can add integer together, I can add integers to rationals, I can make new rationals, I can add integers to reals (floating-point thingies that are very dangerous, nothing brings fear than a floating-point number, numerical analysis - the blackest art I know). We can deal with complex numbers, etc. But, those things are built in. How about dynamically extensible generic operations? Now, we can do that. Of course if you separate compile time and runtime, something weird is happening here. I want to be able to dynamically extend things while my program is running. I want a program to compute up what it is going to do. Remember, in the old days we used to program in the assembly language. It was a great language becaue you could write the next instruction you are going to execute. You could put into the place you are going to go to. It just was. Many interesting programs were written that way and it was very flexible. There is too many fearful people in the audience. I an see a lot of people cringing, but the fact is, you can do it in Lisp also - you can eval something you cons up. That is very useful. 

### [Arithmetic on Functions](slides/page_6.pdf)

I can expand this to the arithmetic on functions. I can add sin and square. I get a new function because that is a classical thing people can do in algebra - if you have 2 functions with the same kind of input, then the sum of those is assumed to be the sum of the outputs. That is for things that are typed procedures with the same number of arguments. I can talk about sum of the squares of sin and cos applied and I get 1. That is an example of simple extension. You have all these nice things. I was wathing somebody talking about scalaz today, and of course you can do that.

### [Symbolic Arithmetic](slides/page_7.pdf)

Then you get to things where Lisp gets things better. There is symbolic algebra. Now, this is also a generic extension. I am not going to explain how it works except that I can tell substraction, multiplication, division, all those things to deal with symbolic entities as well, literal numbers. And what I get is a symbolic expression as a result of such a computation and I can of course ... nice things [that](slides/page_7.pdf) is a fragment of a program that came out. So I can write a program that writes a program, and I can use it. I can tell you a good example of the use of that. It is numerical analysis example - Gear integrator, for Siff equations, differential equations. It turns out there are some polynomials you have to compute up. If you compute them ahead of time you will double your step size. But if you want to be able to make the step size any size you want, you want to be able to compute the polynomial at the moment. So you write something that symbolically does that, then you pass that through compiler as you need it and then you run it and use it, in the same program that is running, integrating along. The point is that you can get essentially fully native code efficiency. I like Lisp because it has uniform representation of programs and data, so that symbolic manipulation produces stuff that I can execute. 

### [Automatic Differentiation](slides/page_8.pdf)

You can stuff that is even more wild. Did you know that automatic differentiation can be done as a generic extension. 


