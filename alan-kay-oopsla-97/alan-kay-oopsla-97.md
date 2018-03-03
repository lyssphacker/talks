
### Encapsulation
This is the simple one. This is the one, by the way, that C++ has still not figured out, though. There is no idea so simple and powerful that you can't get zillions of people to misunderstand it. You must, must not let the interior of any one of these things to be a factor in the computation of the whole. This is only part of the story. The cell membrane is there to keep most things out, as much at it is there to keep certain things in. I think our confusion with objects is the problem that in our Western culture, we have a language that has very hard nouns and verbs in it. Our process words stink. It's much easier for us when we think of an object—and I have apologized profusely over the last twenty years for making up the term object-oriented, because as soon as it started to be misapplied, I realized that I should have used a much more process-oriented term for it.—The Japanese have an interesting word, which is called ma. Spelled in English, just ma. Ma is the stuff in-between what we call objects. It's the stuff we don't see, because we're focused on the nounness of things rather than the processness of things. Japanese has a more process-feel oriented way of looking at how things relate to each other. You can always tell that by looking at the size of the word it takes to express something that is important. Ma is very short. We have to use words like interstitial or worse to approximate what the Japanese are talking about. The realization here—and it's not possible to assign this realization to any particular person because it was in the seeds of Sketchpad, and in the seeds of the air training command file system, and in the seeds of Simula. That is, that once you have encapsulated, in such a way that there is an interface between the inside and the outside, it is possible to make an object act like anything.
**The reason is simply this, that what you have encapsulated is a computer.** You have done a powerful thing in computer science, which is to take the powerful thing you're working on, and not lose it by partitioning up your design space. This is the bug in data and procedure languages. I think this is the most pernicious thing about languages like C++ and Java, is that they think they're helping the programmer by looking as much like the old thing as possible, but in fact they are hurting the programmer terribly by making it difficult for the programmer to understand what's really powerful about this new metaphor. People who were doing time-sharing systems had already figured this out as well. Butler Lampson's thesis in 1965 was about what you want to give a person on a time-sharing system, is something that is now called a virtual machine, which is not the same as what the Java VM is, but something that is as much like the physical computer as possible, but give one separately to everybody. UNIX had that sense about it. The biggest problem with that scheme is that a UNIX process had an overhead of about two thousand bytes just to have a process, and so it was going to be very difficult in UNIX to let a UNIX process just be the number three. You would be going from three bits to a couple of thousand bytes, and you have this problem with scaling.

### Every object should have IP
Here's one that it is amazing to me that we haven't seen more of. For instance, one of the more amazing things to me, of people who have been trying to put OOP on the Internet, is that I do not—and I am hoping someone will come up afterwards and tell me of an exception to this—but I do not know of anybody yet, who has realized that, at the very least, every object should have a URL, because, what the heck are they if they aren't these things, and I believe that every object on the Internet should have an IP address, because that represents, much better, what the actual abstractions are of physical hardware to the bits. So this is an early insight that objects basically are like servers. This notion of polymorphism, which used to be called generic procedures is a way of thinking about classes of these servers. Everybody knows about that.




Here's one we haven't faced up to much yet, that, now we have to construct this stuff and soon we'll be required to grow it. It's very easy, for instance, to grow a baby six inches. They do it about ten times in their life and you never have to take it down for maintenance. But if you try and grow a 747, you are faced with an unbelievable problem, because it's in this simple-minded mechanical world, in which the only object has been to make the artifact in the first place. Not to fix it. Not to change it. Not to let it live for a hundred years.

So let me ask a question. I won't take names. But how many people here still use a language that essentially forces you—and the development system forces you to develop outside of the language; compile and reload, and go, even if it's fast, like Virtual Café.—How many here still do that? Let's just see. Come on. Admit it! We can have a Texas tent beating later. [Smiles] [Laughter] That cannot possibly be other than a dead end for building complex systems, where much of the building of complex systems is in part going to go into trying to understand what the possibilities for interoperability is with things that already exist.

I just played a very minor part in the design of the ARPANET. I was one of thirty graduate students who went to systems design meetings to try and formulate design principles for the ARPANET, also about thirty years ago. The ARPNANET, of course, became the Internet, and from the time it started running—just around 1969 or so—to this day, it has expanded by about a factor of a hundred million. That's pretty good. Eight orders of magnitude. I talked to Larry Roberts about this the other day. There is not one physical atom in the Internet today, that was in the original ARPANET. There is not one line of code in the Internet today that was in the original ARPANET. Of course, if we had IBM main frames in the original ARPANET, that wouldn't have been true. This is a system that has expanded by a hundred million, has changed every atom and every bit, and has never had to stop. That is the metaphor we absolutely must apply to what we think are smaller things.

