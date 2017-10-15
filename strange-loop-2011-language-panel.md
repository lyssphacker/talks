## [Language panel](https://www.infoq.com/presentations/Language-Panel)
at Strange Loop conference on Nov 14, 2011  

### Summary
Gerald Sussman, Rich Hickey, Allen Wirfs-Brock, Joe Pamer, Andrei Alexandrescu, and Jeremy Ashkenas, moderated by Dean Wampler answer questions from the audience on programming languages.

Sussman:
The really worst thing in programming languages is complex syntax. As alan perlis quipped, syntactic sugar yields cancer of the semicolon. The problem with complex syntax is that it hides possibly important to understand mechanisms, but more importantly, it makes it very difficult to write programs that manipulate programs, that read them, write them, analyze them. I often have programs that write programs that I want to run inline, for example numerical programs that are constructed from symbolic algebraic expressions. that is nice feature of Lisp, which has lots of parentheses, is uniform representation of program as data, and ability to execute code that you just constructed, and as a consequence I would say, my mantra here is, syntax without representation is tyranny.
