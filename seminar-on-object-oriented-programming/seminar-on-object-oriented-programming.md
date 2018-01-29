## [Seminar on Object Oriented Programming](https://www.youtube.com/watch?v=QjJaFG63Hlo)
Note: This talk presents how Smalltalk group at PARC was thinking about OOP during 70s and 80s (and beyond).

### First known form of OOP
I wrote my first program that I would call object-oriented in 1962 and people have been writing programs in that style even earlier than that. In my particular case I was a programmer in the Air Force at Air Training Command in 1962 there were no standardized operating systems of (course that's true today). But back then there was actually a reason for it nobody had gotten around to the idea of thinking it might be useful, and Air Training Command had a problem of moving tapes with records of various kinds on them from one Air Training Command base to another. The machines back then Burroughs 220, which were machines that have had about five thousand characters of storage and were about the size of this room and were great coffee warmers. My image of them is with this huge set of boxes with a row of pots on top trapping the heat as a came out.  Now the problem that they had was that there is no way to standardize on what the formats of the different records were. They changed and the operating system. It was usually just the kind of a loading program and so there was no way of standardizing on that and they wondered how can we actually read these data records if everything is constantly changing and nothing holds still. Somebody thought up a great idea. That idea was to have the records shipped in the following format. Each tape file had three sections to it: the front section was fairly short, it had a bunch of relative pointers into the second section which contained bunch of Burroughs 220 code and that code knew how to deal with a third section which had the actual data records. There are usually about 20 or 30 what we would call messages today. 20 or 30 entries in the first part and the code that came along with the tape records knew how to deal with all the data. **So in current day terms what the Air Training Command was doing (I think it was as far as the late 50s) was to ship an entire class of objects. The class was shipped with the protocol, with all of the code, and with all of the data in a form in which you did not have to penetrate any of it in order to make use of it.** That was used for a number of years as a technique until COBOL came in and the Air Force forced all of those good ideas to go away in order to standardize and COBOL which is a much weaker conception going back to the notion of data structures that are fragile.

### Encapsulation
Our bodies have approximately a trillion cells in them and each cell is rather complex. Each cell has many millions of components in its own right so one of the ways nature discovered to control complexity and the kinds of interactions that are likely to happen is to try and encapsulate them in various ways. This is a familiar principle to us. It's something that we use in regular program as well. Trying to encapsulate and the question you're always asking when you encapsulate, we're going to ask this quite a bit later, is just what is encapsulated. what kinds of things are we trying to control are usually in regular programming what we encapsulate are sections of programs that occasionally will encapsulate with regard to a protocol for dealing with some system we don't want to inquire about the internals of. **What biological systems encapsulate is the actual environment in which most important processing takes place. There are very few object-oriented programming languages that go that far. The average object-oriented programming language encapsulates not the environment but in fact something like the state of a data structure along with the procedures that know how to intimately manipulate it and try and tie those two areas together in a way that they cannot be penetrated from the outside.** When people speak of an object-oriented programming language like Objective C or C++ they're talking about even less than that because there the encapsulation is almost a convention. It's done by means of macros, the amount of protection at runtime that is delivered is rather low, so there all of these gradations. Now biological systems encapsulate with a vengeance because nature discovered that if you give each cell its own little captured ocean and let it devote about 90% of its actual energies to simply protecting itself from the outside world as though the outside world were hostile then you get a situation where you can build very large structures rather safely, and
encapsulated is not just the saline solution, not just the organic molecules, but also encapsulated not just the programs that drive the cell but in fact encapsulated in biological organisms as many of you are aware is **the entire plan for the entire structure.** Now we don't generally do that when we write an object-oriented program but in fact people are starting to do that now in artificial intelligence.

### Basic principle of recursive design

There's a principle in design that people came up with many years ago, it's called the basic principle of recursive design and the idea is make the parts have the same power as the whole. We know in the factorial example that a recursive program like factorial, it's charm is it's able to reinvoke itself as the conditional branches and so in some sense, as long as that is true, the program remains as stong as it was when you entered it, because you can always reenter it instead of getting diluted away. Now another thing that that crossed my mind when I was pondering these ideas back in the 60s was why if that is such a powerful idea, why is it that we take a very powerful idea like a computer and dilute it immediately in most programming languages by dividing it up into data structures and procedures. Data structures don't have the same power as a computer. They're static, can take on marks, but they're once you get a data structure, it just sits there. Procedures don't have the same power as computers because they can't remember state. They have to have something additional so what we did in the guise of following standard mathematical notation in the 50s when Fortran was developed was to mimic standard mathematical notation without thinking about this basic principle of recursive design because people didn't write recursive programs back in the 50s, and so the baby is thrown out with the bathwater almost immediately in a standard procedure and data structure language. And it occurred to me and other people who are thinking about these ideas back then what if you didn't do that, what if the only subdivision you ever made in a programming language was a subdivision of a computer into a computer. You're never allowed to subdivide the computer into something that was less than the computer. And what does that mean? That means that each subdivision has to be something like a black box that has inside of it some mixture of state and process. From the outside you can only invoke behavioral attributes rather than invoking method attributes. And what I mean by that is this is something that was even in Fortran because the earlier designers of Fortran realized that there is a very funny correspondence between procedural things and data structure things so for instance when you say sin(30) in Fortran you can't tell by looking at that whether you're invoking a function or whether you're accessing an array. And that was not accidental back then because of course they thought of arrays as being a kind of a function and they wanted you to be able to write arrays (huge tables) still done today in order to do functional evaluation very quickly. What they didn't realize is that you wanted to be able to trade-off between the two, but that notion of just saying sin(30) without indicating how it is to be computed is the essence of the kind of abstraction that object-oriented programming is all about. It's carried very far here by this strong membrane of the object so that what we're dealing with here are behaviors ...

### Messages in most cases cannot be commands

Messages in most cases can't be commands or you're violating the notion of the object as being in control. Now most object-oriented systems today when you do what is called sending a message you are issuing a command. Objective C, C++, even Smalltalk 80, in all of those systems a message is actually something very close to if not identical to a certain kind of procedure call. But in fact in the original scheme, we can talk about the implications of why this is a good idea, in the original object oriented systems that were so successful messages aren't commands at all, what they are are desires
(I'd like to have this happen). Just to give you an example of why, imagine we have an object masquerading as a critical system file, and the question is, should just anybody be able to come up and issue the command to it turn byte 5 to 0? Now it's done all the time but in fact in an object-oriented system you would like the object to be able to protect itself so that even a person who has a pointer to it, even a person who has the knowledge of which command is the right command, that both of those do not imply that you have permission to actually change that file, so when I talk about an object-oriented system I mean an object in which the worst you can do to an object is to simply indicate to it that you would like it to do something for you, and the best that can happen is it will do that. The worst that can happen to it internally is it will simply refuse it, may take your name and give it to the principal later if you've done something wrong ...

### Assignment has to be replaced by "advice"

Because the object is no longer a data structure in any sense that we regard it, assignment is something that can't be done from the outside either. So the assignment statement has to go away in the form that we know it as an irrevocable change to a variable or a slot in a data structure. An assignment has to be changed by something that we can think of as being advice or influence. So again this notion of getting an object to change it's state is something that we normally don't do in object-oriented programming because normally in object-oriented programming we are not simply trying to imitate data structures. Now to be a data structure is that thing that if you send it to somebody else, you're giving them permission to change it that's what I mean by a data structure. So it's clear that some of the things that we call data structures in normal parlance in a system with an operating system that offers some protection, are not strictly classical data structures by that means. Certain files usually have protections on them so that in a good operating system when we send a file from us to somebody else we are not can conveying to that person the same level of protection necessarily that we have been granted.  So in a good operating system, this may be an operating system that you've never seen, but there have been operating systems in the past, there exist operating systems now, so that if you have a certain set of permissions for a file and you wish to give it to your friend (suppose you have the the magic permission to change the any byte in the system file because you're a honcho) then you might wonder should I be able to pass on those permissions to the next person that I give this file to.  The answer for good operating system is no. Each person should get their own permission separately and when they receive this file, it's their permissions that are granted by the operating system that obtain, not the permissions passed on to them by somebody who had the file before. So you can think of taking this desperately important file, passing it along and when it goes to somebody who is less to be trusted with it, they have fewer permissions on that. There are fewer things that they can do with it and then they pass it on to somebody again that may go back to a trusted person, that person should be able to reinvoke those operations that were taken away. There are whole schemes for doing this, and is called capability protection. Capability protection is again another one of these old ideas from the 60s, intertwined in a very strong way with object-oriented design that is now coming back. Capability is simply a technique for protecting objects in a stronger way than normal digital computers allow them to be done.

### Reasons for dealing with objects
Probably 90% of the reason to me for dealing with objects at all has to do with their abilities to protect in various ways.  Protect by encapsulating various kinds of things, almost always state, less often control is encapsulated and so forth. Then about 10 percent of the use of object-oriented programming has to do with its ability in whispering to you how you might design a system better.

### Data abstraction vs OOP
The way objects are used today is a little bit confusing because they're intertwined with a another set of ideas that came out of the 70s that are very similar, particularly in implementation these days and that's what's called data abstraction.  
Data abstraction looks a lot like object-oriented programming but its intent is different. The intent of data abstraction is to take a system that you're familiar with, like Pascal or Fortran, that is starting to run into difficulties of various kinds. Difficulties are usually a representational ones. I think everybody had the experience programming in a language with data structures. You get this big system done, you decide you need to change your representation and the next thing you know you're hunting down all of the procedures that think they knew about the old representation and the rule of the universe is that there's always one or two that you don't find so you slide in the new representation and a couple of months later one of those procedures is invoked and all of a sudden you have a crash and people wonder why. The answer is the critical knowledge has actually been spread out in such a way that it can't be recovered. It's like what you have to do after you do a multiplication, in order to recover the operands you have to do much more work. It is like the difference between differentiation and integration. The same thing is true is once you've lost information in a system, once the entropy has
gone up, then it's very hard to get it back. So one of the things that you do with objects is to maintain as much informational content as you possibly can in a smaller place as possible. Now data abstraction techniques use a similar way
of wrapping an envelope around a data structure and invoke operations by means of procedures in order to get it to be a little bit more representation independent. Ada for instance is a language that is a data abstraction language, it is not an object-oriented language and even the the people who actually understand Ada don't claim that. But you can do certain kinds of things that are now today called object-oriented in Ada. So this envelope of procedures is wrapped around the data structure in an effort to protect it, but then what happens is that this new structure that's been created is then treated as a data structure by all the rest of the program. The result is, particularly in Ada, is that the programs are not small. The programs aren't any smaller than they were before, and one of the hallmarks of object-oriented programming if you have any sense of whether you're doing it right or not, is that the programs are remarkably smaller because there's a way of using the design that is not simply imitating a bad old idea which is data structures and trying to shore it up by putting it in an orthotic brace, but in fact to go beyond the notion of data structures. So for instance in a Ada way of of doing object-oriented programming one typically comes out with something that looks very much like a data structure. It has fields that are to be written to, it has fields that data is to be taken out of, the structure is static, there's no actual process going on, and it's essentially a slightly more abstract way of doing data. Typically, a good object will not actually permit you to write assignment statements to it at all because an object generally will not look at all like a data structure. Just to give you an example, we can contrast a personnel record as it might be done in Ada in, which we still wind up with fields as we had them before. Some of the fields might be a little bit more connected, but it's still a large thing. It's still passed around as a passive object. We could contrast that with an object-oriented approach with which would be to turn the personnel record into something much more like a real person. In other words, this personnel record instead of sitting there on a file waiting to be manipulated would actually be trying to participate actively in some sort of simulation. Instead of changing the person's age from the outside, the way you might do in a data record, the age of the person would change dynamically as the birthday was passed because there was something in this object that was actively looking at the clock, actively running in some sense. The notion of being able to edit the object from the outside would be much less in the sense of editing the actual fields, so objects even in a programming language in which everything is an object like Smalltalk tend to be larger things than data structures. They tend to be components, active machines that fit together with other active machines to make a new kind of structure.

### It is one thing to build cells and another to build tissues
To me this is what object-oriented programming is about. It's not saving data structures from itself, it's not making a slightly fancier data structure, it's not even making a data structure that can implement certain kinds of constraints within itself and so forth. It's thinking of those objects as independent machines. Going back to this whole biological notion that it's one thing to build cells and it's another thing to build tissues and for people who are just starting out in object-oriented programming they're usually thrilled that they can build cells but the real goal is to be had when you move from cells to thinking about what are the tissues what are the conglomerations of these atomic style objects into components that if you were to have three or four hundred of them in a repository usable by any programmer, what would you be able to build. Could you be able to Tinkertoy things together, could end-user programmers be able to do a considerable amount of the programming and retailoring and so forth.

### For programming in the large objects aren't enough
The reason is that at some point it's not simply a matter of piecing together something that is supposed to run it's a matter of being able to verify different sections, different parts, different modules independently, to be able to unplug and replug and even I think in many cases it's desirable to allow different implementation languages to actually used.

### Separate outside from the inside, protocol from methods
The main principle in object-oriented programming is to separate the outside from the inside, so on the outside we have a variety of messages that we're willing to respond to, and on the inside we have some methods that may or may not correspond to these things on the outside because whatever the idea is we're not supposed to understand what the inside looks from looking at on the outside. And outside thing might even correspond to a little data structure inside a thing. Equally innocent might correspond to an enormous amount of code. There might be code in here not directly connected to this and in fact some of the messages that the object may be able to receive aren't directly characterized in terms of some outside protocol. Lots of different variations here but the most important one here is that we're trying to separate a protocol from some methods at this level.

![slide1](slides/slide1.png)

### Protection does not guarantee that you have an architecture
We started having zillions of objects interacting in a sea of messages. In fact some of the objects might not even be on the same machine, they might actually be over here. **In a good object-oriented system you shouldn't be able to tell what machine you're running on. That's what messages are all about.** Very quickly when we're starting to build a large system down here we've got something interesting, we have absolute protection but we still have confusion because you can have thousands of diamonds that are impervious to all normal wear and tear and still not be able to build the simplest structure out of them. They may be too shiny, may not be able to pile them up, they may not fit together, but they're perfect. So what I'm trying to say is that the protection issue is a critical one, but it still doesn't guarantee that you actually have an architecture. 

![slide2](slides/slide2.png)

### Protocol is the most important and most fragile part of object-oriented design
How complicated protocol gets is the most important part in any kind of object-oriented design but it's also the most fragile. The fact that there's nothing to protect print is absolutely critical. Let me give you an example of what we could do to protect print. One of the things we could do is instead of having print just be code, we could actually have a print class and it's offspring, it's instances are actually structures that look like this. In other words each offspring of print is a message-method pair in which unrestricted code writing over here is not allowed. This is interesting idea because if you can write anything here then J. Random Programmer often will as you go along and the fact that the system seems to be conventionalized at this protocol-message level, which is the very charm of object-oriented programming, why object-oriented programs work so well, why they fit together gets destroyed as the amount of generic information in the actual methods gets diluted. But another way of doing an object-oriented system is to actually make classes for each of the major code types that you're going to write and what you get here is something that would insert itself in here, but in fact the only codes you're allowed to write are certain little restricted boxes in here, and this thing guarantees that it's going to print for you. It's not going to go off and zero byte five of some system file. Because it came from a print class and because the print class does printing type things every piece of code that goes into a protocol actually is going to do something like printing and what you're allowed now is a certain amount of parameterization, a certain amount of freedom, but the meaning of print now has been nailed down because there's some actual code from the print class sticking behind here that you can't see, that's going to make every effort to deliver a result. This is like types in typed languages except it's stronger because it can controls the goal of the result, the goal of the result not the shape of the result. In a typed language when you have a typed variable or typed procedure, what you can state is that might have some integer parameters and I'm going to deliver a floating-point result, what you can't say in the typed statement is what the intent of that procedure was. The only intent that you could indicate is that it's going to give you some sort of floating-point result. You can't say it was supposed to give you a sine or cosine or anything else. That is up to the convention of the actual programmer itself so what I'm just pointing out here is that if you take a system in which there is a protocol, you can get a lot out of it just by having the protocol be a convention, agreed on by everybody. As you go into a larger and larger system that inside-outsideness will protect against the inside getting dissolved by some hostile action by the outside but what will get diluted as you go to a larger and larger system with more and more programmers is whether the protocol is going to have any meaning. Practical example ... ParcPlace Smalltalk has approximately 5000 of these green things, each one of them can be
reused by inheriting it from somebody else. The number of red things it has is on the order of 2100. That means that the amount of how generic the code is with respect to the protocol is not much. The number should be more like 400 or so different red things (400 concepts) and say 5000 realizations of those concepts.

![slide3](slides/slide3.png)

### Configuration language
Configuration language can be independent of all of your method languages. It's something that is dealt with at the operating system level, it's something in which the protocols are chosen as much as possible ahead of time, it's a standard vocabulary of concepts that you're going to use to write in, it's one in which the protocols are controlled by active code that give you places to write code and insert other code that allow you to bring over a COBOL routine or a Fortran routine or whatever the heck you want and bind it in. It's a binding mechanism, it's a way of setting up environments for debugging modules independently of each other, it's a way of assuring yourself that a module will be able to move from one place to
another, it's a way of discovering whether you want to use a module so at some point the ability for human to read this configuration language is going to be much more important than the ability to write it. ... I only know of one actually good configuration language that's been done, a language called C/Mesa which was done by the PARC computer science lab about ten years ago and it served exactly this purpose, and here are some of the things it can have there. Some things that you'd expect just from your previous experience. You'd expect that there would be some sort of message name for something you'd expect that there would be parameters so that you would have input expectations, output expectations. A good configuration language has executable predicate. You can think of as a goal that they may have a variety of them. When I say input expectations I mean not just the types of the parameters that you expect to send to it and the types of the results, but also preconditions on the input side and goals on the output side. You can think of those as being executable. There are environmental expectations. One of the difficulties in most object-oriented programming languages is although you can protect an object, what you don't have any sense of when you want to move an object is what the object itself expects to have as environment.

### Modularity in object-oriented programming is slippery
In Smalltalk you can write an object, move it for one place of a particular Smalltalk system to another, but when you want to take it out of your Smalltalk system and give it to somebody else, a Smalltalk system you often are unpleasantly surprised. And it's not that the object has been solid in any way, it's that it has some other assumptions about it's environment that you weren't thinking about before. In particular, Smalltalk allows you to do the somewhat obscene thing of allowing you to go and change existing super classes to make them more the way you like. The benefit of this is that every class and the system feels this improvement and the problem with it is if that improvement is important then you've all of a sudden have done away with your portability, so what I'm trying to point out here is that the modularity you get in object-oriented programming is slippery and one of the most critical things to do is to be able to pin down the amount of modularity that's actually there. People have designed configurations languages in such a form that you can actually from the runnable parts of the stuff derive an explanation mechanically of what the method and what the module itself is supposed to do.

### Inheritance
Inheritance is in object-oriented languages is how you share things. It has been a goal of people in the last 20 years who do this to write very small, very reusable, very compact code. The goal is to make things that are shared as abstract and inheritable as they can possibly be. So you want the smallest number of maximally indepenent concepts that you can Tinkertoy together and have some confidence that the active Tinkertoy is going to give you something that also still works. The whole idea in object-oriented style is to linearly combine things together. 

### Modularity of control
In most object-oriented systems the modularity that is gotten by them is one that is regard to the state that you put in  each object. What isn't modular is the control. This is another set of issues to talk about. So for example one of the things that you may see when you're looking into an object-oriented programming is you may see the state and each neatly encapsulated but you may see control going all over the place. What happens when you send a message? The answer is often, I don't know. Goes here, goes there, and find somebody here, talks to this guy, dozens of things happen. And I can't even tell whether control is ever going to get back to me. That's often the state of affairs. Now what would happen if we actually made control modular? We'd have something more like this, where instead of control going through the objects, the objects themselves are sitting in a sea of messages but they don't actually originate them themselves. How is that possible? Well one way you can imagine for it to be possible is for the objects to simply say I need to know the following. Object-oriented system we've just developed at Apple, one that we did at MIT, is an object-oriented system in which you never send a message, only receive. How is it possible? Well the system contrives to make the messages get to you by looking at your needs and looking around to see who might supply those needs. Suppose your a button whose job is to move the corner of a window. So one of the ways of programming that is for you to be in a loop, constantly looking to see if the mouse is coming into you. It's a polling solution to the problem where somebody is polling somewhere but you're constantly looking to see whether the mouse is coming in. When the mouse comes in then you say, now I know what to do. I'm going to latch on to the mouse's coordinates and, I'm going to tell my window owner exactly how he should be moved around and so as we move around the corner, the window corner moves around itself and so that's this kind of style of programming. Control is explicit. We have to poll to find out things that are going on. The other way of doing it is I could just say I need to know when the mouse comes in to me and then I can do my job. This is like an on condition. But it's an on condition that has to be scoped because we can't have it happening every time, for instance the mouse button goes down. But we can imagine that this guy can say, I have a set of conditions, I'm not going to explicitly look for it, I'm just going to tell the world that if I had these conditions come true for me then I would be able to fulfill my obligations to the rest of the system.
101:05I'd know what to do likewise the window
101:08that encloses this guy could also have a
101:12set of conditions that say well if the
101:14corner if my corner guy starts moving I
101:17should probably move too
101:19I'll change my size if he moves so if
101:23only if somebody would let me know that
101:24then I'll go along see what this is like
101:27this is like constraint programming okay
101:29we're going from
101:31a procedural style which controls past
101:35explicitly around to a declarative style
101:37in which were simply indicating needs
101:40and the system without having to do any
101:43problem-solving is picking up the slack
101:46by providing the actual information in
101:49the forms of messages HyperCard has this
101:51about half way it's a technique we've
101:54been experimenting with at Apple for the
101:56last couple of years and what it looks
102:00like it's able to do is to completely
102:04remove the necessity for actually being
102:07able to follow a control flow what does
102:09this mean when you move an object from
102:11one place to another
102:19when you move an object from some place
102:22into this kind of situation nothing is
102:26going to happen with sorry kind of a
102:30tiny screen isn't it and you put in when
102:33you move a new object in here in this
102:36kind of situation nothing is going to
102:38happen to that object unless you go in
102:40and recode somebody else in order to
102:42send it some messages right and so my
102:47modularity of being able to move an
102:49object from one place to another depends
102:52on me being able to do some kind of
102:54modification and the system is already
102:56there that's not so good it's good in
102:59the sense that this object is guaranteed
103:01not to hurt anybody and it's going to
103:04protect its own self from being moved
103:06around but in fact I still have to go in
103:08and make some sort of modification in
103:11order to get control the flow when I
103:19put in a new blue guy here
103:29and he has all his needs specified is he
103:34going to be able to run why
103:44because he doesn't have because the
103:47whole idea is that he's not intertwined
103:51with anybody else's control he's simply
103:54saying I know what I need god damn it
103:58then the question is can the system
104:00actually deliver those needs just
104:02because he's a new thing and the answer
104:04seems to be yes this is a peek into the
104:07object-oriented programming of the next
104:09couple of years in interesting you know
104:12if this the need to do things this way
104:14came out of yet another project with
104:16children all of the object-oriented
104:18stuff has developed at Park and the
104:21Macintosh user interface came from a set
104:25of designs to try and allow children to
104:30do serious programming on a computer
104:32that was what forced object-oriented
104:34programming out into the open the last
104:37set of stuff that we've been doing with
104:38children at Apple forced this out of the
104:41open because we wanted children younger
104:42than nine to be able to program and
104:45children younger than nine have a very
104:46hard time following control flow of
104:49course when we're thinking about that
104:51we're thinking well of course they have
104:52a hard time following control flow so do
104:54we except where you see the problem is
104:59adults are used to suffering so it's why
105:04I like why I like to design for children
105:06so designing this new programming
105:08language for children I'm going to give
105:10you a little example of some of the
105:11stuff programmed in it this notion of
105:17making control completely modular by
105:20going to a needs thing became apparent
105:23yes
105:27yes
105:33yeah well it's complicated because I'll
105:41give you I'll give you a simple example
105:44and then maybe we can generalize it a
105:47little bit the motivation came from a
105:50couple of years ago of you know
105:53wondering why it was so easy to program
105:55in spreadsheets and wondering what
105:58spreadsheets would be like if there are
105:59more object oriented I've always thought
106:01of the spreadsheet cells as being almost
106:03an object and spreadsheet cells have
106:06this nice characteristic that they they
106:09are these aren't they in other words the
106:13very act of writing the spreadsheet
106:15expression indicates to the rest of the
106:17spreadsheet system what your needs are
106:19now usually they're pretty simple needs
106:21they're just I need to know the values
106:23of so-and-so cells relative to where I I
106:26am but I got interested in generalizing
106:29that and started off with a spreadsheet
106:34system that I did in small talk that had
106:38a spreadsheet optimizer that first
106:41started off simply trying to look at
106:45places you wanted to get values from and
106:48building a propagation network rather
106:49than executing every cell every for
106:52every change in this especially I think
106:53most of you were aware that most
106:54spreadsheets today do not execute every
106:57cell there's a propagation network built
106:59by the spreadsheet compiler that you
107:01don't see that tries to find you the
107:06minimal number of things that have to be
107:08executed every time the change is made
107:11in the in the spreadsheet I started
107:13working on that and then the next thing
107:16is to go to billions where you're
107:19interested in whenever something like
107:21for instance whatever this is equal to
107:23that I would like to do something or
107:27whenever this is less than that I'd like
107:28to do something and the I'll just give
107:32you a hint of it
107:44so they start out with this fairly
107:50simple idea that if you have a variable
107:52somewhere one of the things that you can
107:57do is to link you can have a link to all
108:05of the different places that ever need
108:10the value of that variable and when this
108:15changes you simply fire off all of these
108:18guys and you get the desired result
108:24let's take an expression now so we take
108:30an expression like a is less than B or C
108:39is greater than equal to D and then ask
108:45what we'd have to do to that to make
108:47that efficient the answer is you make
108:50this thing into a little tree and at
108:53each stage each node of the tree you
108:59hold the very the value of the things so
109:03far
109:10so in this case the a value would be
109:13linked through here and you can think of
109:17the tree is pointing upwards
109:29okay and we can presume that this let's
109:33make this an just for the heck of it
109:42see that this is false and we assume
109:45that this is true and that this is false
109:50let's do it the other way I make this
109:52true
109:55this false so the idea is now if it
110:00changes the insight here is that all you
110:03have to do is compare it to whatever the
110:06current value of B is let's say this
110:09goes to to true you don't have to
110:12recompute this guy because it didn't
110:13change it's already part of this frozen
110:16result and then you come up and
110:18recompute this guy so you bait what you
110:21basically have done in this technique is
110:23to have sorted the actual computation
110:25that you have to make this this tech
110:28this way of doing things is called a
110:30continuously evaluating expression
110:41so it's a conglomerate of things it's
110:43actually a little computation engine
110:44designed to compute in parallel and only
110:48the stuff that needs to get computed
110:50gets computed so you the computation now
110:53the compiler instead of compiling
110:54machine code in a system like this is
110:56actually compiling a propagation people
111:00are interested in these techniques I
111:01refer you to the books on functional
111:03programming mostly being written in
111:07England these these days functional
111:10program is about this and well-behaved
111:14functional programming languages have
111:16the property that you can take any
111:17computation that has variables in it and
111:21through a fairly simple compilation
111:24change it into a network that has no
111:27variables whatsoever but simply routing
111:29x' for values does that sound please
111:33please interrupt me if that's it doesn't
111:36sound reasonable is that sound reason
111:38it's intuitively reasonable isn't it
111:41because what does a variable as a place
111:43you go to to get a value but of course
111:46you can what you really need in a
111:48computation is simply a value delivered
111:50you don't need the value to be anywhere
111:51except where the operator is so by using
111:56a combination of those techniques you
111:59can actually remarkably enough it's
112:07actually it's always surprising when
112:08these things work you can actually go to
112:12a thing that's an extreme generalization
112:14of a spreadsheet cell that does an
112:19enormous amount of parallel computation
112:22but in a way in which you see none of
112:24the interactions yourself
112:31now because of production production
112:34system it it's not at odds with the
112:37production system it's on this it's not
112:39like ops five as an example which is a
112:43production system I understand people
112:44use here it's basically it's orthogonal
112:50to whether there's a production system
112:52trying to do things or not
112:54ops five has an example in which the you
112:58have to order the rules yourself to a
113:01certain extent in order to in order to
113:03get efficiency and so forth and you can
113:08think of this as something which is
113:11independent of whether there are rules
113:12and I didn't say there are rules here
113:14what I said is that what we actually are
113:17interested in is whether there's whether
113:20there's a set of conditions that can
113:21deliver to me what I actually need one
113:24of the things you could implement with
113:26this idea is a production system I'm not
113:30but it doesn't lie it isn't particularly
113:32like a production system you could
113:34implement a production system using the
113:36idea though
113:37do you understand to say it just one it
113:42yeah because it because some production
113:44systems have to be executed in sorry
113:48we're getting killed for time we only
113:50have a half an hour so what I would like
113:52to suggest is that we just sit still
113:54while they change the tape is that okay
113:57should only take them 10 seconds
114:11I was brought up about what do you do
114:15with real time in fact what do you do
114:18with time and historically the first
114:28object-oriented programs that were done
114:30outside of machine code were done in a
114:33programming language called Simula and
114:36Simula had this way of looking at time
114:38the Simula he had
114:47a bunch of objects
114:53one for each entity that you're trying
114:57to model so the
115:05these guys might be modeling pipes
115:14and so forth and the blue the blue guys
115:16might be modeling reactors in a chemical
115:23plant or something like that but
115:27basically as far as seeing they're
115:28concerned they're all objects they're
115:31all trying to execute at once trying to
115:37get to the new trying to move advance
115:40the entire system time and they had this
115:44problem of if you have a system time the
115:46system clock that's going on
115:48how can you compute because you might
115:52actually run out of time for computing
115:57before you can actually advance to the
115:58next system time so what the similar
115:59people realize that they wanted to do
116:03was in between the system clock so
116:07system clock might be one and the next
116:13time any of these guys had to compute
116:17was two so what it would do is it would
116:23do all of the computing in between the
116:29ticks of the clock so the computing was
116:31actually outside the space of the
116:32simulation so Simula this is a non
116:36real-time situation simular running on a
116:39mainframe would compute an arbitrary
116:40amount in between each state change so
116:44guarantee that each as much as it could
116:46possibly do it would settle down the
116:48state of each one of these objects
116:50during this time when they were all in
116:53process as soon as that that had
116:55happened then it would say okay now I
116:57can go to the next time on the clock it
116:58is now - what do I have to do now then
117:02the clock could be frozen would compute
117:03like mad again advance the clock again
117:06now of course there's a huge conflict
117:10that's the way you generally do it when
117:12you're doing object-oriented program
117:14huge conflict between this and when you
117:16want to do real-time things because um
117:19real-time things you don't get to stop
117:21the clock the clock is moving along
117:25and of course one of the answers is if
117:29you don't have enough computing power to
117:31compute before the next time the clock
117:34ticks then you're dead anyway
117:36okay so let's assume that we have enough
117:38computing power and just to ask what we
117:42can do an object an object-oriented
117:44design to reconcile what time actually
117:49means and the way people generally think
117:54about time and object-oriented
117:55programming as time has entirely to do
117:57with who can view what when so it's a
118:02viewing operation so let's suppose we
118:04have our objects here and we have some
118:10views
118:18attached to the objects we can ask what
118:22is it like if one object is viewing
118:24another
118:30the first question I just should ask
118:32everybody this is absurdly simple once
118:37once you see it but the first question
118:40is when should I not be viewing the
118:42object when it's in transition right so
118:49it means I have to have at least a
118:51two-phase clock so the object really has
118:58two two states it's going in one is it's
119:00trying to settle itself to what it
119:02thinks as a stable state and the other
119:04one is one that's going to allow itself
119:06to be viewed
119:07okay so mmm let's we can do that and
119:11it's sort of a sort of a diagram here
119:19so here's the here's the object and
119:23here's the view so what we're saying is
119:27that when the object is computing we
119:30can't view and when the object is
119:34viewing we can't compute
119:45so we're gonna have a bunch of these
119:48little phases like this now that's not
119:53always useful sometimes this viewing
119:58thing is very long so the viewing can
120:02actually hold up the progress of the
120:04computation and so what can we do there
120:11this is suggested by actually this model
120:14so far just just curious to see if it
120:16suggests anybody what would be a good
120:17thing to do if to break this rigid
120:22synchrony we have what can you do yeah
120:27we could that's what's called slippage
120:30so we could actually arrange a slippage
120:32model so we let the as before as we had
120:37before we let the object compute and
120:41what we take is a copy of it that we let
120:47the viewer view
120:54and so the object in simulation can have
120:57an quite a number of phases as it goes
121:00along and every once in a while we get
121:07to view it
121:13we take let's say we take this guy right
121:15here okay now what's interesting is in
121:20an object-oriented system this slippage
121:23model is usually computed automatically
121:25by the the object in the view both of
121:29which are objects when you hook the view
121:31up to the object what they do is
121:34exchange information because one of the
121:36things that the object has some sense
121:37about is how long it takes it to settle
121:40it state typically the view has some
121:43sense about how long it takes to
121:44abstract the view and so they actually
121:46arrange and build a little buffer in
121:53between themselves and that buffer has
121:55the actual amount of information to
121:59allow the slippage to happen so the way
122:02this intertwines with doing real-time
122:03and deterministic computing is almost
122:06all real-time solutions to queuing
122:12problems knowing some sort of
122:15determinism they actually aren't
122:16completely deterministic what you
122:18usually do is you're saying I have some
122:20limits that I want to guarantee the
122:25computation is going to take place in
122:26between it I'm going to do enough
122:27buffering to make sure that those limits
122:30get down so for instance when you're
122:32doing real-time reading of records from
122:36Fast disks and so forth you set up
122:39buffer areas because you don't want to
122:42have to have real kind time constraints
122:44in every part of your real time
122:47computation in an object-oriented system
122:50these are usually handled by having
122:54what's called a viewing model small talk
122:57has one called models views and
122:58controllers which is quite general and
123:00has the facilities in it for generating
123:03all manner of slippage models in between
123:06by you putting on the outside what it is
123:09that you actually need to know from
123:11these objects at some point of course
123:13you can break it down there's no real
123:15time system you cannot break down but
123:18this gives you the maximum amount of
123:19automatic buffering that the system can
123:22generate without having to be explicitly
123:23programmed
123:27yeah very very large how can you well
123:51the way that's usually done is by trying
123:53to again it's that you know the stuff
123:57isn't a panacea but what you usually try
124:00and do is when you write a device driver
124:04in an object-oriented language what you
124:06try and do is ask what devices are
124:09likely to be like this device now what
124:12is this like so when you write when
124:17people do a user interface and an
124:19object-oriented language usually they
124:21don't write a driver for the mouse or
124:23for a tablet or anything else what they
124:25come up with is an abstraction of what
124:28it means to it's usually call a pick
124:30device it's an abstraction of what it
124:32means to be able to do selection and
124:35tracking and then one programmer at one
124:39time writes code for that and then if
124:42you come up in a system and it has a
124:44specific device you may have to write a
124:46line or two of additional code but it's
124:48written in a subclass below that the
124:51main driver is already written already
124:52been written in it's um it's not just
124:55doesn't just serve as the code for what
124:56you're doing it serves as the model for
124:59how you treat the actual devices when
125:01they're put in there so I'm part of the
125:04part of the the charm of the system is
125:07to be able to get away from the from the
125:10particular as much as possible and
125:13program as much as possible in the
125:15general case the whole act of
125:20subclassing is basically saying to
125:21something I want something just like you
125:23accept and the theory behind this which
125:28seems to work is that it is much easier
125:29to program differentially than it is to
125:32program from scratch it's much easier if
125:34you see something that is like what you
125:36want and you can get it
125:38in a way that um doesn't damage anything
125:42else then if all you could make have to
125:45make as incremental changes to it then
125:47you should be way ahead that's not
125:50always true you know there are always
125:53pathological cases always pathological
125:56cases but generally speaking like this
125:58is an example where the whole strategy
126:01once it was thought out was realized oh
126:04yeah this is something we can use it's
126:05not just for user interfaces we can use
126:07it for every kind of device drivers we
126:09can use it for every kind of real-time
126:11stuff where we have two different clocks
126:14going at two different rates and we're
126:15trying to synchronize in some way why
126:18should we have to write this over and
126:20over again why should some program we
126:21have to figure it out over and over
126:23again it's not that we have the solution
126:24to every possible problem but what we're
126:26saying is we've got a solution it's the
126:2980/20 rule get a solution to the
126:32eightieth you know 80% of all of the
126:34code you're ever going to have to write
126:35if you can put that into a superclass
126:39and then distribute it automatically as
126:42part of the solution so small so small
126:43that when you when you're doing a
126:46viewing operation and small talk you
126:48don't even have to think to yourself
126:49whether you should worry about
126:52synchronization or not until long after
126:56you may decide that you need it then you
126:58just have it oh it's already in here I
126:59just got it for free when I subclass the
127:01class view well try think like I say an
127:06ADA it's a little bit harder because you
127:08can't do those super classes that have
127:10all those goodies lying in there you
127:12have to you can do it with a macro
127:14operation people do to super classing
127:17and ADA by making macros that allow them
127:21to do a kind of copying and stuff
127:48No well in small talk no you can small
127:53talk allows you to dynamic basically
127:55small talk has no concept of loading
127:59code so everything is there
128:02dynamically into there and at any point
128:05you can go in examine any piece of code
128:08in the system you can rewrite any piece
128:09of code in a production case you really
128:12don't want to allow just anybody to go
128:15in and rewrite a superclass because of
128:19course the work it's really bad if they
128:21if the superclass starts doing something
128:24different
128:25generally when people go to rewrite a
128:26super classes to improve the algorithm
128:29that hundreds of applications are
128:32already using like you may go in and
128:34improve the sort algorithm yeah
128:51right that's why I was talking about the
128:55configuration so my belief is that in a
128:58production case you must have something
129:00like the configuration setup or else
129:05it's just too fragile it's not it's it's
129:09fragile in a funny way because in small
129:10talk we used to give $5 bills away to
129:15anybody who could crash the Smalltalk
129:17system it's very hard to crash an a good
129:21object-oriented system because there
129:22isn't anything you can get to that where
129:24you can actually hurt more than one
129:26layer of thing and then the system's
129:29says hey wait a minute what are you
129:30doing
129:30like in the small talk debugger as
129:34you'll discover I think there's a
129:35tutorial coming up has the anytime
129:38there's any kind of an error the system
129:42doesn't crash there was there's no
129:44concept of crashing the error is simply
129:47set aside as just another process and
129:50once when we were debugging the system
129:52we found 1,700 suspended errors waiting
129:57for somebody to take care of them and so
129:59I'll talk didn't care you know it's just
130:00an error comes up fine you know um set
130:04it aside it's right there you can go
130:06back to it anytime you want but keep on
130:07running it just keeps on running so the
130:11that's one of the reasons why we didn't
130:13do a configuration language because we
130:15were programming in the small and you
130:16couldn't hurt yourself
130:18so as the the worst he could have
130:20happened was something annoying they
130:23would come up but it wouldn't crash what
130:25you're doing so somebody who fixed it or
130:28make a note of it but I think that's
130:29intolerable in the production sense
130:33where you really don't well you have
130:36people who aren't part of the same group
130:38and so forth that you really have to
130:39have a configurations language and the
130:41super classes are the ones that you want
130:43to have most understood and most nailed
130:46down in particular the for instance in
130:53small talk it's often to make things
130:56like the sorting stuff parametric so
131:00you're actually sending in sorting
131:03objects that will do sorting for you
131:05as parameters rather than even putting
131:09that in embedding that into the the code
131:12just because you don't want somebody to
131:13try and change it that way you'd rather
131:14have it be something separate that you
131:17can dynamically bind in really good
131:20superclasses don't do much except act as
131:23really good binding mechanisms for other
131:27stuff that's going on
131:39yeah
131:43yes there is you can but again the the
131:48original the original small talk for
131:50example didn't use a kind of procedure
131:53call in order to send it really acted as
131:57though you're on a network and if you're
132:00interested in what order things had to
132:03be done in they they could actually be
132:06stamped and recued at the other end and
132:09people do do that when when you run
132:12small talk over the network people make
132:15the connection to the network by having
132:17what are called phantom objects and a
132:20phantom object is a stand-in from the
132:22object you're trying to send the net
132:23right because you're always sending a
132:24message to something
132:26so suppose yours suppose your
132:39so if you're over here and you think
132:45you're sending a message what you think
132:47you're doing is sending a message from
132:49object a to object B and but they may be
132:53on different machines and so what may be
132:55really going on is object a is sending a
133:01version of object B
133:11which is really going over the network
133:14to the real be again these are called
133:18Panem objects and usually there's just
133:21one class of them and whatever you're
133:24distributing a copy a computation
133:26usually the environment for the objects
133:31just consists of a few local objects and
133:35the rest of them are phantom objects the
133:36phantom objects take care of all the the
133:38network stuff and synchronizations and
133:43reorderings and other kinds of things
133:44that you have to do when you're going to
133:45slower slower media that's a
133:49well-established technique and any good
133:51object-oriented language you can set
133:53that up literally in an afternoon today
133:57oh it's quite instructive to think about
133:59what it means not to send just a message
134:02but to send an object from one place to
134:03another what part of its environment do
134:05you have to bring along with it in order
134:08for it to be understood see in theory
134:10sending an object let's say we send
134:14objects see across
134:20well si may not be terribly understood
134:24on the other side on the other hand it's
134:26still active so if your network has the
134:31rule as ours did it park that whatever
134:33an object shows up and its class isn't
134:36there its class a clone of its class
134:40gets sucked over with it so you compare
134:44that to sending a data structure which
134:45is sending bits and how fragile they are
134:50because you're not sure that there are
134:51procedures at the other end to know them
134:53here you're ensuring that either nothing
134:55at all happens or the right procedures
134:57are actually automatically sent along
134:59and so you can it's remember that story
135:02I told the beginning of the Vosges 220
135:04that's exactly how the training command
135:07protected their their tapes you just
135:09make sure the procedures go along with
135:11them and it's quite easy using these
135:13phantom objects to make that automatic
135:15so you can think of the network of
135:18objects as constantly rebalancing itself
135:21as to where the code actually is
135:35I think I believe that's true and from
135:42Park
135:43yeah it's written it's been written up
135:49yeah well my message to you is this is
135:52the same reason I told you the Arthur
135:53Andersen story is they have exactly the
135:56same you know their their attitude to me
136:01was kind of interesting they said they
136:03went to several phases and this is
136:05probably you're in one of these phases
136:07right now as well it went through one
136:09phase where the first phase with objects
136:12it was like magic God all the things you
136:14could do code is so small the second
136:16phase was complete disillusionment when
136:19they realize that for instance small
136:21talk which they were using as a model
136:23didn't scale they said you know what is
136:26you know is this the emperor's new
136:28clothes or what and I said no it's just
136:31because the part of the reason small
136:34talk wasn't built to scale was simply
136:36because we were able to do an enormous
136:39amount with very tiny programs and we're
136:43designing for children anyway and when
136:47you want to use these ideas and they're
136:48in the in the large I believe that you
136:51have to do a little bit more then you
136:53can go out on the street and buy that's
136:55what I'm my message to you is that and
137:00it was to Arthur Anderson that you know
137:02a lot about what it can once you've
137:05learned the object-oriented style which
137:07I believe is the right way a protecting
137:09state of the right way of making
137:12components the right way of making urns
137:14superclasses right way of sharing
137:16there's a whole bunch of right things
137:17about it in order to make it work in the
137:20large you then have to sit down and
137:23protect that by coming up with a
137:25configuration language and you can do
137:27yourself a lot of good by doing that
137:30carefully because the configuration
137:32language can include languages that you
137:34already have hundreds of programmers
137:36that know how to write in in other words
137:39the configuration language can be a way
137:41of protecting programs that are already
137:44written in COBOL and Fortran as well as
137:48new programs written in Ada it should be
137:49a really separate way you think of isn't
137:52and the architecture is opposed to the
137:54bricks of actually building the thing
137:57the architecture to me rules life is an
138:00architecture it wasn't
138:02as early as the turn of the century
138:04there are people that thought memory
138:05there's the stuff called protoplasm
138:07written about in books was supposed to
138:11be some special kind of material that
138:13you can build living things out of
138:14because people didn't believe that
138:16ordinary chemicals could bake you could
138:19make a living thing out of it wasn't
138:21really until 20 or 30 years ago that it
138:24was really shown quite definitively that
138:28we actually are just an architecture in
138:30fact we know now that the atoms in our
138:33body are actually recycled about every
138:35seven years so you and I as individuals
138:39are patterns in space the material is
138:42moving through we don't have the same
138:45atoms in our bodies that we had seven
138:47years ago we are a pattern and
138:50interesting things made out of the
138:53patterns you have - you know I have to
138:55have some understanding of the bricks
138:56and stuff which I think everybody is
138:58getting now but at some point you'll
139:00realize that the power of this stuff
139:02isn't from what the bricks do and that
139:04the bricks are have integrity the power
139:08of the stuff is from the architectures
139:11that you can create and the
139:12architectures have just been scratched
139:15now up until really a couple of years
139:19ago there probably been less than a god
139:21I don't know 100 or 200 people over two
139:24decades actually doing this stuff so
139:28it's the and the problems that have been
139:32worked on have tended to be small the
139:35reason I believe that object-oriented
139:36programming works well in the large is
139:38simply because it works well in the
139:40biological world and I see no reason why
139:42it is going to fall down in any way when
139:46we go large but in order to in order to
139:49make it work we have to either look at
139:51the biological world war which is the
139:55biological reason of urging can a
139:57configuration language or we have to go
139:59after for other reasons of just
140:01realizing hey this stuff gets fragile at
140:03this point what do we actually need and
140:06the answer is a configuration language
140:14but I think that there might be some
140:17immediate benefit these ideas of
140:20object-oriented design where you have
140:23existing systems that because it would
140:26nature
140:27the islands of automation approach have
140:29gotten tremendous ly complex and you
140:32need to be able to characterize various
140:35things possibly the concept of objects
140:38to help you do that and to help them
140:40understand what are the objects of one
140:43of the Linc
140:46right well I'm trying to think of it was
140:51Rudolph's irken that said you can't if
140:54you want to be a piano player you should
140:55spend half of your time reading books
140:57and his his point was is that if you
141:02spend all of your time just learning to
141:04move your fingers you have not absorbed
141:07any contact the context necessary to
141:09play any real piece of music that
141:11there's there's something else besides
141:13the practical application of the of the
141:16technique and I think that the somebody
141:18was asking me at the break it was a very
141:21good question actually which is and the
141:26it had to do with she doesn't sounds
141:30like objects make you do a lot of design
141:33and anyway but you know it wasn't said
141:37stupidly at all it's just said isn't
141:40that hard and I said yes it is hard and
141:43it's hard whether you've got objects or
141:45not the main reason is that objects
141:48provide both an excuse for designing and
141:51they also give you a framework for
141:52holding the design every little bit of
141:55design you do you get rewarded in an
141:57object-oriented system for having done
141:58it you really get rewarded where's it's
142:02hard to get rewarded in a in a procedure
142:04data structure system because often the
142:07design has nothing to hang itself on
142:10there can be local good things but you
142:12can't propagate the design forward the
142:15way you can in an object-oriented system
142:21I don't know because I haven't hung most
142:25you know Edward de Bono's says the
142:27problem with most American companies is
142:29that when they get in trouble they
142:30redouble their efforts so you know the
142:36idea is that we're basically too
142:37industrious for our own good and once we
142:39learn a technique we tend to put our
142:41head down and just fight like mad rather
142:43than trying to smart our way out of it
142:45like I said I particularly efference to
142:49me I had actually seen these techniques
142:50and actually programs using some of
142:52these techniques for five years for a
142:54period between 1961 and 1966 before
143:01Simula hit me on the head and hit me on
143:04the head just because at that point I
143:06had a problem that was much harder than
143:08I wanted to program it was the first
143:10time I was willing to actually see that
143:13was when I was going through insane
143:14minutes and I said to myself holy cow
143:17this is so you know there's just nothing
143:20here all I have to do is this and that
143:21I'm done you know all of these things
143:25fall in I was actually programmed in the
143:27game of space war you know which is one
143:30of the first video games but it wasn't
143:31even a video game back in the in the 60s
143:34and they're all of these it's very hard
143:35to do in an ordinary language because
143:37you have all of these spaceships and you
143:39have planets and you have torpedoes and
143:42when I was looking at Simula I was
143:44trying to get figure a way out of doing
143:48this I didn't want to do it in 30 pages
143:50of alcohol or so and I was trying to
143:53figure out a way and all of a sudden it
143:55occurred to me that every single thing
143:56in space war and Simula was the same
143:59thing the only thing was different was
144:01the costume they were wearing the
144:03planets were the same the spaceships
144:05were the same the torpedoes were the
144:07same there was like one line of code
144:08difference in each of their behavior and
144:11they all had to obey Newton's laws they
144:13all were interacting with each others in
144:15exactly the same way it was trivial and
144:17I wrote that program and a half a page
144:19of code and I never looked back since
144:21because the you know the that is the
144:25thing if you don't find this folding up
144:27of complexity into simplicity then
144:32either you're working on a truly hard
144:34problem
144:35which really really do exist
144:38or there's probably a rotation of the
144:40situation that you haven't examined yet
144:43you're probably still thinking the old
144:45way in thinking in terms of particulars
144:48rather than generalities we're so used
144:50to programming up each specific thing
144:52that's hard for us to think of avoiding
144:54that then we only have to to program up
144:57one general thing and then write a
144:59couple of lines of code for each of the
145:01particulars and we're done that's a
145:03really good test in this stuff and it
145:07accounts for the religious fervor of
145:09people who have had this happen to
145:11themselves as after pounding your head
145:12away on a system to have it fold up like
145:15like there was nothing there it is the
145:17most amazing thing they have an
145:20operating system go away to something
145:22that is practically a clock which is
145:25what it is in an object-oriented system
145:26because what do you need in an operating
145:27system well once you've got the ability
145:30to sustain objects and stuff like that
145:32you practically only need a clock you
145:34only need to get control routed around
145:36and everything else is written
145:37essentially as an application on top of
145:40that kernel that's a very modern way of
145:42looking at things and it's a terrific
145:44way of thinking about doing stuff
145:56okay yeah
146:00that's a very good question
146:03some of these idea a relational database
146:08everybody knows what a relational
146:09database is right okay so the the there
146:16are several things a relational data an
146:19item in a relational database has fields
146:24it has some of some of the things and
146:26depending on the data dictionary that
146:28the relational database wants to sustain
146:30you can occasionally do some integrity
146:33constraints the most relational database
146:35is friend for example is very difficult
146:37to do the following thing in a data
146:40record and that is make sure that Joe
146:42blows age is always the right one when
146:45you ask it because when you ask
146:47somebody's age in a relational database
146:49what it expects to do is to go to a
146:51field and find a number and bring it
146:54back to you right in an object system
146:58what you would have there is you'd sent
147:00the message age to the object and it
147:05could just go to a field and bring back
147:07a number but a smarter one would
147:09actually look at the guy's birthdate and
147:11compute his age for you right then and
147:15so you'd always get the right answer
147:16every time you asked aged you would
147:19always get the right answer from the
147:21object you would not get it from the
147:22relational database unless you're doing
147:24careful updates that's one difference
147:28the other difference is that in a in a
147:31relate in any kind of a relation it is
147:35extremely difficult to embed code
147:37although people sometimes do by
147:39embedding it on the outside of the
147:41database rather than on the inside with
147:44it so for doing a dynamic simulation for
147:47instance is quite difficult a good way
147:49of understanding where relational
147:51databases is going to go comes out of
147:53one of your own products and an industry
147:56that McDonnell Douglas is one of the
147:58leaders in Amanda's CAD CAM CAD cam
148:01can't be done on relational straight
148:05relational databases there simply aren't
148:07enough hooks in there to deal with all
148:09the things it's not you can't store the
148:11data so you can't deal with all the
148:13other things that the relational
148:14database database can't store that
148:18cad/cam requires so object-oriented
148:23servers like the gemstone or this the
148:27ontological rated servers are ones that
148:32the CAD cam industry is going towards
148:34now these allow you to do all the things
148:36that you're used to doing with
148:37relational database but also give you
148:39this extra level of abstraction that you
148:43get from objects what's nice about it I
148:46think for people worried about
148:48transitions is that there's a fairly
148:50reasonable transition almost everything
148:51gets better when you go to an
148:53object-oriented database server for
148:56instance I think most people would like
148:59for instance to have joins be real
149:03things rather than a made-up thing for
149:07the moment and they can be in an
149:09object-oriented database most people
149:11would like to have views be things that
149:14you can add it back through or views
149:15that you can view whereas a view in a
149:19relational database is an extremely weak
149:21notion of the whole notion of what view
149:24is where in an object-oriented system is
149:26extremely easy to have a view look like
149:29the set of stuff itself and so you can
149:31put another view on top of it and
149:33cascade them and so forth and all of
149:35those things are being done right at
149:38this moment with object-oriented servers
149:47excuse me yeah I think for also because
149:59the the tutorial it's going to happen in
150:01a couple of weeks is going to be one of
150:02the people from this digital company the
150:05company that does small talk V I want to
150:08just mention again that besides the fact
150:12that it's cheap small talk V I think is
150:15only $99 on the IBM PC and 150 on the
150:18Mac so it's the cheapest small talk they
150:21have by far the best manual none of the
150:24other manuals are even in second place
150:27because they actually don't believe that
150:30you understand about object-oriented
150:31programming in the beginning of the
150:34thing they actually write the manual
150:35there's a splendid tutorial hands-on
150:37tutorial for getting versed with all of
150:40the object-oriented lore and
150:42sub-classing and building a very
150:45powerful little application another
150:47thing that they give you for free in
150:51with small talk I don't have any stock
150:53in the company I haven't made a cent on
150:56small talk but what they do is they also
151:00give you for free a full-blown
151:03implementation of Prolog Edinboro Prolog
151:06written in small talk okay and just to
151:13give you an idea this whole
151:13implementation of Prolog written in
151:15small talk with its own user interface
151:17its own browser its own debugger and
151:19everything else is less than 20 pages of
151:21code okay and if you've ever tried doing
151:25anything like a programming language
151:27like this is a convince err okay and it
151:30uses object-oriented programming for
151:33what it's really it uses the fact for
151:35instance in small talk everything is an
151:37object everything is an object and
151:40protected including the things that you
151:42think of as stack frames and ordinary
151:44languages that you can't even get to how
151:46is it the bugger written in small talk
151:48well this stack frame is simply an
151:51object so you simply write a method that
151:53allows you to ask the guy well what do
151:56you what do you have here what do you
151:57have here can you advance your PC what
152:00see I mean I mean the debugger is like a
152:03page and a half long because it actually
152:05is part of it's just a subclass of class
152:09stack frame prologue is so simple in
152:12small type because they actually take
152:14the stack frame as an object and
152:17implement prologues control structure
152:19directly in using the small talk using
152:23small talk sone stack frames but using a
152:25non stack protocol which is what the
152:28Prolog backtracking requires this is
152:31gorgeous stuff and it's done completely
152:32without impinging on the integrity of
152:36small talk itself the two systems are
152:39integrated together and so you can do
152:41Prolog unifications into small talk
152:44variables and vice versa so it's a
152:47perfect example of what an embedded
152:49system in an object-oriented system
152:50looks like they give it to you for free
152:52you can do real work in it if you just
152:54want to use it but people are really
152:56interested in why this stuff is powerful
152:58that's an example of where the power of
153:02it is actually concentrated and used by
153:04some design thinking here's another one
153:08most object-oriented languages don't
153:12have a complete model so for instance
153:16when Simula for instance has classes so
153:21you have a class paragraph or a class
153:25string but Simula doesn't have classes
153:29be objects so if you have an
153:32object-oriented one of the choices you
153:34could make is to have everything in the
153:36language be an object why not that means
153:38if there are things called classes there
153:42must be a class class a class whose
153:45instances are the classes okay that
153:50sound shaky
153:53let me just let me just draw it cuz it's
154:09so I'm going to draw classes in red so
154:15this might be integer might be fraction
154:21might be paragraph this might be
154:24document this might be file and there
154:29are instances I'll draw in green this
154:32might be three and this might be for
154:34this might be three quarters this is a
154:40paragraph of text and so is this one
154:44this is a whole document this is a whole
154:47file here's another one they have lots
154:51of instances of these classes they've
154:53been on Simula these red things in an
154:56ADA these red things aren't around at
154:59runtime
154:59they're like macros they just help
155:02create the structures underneath that
155:04these green guys can work with but in
155:07small talk these are really objects and
155:11the question is is if they're objects
155:13what are they an instance of what is
155:16common to all of these things
155:19somebody tell me they're all a class so
155:23what what's common to all of these what
155:25do they do they all make instances right
155:30I mean they're the thing that holds all
155:32of the information that's necessary to
155:34make multiple instances and so you can
155:37imagine that there might be a thing
155:39called class class whose own instances
155:48are these guys
155:55okay that sound reasonable why not okay
156:03down remember I can subclass what do you
156:08think it might mean to sub class class
156:11class let me do that let me use another
156:16color here
156:23so I'm going to sub class class class
156:24here look just in general what is the
156:31sub class of class class going to be
156:33able to do it's going to no it's not
156:36gonna make some classes it's gonna make
156:38be able to make classes like these guys
156:40plus something else then I'm gonna add
156:43right there because anything that's of
156:48class class is going to make classes so
156:51any subclass of it is going to make
156:52classes now here's an example of
156:55something we did at parc many years ago
156:57we wanted to do a system in which every
157:02instance was data-driven okay in other
157:06words we wanted to do a data flow system
157:13inside of small talk in which the every
157:17thing that happened to some variable in
157:22an instance could be propagated to the
157:24next thing that meant that every
157:25instance had to have besides the places
157:29in it that an ordinary instance has
157:31here's what an ordinary instance looks
157:35like it's a thing that has slots in it
157:37for holding values and plus what we
157:41wanted to do was to tack onto that some
157:47pointer information that would link all
157:50of these guys together so we'd actually
157:51have a data-driven
157:53network here now how do you suppose we
157:56did that sub class class class
158:02right the various places I could do that
158:04but what if I did it up here and put
158:07that information in here and now every
158:14every class that this guy makes whatever
158:21it is is going to have the property that
158:24the instances of it regardless of what
158:27these guys are as I go along making up
158:29new classes for this kind of thing and
158:30that kind of thing every one of them is
158:32going to have the property that the
158:33instances are going to be instrumented
158:34this way see how high that change was
158:37made what I did is I actually change the
158:40meaning of what class this was in the
158:43system with one operation I just
158:45subclass a very very high-level guy and
158:49all of a sudden I got essentially a new
158:51small talk with a completely different
158:54strategy for how these things strategy
158:57independent of what the new classes are
158:58going to be okay that's the power of
159:02this stuff it's not the direct stuff
159:06that you can do that's so appealing now
159:08it's the meta stuff that you can do
159:10that's so incredibly powerful because
159:13you can literally when you have a new
159:16idea that's important you can literally
159:18distribute that idea over the entire
159:20universe with just a few changes in a
159:24system like this
159:25well let's I think we're about done let
159:28me let me give you a one of our favorite
159:33stories and as a winch and Winston
159:38Churchill story widget Winston Churchill
159:41jokes always have them at a party after
159:44a bunch of whiskeys
159:46and I'm sure everybody knows the one of
159:49the he was incredibly drunk and a woman
159:53came up to him at two o'clock in the
159:55morning and said mr. Churchill you're
159:57disgustingly drunk and he looked at her
160:01said and you Madame are indescribably
160:03ugly but in the morning I'll be
160:05indisputably sober
160:11so this particular this particular
160:14Churchill joke a little earlier on the
160:16party he hadn't had quite as many
160:18whiskey's and the hostess of the party
160:20came over to him quite agitated and said
160:23mr. Churchill I'm just really upset I
160:26don't know what to do I saw a famous
160:28Earl over there steal some of my silver
160:32salt shakers what should I do
160:33Churchill thought for a minute and stuck
160:35his cigar in his mouth and went over to
160:38the Earl along the way he took a salt
160:40shaker himself and put it in his pocket
160:42and we got over to the Earl took it out
160:45of his pocket and said I think we've
160:47been noticed perhaps we should put these
160:48back so that's my version for why we won
160:54World War two in other words if you want
160:57to get people to do something to go
161:00along with you you have to involve them
161:01in the same conspiracy and
161:04object-oriented programming is a kind of
161:07conspiracy that people are just finding
161:09out about it I hope I've been able to
161:10involve you in a little bit and I hope
161:12you will involve others thank you
161:14[Applause]
