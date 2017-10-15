
## [Flexible Systems: The Power of Generic Operations](https://www.youtube.com/watch?v=cblhgNUoX9M)  
by Gerald Jay Sussman  
given at [LispNYC meeting](https://www.meetup.com/LispNYC/events/227620989/?_cookie-check=8KI918CyErqAITjD)  

### Abstract

Most systems we build work well for the application that they were designed for, but they are brittle in that adapting to even small changes in the problem requires large changes in the code.  Can we optimize for flexibility, trading off other virtues like proofs of correctness or efficient execution?  I think this is often the right path.

Indeed, Postel's Law, "Be conservative in what you do, be liberal in what you accept from others," is strong advice for enhancing robustness in open systems.

In the spring term I teach an advanced programming class, where the goal is to learn how to avoid programming oneself into a corner.  One of the most powerful (and dangerous) techniques for enhancing flexibility is the use of extensible generic operations.

I will show where it is to our advantage to make systems with extensible generic operations, and how to control such systems. 

### Introduction

I have been programming computers for ridiculously long time, since 1962, when the then undergraduate, eventually my provost, Joel Moses, was an undergraduate at Columbia and taught a class in computer programming for high school students. I learned how to program on 650 data processing system which had 2000 decimal words of 10 decimal digits represented in bi-quinary on a drum which took 12.5 ms to turn around. There was an assembly language which involved 2 addresses, one of which was next instruction location so you could optimize you program so that next instruction will be just after you've done this one. That was my original experience with programming. I programmed in almost everything since then and as a consequence I learned more ways to screw yourself with the computer than almost anybody I know. That is certainly what I want to talk about today, because it seems to be that one of the biggest problems people have with programs, is writing programs that are dead ends. 2:28