When we think programming is small, that's why your programs are so big. That's why they become pyramids instead of gothic cathedrals. Next. [Slide]

Here's the other big source. Certainly the greatest, single language along with Simula of the sixties, I think. One with as many profound or more profound insights—LISP. On page thirteen of this book that was published in 1962, there's a half page of code which is the reflective model of LISP written in itself. All the important details of LISP semantics and the guidelines for how to make a LISP interpreter are in that half page. It is this aspect—this meta-reflective aspect—that to me, is the saddest thing about what is happening with Java. When Java first happened I thought, Well, it's legitimizing something that most people have not believed in for a long time, which is this byte-code approach of being multi-platform like we had at Xerox PARC.—It's not a new idea. It actually goes back into the sixties. But when I looked at Java, I thought, My goodness, how could they possibly—and of course, we know that the history was more about programming toasters, originally, than being on the Internet—but, my goodness, how do they hope to survive all of the changes, modifications, adaptations, and interoperability requirements without a meta-system. Without even, for instance, being able to load new things in while you're running. The fact that people adopted this as some great hope is probably the most distressing thing to me, personally, as I said, since MS-DOS. I mean, it represents a real failure of people to understand what the larger picture is, and is going to be. Next slide.

This notion of meta-programming. Lots of different ways of looking at it. One of them is that, any particular implementation is making pragmatic choices, and these pragmatic choices are likely not to be able to cover all of the cases, at the level of efficiency, and even at the level of richness required. Of course, this is standard OOP lore. This is why we encapsulate. We need to hide our messes. We need to have different ways of dealing with the same concepts in a way that does not distract the programmer. But in fact, it is also applicable, as the LISP people found, and we at Xerox PARC found; you can also apply it to the building of the language itself. The more the language can see its own structures, the more liberated you can be from the tyranny of a single implementation. I think this is one of the most critical things that very few people are worrying about in a practical form. One of the reasons why this meta stuff is gonna be important, in such a way that nobody will be able to ignore it, is this whole question of, How do we really interoperate on the Internet five and ten years from now. I don't believe Microsoft is going to be able to capture the Internet. I think it's too big. I think there are too many people supplying ideas into it, and I think that people are going to be sophisticated enough to realize that an IBM or a Microsoft type solution is simply neither called for nor possible. What that means is that there's going to be dozens and dozens—there almost already are—dozens and dozens of different object systems, all with very similar semantics, but with very different pragmatic details. If you think about what a URL actually is, and you think of what an HTTP message actually is, and if you think of what an object actually is, and if you think of what an object oriented pointer actually is, I think it should be pretty clear that any object-oriented language can internalize its own local pointers to any object in the world, regardless of where it was made. That's the whole point of not being able to see inside. A semantic interoperability is possible almost immediately by simply taking that stance. This is gonna change, really everything. Things like JavaBeans and CORBA are not gonna suffice, because at some point one is gonna have to start really discovering what objects think they can do. This is going to lead to a universal interface language, which is not a programming language per se. It's more like a prototyping language that allows an interchange of deep information about what objects think they can do. It allows objects to make experiments with other objects in a safe way to see how they respond to various messages. This is going to be a critical thing to automate in the next ten years. Next slide.

[The slide is showing the book cover: The Art of the Metaobject Protocol]

So here's a great book. How many people have read this book? When they wrote this book, I called them up and I said, This is the best book anybody has written in ten years, but why the hell did you write it in such a LISP centric, closed club centric way? This is a hard book for most people to read. If you don't know the LISP culture, it's very hard to read. If you don't know how CLOS [the Common Lisp Object System] is done, it's a very hard book to read, but this book has some of the most profound insights about, and the most pratical insights about OOP, than anybody has done in the last many years. I really commend it to you. If there are any university professors here who would like to get the next [unintelligible] balloon, I will give it to anybody who rewrites that book so that the general object-oriented community can understand it. It would be a great service to mankind.

What happened in most of the world, starting in the seventies, was abstract data types, which is really staying with an assignment centered way of thinking about programming. In fact, when I made this slide, C++ was just sort of a spec on the horizon. It was one of those things, like MS-DOS, that nobody took seriously, because who would ever fall for a joke like that. [Laughter] Next slide, please.

