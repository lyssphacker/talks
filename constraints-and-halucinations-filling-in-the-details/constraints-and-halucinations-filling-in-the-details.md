
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



#### Some related links:

[Somewhat related slides](http://cap.csail.mit.edu/sites/default/files/Sussman.pdf)
