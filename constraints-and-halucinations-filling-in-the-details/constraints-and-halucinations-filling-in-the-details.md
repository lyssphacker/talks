
## [Constraints and Hallucinations: Filling in the Details](https://www.youtube.com/watch?v=mwxknB4SgvM)  
by Gerald Jay Sussman  
given at Google sometime in 2013  

Abstract:  

Ever since I was an MIT undergraduate I have been pursuing several overlapping goals:

1. To formally understand the modeling and problem-solving strategies used by scientists and engineers.

2. To automate parts of this modeling and problem solving.

3. To devise linguistic support for expressing this how-to knowledge in a way that can be understood by a human reader as well as executed by a computer.

4. To use this computational medium to communicate how-to skills more effectively to students of science and engineering.

In pursuit of these goals I have been inspired by an idea that I gleaned from conversations with Jerry Lettvin about neurophysiology when I was an undergraduate.

I will advance the following cognitive-science hypothesis: Much of what we call intelligence is filling in details in pre-established networks of constraints. Indeed, I believe that most of the reason that humans are successful problem solvers is that we can often turn complex problems into finite networks of constraints that can be attacked with with a simple process called "propagation".

For propagation to be effective it will be important that the constraints and the data that they manipulate be finite and discrete, often "symbolic", expressions.

It will turn out that appropriately configured constraint networks can be a parallel computational architecture that can be used to track the provenance of data, explain the reasons for a belief, attribute blame for a failure, learn from mistakes, and allow a system to hold multiple locally-consistent worldviews in a globally-inconsistent "mind".
 
I will illustrate these ideas with techniques for formalizing some problem-solving strategies. It will be necessary to interweave yet separate the results of a computation and the strategy by which it is accomplished. Some deductions are strategic deductions and some are actual result deductions. To effectively represent strategies it will be necessary for propositions to be able to refer to other propositions. For example, rules will have to be able to be triggered in the case that the belief status of a proposition is unknown.

The propagation model of computation supports an appropriate infrastructure, a kind of plumbing for building such systems.

### Introduction (by [Chris Hanson](https://people.csail.mit.edu/cph/))

This is Gerald Jay Sussman, my mentor and good friend, who has probably taught at least a few people in here. He is one of Marvin Minsky's early students, has done a lot of interesting things in his life and he is going to tell us about the latest stuff he has been thinking about. 

### Halucinations are necessary in order to perceive

One thing I am going to start with is very old stuff. When I was an undergraduate, which was a long time ago (64-68 at MIT), there was a fellow named Jerome Lettvin, who was a very interesting character. I would go to talk to him occasionally. He had ideas about neurophysiology which were mostly very good and sometimes wrong, but it did not matter cause his stories were so good that it did not matter whether they were right or wrong. They could have been good ways of thinking for lots of things. One of the things I learned from Mr. Lettvin was that almost none of what we perceive is the stuff that is out there. That in fact we make up most of it. And in fact it's essential from his point of view that we have make up the content. So I want to talk about filling in details and that basically hallucinations are necessary in order to perceive. Then I want to show how that leads to invention of a kind of system for doing reasoning which is not unusual but which mirrors that way of the working with the world. 

### [Cognition involves filling in details](slides/cognition-involves-filling-in-details.png)

One of the observations is that in order to see or perceive things you better fill in details, there are details that come from everywhere, that in fact is essential to halucinate details if they are not there and it happens very fast. Look at this [picture](slides/cognition-involves-filling-in-details.png). Everybody sees these 2 scenes. What is this? - a car. What is this? These are the same bit patterns, just flipped. You created the scene that was not there. These are the actual bits. There is a wheel, it is all there. The same bits. 

### [Kanizsa's Triangle Illusion](slides/kanizsa-triangle.png)

Do you see the triangle that is not there. Everybody knows that isn't there, however you see it very well. This is an important observation. Btw., we know that bees do that also. They can see Kanizsa's triangle, but pigeons do not. This is sort of a wiring thing. Bees have been tested. You trans bunch of bees to go to a place where there is sugar water and one of these images (with a triangle), and you move that around, and eventually you see that bees go to the Kanzsa's triangle. Well, there are clues here, there are local clues. 