Actually, my favourite C++ story is, at Apple, there is this operating system, remarkably, coincidentally named Pink. [Smiles] [Laughter] It was so great! There are two interesting features of this operating system that they were working on. One was, it was always going to be done in two years. [Laughter] We have known some really great operating system designers over the years, and I do not know of any decent operating system that has ever been done in two years, even by people who had ten times the IQ of the pink people. The other thing about it was, it was gonna be done in C++ for efficiency. [Smiles] [Laughter] Oh, let's not do it in Smalltalk, that's too slow! Let me tell you, there's nothing more inefficient than spending ten years on an operating system that never works. [Laughter and applause] Actually, the worst ones are the ones that appear to work. [Laughter and applause]

Let's take our pink plane, and we can also use this McLuhan quote—my favourite McLuhan quote—"I don't know who discovered water, but it wasn't a fish." He meant us as the fish, and he meant water as our belief structures—as our context. If you had to pick one cause, of both particular difficulty in our field, and also a general difficulty in the human race, it's taking single points of you and committing to them like they're religions. This happend with Smalltalk. There's a wonderful quote by Schopenhauer, a German philosopher of the nineteenth century, who said, "Every idea goes through three stages. First, it is denounced as the work of madmen."—This is what Swift called "A Confederacy of Dunces"—and then later, it's remarked as being totally obvious the whole time, and then the last stage is when the original denouncers claim to have invented it. [Laughter] That's when it gets in its religious stage. To me, the most distressing thing that happened to Smalltalk when it came out of Xerox PARC, was, for many respects and purposes it quit changing. I can tell you, at Xerox PARC there are four major versions—completely different versions of the language—over about a ten year period, and many dozens and dozens of significant releases within those different versions. I think one of the things we liked the most about Smalltalk was not what it could do, but the fact that it was such a good vehicle for bootstrapping the next set of ideas we had about how to do systems building. That, for all intents and purposes—when Smalltalk went commercial—ceased. Even though there is a book—the famous blue book that Adele and Dave wrote, that had the actual code in it for making Smalltalk interpreters and starting this process oneself—almost nobody took advantage of this. Almost no university took advantage of it. Almost no commercial [unintelligible] took advantage of it. What they missed was, to me, the deepest thing I would like to communicate with you today, and that is we don't know how to design systems yet. Let's not make what we don't know into a religion, for God's sake. What we need to do is to constantly think and think and think about what's important. We have to have our systems let us get to the next levels of abstraction as we come to them. The thing I am most proud of about Smalltalk, pretty much the only thing, from my standpoint, that I am proud of, is that it has been so good at getting rid of previous versions of itself, until it came out into this world.

One of the reasons we got involved in doing Smalltalk again, after, for me, it was sixteen years of not working on programming languages. A couple of years ago we started this project called Squeak, which is simply not an attempt to give the world a free Smalltalk, but an attempt to give the world a bootstrapping mechanism for something much better than Smalltalk, and when you fool around with Squeak, please, please, think of it from that standpoint. Think of how you can obsolete the damn thing by using its own mechanisms for getting the next version of itself. So look for the blue thoughts!

I was trying to think of how I could stop this talk—because I'll go on and on—and I remembered a story.—I'm a pipe organist, and most pipe organists have a hero whose name is E. Power Biggs. He kind of revived the interest in the pipe organ, especially as it was played in the seventeenth and eighteenth centuries, and had a tremendous influence on all of us organists. A good friend of mine was E. Power Biggs' assistant for many years back in the fourties and fifties. He's in his eighties now. When we get him for dinner, we always get him to tell us E. Power Biggs stories. The organ E. Power Biggs had in those days for his broadcasts, was a dinky little organ, neither fish nor foul, in a small museum at Harvard, called the Busch-Reisinger Museum. But in fact, all manner of music was played on it, and one day this assistant had to fill in for Biggs, and he asked Biggs, well what is the piece played, and he said, Well I had programmed Caesar Franck's heroic piece—and if you know this piece, it is made for the largest organs that have ever been made. The loudest organs that have ever been made, in the largest cathedrals that had ever been made, because it's a nineteenth century symphonic type organ work, and Biggs was asking my friend to play this on this dinky, little organ.—He said, But how can I play this, on this? Biggs, he said, Just play it grand. Just play it grand. To stay with the future as it moves, is to always play your systems more grand than they seem to be right now. Thank you.