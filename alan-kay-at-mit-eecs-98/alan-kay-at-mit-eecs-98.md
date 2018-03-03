### [Alan Kay at MIT-EECS 1998 Fall Semester Colloquium Series](https://www.youtube.com/watch?v=BUud1gcbS9k)

### Bob Barton
Bob Bob Barton was probably the greatest computer designer who ever lived.

#### Basic idea of recursion is make the parts have the same power as the hole. Objects can act like anything.
I was really lucky there's nothing like luck when you're trying to have an idea. It's better than anything. 
There I was looking at Simula trying to figure out what the hell this thing was, all these things going around, and then
all of a sudden I realized oh yeah Simula is a language that's trying to be like biology but it isn't. But it's trying.
Because if you really went a little further in the biological thing you start getting these wonderful things about it
and furthermore it's recursive to the hardware of the machine in a way that is really marvelous. Bob Barton always used
to say, basic idea of recursion is make the parts have the same power as the hole. Now if the hole is a computer how
can you possibly claim that a data structure has the same power as a computer. It doesn't. How can you claim that a
procedure has the same power as the computer. And again this is one of these things where you realize, oh yeah these
mathematicians in the 40s and 50s they didn't know what they were doing, they thought functions and sets were the way to
do this but the computer is a more important idea than functions and sets. It's this whole thing and in fact here at
project Mac and out at Berkeley people were starting to make what we call virtual machines, a little different than 
today's terminology but the idea is to give each person on a time-sharing system a logical machine that acted and
you might have a hundred of them for 100 users and I was thinking yeah that's a really great idea except we need
hundreds of thousands of these things because then we can model anything that we want and you get this wonderful thing
just like from the same stuff there are hundreds of different kinds of tissues in our body all from the same DNA
And then there's this insight that yeah and you can even model programming language things, you can step out away from
the compiler and actually simulate programming language ideas.

#### DNA needs a cell to make a cell
In computers you can pull the DNA out like Simula was doing with its classes and that's really powerful. And then here's
an idea that was, I ascribe it, I don't know where exactly but I certainly think of Peter Deutsch's PDP-1 Lisp done here
at MIT when he was only 15. As an example because this is a system that had no operating system it was just a Lisp,
interactive Lisp and he had fixed it up so you could control the entire machine. And what a great idea
because what is an operating system anyway except something you can't fix when you need to. And when you do fix it you
have to fix it with a programming language, and Peter had just cut out the middleman there. And the late binding structure
of Lisp made it possible to do this on the fly. I think he was the first one to do that. That's kind of like this notion
that DNA actually doesn't do much by itself. A lot of viruses are almost naked DNA, but they need a cell to know how
to make another cell. This is the most interesting part of biology I think which is what's called morphogenesis or
embryogenesis, which is how do you get from something that is only coding for proteins, 60,000 proteins in our case, 
to something that's like a baby. The answer is you have to have something else which is a set of structures and
a place for sending messages that allow that to happen. That led to this idea that if you extend complexity out
far enough at some point we'll have to start growing software, that is we won't like, in the simplest case, we don't want
to ever build a system from compiling word processor files and making a load module. I think most people would love not
to do that anyway because as you get more and more complex just things like the initialization problems and getting
everything set up and linked together is such an incredible thing. You really want to start with something that's already
working and just make it incredibly better over and over again.

#### Late binding
These kind of situations are when late binding starts becoming a more and more important idea. And if you think about it
almost every advance in software has been a kind of late binding and I believe this statement is just as true today as it was back then, that is we just don't know enough, we don't have an engineering discipline and so even when we're doing something that looks like the project that we did the last time, it turns out to have a huge learning curve and the problem is if we're using an early bound system, back in the old days like Algol or Fortran or COBOL or machine code, nowadays like C or C++, just as you start learning something, the system has gotten too rigid to be reformulatable, so you say, no we have to get the deadline done, let's leave those ideas until later. Do those ideas ever get in? Forget it.

#### There are Maxwell's equations for computers
So coming back to Lisp here. This is like the entire world, this is like Maxwell's equations here, it's one of the greatest
things anybody ever did for us because it's not just doing a Turing machine. This is a Turing machine that has slope. You can get from here to where you want to go very very rapidly and actually this is a fun thing about being part of an art because as I was talking about this I could feel chills going up and down my spine right now because this is real power, intellectual power and realize that if you could take what was great about Lisp and add this biological, ecological way of doing things to it you'd have something pretty darn interesting.

#### Being compatible on all the systems on the Internet
What's germane to this talk is that at Xerox PARC we had lots of different hardware architectures, we just like to build computers. They all have different CPUs on them and Smalltalk ran on all of them bit identical so it wasn't the way some systems are today. We wrote a book about it but when commercialization happened things started degenerating, entropy set
in. Here's an example. So this is one of the most respected Java developers and in this book he actually says that any
seasoned Java programmer will quickly note that write once run everywhere is a myth along the lines of Paul Bunyan. Now it happens to be true but it is unbelievable to me that they would be so complacent about it to actually write it down, because isn't Java supposed to be compatible on all the systems on the Internet? So this is bad.

#### Today's architectures are 60s mainframe hardware and software
I claim that the architectures people are dealing with today are basically 60s mainframe hardware and software. If we look at Intel and Motorola, they've never really gotten, I mean Intel started off as a pocket calculator, never got beyond that much. Motorola started out as a kind of a PDP-11, very early architectures. And then very typical 60s software as done before 1965. Bad operating systems, layers, applications. And then grafted onto that today are some things from Xerox PARC, TCP/IP, PostScript, laser printing, more expandable architectures.

#### MetaSqueak: Bootstrapping
Metaobject protocol. Well we don't do it quite the way Gregor and Danny do, but let me just show you how we made the system. So we went to the book we wrote and actually took an old Smalltalk, we typed the code for the VM that we'd written in this book which nobody has ever read into this Smalltalk system to make a simulator of what the virtual machine should be. Then we wrote a translator of the simulator and then we use that to make ourselves a new VM that did not have any of this old Smalltalk in it. And then we moved over the image which has all of the objects in it and now we were completely free. That took about a month and a half or so to do. And all of a sudden we have a completely machine independent version of Squeak and all of these different ports have been to take this guy and first improve it, like when we put in the music we did the programming of the VM by making the simulator do what you want and then getting this translator to make you a new VM so you never write any C code by hand. And the ports are all done by simply diverting the translator to different target machines.
So all the ports in fact were done in less than two weeks by people we'd never met before, that just found this on the Internet and and did it. 

#### Serialized updating
The last part of it is this whole worldwide community is held together by synchronized code so at any point in time I can 
update code from server and if I say Disney internal updates or Squeak public updates it will go out automatically to the nearest mirror server and find the latest updates and serialize them in. This system has not been built from source listing since about 1975. It's never been stopped. It's kind of important to think about that.