### [Cognition fills in details](slides/cognition-fills-in-details.png)

[David Waltz](https://en.wikipedia.org/wiki/David_Waltz), great wizard of when I was a graduate student, invented a mechanism of being able to label line drawings so that you can image that there a 3D objects. If you look at [this](slides/cognition-fills-in-details.png), this a line that is sticking out at you, "-" is inside, so this is some kind of depression in a surface. This means it is an open area, that behind this is nothing, so this is a hole that goes all the way through. For this one over here, we are looking at something that is floating in space and is coming up which is like truncated pyramid. This one is on the table and is a truncated pyramid. These are little programs which Waltz wrote, which were beautiful, which could take a bunch of lines and produce these labelings. The way they did it is quite clear. In this (lower right case), all possible labelings of that corner are known - there is some kind of catalog of them. All possible labelings of any corner are known. There has to be consistency. When lines come together, they have to be the same label, and that is the whole thing. It is very much like with the Kanizsa's triangle, that local evidence is put together to make a global interpretation. 

### [Circuit Analysis is filling in details](slides/circuit-analysis-is-filling-in-details.png)

Here is the one I got involved in 1975 with my friend Richard Stallman, who is btw the reason why you have free software. In fact, your company is probably dependent on him. When I was beginning to be assistant professor at MIT, around 1973 to sometime later there, I was teaching introductory electrical circuits class some of the times and I observed that the teachers did not teach the students what they did. What teachers taught the students is lots of little equations, where you have to make equations for each of the parts, make equations for the way they are hooked together and you solve the equations. But unfortunately that is not what real electrical wizard does, so it was important to figure this out and write a program to do it. Part of my intention was to take the program that is written so clearly that I can give them to students and then they understand how to do it. Let me show you what I do when I see circuit like this ... (follows circuit analysis). I do not want to teach EE here, but I want to show you a method by which I am reasoning. I am using local information and propagate it around as far as I can. I am using the diagram as my memory, i.e. the diagram is finite number of places I can write things and if I am actually doing this job I would be writing down answers that I computed on each of these places, and I can trigger off stuff that is nearby. So that is a local analysis. If that was more complicated, there might be one simultaneous equation, like this feedback. Feedbak amplifier. One equation with one uknown. There might be two equations with two unknowns. That is the most horrible situation I can imagine. That's what real engineers do. 

### [Details appear from all directions](slides/details-appear-from-all-directions.png)

You are at home in your bedroom and elephant appears just in from of your bedroom door, can elephant come into the bedroom with you? Why not? The reason is that the elephant is to big to get throught the door. You look at the thing and say, my door is not big enough to do that. You are constructing a visual image, which then being run by your visual system, and then being analyzed in such a way to produce the answer to this question. This is another example of such a thing. 

### [Not enough time!](slides/not-enough-time.png)

Here is really interesting thing. What is your name? That was 500 ms at most between when I finished the answer and he answered. Neuron time is about 5 or 10 ms. The fastest the neuron can do. That is few 10s of steps. I do not know how to make a computer ... I do not care how parallel the computer is (that is completely different question) ... how do I solve the problem of doing, phonology, morphology of words, the syntax, semantics and problem solving, back to the syntax, back to morphology of words, back to phonology, and then produce the muscle movements to answer the question, in 500 ms? There is not enough time. It means we do not know how to compute. That is one of things that was bodering me for a while. Yes, our computers are billion times faster than that, step by step, but that does not help when you look at the problem like this. We really do not understand what we are doing which I think is very important. 

### [Propagation](slides/propagation.png)

So what I am going to tell you about a particular model of computation which is modelling what I am talking about. I am imagining a mechanism made out of a lot of little autonomous machines. Each machine is basically looking at neighbors, little cells (not biological) that connects to. Cells contain information. When information appears in some of the cells, a propagator might say, oh that is enough information for me to change something else. That is all. Nice property of the model is that it is scalable. Because everything is nice and local like this, it also turns out that it can avoid lots of the problems of parallelism when you are trying simulate serial things with parallel. The hard thing is not making parallel machine, the hard thing is to simulate serial process on the parallel machine. If we realize that what we really want to do is write parallel processes in general, this problem mostly goes away. There is a breakthrough that makes this even more possible by my graduate student Alexey Radul who did his doctor's thesis in 2009. In fact, his breakthrough is that values in the cells are not the values like 32. It could be, but they might be something like information, that some is greater than five and less then a hundred, partial information. Only thing that propagator can do is increase the content of information in the cell by restricting possible values that can be there. This has super wonderful property from parallel processing point of view that things eventually converge. It is eventual consistency feature. You can imagine things like ... I gave an example of numerical intervals, but unification patterns that people use in things like logic are perfectly plausible in such thiings as well. Also, algebraic expressions merge by equation solving. I do not know what to do about probability distributions. I do not understand probability, I can assure you of that. There has been of course this wonderful pile of work by all the wonderful Bayesians which has taken over the world for good reason. Edwin Thompson Jaynes is basically founder of that stuff and the other end of it is ... people who opposed him is Mr. Fisher of Fisher Information and they were fighting years before we got involved with computers, but remarkable thing is that they are both right, so you have to be careful - frequentists and Bayesians are right. They argue all they want, but they are asking different questions. But that is a whole different story. So the answer is, probability is pretty bad for a reason. Mr. Jayens in the second chapter of his book explains that logic is actually subtheory of probability, a specialization. Now, we know that logic is at least exponential in solving problems, SAT problems for example, so that is awful. Probability must be worse if you want to compute distributions because if we compute the probability of distributions we would get answers for the logic. So I cannot believe that that is an effective mechanism. On the other hand there are some very smart people, one of whom you may heard of, Vikash Sinha. He recently got his doctor's degree working for Josh Tanenbaum, where he approximates probability of distributions by sampling. A very elegant piece of work and I highly recommend reading about it. But I really do not understand probability. 

### [Example: Distance to M87](slides/example-distance-to-m87.png)

I am going to give an example which is purely about how to use propagators ... I am not going to say how they work inside because it is easy ... I highly recommend reading a paper by Alexey and me called [The art of the Propagator](http://web.mit.edu/~axch/www/art.pdf)  which basically explains how to write programs. In fact it truns out that the paper is also executable. This is also basically his Phd thesis that is written in the format that it can be loaded in an appropriate way to MIT Scheme system and it will just run. That is a literate programming style hack. I am going to tell something I know a lot about, which is astrophysics. How do you estimate a distance to a galaxy? This is giant galaxy in a Virgo cluster, M87, one of the largest galaxies we know of,

### [Propagation carries provenance](slides/propagation-carries-provenance.png)

I am going to make up some propagator cells. Specifically, I am gong to make up a cell for something call the distance modulus. You do not have to know anything about what these things mean. It is not relevant what they mean, I want you to see how things are hooked together. So, I have a distance moduls and a distance cell. Distance modulus is something that you measure by looking at the intensity of the light coming from this object and having an estimate of the actual absolute luminosity. ... Here is propagator called constraint propagator (c:mu<->d) which connects those two. I am wiring them together. Imagine these little machines being made. This propagator looking at these cells and saying ... um, is there anything happening. I am going to tell distance-modulus that the value is 31.4 +- .3 in some unit, and it has been told to us by VanDenBergh1985 when he took some images. He produced a big table you can find in literature. ... I can now ask what is M87:distance in Mpc. What you see immediately from here that I got this infromation by propagation from there. Provenance is being carried. 

### [Simple explanations](slides/simple-explanations.png)

I can ask various explanations, like "How do you know this?". Give me level-2 (very simple) explanation. It says a stupid thing, how it got it. 

### [More detail](slides/more-detail.png)

I can ask for more detailed information. 

#### Some related links:

[Somewhat related slides](http://cap.csail.mit.edu/sites/default/files/Sussman.pdf)
