### Dynamic Languages Wizards Series, Spring 2001

#### [Panel on Compilation, April 24, 2001](https://www.youtube.com/watch?v=wbEMFMioLto)

David Detlefs, Will Clinger, Martin Rinard, and Mat Hostetter  
Sun, Sun, MIT and Curl respectively.  

David Detlefs worked on C++ and Java  
Will Clinger worked on Scheme.  
Martin Rinard worked on Self, Jade and Java  
Mat Hostetter worked on Curl.  

dynamic languages it's uh I'm Greg
0:02Sullivan your moderator today and um
0:05this is actually part of a course that
0:07myself
0:09Jonathan Bachrach and Kostas are kudus
0:11are teaching a graduate seminar on
0:13dynamic languages and later when we get
0:15to questions will give preferences to
0:18students in that class but everybody
0:19will be invited also this is being
0:22webcast and recorded so and you can find
0:26out the recordings and also more
0:28information about our group and upcoming
0:30seminars and so forth
0:32at our website under the AI left AI lab
0:36webpage slash project slash dynamic
0:38languages let's see the first half for
0:43slightly more than half of this hour and
0:46a half panel will be sort of scripted
0:50questions and answers with the panelists
0:52take the questions are very broad you've
0:55seen them already on the announcement
0:57and we'll just do a round-robin style
1:00from panelists to panelists each will
1:03have like two or three minutes per
1:04question and then the last half hour or
1:07so will open it up to general questions
1:10all right first I'll give you some quick
1:12vials of the people here will clinger
1:16has been at Indiana University
1:18textronics like light chip software
1:21University of Oregon and now is at
1:22Northeastern University University and
1:25also spending a sabbatical year at Sun
1:28Microsystems and just finishing up in
1:31the java technology research group he's
1:33written compilers for mac scheme and
1:35larceny and approved cogeneration
1:38algorithm for mac scheme correct and
1:41lately he's been doing a research on
1:43garbage collection next down is Dave
1:46Detlef senior staff engineer at Java
1:48topics group at son labs he got his
1:51bachelors at MIT worked at TRW then a
1:55staff programmer here at MIT at the LCS
1:59and then got his PhD from Carnegie
2:01Mellon in 1990 then he's with jak
2:04systems Research Center doing garbage
2:07collection program ever
2:08has been at Sun since 1996 he's working
2:12on JVM implementations including garbage
2:15collection jets and synchronization next
2:19we have Matt Hostetter one of the
2:22original was a member of the original
2:23LCS curl project and now and then a
2:26co-founder of curl corporation and
2:28architect of the compiler team matt has
2:32a responsibility for various pieces of
2:34the curl runtime and before curl he Matt
2:39implemented dynamically compiling CPU
2:40omlette emulators emulating various
2:43machines including the Apple two and a
2:45Mac and last is Martyn Renard did his
2:50undergraduate at Brown and his PhD at
2:52Stanford in-between worked at two
2:54startups one doing electronic publishing
2:56the other doing computer aided drug
2:58design he wrote the first self to bugger
3:01when he was in Dave ungar's class and
3:05written a bunch of papers and has done
3:08mostly work on static analysis in
3:11particular pointer and escape analysis
3:13focusing on multi-threaded programs
3:16alright so again the questions are a bit
3:21general and and I've asked and we've
3:23asked the panelists to to produce some
3:26specifics and to try to tie the answers
3:28in with compilation of dynamic languages
3:31and we'll start with well and the
3:33question is what is your guiding
3:35philosophy
3:38my guiding philosophy is that nothing I
3:40say has anything to do with the opinions
3:42of my employers technically though my
3:45guiding philosophy is that humans are
3:47stupid to succeed in any cognitive task
3:50we have to rely on abstraction the
3:52purpose of abstraction is to simplify
3:54things so our limited brainpower will
3:57have some chance of success abstractions
4:00are judged by how well they simplified
4:02so I seek some simplicity through
4:06abstraction that's not to say that I
4:08like simple abstractions overly simple
4:12abstractions such as thread models of
4:14concurrency are often quite complex in
4:16use what I am saying is that I like
4:19abstractions that make thinking simpler
4:22that's enough metaphysical rant now I'm
4:25going to rant about compilers we used to
4:27think when we wrote a program that we
4:29were programming the hardware we also
4:32thought software was much easier to
4:34design and to change than Hardware
4:37compilers were developed to make
4:39software easier to write at that they
4:42succeeded but the compilers did
4:44something even more important they
4:46decoupled software from hardware this
4:50decoupling had several consequences one
4:53is that programming languages developed
4:54as a kind of abstraction of the hardware
4:57these programming language abstractions
5:00eventually became more important than
5:02the hardware itself this turned the
5:06software Hardware dichotomy upside down
5:08for several decades now it has been
5:11easier to change the hardware than the
5:13software I'm not saying it was easier to
5:15design but to change the hardware and
5:18the software on the hardware side this
5:20was tremendously liberating and led to
5:23spectacular progress on the software
5:25side it has been a bit stultifying
5:28because it led to too much
5:30standardization of substandard
5:31programming languages operating systems
5:33and application programs I wanted to end
5:36on a negative note David
5:43I think wills been working with me a lot
5:46recently that that's one reason why he
5:47believes in the stupidity of programmers
5:51so I agree a lot of what we'll said our
5:55purpose in in the universe as
5:58programming language implementers is to
6:00make it easier to write software by
6:04providing nice implementations of
6:06high-level languages so that people can
6:09get do the interesting things that
6:11software allows us to do more easily and
6:17obviously we want to take as many of the
6:20details of producing good software out
6:23of the programmers domain they shouldn't
6:25have to like register allocation you
6:27don't worry about putting reg
6:29declarations even if you are programming
6:31and see any more GC versus malloc and
6:34free is a mostly solved problem in
6:35lining you probably don't want to be
6:37specifying yourself you want that to be
6:40handle automatically because you make
6:41those decisions wrong and your program
6:44changes even if you make them right your
6:45program changes and they're wrong again
6:47so that has to be handled by the system
6:49and that's that's our job
6:51so that's all motherhood and no one will
6:53disagree with that so much in this
6:55context I'm going to say one more thing
6:56that will be slightly controversial
6:58perhaps in terms of language design
7:03while I'm all in favor of dynamic
7:06features in language implementation I'm
7:08not very much in favor of dynamic
7:12features in language design I think it's
7:17it's people often espouse such things
7:20for what I view as somewhat immature
7:22reasons you know related to the amount
7:23of typing they have to do you know and
7:26typing is a negligible fraction of
7:29getting a real program to work obviously
7:31so the more information you can put in
7:34your program and the more we've done
7:35than it is with other information and
7:36the more checking you can have done
7:38statically and automatically the better
7:41I think in getting programs to actually
7:44work consider civil engineering you know
7:47if you were to go over that that bridge
7:49there building downtown without having
7:51it
7:51then simulated within an inch of its
7:54life you wouldn't be very confident why
7:55do we allow the same thing to go on with
7:57software I hope we don't in the future
8:01so let me tell you a little bit about
8:03the philosophy behind the curl language
8:04there's probably more of you have heard
8:05of job and then curl we started as an
8:08MIT research project and our goal was to
8:10integrate code and content and also to
8:12have a gradual learning curve from a
8:15simple sort of markup style HTML level
8:17all the way up to a full object-oriented
8:19programming but all in one system in one
8:21language where you can continue to use
8:22what you knew before and it still works
8:25even at the higher levels so in order to
8:30satisfy both ends of the spectrum we
8:32made a few decisions in our language you
8:36don't have to put in types and curl if
8:38you don't want to if you're someone
8:39hasn't even heard of a type like my
8:40mother putting together a web page she
8:41doesn't have to if a program will run a
8:43little more slowly and gets less
8:44checking but I I agree entirely with
8:46what Dave said about the need to have
8:47strong checking so curl also has the
8:51possibility for full strong type
8:52checking and more and so that trying to
8:56satisfy those two different types of
8:58users has been a real challenge for us
9:00but it also I think is a strength
9:02another part of our philosophy is we
9:04decided early on that we wanted curl to
9:06be compiled directly from source code we
9:08think one of the reasons HTML has been
9:10successful is that you can just sit down
9:11to look an HTML page and see how its put
9:13together copy the parts you want to your
9:15own page and use it without having to go
9:18through any complicated compilation
9:19steps or use any other tools just click
9:21reload in your browser crawl has that
9:22same flavor because we want to have that
9:25same kind of success Microsoft claimed
9:30that one distinction between their il
9:31sort of their virtual machine and a Java
9:33Virtual Machine is their il was designed
9:35to be JIT compiled from the beginning
9:37and the java virtual machine was
9:38designed to be interpreted although of
9:40course that they've had a lot of success
9:41JIT compiling of since then curl was
9:43really just designed to be compiled from
9:45source code in the very beginning which
9:47has allowed us to have some kinds of
9:49higher-level language constructs you
9:51can't express in a in a more fixed byte
9:53code such as British kinds of looping
9:55constructs that avoid bounds checking in
9:57arrays we know at a higher level we can
9:59prove they're safe and don't have any
10:00security holes but be very hard if you
10:02broke it down all these little pieces to
10:03recover that information another part of
10:06our philosophy is that compile-time and
10:08run-time are blurring together you know
10:09back when I was a student we'd always
10:11talk about while you push everything the
10:12compile time that you can so that the
10:13less happens at runtime
10:15our system just bounces back and forth
10:17between it to all the time you can you
10:19can generate code on the fly and compile
10:21it you can have arbitrary macros that
10:23transform source code to source code
10:24while your program is running whatever
10:26you want I think the distinction in
10:28compile and run time has been artificial
10:31and
10:32it has had a cost one other piece of our
10:37philosophy is that our curl is written
10:38in itself we decided from the beginning
10:40that we want to you know eat our own dog
10:41food so to speak and that's actually had
10:43a big impact on our language design
10:44that's one of the reasons we have as
10:46many features to turn on compile time
10:48type checking in our languages because
10:50we had to use it ourselves for a long
10:51time and so we found all the the
10:54problems and annoyances and hopefully
10:55lining them out and the last piece of
10:58our philosophy is that we want to have
10:59an extensible syntax so that users would
11:02be able to add to a language themselves
11:04and we'll talk more about that later so
11:08let me preface my remarks by saying that
11:11you should geared mainly towards my
11:12research philosophy I was out in
11:15industry doing things I might have a
11:16different philosophy
11:18so the guiding philosophy behind my
11:19research is that you look at languages
11:21and you see that there is a general
11:25mechanism for doing pretty much anything
11:26you want to do need some memory fine
11:28allocated on your garbage collected heap
11:30you want to run your program great
11:32executed sequentially all this kind of
11:34stuff
11:35now one style of research is to say well
11:38let's take these general-purpose
11:39mechanisms and make them as efficient as
11:41we possibly can let's compile the
11:42sequential program down to really type
11:44machine code let's build these really
11:46fantastic garbage collectors that go off
11:48and you know scan the heap unbelievably
11:51fast okay this is not my style of
11:53research my guiding philosophy is that
11:55there's no program in the world that
11:57really needs all the generality of these
11:59mechanisms and in fact if you look at
12:01any program you'll find there's certain
12:03properties that program has and you can
12:05only find out those properties you can
12:06take out these inefficient
12:08general-purpose mechanisms it's really
12:09efficient tailored mechanisms and the
12:12guiding philosophy is there's always
12:14some way find those properties out
12:17okay so maybe you have to dynamically
12:19instrument the program and find out
12:21what's going on and get some idea of
12:22what they are maybe you need to go off
12:24and statically analyze the program for a
12:26couple of hours to figure out what's
12:27going on but the guiding philosophy here
12:29is that you wanna make the program run
12:31faster and do better things for the
12:32programmer by finding out the specific
12:35properties of the program you have at
12:36hand and exploiting those properties and
12:39the philosophy is it's always possible
12:40to do that
12:42right next around Houston oh wait wait
12:46wait I wanna say one more thing so so
12:48we'll talked about stupid programmers
12:50and I kind of agree with them if you're
12:52a couple of months before the deadline
12:53but my experience is that the closer to
12:55the deadline to get the smarter they get
12:56to the point where a couple of hours
12:58before the deadline they are
12:58unbelievably smart and and the bottom
13:04line is your language is better be able
13:05to get out of the way of those
13:06unbelievably smart programmers dinner
13:07it's not going to be accepted by people
13:09because it won't get because it won't
13:10satisfy their needs won't allow them to
13:11get the job done when it really matters
13:17it was derelict that date for the next
13:20one so keep in mind this is a part of
13:23relate to a seminar for graduate
13:25students so we're looking for these
13:27things that aren't solved also so and
13:29the question is what do you see is the
13:31interesting open problems and future
13:33directions particularly with respect to
13:35programming languages and so forth I'll
13:37mention two the first one is dynamic
13:41compilation with Java we have the
13:43widespread adoption of a of a system
13:46where for historical reasons mostly the
13:50model was you're going to download some
13:52set of class files essentially
13:54isomorphic representations of the source
13:57code and then execute them and the
14:01original model was going to be
14:02interpretation and that's not fast
14:04enough so people started making JIT
14:05compilers just in time aka dynamic
14:07compilers so the question the first
14:11check compilers weren't competitive say
14:14with compiling the corresponding C
14:18program now the analogous C program
14:20offline and gradually we've been
14:23sneaking up on that the the research
14:26question is can you in a dynamic
14:28compilation system get the code quality
14:32of offline compilation without excessive
14:35overhead you know compilation times
14:39similar to the offline compilation times
14:42invoked at runtime which is pretty much
14:44unacceptable
14:47that's an interesting question I think
14:49I'm hoping the answer is yes because of
14:52a combination of compiling most of the
14:56code quickly with a very fast medium
15:00code quality compiler and then
15:02concentrating a highly optimizing
15:04compiler on a few hot methods and
15:10there's some hope that that will yield a
15:12best of all worlds system and that
15:14that's still a very interesting research
15:15question the second thing related to
15:20that this is quite one sub-point B is
15:25can you do dynamic measurements of the
15:30system while it's running in some
15:32initial or continuously that will allow
15:35you to use this dynamic compilation
15:37infrastructure to recompile optimizing
15:41for the actual code paths taken other
15:44beat observed behaviors and achieve
15:47results much better than offline
15:51compilation without the dynamic
15:52information so that's a very interesting
15:55research question somewhat related to
15:58that the second top-level thing you go
16:01anywhere and there's this motherhood
16:03section a lot of people's talk saying oh
16:05well crosses are getting faster but and
16:09memories are getting bigger but the
16:11parts of memory you can actually get to
16:13the caches in reasonable time aren't
16:15getting any larger relatively speaking
16:17so obviously cache utilization is
16:20important with languages like Java and
16:23other languages where you're insulated
16:26as a programmer from being able to ask
16:29questions about the actual physical
16:30layout of objects in memory that that
16:35installation allows the system to
16:37transparently reorder fields and objects
16:40break objects and to move objects so to
16:43enhance their locality so I think a
16:45really interesting question over the
16:48next few years is will we be able to do
16:50dynamic measurements that allow us to do
16:54all those sorts of restructurings in
16:56order to enhance cache
16:59locality and thus cache speed sorry over
17:09yeah I view this concerns one specific
17:12issue that we're having to address
17:13because Curl has compiled from source
17:15code down to machine code on the fly we
17:18have a little more overhead than like
17:20the java virtual machine and similar
17:22systems so for us we're trying to find
17:24ways to reduce that overhead as far as
17:26we can what we've done so far is we've
17:29pushed lazy compilation to the point
17:32where we don't even look at things that
17:34we're not going to use for but we sell a
17:38little bit more work to do there for
17:39example you can imagine if the user
17:41defines a class it would be nice to do
17:43that parse nothing about that class
17:45except its name until someone needs a
17:46little more information maybe when
17:48someone needs to know a field you just
17:50process the minimal amount of
17:51information you need to find out where
17:53that field is and the object that don't
17:54do anything else and actually go to
17:56create the object and maybe you compile
17:57a little bit more a little bit more and
17:59so on that model is very different than
18:01a traditional compiler model we just
18:03have several separate passes you make
18:05the program and then you're done and
18:06this is a lot more sort of lazy
18:09dependency graph learning of their
18:11approach so that that's a big challenge
18:13for us
18:16another interesting example if you look
18:19at like parameterize types they're
18:22pretty good like C++ templates the fact
18:24that let you write code you can
18:25specialize different purposes I mean the
18:26syntax to me out would be you want but
18:28the the idea is good there's not quite
18:30general enough we just a diet curl the
18:33other day we wanted to have a
18:34parameterised type and you wanted one
18:35method to be completely different if the
18:36target was something else well we don't
18:38have a way to express that now but it
18:40seems like there'd be a natural
18:41extension of letting programmers do what
18:43it is they want to do give me a little
18:44more flexibility how to design their
18:46class um that sort of a language design
18:48challenge for us and one other thing I'm
18:51interested to see how it plays out is
18:53with with this trade-off between
18:55compilation time and runtime one of the
18:58sort of obvious trade-offs you can make
19:00is to say well you know we'll compile
19:01things offline when you go to bed at
19:03night will sit there and optimize the
19:04code that you downloaded that day so
19:05tomorrow is faster I'm not sure if
19:08that's going to win out or people are
19:09just going to make their compilers
19:10faster and faster over time said
19:12sort of complexity isn't necessary
19:13that's something else we're going to
19:15explore
19:19okay all right so here's what I think
19:24programming is a human activity and for
19:27the purposes of this discussion there's
19:28two kinds of people there's people who
19:30like to experience life you want to
19:31press the button and see what happens
19:33good bad and different you know they
19:35just wanted to what happens there are
19:37people who want to plan they want to
19:38think about the future predict what's
19:39going to happen set things up so it all
19:41works out and then you know hit the
19:43Domino one into watch all the dominoes
19:45fall down all over the table and the
19:47precise order that they have planned out
19:50now the great thing about dynamic
19:52programming environments is that they
19:54let you change things dynamically did
19:56you put value so you know I don't like
19:57the way things are going right now I
19:58want to reload some different part of
20:01the system with a changed implementation
20:02but the problem is the current
20:05environments that you can get like this
20:07they don't support either kind of it
20:09either the two kinds of people very well
20:11here's what happens if you're an
20:13experience where you say you know I
20:15think it would be a cool thing to do - I
20:17don't know replace the implementation of
20:19vectors internally with linked lists
20:22let's see what happens
20:23okay so you go away in half for 10
20:25minutes and push you know push the
20:27button and boom there it is
20:28you know all of a sudden all of your
20:30vectors are linked lists now but you
20:33don't get the full experience because
20:35the system isn't designed to let you see
20:36what's happening what happens is you
20:38know maybe some part of it runs really
20:40slowly maybe some part of it you know it
20:42takes a lot of garbage collection time
20:44or it didn't before but you really can't
20:45figure out what's going on in the system
20:46so let's say you're a planner you get
20:50the idea you know you say it might be a
20:51good idea to replace all my
20:52implementations of vectors with one plus
20:54its internal but now you want to know
20:57what's going to happen if I do this well
21:00you'd like the system you'd like to be
21:03able to peer into the system
21:03transparently see all the places that
21:05you use vectors understand the context
21:07in which they're used understand the
21:09performance the implicit performance
21:11expectations that clients have of them
21:13understand how they're anything are
21:15interacting with the garbage collector
21:16understand what happens to vectors as
21:18you run the program again there's little
21:21support to this you've got to do a lot
21:22of typing in your debugger to find out
21:24this kind of information
21:25so what we really need is a system where
21:28you've got the internal structure of the
21:31system and what's going on in it
21:34designed to be exposed visually at a
21:37very high bandwidth to the person using
21:39the system it would be really helpful to
21:41both kinds of people because then when
21:44the experiences go in and hack the
21:45system they get a much better experience
21:47because there's a whole lot more stuff
21:49going on that they can see and
21:52understand the planners are going to
21:53have a much better time because they
21:54have a much richer planning experience
21:55you can sit down there and think about
21:57all the wonderful things that will
21:58happen if they do this happen okay so I
22:01think a more open system where you could
22:03see what's going on in the object I
22:05think the early small talk systems did
22:07this very well or at least much better
22:08than current systems do because there
22:10you can you know say I want you know I
22:12can see what's this object look like
22:14boom it flashed the object up under you
22:16you can click on the links and you get
22:18this big chain of objects on your screen
22:21and it was much more open than a lot of
22:23systems are I think there's a couple of
22:24reasons why systems have tended not to
22:26be as open as they might otherwise be
22:28one is that you've got heavy-duty
22:29compilers out there morphing the code
22:31beyond recognition so it'll execute
22:33efficiently which is a great goal but it
22:35makes it difficult to reverse all those
22:37snips of compilation and expose the
22:40abstraction back to the guy who's using
22:41the system and the second reason is that
22:45people have taken abstraction too
22:48seriously
22:48they've taken action they take an
22:49abstraction believe that it's always
22:51right to hide what's going on behind
22:53this little curve but I don't think
22:55that's true if you're looking at the
22:56behavior of a system and trying to
22:57figure out what's going on there you
22:59want to be able to see everything
23:02okay so that's that's one future
23:04direction how do you make these systems
23:05open while preserving all the good
23:07things they do for us
23:07the second future direction I think is
23:11that people are going to replace pipe
23:13systems you know one you're going to
23:14have typed languages anymore what you're
23:16going to have you're going to have a
23:17dynamically typed language a dynamically
23:19safe language with a bunch of stuff on
23:21the side that tells you what's going on
23:23so now instead of having just a single
23:26type language and use to express your
23:28expectations of what the program is
23:29doing you have you can have
23:30general-purpose assertions
23:32general-purpose properties and you have
23:34very powerful mechanisms to come in very
23:35powerful analyzers to go in and verify
23:37that your crew that your assertions are
23:39correct so I think you'll see much more
23:41powerful languages replacing type
23:42systems and type systems moving and
23:45they're there they're more powerful
23:47successors moving away from the core
23:49language into metal languages and things
23:52that are separated from the program but
23:53conceptually untouchable
23:58okay well what I think the world of
24:00dynamic languages needs more than
24:02anything else is a runtime system that
24:05supports dynamic language as well and
24:07runs on all major hardware platforms
24:09this is technically feasible but we
24:12don't have it and I'm really not
24:14optimistic we're going to get in anytime
24:16soon the last the previous panel
24:19discussion was about run time did anyone
24:22here notice that no one even mentioned
24:24the Java Virtual Machine or
24:26microsoft.net common language runtime at
24:30a discussion on runtime the Java Virtual
24:33Machine was designed to run Java and it
24:36doesn't support other dynamic languages
24:38at all well microsoft.net runtime might
24:41be slightly better in that respect after
24:43all it has to support C++ C sharp Visual
24:46Basic some other things
24:48Haskell who knows okay well so maybe
24:53it's better but I doubt where the
24:56Microsoft is going to push all that hard
24:57to make the not dotnet common language
25:00runtime universally available on non
25:03Microsoft platforms so right now C - -
25:06for a compiler writer c- - might be the
25:09best portable target for dynamic
25:10languages in general and it isn't a full
25:13runtime system it's basically a portable
25:15optimizing assembler whose most
25:17attractive feature is that it isn't
25:19actively hostile the things like proper
25:22tail recursion and garbage collection so
25:25why do I think a portable runtime is so
25:27important it's because the world of
25:30dynamic languages is still a small one
25:32we can't afford to squander all of our
25:35energy building separate backends and
25:38runtime systems for every language and
25:40for every platform
25:43we also need to reduce the volume of
25:45trusted code and a portable runtime
25:48helps with that doesn't solve the
25:50problem but it helps here I think we
25:53need to distinguish safety properties
25:54from correctness has been a lot of work
25:57in recent years on verifying some safety
25:59properties at runtime or load time for
26:01example the bytecode verifier in java or
26:05typed assembly language things like that
26:07but if you if you're concerned about
26:09correctness not just safety properties
26:11you really have to do something about
26:13the entire path you need a trusted path
26:15all the way from source code to machine
26:17code and to minimize the volume of
26:19trusted code with respect to correctness
26:21that's I think a major research area
26:27all right a third question is asking the
26:31assembled wizards what little known
26:33secrets would you like to share with the
26:34audience this would be how do you get
26:37the computers of the languages to to
26:40perform their magic what's behind the
26:41scenes let's start with Matt okay one
26:46thing that wasn't obvious to me when I
26:47started looking compilers was that just
26:49how effective even lame optimizations
26:51can be you can take a compiler for a
26:54language and just do the simplest thing
26:56maybe a little constant folding and a
26:58very trivial register allocator you do
27:00the job right you'll be two-thirds as
27:01fast as a good C compiler and for a lot
27:03of jobs that's good enough and there's
27:04no need to go off and do a lot of fancy
27:06optimizations another thing I found
27:11surprising was that these days gifs can
27:14often generate better code than the
27:16static compilers because they just have
27:17a lot of access to dynamic information
27:19the static compilers didn't they know
27:21how to reorder things as David inch they
27:24can reorder fields even even potentially
27:26dynamically inline things to get called
27:28a lot these are all things you can't do
27:31offline some people have done these
27:33profile directed feedback systems for
27:35static compilers where you run the
27:36program collect some information and
27:38then we compile the program using that
27:40that still doesn't help you if the
27:42behavior program depends a lot on the
27:43data where the JIT system can always
27:45adapt to whatever is actually happening
27:47right now with the program so I think
27:48that's really interesting
27:51another thing that you shouldn't be
27:52afraid to do if you're writing a
27:53compiler is just write a translator from
27:55your language to see when they're
27:56getting started our system still uses
28:00that to bootstrap ourselves and it's
28:01useful if you want to courts or new
28:02platform there's no need to just get
28:05started right away with a full JIT now
28:09if your language is really dynamic that
28:10may restrict what features your compiler
28:12can use but usually you can use enough
28:13of a subset that a C translator will
28:16work another thing that you should pay
28:20attention to is use domain specific
28:23languages where you can when running a
28:24compiler next and yak have been very
28:27popular not just because someone else
28:28wrote them and they work but because
28:30they let you write Express really
28:32complex ideas concisely in the race
28:35projects I've done it that the first
28:36thing I've done is I've sat down just
28:38written up a file describing the
28:40say to architecture I'm working with the
28:4268 km later I wrote I wrote a big
28:44description of the architecture and use
28:46that to machine generate a sort of
28:47interpreter for the processor later on I
28:49got more aggressive and modified my
28:51translator to actually produce a
28:52compiler that created x86 code and that
28:54was possible because there was the
28:56domain specific language encoding the
28:57semantics in one place definitely a big
29:00one to do that so I really don't have
29:05any little known secrets by having AI
29:07publish them they cannot a well-known
29:08pearls of wisdom or whatever they were
29:10so I guess it's as close as it comes
29:13it's just my general philosophy of you
29:16know you should it's always possible to
29:18figure out what you want to know about
29:19of a program if you know it's true sort
29:21of intuitively the high level at the
29:23programmer level and you can automate
29:24that process more often than you think
29:26so thank you lately well I came up with
29:30four little known secrets maybe some of
29:33them are wider known than others the
29:35first one is the usefulness of the
29:37PowerPC srw I in an instruction rotate
29:41leftward immediate then and with masks
29:46kidding I'm not kidding but I'm not
29:49gonna say anything more about that the
29:51second one is the synergy between proper
29:54tail recursion optimization of leaf
29:56procedures and frame optimization in
29:59properly tail recursive compilers the
30:02number of leaf procedures whether you
30:03reckon statically or dynamically goes
30:05way up and the number of stack frames
30:08that that you allocate can go way down
30:10the functional world knows this but the
30:13object-oriented world hasn't really
30:14caught on yet number three the synergy
30:18between program transformations and flow
30:20analysis flow analysis becomes more
30:23useful when combined with program
30:24transformations that rewrite the program
30:27into a more easily analyzed form and so
30:30they contribute to each other in a very
30:31interesting way things like inlining
30:33lambda lifting splitting of of
30:37polymorphic procedures into monomorphic
30:39procedures things like that it's
30:42so there's a real synergy there and it's
30:44amazing how much that buys you when you
30:46start to look at it and number four why
30:49generational garbage collection is a win
30:52not that it is a win but quiet it is a
30:54win
30:54you often hear that most objects die
30:57young that's true but irrelevant when
31:01general garbage collection is a win it's
31:04because there are lots of objects that
31:06die young and lots of objects that don't
31:09you can waste a lot of time by looking
31:12at those long-lived objects on every
31:14collection the tenure process is a very
31:19inexpensive way to isolate and then to
31:22ignore long-lived objects want to echo
31:28some previous comments well one thing I
31:32that surprised me when I started working
31:34on Java what we our group was trying to
31:38do research in Java garbage collection
31:41so we had an existing product that we
31:44were trying to do this research in and
31:47we discovered that garbage collection
31:50wasn't a problem because it had an
31:51interpreter only at that time and the
31:54denominator was so large it didn't
31:55matter what we did about garbage it was
31:57a negligible fraction so we started
31:59working on increasing the denominator so
32:04that making GC a problem so we could
32:05work on it so we inherited a JIT
32:09compiler from the product group that was
32:11what we'll call a template based JIT
32:12compiler you know you have your your
32:14byte code program and the compiler
32:17consists of a big loop for each byte
32:20code instruction through a big switch
32:22statement for the byte code and amidst
32:24some code for that instruction so we
32:29hacked on this for a couple years and
32:32much as matt said it's amazing how close
32:37you can get to high-quality code on a
32:40very low cycles per byte code budget you
32:43know this tournament there's no
32:45intermediate language here there's a you
32:47know two passes and then one pass
32:49through a little bit of analysis another
32:51pass to generate code it you can do
32:54kind of online versions of your favorite
32:57optimizations and be surprisingly
33:00effective I mean we did where's the list
33:04kind of round-robin probabilistic
33:07register and allocation and that worked
33:09out pretty well at least on a register
33:11rich architecture like the spark where
33:13almost anything will work out in
33:15fairness common sub-expression
33:17elimination constant propagation even
33:20when as far I did like of six months of
33:23work where I analyzed innermost loops to
33:26do array bounced check elimination even
33:29including hoisting a predicate that you
33:32could test outside the loop and if it's
33:33true you can eliminate the bounce check
33:35within a loop otherwise you execute a
33:37none optimized version of the array all
33:40of this is was accomplished in a
33:42compiler events so we had that compiler
33:46we had another compiler which was an
33:48adaptation of a traditional compiler to
33:50be a JIT and the factor in compilation
33:53speed was something on the order of
33:55between ten and a hundreds
33:57figure 30 so we can get within two
33:59thirds of the formants at a thirtieth of
34:01the cost so that's really surprising it
34:04means that it's if you'd never
34:07worthwhile to interpret more than a
34:09negligible fraction of the time because
34:12it's it's so cheap to do it if you can
34:15have a compiler like this you can have
34:17almost all the code you actually execute
34:19be at least compile to that level though
34:24it is still occasionally useful to
34:26optimize to interpret at least a couple
34:29executions of a method in the Java case
34:33because then you can do all the cont the
34:37symbol resolution that you have to do
34:41that you know the language says you have
34:43to wait and do it when you first
34:45encounter it so you get more a little
34:47bit of information to guide that first
34:49compilation and then if you want you can
34:52do that first compilation to gather more
34:53information to guide a later optimizing
34:55compilation if that turns out to be a
34:57hot method so that was surprising to me
34:59and I think it's not often appreciated
35:04thank you okay the next question is keep
35:10in mind that the context here is both a
35:12graduate course and also the AI lab
35:14where there's a sort of long history of
35:16dynamic languages that never quite
35:18caught on and so in the question of okay
35:21the question is what good ideas have
35:23been dropped about whose time has come
35:25and I'll start with mine okay so the
35:28first set of good ideas whose time has
35:32come is driven by the fact computers are
35:36moving out into the physical world and
35:38interacting the physical world more and
35:39more and more and more which means that
35:42the effects they have on the content on
35:46the objects that compute with and effect
35:48are more and more difficult to reverse
35:51which means you care more and more about
35:53the correctness of your program and what
35:55it does so there's a couple of ways to
35:57attack this problem one way is to say
35:59well I really care about this I have in
36:03fact I'm going to engineer my system I
36:04can state my requirements pretty
36:06carefully I can translate those
36:08requirements down into properties that
36:10my program have to satisfy I'm going to
36:12prove my program has these properties ok
36:14so I think there's room here for what
36:16most people think of as a bad idea
36:18namely full program verification it'll
36:20be real interesting to see how close we
36:22come to that over the next 10 20 years
36:24because you'll notice that there's been
36:26a lot of emphasis recently on formal
36:28methods and people are starting to prove
36:29more and more and more sophisticated
36:31properties of programs but people I
36:35still think you full program
36:36verification being as comfortably out of
36:39range and I think that may change for
36:42some small classic programs that
36:44interact intimately with the physical
36:46world
36:47another question is not another way of
36:49getting there is to say well ok I don't
36:51necessarily want to verify your program
36:53but my program is simple enough so that
36:55I can just basically simulate everything
36:58you could possibly do I need a model
36:59checker so I can write down a couple of
37:02properties and sit there and let the
37:03computer run and run and run and run and
37:05run and explore the state space it's
37:06something suitable level of abstraction
37:08and see what'll happen it's been very
37:09successful in the hardware end of things
37:12I think there's a chance that it'll be
37:14very successful with software
37:16so but let's say that neither of these
37:18two technologies works out well there's
37:20a third technology that is and you have
37:23to read and you have to believe the
37:25reason these first two technologies
37:26aren't going to work out because people
37:27are going to find it very difficult to
37:29express what they want their program to
37:31do so this means that these two
37:33technologies don't work out and you need
37:35a reliable piece of software you have to
37:40rely on something else to tell you what
37:41the top can tell you the properties that
37:43the program should have okay so well
37:46that's an artificial intelligent program
37:47right so you have to have an automatic
37:50programming system that will go in and
37:52make all the assumptions about the world
37:53and have a little knowledge about the
37:54world that you can't get people to tell
37:56you well we'll see if that works out
37:58that'll be an interesting interesting
38:00scenario and finally if you don't
38:03believe in any of these the alternative
38:05is just to sit down and let people do it
38:06themselves live been doing it for all
38:08these years and I think whether that's
38:11acceptable to people or not is going to
38:14be less of a technical question than a
38:16social and legal question I think if you
38:19can show that there's an alternative
38:21that you can deploy that would prevent
38:23accidents it's going to be very
38:25difficult for people to defend in court
38:27software that wasn't developed using
38:29those methodologies or tools I think
38:32that's going to be a that it's possible
38:36if that's the one thing that will drive
38:38people towards developing these kind of
38:40software and more reliable ways okay so
38:42that's one so here's another idea whose
38:45time sort of has already done but I just
38:47like to be emphasize it higher level
38:49programming languages things like Perl
38:50you know kernel is a great language if
38:52what you want to do is is a pack a bunch
38:55of text green text strings in a file
38:57back in the 70s there is this language
38:58called set L where you you know we
39:02didn't program with integers and arrays
39:05and things like that you program with
39:06sets and Relations which was very nice I
39:08think the the standard relationship that
39:11you have between objects right now is a
39:12reference from one object to the other I
39:14think the wrote the reason you have that
39:15relationship is because it's very easy
39:17to implement
39:18relationship using a single word pointer
39:20on a machine and I think the time is
39:21right to start looking for more for
39:24richer relationships between objects
39:26built into languages and not worry as
39:29much about the implementation cost it
39:31did having those features might might
39:33might might might contain I guess some
39:38ideas whose time has come and gone to
39:40stay gone
39:41dynamic inheritance you guys so you guys
39:45remember dynamic inheritance so dynamic
39:47inheritance is a concept that you know
39:48hey I'm a Class A right now but maybe
39:51later on the same object needs to be a
39:53clarity and you know you look at the
39:56code and you can do some unbelievably
39:58cool things with this right you know you
40:00you know your your your your object at
40:02the front of the list is behaves
40:03differently from all the objects in the
40:05middle of the list behave differently
40:06from objects at the end of the list and
40:07you type three lines of code you're
40:09doing some really cool complicated thing
40:10and but it turns out that you just can't
40:13deal with the complexity of this when
40:14you build big systems or even
40:15medium-size systems or even quite
40:17frankly small systems so that's a cool
40:20idea whose time I think has come and
40:22gone and it's going to be gone for a
40:24while and I'd even generalized this to
40:28multiple inheritance and perhaps even
40:29arguably single inheritance like this
40:32here which is because you can view
40:33single inheritance something that you
40:35ought to do not at compile time not at
40:38runtime but at you know when you're
40:40typing in the editor this is an idea
40:42that kind of comes in comes and goes and
40:44will be interesting to see whether
40:46people like that where you're
40:48programming or not
40:50but anyway I guess I've said enough so
40:52yes you're up well okay a good idea
40:56that's been dropped but whose time has
40:58now come on call a universal compiler
41:01oriented language that's that's the
41:04portable runtime system I was talking
41:06beyond that I found it easier to list
41:09bad ideas like Martin that that haven't
41:12been dropped but whose time is
41:13nonetheless past finalize errs for
41:18instance a friend on Sunday night a
41:20friend was telling me the C++ was much
41:22better than Java for his application
41:24because he couldn't predict when a Java
41:26finalizar would run I asked him I asked
41:29him why don't you just call a pseudo
41:31destructor method explicitly whenever
41:33the relevant object goes out of scope he
41:36said it's Harry in the presence of
41:37exceptions and some programmers bound to
41:40get it wrong or forget to do it at all
41:42okay why not make it impossible to
41:45create these objects except by using a
41:47macro that generates the finalization
41:48code automatically he said Java doesn't
41:51have macros he had a point
41:54I think programming language designers
41:57have been avoiding macros because they
41:59hate C macros well C macros ought to be
42:02hated but designers have drawn the wrong
42:05conclusion from their badness as bad as
42:08they are
42:08programmers use them why because they
42:12serve a purpose language designers
42:14should not be so arrogant as to think
42:16that their language is so much better
42:18than C that no project will ever need a
42:21syntactic abstraction that the designer
42:23failed to anticipate hygienic macros are
42:27a major win so that's the good idea
42:29another bad idea explicit the allocation
42:32the good idea garbage collection is no
42:34longer controversial so I won't say
42:36anything more about it another bad idea
42:38threads by which I mean the abstraction
42:40that views computation as a small army
42:43of creatures hammering away on a
42:45monolithic shared memory to keep them
42:47from hammering each other's thumbs
42:50you know you mentally carve that
42:53monolithic memory into shared pieces
42:55that require synchronization and
42:57unshared pieces that don't why not use
43:01that mental carving as the fundamental
43:03abstraction why not make that
43:05abstraction explicit in the source
43:07program so the compiler and runtime
43:09system can enforce it you'd get better
43:12compiler optimization that way too
43:14another bad idea over reliance on side
43:17effects for example the use of
43:18assignments to initialize objects you
43:21shouldn't have to have a clever compiler
43:23to distinguish initialization of
43:25immutable instance variables from side
43:27effects to mutable variables Const
43:29should be the default and mutable should
43:32be the keyword that you have to use when
43:34you want to have side effects another
43:36bad idea there are lots of them signed
43:39and signed arithmetic modulo some power
43:42of two programmers just can't be relied
43:45upon to remember that half the laws of
43:47arithmetic don't hold a good idea whose
43:53time is nonetheless past I think whole
43:55program optimization as has been
43:57discussed already we're moving toward
43:59load time and dynamic optimization and I
44:01think that's the way we'll be going in
44:02the future ok
44:05okay I got two possibilities that I have
44:11a hard time with this question but
44:12there's partial evaluation has a long
44:15heritage in object-oriented languages
44:18sometimes it's come up in the guise of
44:20specialization where you have a method
44:23and you I think that technical term
44:26really means have a method where you get
44:31to assume that you know the actual
44:33dynamic type of this but so there's a
44:36lot of situations in which you might
44:38wish to augment call sites to note
44:44commonalities or common things in the
44:48calls to a method and then optimize a
44:50version of the method so that it
44:52performs better for those common call
44:54patterns for example we talked about
44:58knowing the dynamic type of the receiver
45:00or perhaps the arguments this would have
45:03been optimizing further method dispatch
45:06within the called method or instance of
45:10or castes for example imagine a
45:14situation where a method takes two array
45:16arguments and then it's going to loop
45:19over them both simultaneously you might
45:22wish to note that it's almost always the
45:25case that those two arrays are of equal
45:27length in order to perhaps get rid of
45:31the bounds checks so there's a lot of
45:33interesting things like that that could
45:35be done the challenge there is
45:37identifying the common patterns the ones
45:40that could be properly optimized for
45:42without introducing excessive overhead
45:45another idea not in compilation that who
45:49has been kind of discarded who which
45:51might be coming around again is
45:52reference counting garbage collection
45:56with Java and the use of of dinette if
46:01Java is a dynamic language here we have
46:03the first use of garbage collected
46:06language anyway for large business
46:10oriented applications we talked to
46:12customers all the time who say well
46:14we're going to run a run our program
46:15with like say 10 gigabytes of live data
46:18is
46:18okay and you know how what can they do
46:22with ten gigabytes of live data well and
46:24we asked them and it turns out that nine
46:26point seven gigabytes of those is in
46:29memory caches of some big database that
46:32that's changing on timescales of weeks
46:35or months so so we have a big heap but
46:39it's it's very nearly static so the
46:44garbage collection algorithms we've
46:46we've worked on we're working on aren't
46:49optimized for that case a very large
46:50mostly static heat so reference County
46:55had they always still have have to trace
46:57the whole heap once in a while and you
46:59know as ten gigabytes becomes a hundred
47:01that's that becomes a little bit dicey
47:04the reference County has the nice
47:06feature that you only concerned with
47:09usually anyway the objects that that are
47:13actually access to his reference pattern
47:15changes so yeah it's a little bit
47:17heretical but maybe that sort of idea is
47:20coming back and there's been a few
47:21papers on stuff like that and PL di an
47:24oops law recently
47:27so I suppose I agree strongly with wolf
47:30claims about that powerful macros are
47:33really the way to go in the future I
47:36mentioned earlier that I think
47:38compile-time and run-time are blurring
47:39together I think the next thing that we
47:41should see is that the language and the
47:42library should begin to blow up together
47:44a little bit too
47:45we've set up a macro system which
47:47unfortunately we're not proud of and
47:49that enough yet to make public which
47:53allows you to do arbitrary
47:55transformations of source code objects
47:56the source code objects at runtime not
47:58just a template-based name and actually
48:00examine the source code do any analysis
48:01you want call whatever procedures you
48:03want we've used that in for example our
48:06graphics system to add some forms which
48:08are tailored to the needs of graphics
48:09programmers for example we have a four
48:11pixel form but lets you iterate through
48:13all the pixels in a pics map and doing
48:15some operation to each pixel this code
48:18that scenario is extremely efficient and
48:20get rid of all the array bounds checking
48:21x' but but also we don't guarantee what
48:24order it happens in when we also allow
48:26it to happen in parallel if you have two
48:27CPUs process in the image the compiler
48:29is free to launch half on each CPU that
48:32kind of extension for these
48:33domain-specific things is really was to
48:35make languages a lot more powerful in
48:37the future I think another good idea
48:39whose time has come
48:40and is integrating documentation with
48:43your code Java doc does this and we've
48:45adopted something similar for our code
48:47it's clearly the right thing to keep the
48:49code and the information about it
48:50together if you look at a current system
48:53like a C program you'll see there's
48:54comments in the headers comments in the
48:56C code some of the documentation
48:58separately and all three of those things
48:59have to be tracked in sync and that's
49:00just silly
49:02the next good idea I think this time has
49:04come is is using good compiler IRS even
49:07in gifs people's intuition used to be
49:09that if you can sit down and make a gyp
49:10you just don't have enough time to do
49:12all the really classic full
49:13optimizations and you have to keep
49:14things simple and small sort of complete
49:16in time they used to be true but with
49:18computers doubling in speed every 18
49:20months or so the fraction of time that
49:22you spend actually doing the compilation
49:24is getting small and small enough that
49:26you can afford to use these nice IRS and
49:29I suggest you do that from the beginning
49:31my personal opinion on this is that SSA
49:34is the way to go
49:35my understand that's what suns using in
49:37there
49:37hot spot Jade with a lot of success and
49:41and one other good ideas time has come
49:43and I mentioned earlier is aggressive
49:44compilation directly from the source
49:45code there's just a lot of advantages to
49:47doing that way and you keep a lot of
49:49flexibility for yourself in future react
49:53a little bit threats I think what will
49:57stoves about breads is absolutely true
49:59now it's almost unbelievably hard to
50:02keep your head on straight
50:03if you don't have a way of knowing that
50:06the data that you're accessing without
50:09synchronization is not accessible to
50:12other threats however I think people are
50:14developing type systems and that kind of
50:17automated reasoning systems that lets
50:18you take this kind of that's you
50:20explicitly separate this kind of data
50:21and when I think and I think when that
50:23happens it's going to become much easier
50:25to program using threads and people are
50:27going to start resonating more with the
50:28power that threads gives you second
50:31whole program analysis I think it's
50:32absolutely true it's very difficult to
50:35do a whole program analysis or
50:36optimization across a large program but
50:38notice that every time you compile a
50:40program with it has a statically typed
50:42that is a static type system you're
50:44doing some form of whole program
50:46analysis it's just that you're
50:47leveraging assertions that procedure
50:49boundaries that let you do that I think
50:51that kind of full program analysis will
50:53become more common and one less thing a
50:57bad idea whose time has come okay so it
51:00used to be back in the early days of
51:02programming languages you'd go into your
51:03programming languages class addictive
51:05and they teach you about the go-to
51:06statement they'd say you know here's how
51:09you write the go-to statement you say if
51:11condition go to label foo okay and you
51:14understood this and then it became and
51:16then people used to late at night think
51:18of cool variations of this one of the
51:20cool variations of this was the
51:21conditional come from statement is what
51:24you do is you'd go down the end of your
51:25program and you'd write this some
51:28condition then come from you know label
51:3040 right here and what that meant was
51:32whenever control routes labeled 40 you'd
51:34evaluate the condition and if it
51:36evaluated to true you'd immediately jump
51:38to the code down at the bottom of the
51:39program and everybody said oh this is
51:41ridiculous it's totally
51:43unusable but it turns out that there's
51:47this thing called aspect oriented
51:48programming and what aspect oriented
51:50programming is you should go out and
51:52read the papers it's a structured
51:54disciplined way of using the conditional
51:57come from operation and that's a bad
52:01idea whose time has come okay
52:07the final question it overlaps
52:10especially with the final panel that on
52:12May 10th which is about about language
52:14design and also reiterate some of the
52:17earlier questions and we'll start with
52:19well it's what are some pitfalls gotchas
52:22for a language design and implementation
52:26well one classic pitfall is to assume
52:28that a sufficiently clever compiler can
52:31compensate for poor design of a
52:32programming language or target
52:34architecture I think I just heard a
52:36variation of it by assuming that a
52:38sufficiently clever verification system
52:40would compensate for a problem in a
52:43programming language another classic
52:47pitfall though is to assume that
52:48compilers are stupid some target
52:51architectures do things at runtime that
52:53ought to have been done at compile time
52:54or link time some programming languages
52:57are intended to give programmers the
52:59power to write more efficient code but
53:01in reality require a very clever
53:03compiler to clean up after all the
53:05incorrect guesses that programmers make
53:07about what's efficient and what isn't
53:11let's see more pitfall slow Club slow
53:13code doesn't fly slow compilers aren't
53:16appreciated just-in-time compilers can't
53:19do heavy-duty optimization so
53:22translating source code into reasonably
53:25efficient machine code has to be
53:26straightforward if it isn't there's
53:29something wrong either with the design
53:31of the language or with the design of
53:32the target architecture if you're
53:35implementing a runtime system for
53:37dynamic language X and language why is
53:40the language de jour of Industry don't
53:43assume that it is enough to support
53:45languages x and y in reality the dynamic
53:49language X won't matter at all in which
53:51case why bother or else it will succeed
53:53in which case software developers will
53:56want to use it in combination with all
53:58manner of other languages including
53:59other dynamic languages
54:04pitfall site so working on Java
54:08I've Java I'm a researcher by
54:12temperament I and my previous experience
54:15in Java I'm in a research group but one
54:18that works very closely with product
54:20groups and the scale of the Java
54:22phenomenon is unprecedented in my
54:27experience well that's not a huge
54:29experience but when something is if
54:33widespread is Java
54:34you can't optimize for the common case
54:36you can't over optimize for the common
54:38case because it's so widespread that
54:39that the uncommon cases are important
54:42too and you want to especially avoid
54:44optimizations that while they benefit
54:46the common case they penalize the
54:48uncommon case for example a not sure
54:52that's a great example but there's Java
54:55has the Java language has the somewhat
54:58unusual design decision that each object
55:02is potentially lockable that that the
55:05lock operation is of method on object
55:08the root of the class hierarchy so it's
55:12not it's assumed that most objects
55:14aren't locked and but when they are you
55:17have to support it so that's an
55:18interesting implementation thing when
55:23there's a lot of implementations of Java
55:25locking most of them are of the form
55:28make assumptions that most objects are
55:31never locked a those that are are seldom
55:35contended for that you know it's seldom
55:38that of this objects are almost always
55:41unlocked when you attempt to lock them
55:43so most of them when contention happens
55:46do some sort of what they call lock
55:48expansion they allocate this other data
55:49structure that corresponds to the
55:51operating system mutex and associated
55:54with the regular object in the first
55:58place so for most programs this is true
56:01if you have an occasional program
56:03however for which many objects are
56:05occasionally contended this is going to
56:07be an inefficient strategy so you know
56:11there's alternate strategies that don't
56:12have that drawback so that's one example
56:13you
56:15don't want to over optimize for the
56:17common case my other pet peeve is moving
56:25runtime in finality into the source
56:27language it's often you know there's
56:32sometimes the phrase a Barban below the
56:33line like here's the virtual machine
56:35interface and the source language is
56:37above it and the virtual machine
56:38implementation is below it and it's
56:40often stated that it it's it's just a
56:43intrinsically good thing to move pieces
56:46of the virtual what are ostensibly
56:48pieces of the virtual machine
56:49implementation out into the source
56:51language for example in Java
56:56there's java.lang reference weak
56:58reference and finalization proper
57:00processing is now largely done in the
57:04source language and I was just talking
57:07with a product engineer recently like 20
57:10minutes before I left here about some
57:12difficulties this is caused because
57:14there's a lock at the source level that
57:17that interacts with internal locks
57:20protecting internal data structures and
57:22you have to get the locking order right
57:23to avoid deadlocks and I just think it's
57:26it's insufficiently appreciated how much
57:29difficulty this sort of thing can cause
57:34another instance is allocating meta
57:37objects for example compiled code within
57:39the heat this has many good things you
57:41have a single shared resource of memory
57:44and you're managing it universally
57:47uniformly but it also causes a lot of
57:50problems when you know it's no longer
57:53the case that all allocations are
57:55explicit in the source code execution of
57:57a program may load a new class that will
58:00implicitly cause allocation and there's
58:03interactions we didn't anticipate
58:05meta-circular compilers that where the
58:08compiler is written in itself for
58:10language like Java you have to think it
58:12is this intrinsically good or it is does
58:15it serve some purpose right if you
58:18already have a compiler that's written
58:21in a lower level language like C++ what
58:23benefit are you actually gaining I just
58:25want to make sure people ask that
58:27question and
58:28answer it to their satisfaction rather
58:30than just assuming that's doing a
58:32language in itself is is an intrinsic
58:35good thing so a few pitfalls I've
58:40noticed one thing to watch out for in
58:42writing compilers is diminishing returns
58:44especially you know when you're in grad
58:46school reading lots of papers a lot of
58:47the papers tend to focus on things which
58:48are very quantitative and easy to
58:50analyze and a lot of those problems just
58:52don't matter from those people there's a
58:54lot of work done on big scientific
58:56matrix codes and things but unless you
58:59expect scientists are gonna be using
59:00your language don't worry about it
59:02focus on something else it's really easy
59:05to get stuck in the trap of you know
59:06throwing together a few benchmarks and
59:07just obsessing over those benchmarks
59:09things as fast as you can because it's
59:10fun but you know that may not make your
59:14your users that the happiest another
59:18problem that every compiler I've ever
59:20seen has had as insufficient testing I
59:22mean there I don't think I've ever used
59:23a compiler didn't have some bugs in it
59:24and that can be really bad especially if
59:27you're working out as a dynamic language
59:28compiler bugs can be security holes that
59:30people can exploit you know if use the
59:32wrong register somewhere well suddenly
59:33maybe they can scribble on memory
59:34they're not supposed to see and then bam
59:36they can take over your machine and wipe
59:37your hard drive but be very very careful
59:40so my advice here is to write just just
59:43tons of automated tests for your
59:44compiler if you can if you start out
59:45doing that early on you'll be happier
59:48you'll get your compiler done faster and
59:50the second thing is just take every line
59:52of code you possibly can just run it
59:53through your compiler and some automated
59:55way all the time even even run it just
59:56just compile it and hope that maybe
59:58we'll catch some asserts firing or
59:59compiler an actual example this sort of
60:02thing that happened to me it was back
60:03when I was working on this Macintosh
60:05emulator where I was dynamically
60:07compiling a 68k program to x86 or
60:09playing the game Prince of Persia the
60:11Macintosh version on my PC I was walking
60:14my little guy across the screen I found
60:15it whenever I climbed up a certain
60:16ladder in a certain screen the guy
60:17vanished and I walked back he was fine
60:20it turns out after live debugging that
60:23I'd gotten a particular case of a signed
60:2516-bit right shipped wrong and
60:27everything about the whole system work
60:29except the guy disappeared in the ladder
60:30and so that was a hole in my test Suites
60:32so it pays to cover all of your bases or
60:36just been a lot of frustrating time
60:37debugging
60:39and the last thing I'm going to say is
60:41watch out for language constructs which
60:42look like they're efficient but are
60:44actually incredibly slow this has been a
60:46problem for us because we want to
60:48support both these naive users who
60:49aren't using types and time to compile
60:50or anything and also the efficient users
60:52you can write 10 characters which might
60:54take 10,000 cycles to run even though it
60:56looks like it will take 5 what we've had
60:58to do there is allow you if your
61:00sophisticated user to tell the compiler
61:02don't let me do these surprisingly slow
61:03things make me say I meant to do it but
61:06if we don't having something like that
61:08people have a very hard time making
61:09their programs run efficiently because
61:10their intuitions may not line up with
61:12your implementation so first got a
61:16pitfall here is gimmicky language
61:18features I've mentioned run or a dynamic
61:20inheritance there's also been a history
61:23of elaborate synchronization constructs
61:26path expressions things that describe
61:28all the operations you want to have
61:30happening on your objects at various
61:32different points in time all these look
61:34very very good when you start saying
61:36when you start comparing them against a
61:38set of small examples but when people
61:40are using them in broader contexts that
61:42tend to diminish and importance
61:43complicate your implementation and make
61:45life harder for everybody
61:47the second dajin this is especially for
61:50people doing research focus carefully on
61:53what your research goals are and
61:54eliminate all other sources of
61:56complexity don't do you know if you're
61:59not doing research on dynamic dispatch
62:02don't build a system that supports
62:04dynamic dispatch if you're not doing
62:06research on on I don't know what message
62:12sending message seems to access
62:14primitive fields right give yours to
62:16make make life easier on yourself and
62:17just let people declare Struck's of
62:24primitive objects with indicators and
62:26things like that and don't don't take
62:27your levels of the abstractions so far
62:29down that you've got to do some
62:30optimizations just to get the basic
62:31efficiency that
62:32but does it that's decibel the other
62:35pitfall is don't go down a rat hole a
62:38rat hole is when you want to get some
62:41results you want to make some program
62:42run twice as fast and you can steal that
62:45you want it that you can make the
62:46program run twice as fast but you don't
62:48know that you can make it run twice as
62:49fast and you spend six months with the
62:52feeling that your one day of hacking
62:54away from a factor of two in performance
62:56okay cut that off really quickly have
62:59some concrete evidence that you can
63:01accomplish your goal before you go off
63:03and investigate amount of time to come
63:04to beacon to to accomplish it have an
63:08advisor with the advanced rapid
63:10detection system have an advisor has
63:11gone down a few of them in the past
63:12itself okay so now we can open up for
63:17questions preferably from students in
63:22our class among but also anyone else
63:32are you
63:39yeah understanding their distinction
63:45you're making between objects can change
63:47your behavior over time versus another
63:50parents so okay so I think it put your
63:54finger on a very good point that is that
63:56objects play different roles of
63:57different points in the computation they
63:58have their they therefore have different
64:00behaviors at different points in the
64:01computation it's important that this be
64:04reflected in programs somehow and one
64:07really cute way to do it is to use
64:08dynamic inheritance right because you
64:10just swing the pointer it's very
64:14attractive I think the way you do this
64:15is you see you structure the control
64:17flow of your program so that you just
64:19don't invoke the bad operations on the
64:20object when it's in the wrong State and
64:22it's suboptimal if you look at it from
64:25that particular perspective but in the
64:27broader scheme of things the fixed
64:30dynamic inheritance is worse than it's
64:33your or at least well you can download
64:47new code you can download new code but
64:51how do I change that old object to
64:52continue so now hold on acknowledge
64:53funds in your code where you go you you
64:55use you have some metal level in your
64:57system right that says so you know hey
65:00I'm changing things now right there's
65:02two levels there's two levels in any
65:04system one is the level that you're
65:06programming in when you're writing the
65:07code the other is the level that you're
65:09operating at when you're managing the
65:10system and understanding this behavior
65:12and I think if you're talking about very
65:14long running systems where objects need
65:16to change the behavior over time or you
65:17need to be able to change the way the
65:20system works
65:20you're better off separating that into
65:22another level where you have somebody
65:24with you who can AC beyond all the
65:26abstractions these see what's going on
65:28in the system it has tools that support
65:30that and you know three do things that
65:33you that your programmer wouldn't that
65:36wouldn't be supported by the programming
65:37paradigm of your language that you're
65:39using I think that now that's my opinion
65:42but the same way to do it so of course
65:44there's going to be a group of people
65:45who go off and say wouldn't it be cool
65:46if we could mix these two metaphors and
65:49have a great language it does it and
65:50maybe they'll go off and do some great
65:52research and find out a good way to
65:54support this kind of stuff but I think
65:56right now I don't know how to do it in a
65:58way that I think keeps me sane or
66:00anybody else
66:02I want to echo that and amplify a little
66:04bit we have there are those within son
66:10that argue that there are customers that
66:12have servers that are supposed to run
66:15the proverbial 24/7 and I sometimes hear
66:1924/7 360 and I get a type error hate
66:23that and and the argument is that they
66:27need to be able to update code
66:28dynamically within the running Java
66:31program in order to fix bugs and this
66:35makes me extremely nervous
66:37I mean if if their method is wrong the
66:44analysis you would have to do it there's
66:47a couple cases in which it makes sense
66:48right you you have a pure function and
66:50your entry it was correct before and
66:54you're introducing a new correct more
66:56efficient implementation of that
66:57function all right that's fine I
66:59understand that but almost every other
67:02case if there were side effects the
67:06trying to do the analysis to determine
67:07the scope of the errors that might have
67:10been left in the rest of the the state
67:12of the currently running system because
67:15of the error in this method it is is
67:17just too daunting to me I can't imagine
67:19us getting that right
67:28from there all the students are saying
67:31the usual thing set aside to program
67:40do you know the FFA you know bring down
67:44certain they pass them as their right
67:47agent you don't have a choice right and
67:50live dependent yeah so you you can't not
67:53solve this problem well you could brown
67:55the plains below okay oh you can't well
67:58I think I think you're missing another
68:00important point which is that which is
68:02that there can be things that are
68:04functionally not working that don't
68:05actually leave long little bits of data
68:07around and that's that arises a lot
68:12Karen
68:14trying to be controversial I'm actually
68:22thinking that the thing is s in their
68:23terms of the context of it distributed
68:26systems where you know the object you're
68:28they're calling to whatever might system
68:30he owned by somebody else
68:31I say we may want help greater they may
68:34want to do something you like another
68:36lovely
68:38comes down I still may be no assumptions
68:42about what it does or its types or
68:43whatever like that and so it seems
68:46that's however related issue of how do
68:47you got a management pension
68:51so my initial reaction is there are
68:57people who criticize the street at
68:59object-oriented programming basically
69:01citing the exact property that you've
69:03just mentioned they say they say
69:05distributed objects type things together
69:07very tightly in ways that makes it
69:09difficult to change the system because
69:10you've got references that go across
69:12machines that are you know what do you
69:13do and need to replace one object with
69:15another and you got to reference the old
69:17object I think it's possible to preserve
69:21some of the attractive features of
69:24distributed object programs and object
69:26learning the program distributed object
69:27programming but you have to take a look
69:29at how you pull back from the
69:32abstractions that have worked so well on
69:34single machines and allow people to do
69:37things like redirect references and do
69:39this kind of meta meta system futzing
69:42that you have to do in a distributed
69:43long-lived system
69:46I don't know I don't know if that's
69:47addressing the issue you thought sound
69:49let's move to tell you something
69:54I'd like to hear Warren how Colonel deal
69:57deals with Mitch mountain code we're
69:59summit manifestations under them and the
70:02other question I have is that David
70:04mentioned that rep coming to DC is
70:06coming back and will mentioned that
70:10finalizes are a bad idea Python uses ref
70:13counting DC to provide good semantics
70:17for finalizer so I'm wondering if this
70:18is a good idea or a bad idea
70:24okay the way it works in curl is you can
70:27take your program and remove all the
70:30type declarations from your variables
70:31and fields and they'll be replaced with
70:34a type called
70:35an e which is a lot like say a type and
70:37Lisp or other languages where all the
70:39type information is carried around with
70:40that object at runtime all the same
70:43operations work on any x' as work on
70:45normal objects for example if you take
70:46an integer and you put it in any you can
70:48add it to another integer it's just that
70:50the compiler whenever it sees an any
70:51being added to something has to call a
70:53runtime support routine that does all
70:55the same work at runtime that the
70:56compiler did to make sure the types are
70:58right and figure out what operation to
70:59perform so it's a lot slower one area of
71:03interesting optimization for us will be
71:05to you know do some type inference and
71:08eliminate some of those any as when we
71:09can we do not do apparently yet we've
71:13been focusing more on the programmers
71:14who want to the most programmers who
71:17want really high performance also a
71:19comfortable type systems going to use
71:20this we haven't really catered to that
71:22people who don't like types and while a
71:23lot of performance yet
71:29yeah so I'm not completely familiar with
71:33Python my my capsule description of it
71:35someone gave it to me was was isomorphic
71:37to module of three without the types so
71:51if it's possible to create cycles which
71:59I assume there's assignment and it is
72:00then it's not possible to give I think
72:05any real heavy-duty semantics to when
72:08finalizar z' should happen so I'm I'm
72:14doubt I'm dubious in case we have cycles
72:20then final answers would never get
72:22called unless you explicitly go and it
72:25has a debt debt our object area where
72:27obviously can't have finalized can't be
72:29GC
72:31other objects that rhyme cycles are GC
72:34because there's a backup start respectin
72:36after that and their plan analyzers if
72:39they have them orbit are eventually
72:41executed the final answers are never GZ
72:44they get put in a bin somewhere where
72:47you your program I have to manually I
72:57don't think I mean if you're going to
72:59allow general-purpose object graphs and
73:02some objects are going to have finalizar
73:04say I don't think it's good idea to you
73:06distinguish between objects that can be
73:09part of such cycles and say they can't
73:11summon some static way say they can't
73:13have finalized errs so so if objects
73:16have finalized errs then I think they
73:18have to be there unreachable ax T has to
73:20be discovered asynchronously by an
73:23asynchronous garbage collection system
73:25and therefore it seems to me the logic
73:28is unassailable that the finalize errs
73:30have to be at least conceptually
73:32executed asynchronously in a separate
73:35thread I've never been able to see any
73:37way around that I think we've got a I
73:41think finalizes are an example of
73:43something that gets put into programming
73:44way which is because the designer is
73:46envisioning one particular method of
73:48implementation namely reference counting
73:51and if you give them a good semantics
73:54that is like a specific definite
73:57semantics and they couldn't have that
74:01semantics if another implementation
74:03technique would use say garbage
74:05collection and generally speaking I
74:08don't like that kind of language design
74:10because it restricts this class of
74:12implementations that can be used and for
74:13right now for a lot of applications
74:16garbage collection works better than
74:17reference counting and so you're
74:19restricting the range of usability of
74:21the language now for Python that may not
74:23matter because Python as I understand it
74:25is generally used in applications where
74:27performance is not a big issue as sort
74:29of performance problems with reference
74:31counting just are not as important as
74:33having a definite
74:34finalizes so that may be a case where
74:36for Python it makes sense but in general
74:38I don't think that's good design
74:41I think that that example of what people
74:45are looking for from finalizes is overly
74:48simplistic I think that one of the
74:50common uses is if you have some model or
74:52some object that models an external
74:54resource and and when when you're
74:57disposing of the object you want to make
74:59sure that the external resource is freed
75:00up as well the classic example being
75:03strings there are other ways to handle
75:05that besides finalizar stuff that's the
75:11one that you should never use so the
75:14question is I mean you're absolutely
75:15right that's what you want to use
75:16finalizer store but memory is only one
75:20kind of resource and an orbit collection
75:22takes care of that and many languages
75:24also take care of Bell descriptors for
75:26you but what about other things what
75:28what should be in a language to take
75:30care of automatic resource
75:33that grows what's going on here is this
75:35confusion of this conflation of memory
75:38deallocation and going out of scope
75:39those are two different things people
75:41use destructors in C++ for all sorts of
75:44things like declare a local law object
75:46up here and then when it goes out of
75:48scope automatically let go the lock was
75:50nothing about memory act the allegation
75:51in an apple so you confuse those two
75:53properties and you get confused right
75:55well when I was saying finalization I
75:58was meaning in the Java sense for those
76:01uses for which you might plausibly not
76:05sure I believe it but for example the
76:07file descriptor closing and I think that
76:11comment about that the tying of one
76:14resource the recycling of one resource
76:17memory to other resources is is a real
76:20bad idea I don't have any great ideas on
76:22what to do about it I think I think that
76:26this points have been made so far that
76:28going out of scopes not the same thing
76:30as becoming unreachable and sometimes
76:32finalization should be associated with
76:33one sometimes with the other as to how
76:35to handle the problem of becoming
76:36unreachable and a heap allocated object
76:38that may be shared among several
76:39structures I think the best way to do
76:41that is to have weak pointers and a
76:44mechanism looked at a program through
76:46explicit program code can use to
76:48determine which pointers are accessible
76:51only through the weak pointer table so
76:52to speak and then if you want to
76:54finalize those to finalize them however
76:56you want and take them out of the weak
76:58pointer table and and and and then the
77:03burden is not on the language implement
77:04or to guess what the intent of the
77:05programmer is is the burden is on the
77:07programmer to express the meaning of the
77:09program
77:16a lot of people maybe you want to talk a
77:27few seconds about the application where
77:30my initial response time is important
77:33versus my long-term long time in that
77:37case is an interpretation the quickest
77:41way for me to get an answer when I've
77:43gotten a dynamic and I don't know what's
77:45going to happen the code just arrived
77:47and I want to get an answer now
77:49like in a webpage yeah the point I was
77:52trying to make is that the sort of
77:55compiler I was describing is so fast
77:58that the number of executions of a
78:02method it takes to amortize the cost of
78:08compiling it versus interpreting it is
78:11quite small on the order of no it's not
78:15less than one yeah so so it's not it's
78:22not that interpretation is dead is that
78:24is that if accepting the case you're
78:29talking about if you're if you're
78:30running for a minute
78:31you better be spending a minut fraction
78:34your time interpretation that that cut
78:36off is on the order of 10 executions of
78:39a method as opposed to 10,000
78:43so
78:46I'd like to dive in the best thing about
78:48interpreters is that they're easy to
78:50write so you can come up with an
78:52implementation really really quickly you
78:54get something going and play with it so
78:55I think that's the primary advantage
78:57we're using interpreters who posted
78:59just-in-time compilers is you eliminate
79:00that huge engineering effort or
79:02substantial engineering effort required
79:04to get your program going
79:07and then put history questions well
79:10lucky there're a programming language
79:11that implemented your kind of threat
79:14semantics called concurrent Pascal one
79:17of the early languages didn't have just
79:19what you were talking about yeah I'm
79:21personally don't know her Pascal but I
79:23was in fact thinking of communicating
79:25sequential processes as the kind of
79:27thing that had the kind of model I'd
79:29like to see in languages unfortunately I
79:32can't comment on in Cresco somebody else
79:35might be able to I can comment on CSP
79:40CSP is an interesting language for those
79:43so basically the idea here is that
79:45you've got a bunch of processes that
79:47encapsulate data and they send messages
79:49back and forth in practice it's
79:51unbelievably cumbersome to use because
79:53you have to be able to predict when you
79:56generate a piece of data who's going to
79:58want to consume that piece of data and
80:01it gets it's really complicated and what
80:04you find yourself doing is you know just
80:08drilling in communication patterns and
80:11if anybody else wants to read that data
80:13you've got to go change code everywhere
80:15that produces it so it's it's it's
80:17really difficult to use in fact it's now
80:19it's great if you have very loosely
80:21coupled pieces of code then you know the
80:25focus is on keeping the pieces separate
80:27not interfering with each other if you
80:28isolate everything using a message
80:30passing it works great but in you know
80:31most sort of moderately coupled systems
80:33you want to be able to get data very
80:34quickly and more importantly you want to
80:36be able to change the data accessing
80:38patterns of your program without having
80:40to worry about who's gonna produce a
80:42who's gonna consume it like I think I
80:44don't think about
80:45we clear object to be concurrent and
80:48then the compiler ensures that only
80:51those kinds of objects can interact
80:53between threads yeah you don't do that I
80:56think that was the name of that language
80:58I never use it myself either yeah no so
81:00few people have really designed what
81:02he's talking about I believe right and
81:05people are continuing to design safe
81:06type systems now for more complicated
81:09minded is that that that support that
81:10kind of behavior is good any other hand
81:13I think it'd be a misstatement to say
81:15that that insulates you from the
81:16complexity of threads if I remember
81:18concurrent Pascal correctly you have the
81:20equivalent of monitors and those
81:22constructs had blocks which were threads
81:25right so you can have several threads
81:28and they would be executing operations
81:30on these monitors and you had all the
81:33the same complexities of the monitors
81:35were implicit mutexes and condition
81:37variables and as far as I can tell it's
81:39isomorphic to thread programming today
81:41well the big differences though is that
81:44you don't get some real insanities that
81:46can happen if you have unprotected
81:47lasers
81:54user experience a lot of people you know
81:57time spent while you're in sort of the
81:58steady state of the program is okay but
81:59waiting for it to come up this is not
82:01and it ties together I think a lot of
82:03the topics that have come up in the
82:04panel Microsoft Windows for example when
82:07its booting up it's doing an incredibly
82:09dynamic general things looking around
82:11you know what kind of hardware is on my
82:12system and you know what kind of
82:14software has been loaded on it but of
82:16course most of that silly it's going to
82:18do the same thing over and over again
82:19every time it just wastes a lot of time
82:20making the same old decisions every time
82:21most of the time when things are coming
82:23up like when Microsoft Word is coming up
82:25you're basically executing at the speed
82:26of your hard drive which on a laptop is
82:28not very good at all there's a lot of
82:30evidence that Microsoft spend a lot of
82:32time optimizing the back as opposed to
82:34other things
82:36sophisticated program rearrangement to
82:39get things lined up in in the right
82:40order and so on that really seems to
82:43affect you know real user experience
82:46much more than traditional kinds of
82:47optimization that sort of galling to
82:49think about the time and I'm not the
82:50last person here
82:51you know we've spent doing things like
82:52you know software pipelining and whatnot
82:54when in all that really matters is how
82:56fast we can pull code from the disk and
82:58then pump it into the machine a related
83:00issue there in curl is we've spent a lot
83:03of time downloading some web page that's
83:05curl content in it we'd like to overlap
83:06the downloading of the displaying so
83:08it's been slower than a hard drive and
83:09so we have this sort of incremental
83:11evaluation model where we're taking
83:13stuff sort of a seriously from the from
83:16the web and then displaying on the
83:18screen as it comes down so you get your
83:20first screen of output fairly quickly
83:22and then it's continued to process stuff
83:23after you go down sort of a similar
83:25issue
83:28in the Java world there's efforts to
83:31have the equivalent of shared libraries
83:34where in one without loss of generality
83:37here's here's a one kind of
83:39implementation you have some process
83:40running that has a bunch of class files
83:44loaded in it and when you start a new
83:46Java process it it Maps those pages
83:52containing the class files that cares
83:55about into its memory and that's a lot
83:57faster than sorry yeah well similar yeah
84:03this is actually how Perl works too by
84:04the way we compile Jacob all packaged we
84:07recorded a shared place in every applet
84:09that you load that of course it just
84:10uses that that same one until it's not
84:12used anymore an interesting research
84:15problem in that area is let's say you
84:18went through the effort of compiling
84:21these class files would you want to
84:23share that compiled code would you be
84:25losing optimization opportunities by
84:28having to compile it in such a way that
84:29it's not specific to each individual
84:31program that uses it etc etc so what's
84:34the trade-off there that that's still
84:37very active research sort of I've got
84:40two more questions
84:43three related questions are any dynamic
84:51languages borrowing significantly to say
84:53they're huge
84:54should they be in three if you convert
84:56say they're into a decent dynamic
84:57language yes they're going from static
84:59dynamic compilation
85:04don't cast questions about sailor yeah
85:07which aspects of Santa do you think
85:09would be appropriate for Chanukah
85:11abolition downplaying because I mean my
85:13understanding they say there is that
85:14it's a somewhat cleaned up version of
85:16C++ to a very first order a guy right
85:21it's in a sort of sort of general static
85:24object oriented language kind of family
85:26right so what what aspects of saying
85:28that II think would be valuable in this
85:30context are being firmly realize right
85:32now I think the most valuable aspect and
85:36the main reason for my benefit from
85:39benefit from elation is the front price
85:41type
85:43which is nicely done it's very powerful
85:45but it makes compilation hurt its left
85:48because you have to do type checking
85:49across modules they're all done yeah
85:52yeah so I mean my opinion is I think I
85:54think this kind of generic typing is a
85:56useful thing it's there's been an in
86:00traditional safety feature that you can
86:02have I think the way to get it is to
86:05have a variable waved way it would be
86:07useful in dynamic systems is to have you
86:11know low the program and run it have an
86:12option to do it without any other type
86:14checking and then have the time checking
86:15be able to be done offline if you wanted
86:17to do it that's that's where I think
86:19you'd get those the best of both worlds
86:22and maybe people would always do the
86:23type checker in which case you know yeah
86:25if it goes away to vote it without so
86:28parameters types for a big source of
86:29overhead for our language because you
86:31might have like an array type and if
86:33just instantiating array of int
86:34theoretically creates 200 methods or
86:37something if you look at the whole class
86:38hierarchy everywhere but you're gonna
86:39use five between you typically we
86:41actually had to spend a lot of time
86:42working on ways to sort of only lazily
86:45compile things as you act if you
86:47absolutely need but there does work if
86:49you can no effort into it
86:55so I think we've heard from several of
86:58the speakers that that and program
87:02annotations are great and that one thing
87:05we'll be seeing more of in the future is
87:07new kinds of program annotations and new
87:10ways of annotating our programs to make
87:13them more efficient so I wanted to hear
87:15from some of you what your opinions are
87:18on what's what's coming soon and perhaps
87:21what should never arrive so what
87:24annotation do you think it's going to be
87:26that it's the low-hanging fruit I could
87:31add this annotation to my dynamic
87:33language it would improve my programs
87:35for men dysley and on the flip side what
87:38annotations do you think are going to
87:40going to get bandied about but but
87:43really are a terrible idea and and we
87:45should focus our attention away from
87:47them as quickly as possible
87:48I guess I'll take a swing at that one
87:54so annotations that are a bad idea any
87:56annotations that tie two pieces of the
87:58program together any annotations that
88:00say for example you know I'm gonna I'm
88:04gonna produce data here and use it here
88:06and that's the only foot that's the only
88:07way that this data is gonna gonna get
88:09you produce is going to get used I think
88:10that's problematic because it it like I
88:13said it ties your program down more than
88:15it ought to be tied down annotations
88:17that I think are going to be very useful
88:19if you're using threads you really want
88:22to be able to keep your private data in
88:23your shared data separate and I think
88:25that's a useful annotation that it's
88:26going to come around
88:27I think parametrize types are going to
88:29make it into Java really quickly
88:31although there's people here who are
88:32much more of an expert on that topic
88:33then than I am I'm paying a guy right
88:35back there
88:38and Dave of course is going to know much
88:40better so I think those are the kind of
88:42the two extremes I don't know what's
88:46what's it's hard to say it's it's it's
88:49hard to come up with that examples of
88:50bad annotations because out okay and a
88:53bad allocate here okay who's good and
88:55who's a great example of a bad
88:57annotation a bad annotation is an
88:58annotation that's not checked like a
89:00comment the problem is the the great
89:03thing about comments is they tell you
89:04what's going on in the code the really
89:06bad thing about them is that they're
89:07wrong sometimes so that's right so
89:14that's that's kind of you'd like to
89:16avoid that if at all possible in the
89:17annotation language so I spent the four
89:21years of my life before I came back to
89:23Massachusetts working out in California
89:25with the group in Dex Cirque in program
89:29verification which was the extended
89:31static checking project which is now
89:33they've continued on they've done a
89:34system release for Java and I encourage
89:36you to check it out I think that in the
89:41future any invariant about you of your
89:45program that you would like to be
89:47checked will be expressible and you'll
89:50have at least a fighting chance of
89:52having a program verifier statically
89:55verify that so you'll be able to give
89:58representation and variants of your
89:59abstract types requires clauses of your
90:02calls specify locking orders so you can
90:05prove absence of deadlock specify you
90:08know these fields of this object are
90:11protected by this lock and verify that
90:13that lock is held whenever those fields
90:15are accessed etc etc I think I hope
90:20because it's the only way we're gonna
90:22really make correct software that that
90:24becomes true in the future that this is
90:25just a matter of course your program
90:27doesn't work until the verifier says it
90:29does I'll give you an easy to implement
90:32one that we borrowed from Dylan Dylan is
90:34this concept of sealing classes which
90:36means that you can't subclass the class
90:38outside of its module that's really
90:40useful for optimization because you can
90:42turn procedure calls and the method
90:43calls because you can see that the
90:44method can't be overridden outside it's
90:47very very cheap to implement
90:48and it has proven a big win
90:54all right guys it was fun huh yeah
