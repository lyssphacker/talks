### Dynamic Languages Wizards Series, Spring 2001

#### [Panel on Runtime, March 20, 2001](https://www.youtube.com/watch?v=SjbtEnfm7_Q)

Richard Kelsey, David Moon, Tucker Withington, Kim Barrett, Scott McKay  
Trenza, ODI, Curl, iRobot, and HotDispatch respectively.  

Richard Kelsey worked on Scheme48 and T  
David Moon worked on MacLisp, Flavors, CommonLisp, and Dylan.  
Tucker Withington worked on CommonLisp, Dylan, and Curl.  
Kim Barrett worked on CommonLisp, Dylan, and L.  
Scott McKay worked on CommonLisp and Dylan.  

there's people
0:06we're gonna start right now my name is
0:09Jonathan bow crack very honored to be
0:11emcee today
0:12this is part of the dynamic language
0:15series there's a website that has a
0:19bunch of information about what we do
0:21and one of the things that we we sponsor
0:25our series of talks where we'd love to
0:31have some more proposals for talks if
0:37you want to get mail about the talks
0:40you can send mail to either Greg
0:43Sullivan there or myself and those are
0:46our email addresses today we're gonna
0:49have a panel that is part of a seminar
0:54that Greg cost us and myself for
0:58teaching this semester here at MIT it's
1:01on advanced object or in a dynamic
1:03language design and implementation and
1:05today we have a panel of distinguished
1:08experts on runtime and this is
1:12particularly targeted towards graduate
1:14students wanting to do research in this
1:16area and we've designed this to
1:19stimulate ideas and towards that that
1:22would be promising as interesting
1:24research ideas or areas to pursue so
1:29we're going to have three panels this
1:31semester today this is our first one
1:34this is on runtime we'll have one on
1:36compilation for 24 and then language
1:40design 510 and the way this is going to
1:44be structured is we're gonna have two
1:45parts of fixed part at the beginning we
1:47have round-robin questions that that
1:50Greg and I have prepared ahead of time
1:52and given them a chance to think about
1:55we'll give them two minutes each and
1:56we're going to be very vigilant about
1:59the two-minute period and then at the
2:02very end we're gonna open that up to
2:03questions
2:04meaning a priority to the students of
2:06the class and then we're gonna open it
2:08up at the public it's going to be an
2:10hour and a half total but I've at least
2:15talked to majority of the panelists and
2:17they're willing to
2:19stay longer and those that can't are
2:21free to leave
2:22that's just so we're gonna go for a
2:25while and I'm sure there's just a lot of
2:27questions this is such a great
2:28opportunity to have such distinguished
2:30panelists I'd like to start by
2:32introducing them I'm really thrilled
2:34that they agreed I could spend an hour
2:37and a half just talking about their less
2:39serious careers but I'll just make it
2:41brief at I'll start with cam Barrett
2:46King Barrett I worked with that
2:48Harlequin he started but by going to
2:52school at MIT he worked at I I am on a
2:54list machine and then he went to
2:57chestnut he worked on common list there
2:59Apple he was a designer implementer of
3:02Dillon Harlequin he worked on the Dillon
3:05runtime and just tons of things there
3:07now he's currently at iRobot he's
3:09working on an embedded real-time lisp
3:12called L as well as applications like
3:15getting robots to go down in the bottom
3:16of the ocean do oil drilling and it's
3:20running Lisp so this is a huge triumph
3:22for this okay we got Richard Kelsey he's
3:27he's had an amazing career as well
3:30he's Skye's PhD from Yale he worked on
3:33the T orbit project there he's worked on
3:36the Haskell compiler he was on the
3:38faculty at Northeastern he was at NEC
3:41working on language research
3:46he's currently he's director of
3:49technology at trends ax and he is one of
3:52the authors of scheme 48 and the scheme
3:55manuals are NRS thank you for coming
3:58Scott McKay is here I'm pleased to
4:01introduce him as well he's he got his
4:05degree from WPI he was I don't know
4:08almost a decade at symbolics working on
4:11just a ton of different things one thing
4:13I'd highlight is he worked on he was a
4:16designer and implementer of of CLM or
4:18Klem depending on what coast you're from
4:20he also was designed an implementer
4:24co-conspirator of the virtual list
4:26machine chief designer at Harlequin
4:30through 1999 worked with me on
4:33and he did just a ton of things there
4:36one was he
4:37did a new version of of ceylon for Dylan
4:41called him and he worked on villain
4:44development environment and lots of
4:45libraries currently he's chief architect
4:48that hot dispatch and he's working on
4:54toolkits for web applications and then
4:59I'm very very pleased to have Dave moon
5:01here who was here at MIT for a long time
5:06and he did tons of things here and I'm
5:09only going to just do a tiny little
5:12survey of those one he worked on the
5:16multics Mac Lisp he worked on he was one
5:19of the main contributors and co-author
5:21of the manual for list machine he was a
5:25technical director at symbolic Sandro
5:27huge amount of the code and he was at
5:31Apple designing and implementing a large
5:34part of Dylan currently he's at ODI or
5:40what would be exelon excellence the
5:43parent company and I don't know all
5:44right well I'm sure you're doing you're
5:46one of the chief architects there thank
5:50you very much for coming
5:51finally we have Tucker Withington
5:54started with a degree at Harvard he
5:57worked at mitre and encore and then
5:59moved on to symbolics where I worked on
6:01the ivory board real timeless virtual
6:03machine just on and on and on tons of
6:05things
6:06he worked at Harlequin with me on
6:09garbage collection wrote the book on
6:12Dylan programming and currently he's at
6:15curl and he's designing and implementing
6:21parts of curl especially the runtime and
6:24just he's just doing a ton of things
6:26over there I really appreciate you all
6:29of you for taking time out today to come
6:31here today we're going to start with
6:34like I said a round-robin two minutes
6:37per panelists I'm going to go over the
6:38questions just very briefly and then
6:40we're going to launch into it and we're
6:43just going to go from the
6:46well actually yeah let's just go left or
6:48right and and the questions are you know
6:53after all this experience which your
6:54which what you feel is a good guiding
6:56philosophy for pursuing this area
6:59what are promising open problems and
7:03future directions that's number two
7:05three little known secrets for good
7:10ideas that have been dropped but whose
7:11time has now come and five pitfalls and
7:14gotchas okay we're going to start out
7:18with number one guiding philosophy Dave
7:20moon two minutes since I know almost
7:24everyone in the room I'm wondering if
7:26the graduate students could raise their
7:27hands we could see if they're actually
7:28already alright
7:36those familiar with my past work will
7:39know immediately that this has not
7:40always been my guiding philosophy but my
7:42guiding philosophy these days is keep it
7:44simple to be very very skeptical about
7:47the advantages of adding any kind of
7:50complexity at all
7:52of course as simple as possible but not
7:55simpler than possible and that's a
7:57difficult judgement but my experience
8:01says it's much easier and much more fun
8:03to design things in a complicated way
8:05than to design them in a simple way it's
8:07much much harder to make things small
8:09and simple so if you want to have fun
8:11make it as complicated as possible but
8:13if you want to be successful you really
8:16need to work hard on simplicity I can't
8:18stress that too much because every idea
8:22that's locally good may be globally bad
8:24and we always overestimate our own
8:27cleverness I know I do and we always
8:30underestimate how much it takes to go
8:33from a great idea that almost works to
8:35something that really works and if the
8:38idea actually is good and we haven't
8:41overestimated our own cleverness and we
8:43haven't overestimated our ability to
8:45implement it our sponsoring organization
8:48whether it's company government and
8:50university is going to stab us in the
8:52back and yank the rug out from under us
8:54before we can finish anyway so we really
8:57need to do simple things that can be
8:59turned into something useful and in less
9:01than a year is that two minutes yeah
9:05that's two is okay Tiger first I have to
9:08make a disclaimer you've categorized us
9:11as wizards but I'm only a journeyman so
9:14if you use any of my incantations and a
9:16broom pops up with a bucket of water
9:18watch out my guiding philosophy at least
9:23for a while has been the CPU cycles are
9:26cheap but people cycles are not I say my
9:30guiding philosophy for a while has been
9:32CPU cycles are cheap people cycles are
9:35not and this applies to the people can
9:38be users or they can be programmers in
9:40runtime systems we become slaves to
9:42cycle counts we believe that if we take
9:44care of the pennies the pounds will take
9:46care of themselves we spend hours
9:48laboring over an algorithm choice or an
9:50implementation to minimize cycle counts
9:53at the expense of our own cycles which
9:55could be more productively used
9:56elsewhere often these cycle driven
9:59choices result in an algorithm that's
10:01less general or less useful to our
10:03customer the application designer or to
10:06his customer the end user and they may
10:10either prohibit or overlook a corner
10:12case that won't be exposed until the end
10:14user gets his hand on the product and
10:16that could be for some length of time
10:19there's a great anecdote in John
10:21Bentley's programming pearl's where he
10:23describes a bug that he discovered an N
10:25Roth which had lain dormant for tens of
10:28years it was an optimization that the
10:31programmer had clearly spent a bunch of
10:33time on a particular corner case and he
10:35did a great job it was very efficient
10:37the only problem was it didn't do what
10:39it was supposed to do it didn't work
10:41Bentley tries to speculate as to what
10:44the cost of this was the guy's original
10:46time invested plus all the interest that
10:49compounded over the years while his code
10:51lay there doing nothing and in the end
10:53the payoff was negative as a consumer of
10:56runtime libraries you should choose a
10:58library for what it does for you and
11:00your cost
11:01in terms of functionality not the one
11:03that produces the best benchmark the
11:05same philosophy can be applied I think
11:07the compilers languages and applications
11:10that you should tune for people cycles
11:12and not CPU cycles
11:19I'm actually going to in a way disagree
11:22with that I forgot these presents run
11:26and hardware constraints are not going
11:29away you know people talk about you know
11:33Moore's law and machines getting faster
11:36and memory getting faster and bigger and
11:38such what that basically does is it
11:41raises where the bottom is it brings
11:44applications that were impossible into
11:47the barely possible and those are where
11:51a lot of the interesting applications
11:52and where a lot of the interesting money
11:54is is new things that you couldn't do
11:58five years ago I'm coming from from
12:06basically the embedded systems world
12:08these days robotics and all of what
12:13we're doing is on that edge where you
12:20just couldn't have done it five years
12:22ago with the at the cost at the price
12:26points that make it economically
12:28feasible I'm going to agree with David
12:33that keeping it simple is really
12:39important use abstractions use them
12:44religiously diligently if you don't you
12:48will pay for it I don't want to think
12:51about the amount of the number of man
12:55hours I've spent over the years undoing
12:59assumptions that have been that have
13:01propagated throughout a large code base
13:06that's it and I'm looking behind us for
13:10like pods so the first thing in this
13:14little slide says make the design as
13:17simple as possible but no simpler than
13:19that and you know it's it's all but it
13:25really is it's all about simplicity but
13:27there's still some requirements right
13:29get your designs correct and get them
13:32complete as possible but you shouldn't
13:35make completeness destroy simplicity
13:37right it's better to make something
13:39extendable by somebody else than to
13:41waste your time making it so complete
13:44and simplicity goes away and sort of
13:48beyond you know I'll just say it again
13:50it's just too important not to keep
13:52saying the only thing that's important
13:54in the design of things like languages
13:57in library is simplicity of API and
14:01obviously you shouldn't you know to
14:03agree with Kim you can't be interfering
14:05with efficient implementation but but
14:09that's a detail and the least important
14:12design goal of all is also we're staying
14:15and that's that simplicity of
14:16implementation isn't actually isn't
14:20actually a useful goal right that's not
14:23the most important thing because if
14:25you're designing things in a layered
14:26composable way and you've got your
14:28abstractions right then the amount of
14:31time that you spend off making sure your
14:33implement your API is simple at a low
14:35level we'll just pay for itself again as
14:37you build your abstractions layer layers
14:39higher and higher yeah same thing I feel
14:44like a pod person but
14:49haha I think it says exactly the same
14:52telling you but I couldn't maybe I
14:53should change my mind and I could favor
14:55complex interfaces just it's finding me
15:01in the note they sent out to us with
15:04these questions at all
15:05it was the line that the use of
15:09PowerPoint etc is discouraged we don't
15:11want to lose valuable time mucking with
15:13technology really seem to sum up but you
15:20you know you don't want to lose valuable
15:22time marking with technology and I think
15:23the part least with PowerPoint isn't as
15:27much purple in itself but the fact that
15:29it wasn't PowerPoint for the problem but
15:30the connecting up PowerPoint with
15:32whatever display technology was
15:33available maybe works maybe it doesn't
15:36work so it really does come down to
15:39interfaces at work and so you have to be
15:42able to connect up what you do with what
15:44other people do or it's never going to
15:47go anywhere I could spend another minute
15:51talking about the ribbon yeah how
15:53wonderful this keeps things simple but I
15:55think I think we've made the point okay
15:58thanks a lot
15:59we're gonna actually change the order so
16:01people get different opportunities of
16:03these different positions okay so we'll
16:10start with you Richard on the second
16:12question which is interesting open
16:15problems and future directions
16:16especially for graduate students
16:19interested in pursuing research in this
16:21area wouldn't you know I didn't have
16:25much written down for this one
16:27- for maybe the really interesting
16:30problems at the moment all come from the
16:34challenge of writing long-running
16:36distributed systems
16:38in that with everything seemed connected
16:42to everything else these days and
16:45programs just to all spend their time
16:48talking to other programs you know what
16:54little advances we've actually made in
16:56give you how easy it is to write
16:57programs we've made almost nothing in
17:01terms of writing distributor an
17:03asynchronous programs and you can sit
17:04down and write a program that's going to
17:06run over a network on a variety of
17:08machines and bun reliably is extremely
17:13difficult and especially if you throw in
17:16there wider interconnectedness of things
17:18and you have to deal with failures you
17:21have to deal with malevolence on the
17:23part of other people and also these
17:26programs are now running they're not
17:27running in a lab they're running out
17:28there they're moving actual money
17:30between machines people's life just
17:32depends on them they say these are
17:34enormous problems and getting programs
17:36to run in those circumstances and to run
17:38for long periods of time so I don't I'm
17:41going to point any actual particular
17:43parts of that but it is it is especially
17:46a run time machine because if the run
17:49time system itself can't perform under
17:52those circumstances whatever program the
17:54program will grow it isn't going to work
17:55either so I think that's where that's
17:59Forli where the real challenge is right
18:00now
18:03it's not okay um I work in a distributed
18:06company so for me one of the interesting
18:09challenges is what do we do about making
18:11distributed programmers work as opposed
18:14to distributed programs work and for me
18:18that means some exhausting things about
18:20I think some some fertile areas for
18:24looking around or really in sort of
18:27areas of I guess what an eyeful would be
18:30called programming by contract and being
18:32able to prove assertions about about
18:35contracts about things so that when
18:37people have made claims about people on
18:40the West Coast make claims about
18:41such-and-such satisfying this this set
18:44of protocols and whatnot you can
18:46actually you actually have some
18:47guarantee that that will work I think
18:50that gets back to distributed programs
18:52as well because as we are loading more
18:55and more untrusted code from untrusted
18:57sources across you know across networks
19:00and whatnot that sort of that sort of
19:03work is very interesting and very
19:05fruitful
19:08Gentiles one of the frustrations in sort
19:13of the work space that I am operating in
19:18is that there is so much variation
19:21between platforms I'm currently working
19:25on a project that is using six different
19:30programming environments to develop the
19:32software and that's painful one of the
19:43one of the reasons for this is that sort
19:48of one step back from the the physical
19:54architectures there's not a month
19:55there's not much commonality there
19:57really ought to be the nearest thing to
20:02commonality there is C compilers that
20:06even C compilers have a fair amount of
20:08variation particularly when you're going
20:12from different classes of machine you
20:14know like a 8-bit 16-bit 32-bit machines
20:18and moving back and forth between those
20:23is is not easy so one of the areas that
20:30I would like to see more were happening
20:32in is tools for making it easier to
20:37develop languages on develop programming
20:41languages and implement them on new
20:43classes and machines one of the area's
20:47well C is used for that by a lot of
20:51people but it has some deficiencies it
20:53has a particular machine architecture
20:56embedded in it which may or may not map
21:00easily between to the what you're trying
21:05to do there's been some efforts along
21:08those lines there's a project called C -
21:13- that looks sort of interesting don't
21:16know whether it's gotten any work any
21:18real
21:20behind it and there's been a number of
21:22others a number of other sort of
21:24proprietary projects along those lines
21:27so that's an area where I think that
21:30there is a lot of potential benefit and
21:35some interesting problems
21:40McKim proof that we didn't all collude I
21:43was gonna say but I am going to agree
21:45with Richard and Scot I wrote down for
21:49future directions safety and reliability
21:52I'm thinking on a smaller scale than
21:55Richard has got it probably doesn't
21:56matter to me that my I am session hangs
21:58or if Netscape or Explorer executes an
22:01illegal operation and if my email
22:04happens to be on an IMAP server that has
22:06a backup system I probably don't even
22:07care if my email client unexpectedly
22:10quits but I get a little more anxious
22:12when my quick and our TurboTax crash I
22:15know they have a reputation they wrote
22:17all my data out to disk but when I start
22:20the program back up and I see my
22:22database being reindex t' or when my
22:25historical stock data disappears or when
22:28my memorize transactions show up in the
22:30category i don't remember giving them I
22:32start to get worried safety and
22:36reliability are boring I guess they must
22:38not sell well because all the successful
22:40products don't seem to have going back
22:47to my guiding philosophy lacking safety
22:49and reliability costs people cycles if I
22:51have to re-enter my quicken data or
22:53rewrite my word document or redraw my
22:56illustrator diagram that's a cost I
22:58don't want to absorb what I wonder is
23:01how many of these false lie in the run
23:03time that the application designer had
23:06no control over how many of these faults
23:08are because the application designer
23:10didn't have a reliable automatic memory
23:13management runtime and had to design his
23:15own manual one instead how many of these
23:18faults are because the implementation
23:20language makes the application
23:21programmer declare types left and right
23:24and then permits an on type save value
23:27to be passed as an argument or assigned
23:29to one of these variables I'd like to
23:32see more research into correctness and
23:35reliability it's been happening since
23:37sixties seventies and I still don't see
23:40it in commercial products
23:44well people always ask me about special
23:46purpose hardware so I think I'd better
23:48answer that now that it takes more money
23:52to successfully introduced a new
23:55microprocessor than it does to send five
23:57people to Mars safely home again the
24:00answer seems like no but I wonder if the
24:03answer box change in another decade
24:05especially now that Intel is halfway
24:07down the road of destroying themselves
24:09as opportunities could open up but what
24:13I really wanted to talk about is as an
24:15open problem that maybe grad students
24:17can actually do something about we used
24:21to optimize for CPU cycles when we were
24:23optimizing performance and you know I
24:25agree with both Tucker and Kim sometimes
24:27you shouldn't optimize performance and
24:29sometimes you should and when you should
24:31CPU cycles don't matter so much anymore
24:33because today's hardware is so
24:35unbalanced with the CPU so much faster
24:38than everything else you know for
24:40performance in most applications other
24:43than digital signal processing memory
24:45latency is king and anything you can do
24:48to improve memory latency or work around
24:50memory latency to improve locality
24:53without the programmer having to do a
24:55lot of work to make memory references
24:59more predictable in a way that whatever
25:01Hardware you're using can actually take
25:04advantage of that is where there's a lot
25:07of leverage in low-level performance and
25:09that's where
25:12although I don't have specific
25:13suggestions it seems to me that's where
25:15language design and runtime design can
25:18actually contribute can I add something
25:21to what I said Tucker and I keep talking
25:23about this and have for the last couple
25:25of years I think there's an open
25:27question which is are you better off to
25:30add on what Dave is saying are you
25:32better off compiling to something that's
25:35actually executed as a virtual machine
25:37or are you better off compiling to the
25:39native instructions of the machine
25:41there's a lot of evidence that suggests
25:44you can actually get much better memory
25:45locality if you're actually executing
25:47stuff out of virtual machine but on the
25:50other hand when you get to say tight
25:53loops well you're not doing as well so I
25:57think there's some very interesting
25:58compiler research to be done in the area
26:00of how to get the balance between doing
26:03virtual machine execution and directly
26:05compiled code my my intuition is is that
26:09is that except for very small regions of
26:13code that emulators in today's
26:15architectures will run better than the
26:17natively compiled code so there's my
26:20harebrained prediction
26:23okay we're gonna move on to little known
26:26secrets that you all been sitting on
26:32I'll start with cam well it doesn't I
26:39don't think it's little-known but it
26:40certainly seems to be less widely used
26:43than or surprisingly underused tomorrow
26:46in my experience is writing
26:49special-purpose code generators yeah
26:53don't write you know define a nice
26:56little declarative special-purpose
26:58language and then write a code generator
27:00for it that way when assumptions about
27:04the underlying architecture change or
27:07the requirements of program change it's
27:10easy to retarget your little code
27:12generator and it's a lot easier than
27:16rewriting all of the generated code by
27:19from scratch
27:21that's just separation of policy of
27:23mechanism which I was talking this room
27:25about 25 years ago
27:28do you generate against expressions here
27:30machine I don't care
27:33see assembly you know generate a C file
27:37and run it through a C compiler generate
27:39the machine you know machine
27:42instructions generate s expressions
27:45whatever is the thing that you need to
27:48have the program written in you know
27:51sort of somewhere further down the line
27:55I've got programs that right for the
27:58right other programs in several
28:00different languages simultaneously
28:01because they you have you know three
28:04programs that need to be sort of
28:07interconnected and kept in sync you know
28:09like a communication protocol between
28:11two processors where you need the data
28:14types to all line up and match up
28:15properly it's way easier to do that by
28:19having one declaration and then a code
28:22generator that generates all the pieces
28:26good Tucker
28:32I wrote something a little more
28:35generally I took a quote from this guy
28:37Earl of Chesterfield who said whatever's
28:39worth doing at all is worth doing well
28:41and I take that as meaning you don't
28:44have to spend a lot of time and not that
28:47you have to spend a lot of time creating
28:48a one-off solution but it means you
28:50should do it well enough that your
28:52efforts can be repaid by subsequent
28:55users a solution that is done well will
28:58get reused it benefits from the use
29:00testing and the longevity potentially
29:03causes it to become polished and refined
29:06when the ultimate extension of this idea
29:08is open source and it's too bad that we
29:13don't have just open source to me the
29:15power of the of Lisp and the lists
29:17machines there's a lot of research that
29:19was done there a lot of secrets that are
29:22still secret they probably are going to
29:25be lost because of proprietary interests
29:28it's unfortunate that that's the case
29:30and flip back to the previous topic I
29:33think a great thing for future research
29:36is to figure out how can we have open
29:38source so we can all profit from each
29:40other's efforts and we still make enough
29:42money to feed ourselves
29:47Dave let me tell you about one sort of
29:52low-level thing people may tell you that
29:55if you want see Here I am talking about
29:57performance again but tough I'm a
29:59performance guy that's not always what
30:01matters these days don't let people tell
30:04you that if you want fast arithmetic you
30:07have to be C and/or for trying to get
30:09the wrong answer quickly it's not that
30:13hard to have a languages semantics is
30:18mathematical accuracy up until you run
30:20out of memory and recognize when you can
30:23compile it as machine arithmetic the
30:25clue the key to that is type inference
30:28and range inference in the compiler and
30:31I'll see if I can give you a 30 second
30:33example suppose you have you know a for
30:37statement or whatever it's called in a
30:38particular language iterating over an
30:41array so the subscript I goes from 0 by
30:441 what you terminate when it's no longer
30:48less than the length of the array with
30:50no declarations at all right away you
30:52know that I is either 0 or I plus 1 so
30:57if you can solve that recursive type
30:58equation and your compiler then you know
31:00that I is a non-negative
31:02and you also know that I is either zero
31:06or it's a value less than the length of
31:09the array plus one so if you can
31:12propagate the sub range restrictions
31:14that come from conditionals then you
31:17know that the value of I is not larger
31:19than the length of the array actually in
31:22your compiler you probably know it's
31:23less than the length of the array plus
31:25one so if you have if so if the only
31:28declaration in the entire program is
31:30what the length function returns then
31:33you know that I is an integer in the
31:36range between zero and that and that
31:39allows the compiler to choose a suitable
31:41representation such as the hardware
31:44support at 32-bit integers so with no
31:46declarations to go wrong and no untyped
31:49casts or any other of that junk the
31:52compiler can take the abstract
31:54mathematically accurate formulation of
31:58the program and get the same machine
32:00code that C would generate now that
32:02doesn't work in all cases but it works
32:04in a lot of cases and I think that's a
32:06good example of keeping things simple by
32:09putting the smarts in the right place
32:12and you've saved a lot of people's
32:14cycles pitcher dirty little-known
32:23secrets out there I don't think I know
32:25them what I have what I do know I've
32:31tried fairly like some extent to get you
32:34everybody can find out about I don't
32:36have anything moment what what I do come
32:40up with thinking about this of course is
32:43all going to be here is to look at the
32:50programs writing programs and programs
32:52learning programs and so specifically
32:55for one time things don't don't write
32:58long times steal them like instead of
33:01instead of coming up with a run time you
33:04write a piece of code that generates
33:05something just translate whatever you
33:07want into some other language and then
33:08use somebody else's wrong time well
33:10alternatively if you are gonna write a
33:12long time
33:13what about write a run time for
33:15something which is already out there so
33:18that people will then you know your long
33:21time will get out there it'll get any
33:22people will use it and because of you
33:25for programming languages that work as
33:28as protocols few of these that means
33:32like PostScript see is now half a
33:36programming language have a protocol I
33:38suspect that most C programs now these
33:40are probably written by others super by
33:41other programs by looking at programming
33:46languages that way we do get this you do
33:49get this kind of multiplicative effect
33:51because people use the language because
33:54they're interested servers it's easier
33:55like clients so if the clients existing
33:57people go out there and write the
33:58service
34:00and so in this way has that one is that
34:04can minimize your work they also can
34:07maximize the utility of your work by
34:10making it possible for other people to
34:12use what you do in whatever in their own
34:14environment but I'm not sure I don't
34:17think that's a secret
34:20it's got okay this isn't this isn't a
34:22secret this is just gonna sound make me
34:24sound like an old fart so the thing the
34:27maybe it is a secret you have to
34:29recognize that this whole this whole
34:32discipline is a craft and that if you
34:35look at any sort of pre-industrial age
34:37craft there's a path to mastering a
34:40craft and that involves you know being
34:44an apprentice learning the skills you
34:46need for the craft and then being a
34:48journeyman well what does that mean you
34:50know in in our in our profession that
34:52means finding the code of people who are
34:55really great and just reading the hell
34:56out of it and figuring out what they
34:58figured out you know stand on people's
35:01shoulders and you know and becoming
35:06masterful at any craft as as a mentor
35:09when she told me you know it just
35:10requires character and discipline and
35:14now I have to tell a Dave moons story
35:16because I didn't actually know this a
35:18long time ago one time I presented this
35:20sign this is before I even do a
35:21character discipline where I don't know
35:23if I've got there yet but but I know I
35:25wasn't there then because I was in a
35:28design meeting for something and I
35:30defended my design and the basis that I
35:32implemented over the weekend and moon
35:34said to me the best put-down ever any
35:37bozo can write code was how he debunked
35:41my design of course I was too pissed off
35:44at the time to actually recognize that
35:46was the best piece of advice I ever got
35:48in my life so now now it's great because
35:53even if you forgot it I didn't and I
35:56thought I pass it on
35:59it didn't really come from you know it
36:02really came from you and I felt well and
36:08truly criticized and so that's the
36:11suggestion that we should have programs
36:13to write our code for yeah I might still
36:23be a bozo but at least okay we're gonna
36:29move on to question number four good
36:32ideas they've been dropped but whose
36:33time has now come and we'll start back
36:37with Dave okay I didn't like the
36:42question very much so I don't know if
36:43this answer is responsive to the
36:45question or not okay I'll talk about
36:48trends in the old days the goal was
36:52efficiency at any cost
36:54and we had languages like C and Fortran
36:57that made you basically decide what
36:59assembly language you wanted except for
37:01a few minor details and then write code
37:05that would cause the compiler to
37:06generate that assembly language
37:09now say in the decade that we're in the
37:12middle of or maybe I don't know if the
37:16periods of exactly decades doesn't
37:18matter in the current Europe the goal is
37:20rapid development maybe that era
37:23actually ended with the stock market
37:24crash it's a little hard to tell you
37:29whether it's hard but the goal is rapid
37:31development so we have things to
37:33facilitate that automatic memory
37:34management extensive runtime checking
37:37and most importantly very large
37:39libraries and that's characteristic
37:41languages like Java and visual basic
37:44common les was kind of ahead of its time
37:46there except the library was way too
37:48small as is obvious if you look at the
37:51Java library you know that doesn't just
37:54didn't cover very much but I think the
37:57trends that is coming and maybe is
38:00starting to arrive again you know it
38:02takes hindsight to know exactly when
38:04these things happen the trend is that
38:06efficiency at any cost is only important
38:10for a few specialized than was written
38:12by a few wizards
38:14right inside your cell phone or
38:16something and rapid development in
38:18itself is just rapid production of
38:20headaches and unmaintainable garbage
38:23well what it's really going to be the
38:26thing that everyone realizes they need
38:28is maintainability and transparency of
38:31software you know the opposite of
38:34spaghetti code I don't I can't tell you
38:38what technologies will give us that
38:39maybe you can tell me the obvious one is
38:42non-textual programming you know
38:44programming in visual form instead of
38:47text but that's been tried over and over
38:49for probably 40 years and has never
38:52worked except in very specialized
38:55areas but maybe that doesn't mean it's a
38:59bad idea maybe it just wasn't done the
39:01right way or something anyway I think
39:02that if you're looking for something to
39:05work on that will become they will hook
39:08into the thought trend in a few years
39:10that might be a good bet maintainability
39:13and transparency the ability to produce
39:15software which naturally and easily
39:18comes out maintainable and transfer
39:22that's all I have to say yeah Tucker I'm
39:27gonna go back to the topic Dave touched
39:29on which is a specialized hardware we
39:31were all taught and never happened but I
39:33I think it is going to happen and I
39:36think there's a number of ideas that
39:39lists and lists machines had that we're
39:42going to see come back and be able to re
39:45exploit the three that I wrote down is
39:47garbage collection tag memory and micro
39:49programming
39:50I wrote a slide on each but I'm just
39:52going to quickly try and skip to two the
39:58one that I think is maybe the most
40:00interesting which is the idea of micro
40:02programming and I'm just going to give a
40:04quote that I that Dave Unger
40:07made sort of off-the-cuff a few years
40:09ago it was like I said and this echoes
40:12something that they've said modern
40:14processors are like nitro fueled funny
40:16cars the excel at the quarter-mile
40:18unfortunately modern programming
40:20languages are like Monte Carlo they're
40:21full of twists and turns and if you look
40:26at the memory hierarchy which they've
40:27also alluded to and you look at the the
40:31ratio of how many registers you have
40:33versus how many bits you can store on
40:36your hard drive and the speed of those
40:38registers and the speed of getting those
40:40bits off the hard drive there's I'm
40:43estimating probably six orders of
40:45magnitude difference between the two of
40:47them and I just sort of looked at what
40:50was on my hard drive today and I will
40:52admit most of it was full of mp3's
40:56followed by a lot of JPEGs from my new
40:58digital camera but the thing after that
41:01was code and the mp3s have a nice
41:04compression algorithm and so do the
41:06JPEGs what's the compression algorithm
41:08for code I think it's micro program
41:14yeah well what you're actually saying is
41:18sort of what Scott said earlier virtual
41:23machine you talk about yeah modern
41:31programming modern processors at the
41:34assembly language layer looks a lot like
41:37what I remember doing microcode must
41:40look like you have many of the same
41:42kinds of issues and maybe that's maybe
41:48that is where things are going
41:54that this sort of addresses Dave's point
41:58but I think one of the things so I guess
42:03this is good ideas who you know that
42:05have been dropped but whose time is with
42:07us again so I'll try to I actually tried
42:09to answer some of that and you know one
42:11of the observation is is that you know
42:13the the arrow we're in right now like it
42:15or not is the Java era I guess you could
42:18tell what I think about that no offense
42:25and the fact is is is for what it is
42:29Java isn't bad and it learns some good
42:32lessons right it learned it learned
42:34lessons about sort of late binding and
42:36it learned lessons about you know the
42:38importance of things like like safety
42:40you know type safety and didn't quite
42:43get it right but it got some of those
42:44garbage collectors
42:46garbage collection interactive
42:47development environments and in fact the
42:51dynamic language community you know that
42:53I'm part of is actually taken some
42:55lessons back from the static language
42:57community and languages like sessile and
42:59Dylan are good examples of that it's
43:02time it's it's time to figure out how to
43:06push the static language community to
43:07steal some more ideas because that's
43:09what masterful people do anyway or I
43:11think they steal ideas and you know a
43:14good idea that isn't the parent in Java
43:17is that classes aren't namespaces right
43:19that's a that's a that's a spaghetti
43:22disaster organizing interfaces around
43:26interfaces or collections of functions
43:28so why isn't code organized around
43:31functions you know why why is code in
43:33Java organized around the abstraction of
43:36a class rather than the abstraction of a
43:39generic function it's time to go back
43:40for that and then the big one
43:42oops my screen just went blank so I'll
43:45have to admit I don't know I can
43:46remember this one syntactic abstraction
43:48is the key
43:49reducing the complexity of code and
43:53nobody has caught on - nobody's caught
43:56on - hygienic macros and it's it's time
44:00for that to change it's super important
44:04I I mean I I can't say anything about
44:07the implementation technology that I'm
44:09using at my company or else someone
44:11would shoot me but in in one language
44:14where so I have some apples to apples
44:17comparison that showing an expansion of
44:20code of 24x for the same code between
44:24between some other language in Java and
44:27I'll tell you that was that's my
44:31worst-case nightmare scenario was an
44:33explosion of 10x so I wasn't even close
44:36and it's all due to the syntactic
44:39abstraction that this other language
44:41provides it's not assembly language it's
44:46not that kind of macros um the other
44:48thing which anyone who knows me is one
44:50of my pet things is is it's time to
44:53think about the the application of types
44:57to to the interfaces of programs
45:01especially in this client-server
45:03relationship we now have we're you know
45:06we're back to the IBM model you know
45:08where you've got a you know you've got a
45:10card bunch on your on your machine at
45:12home it just has a return key instead of
45:15a you know an enter button then you know
45:17a packet goes out instead of a punch
45:18card and that just means that getting
45:22talking about types across the network
45:24in a way that both of those expensive
45:27pieces of hardware that you have can do
45:29something useful
45:30oh and the idea that came from with
45:33coelom and dynamic windows before that
45:36so that's an idea that's been around for
45:38oh I guess in the sicker Ali's paper for
45:4020 years now
45:47I strongly mention that i I have caught
45:49on to hygienic macros so somebody has
45:55but even sort of a big IBM systems what
46:01see what the thought thing that I picked
46:03up on is a good idea this time as has
46:05come back is time sharing and used to be
46:10computers these big expensive things and
46:12because of that you had to share them
46:14other people and a whole lot of work
46:16went into setting them up so that people
46:19could share them without stepping on
46:20each other too much or getting into too
46:22much trouble and the computers going
46:25cheap and everybody can have their own
46:27and nobody paid attention to anymore
46:29so now have these computers whether is
46:33essentially whatever program you want
46:35and it can do whatever it wants
46:38somebody's talking to is it
46:42we're affordably formatting the hard
46:43drive is a right good virus thing yeah
46:54so and it's - now that leaves are so
46:57cheap so in fact you are the only person
46:59sitting at the computer but because that
47:00computer is you know either probably
47:03connected to a network and even if it's
47:05not that it's running a lot of programs
47:07written by other people and so you start
47:09something and it starts something else
47:11and it starts something else so inside
47:12there's this all these different
47:14programs running on your machine some
47:15which you probably didn't know about so
47:18it is turned back into a multi-user
47:20machine
47:21and so we need to go back to the dealing
47:26with it as a multi-user machine and - so
47:29the different programs can run and not
47:31step on each other now I'm not
47:33suggesting that we just go back and take
47:34out yes and depending on machines
47:36nowadays because but you do need some
47:46these programs have to be able to run
47:47with each other and they need to protect
47:49themselves from each other and the
47:53operating systems available today aren't
47:55going to help very much since they
47:57either never heard of protection or are
47:58still using protection from 1960 and it
48:03really took so really it turns into a
48:05language level issue and I think you can
48:08solve much better from the language in
48:10the language level using techniques that
48:14have been around for for a long time
48:15that I are coming back it's abusive and
48:19kind of useful so I guess the one that
48:22I've been looking at recently as
48:24capabilities which in
48:29and the area I work in so that comes to
48:32becomes lambda the ultimate security
48:34tool pretty good that's the idea whose
48:51time has come back is in sitting time
48:53sharing and all the solutions and clubs
48:58that come
49:00okay we're moving on to question five
49:04pitfalls of gotchas and then your time
49:07has come again Ritchie
49:14right so if I actually brought down a
49:17whole bunch of things here and I was
49:19thinking great if they come this way I'm
49:20one of these one of the mentioned before
49:23let's start at this end good I only have
49:25one thing which is as a pitfall it's the
49:32but I've got written down there's the
49:34myth of the small language and he's from
49:40the scheme community right all of these
49:45is always these languages out there and
49:47I'm just languages but sort of protocols
49:50and all these things and if I guess
49:52comes back to where this sort of been
49:54talking about throughout this and that
49:57is that nothing to sitting on summation
49:59on the bar so if you write a small
50:02language then either it just disappears
50:05that doesn't matter or if people
50:08actually start using it for something
50:10then it's slowly going to build up
50:12people are going to write more programs
50:13in it they're going to use it for things
50:14you didn't think of they're going to try
50:16and connect it to other programs to
50:18other protocols and different ways and
50:20so it goes and the crosnes grows so
50:23initially you thought your little
50:24language as well people just write small
50:26programs right I don't need main space
50:28control right and then then you see the
50:31first 10,000 line program in this baby
50:33oh my god how could they do that
50:35so so you really have to think about you
50:39know even as you know scheme is a small
50:42language say but but even as a small
50:45language to be useful and to and if it
50:50if it succeeds and gets widely used it
50:52will be a big language so you have to
50:55start right from the it to something
50:56beginning thinking about as a big
50:58language including the kinds of features
51:00that big languages use and also is a
51:02library right there's all kinds of other
51:05pieces of software and equipment and
51:07whatnot people getting more connected so
51:09they need that they need to be able to
51:11do that because if you don't put it in
51:13they will so you have to you have to
51:17think big and one way to do this is to
51:20you know piggyback on top of other
51:22you translate into other languages then
51:25you can take advantage of but they've
51:26done in terms of interfacing and in
51:28solving these same problems but you have
51:31to think about them they can't just sit
51:32down and write a small language in
51:37scott-young with him ignoring
51:41scalability is a pitfall you just even
51:45when you're keeping things simple you
51:47have to make sure you're not painting
51:48yourself into a corner and yeah well I
51:55guess the other thing is what they've
51:56said right at the beginning which is you
51:58know thinking that you're smarter than
52:00you actually are and you know maybe
52:03everybody is like SuperDuper smart but
52:06the fact is is you know after you've
52:08written something and are suddenly
52:09forced to come back to it a year later
52:11you know even if you were that smart at
52:14the time
52:14you aren't now so that's yeah yeah I
52:21mean the PIP maybe it there's just a big
52:24pitfall is that this is just really hard
52:26stuff and not realizing that it's really
52:29hard this is a huge mistake
52:34yeah I didn't really come up with
52:37anything here because there are so many
52:40small choice you know small things that
52:42just kill you all left and right and
52:50but so many of them just come down to
52:55abstraction violations not using good
52:58abstractions and that will haunt me
53:05Tucker
53:07keeping with my theme that I'm only a
53:10journeyman not a wizard I came up with a
53:13bunch of quotes from some real wizards
53:16but I'm just gonna read my favorite one
53:19which is from Michael Jackson the rules
53:21of optimization rule number one don't do
53:24it rule number two which is for experts
53:29only don't do it yet Dave that's all
53:40looking over my list of pitfalls of
53:43gotchas here none of them is actually a
53:44pitch a pitfall or a gotcha so I'll give
53:48you one pitfall / gotcha from my current
53:51work and they'll go over what I have
53:54prepared if you're using C++ and you
53:59want to write portable code don't use
54:00any of the features of C++ because none
54:03of them work at all compilers and for
54:08wizards don't you see I said some some
54:16advice it's not really specific pitfalls
54:18again keep things as simple as you can
54:22but not simply work really really hard
54:23up front to make things simple when
54:28you're done making your design simple
54:31and you're going to actually implement
54:32something start with a small working
54:36system and expanded incrementally adding
54:39functionality
54:40adding performance it's much easier to
54:43do it that way the big bang way only
54:45works for God everybody else has to use
54:49evolution related to that one of the
55:01most boring things to do in the entire
55:03world is writing test Suites but it's
55:07really really worthwhile to do if you
55:10have test Suites and unit tests that is
55:13both tests of a large functionality and
55:15tests of the pieces you and they have
55:18good coverage you can make changes with
55:22some confidence that that if they're
55:23wrong you'll find out about it fast
55:25which gives you a lot more freedom to
55:27make small changes and experimenting
55:29with things and finally one piece of
55:31advice which I shouldn't have to say but
55:33I keep having to say this over and over
55:35sometimes an error message actually
55:37means exactly what it says and in your
55:42own code you should strive to increase
55:44the number of such error message
55:48what's all I have to say thanks ok we're
55:51going to open it up to questions and
55:53we're gonna give priority student grad
55:56students and particularly grad students
55:59in our class we
56:03you have a mic here should work pick you
56:06up if you want to stand up first
56:11who wants to go first
56:15I just have a quick question for
56:16something that Scott said you were
56:18saying that you were concerned about
56:20Java being a language where the central
56:25focus should be on the function and yet
56:26all the file systems are being done
56:28based on the class when you say Java
56:31might be an example of you know a
56:32language which is trying to focus on the
56:34class rather than being a function and
56:37in that case wouldn't it make more sense
56:38to Pridgen to actually be that way um
56:41Mike I guess I think that if it might
56:46want to focus on that and and I don't
56:48know the evolution of Java from from day
56:51zero so it's really hard to it's I guess
56:55that's another pitfall is
56:56second-guessing right I'll try I'll try
56:59not to do it but but you could argue
57:01that for instance the genesis of that
57:03came from the maybe you can correct
57:05justice when you're trying to download
57:06something over the network a class is a
57:08pretty good modularity of something
57:10you're going to slurp up over the
57:11network especially when you equate file
57:14and class but on the other hand when
57:16you're really decomposing something into
57:18into the natural functions of the
57:21protocol they don't always lie along
57:23class boundaries for instance and you
57:26don't have to look very far in Java to
57:28see where it just starts to fall down
57:29right I mean the math library was put in
57:32very early for example and and it and I
57:35mean it must have been one of the very
57:37first extra libraries and that model had
57:39already started to break down by the
57:41time they got that far and particularly
57:44in the face of you know multi-method
57:47salih C loss or Dylan or sessile you
57:50know where does something live right you
57:52just can't think about it that way and I
57:54think it's you know I you know I don't
57:57think multi methods are a good thing
57:58just because I happen to come from that
58:00community it's just sort of the way it's
58:02just the way functions work that's what
58:04they do for a living
58:06so did that answer your question okay
58:15uh-huh let me give the God since don't
58:19be shy
58:23for whoever is interested in answering
58:27this so a lot of theoretical work has
58:31been done on various types of program
58:34analysis and you know that analysis of
58:37properties of functions and procedures
58:40and variables and things like that and
58:42in a few cases those types of analysis
58:45have gotten into languages in
58:48semantically interesting ways like for
58:50example the whole chapter of the java
58:52spec is is on this concept of definite
58:55assignment and that turns it turns into
58:57a useful semantic property that you can
59:00rely on in your programs and and you
59:02know you can envision tons of other
59:04properties like that that could that the
59:07language could semantically help you out
59:09on I don't I don't see many of those
59:11actually appearing in language is why do
59:14you think that is and do you think it's
59:16something that like needs to be worked
59:19on how do you think you know that could
59:21be addressed but like things like for
59:23storage allocation you know all kinds of
59:27other properties that you know you can
59:29make improvements on that way
59:33probably more than one of us should
59:35answer at home my take is most language
59:38designers or not intellectuals that
59:39they're not really as interested in
59:42thinking you might hope they just want
59:46to get some language done and start
59:47using it and so stuff like that is art
59:50and so it tends to get dropped because
59:52it's too hard to do a good job on um
59:55that comes out of some some of my
59:59language design experience would support
60:01that I do think that there could be some
60:03value in getting more semantics of the
60:06program you know written down in the
60:08program I don't like the example you
60:10gave from Java because I think that's
60:12just trying to paper over a defect in
60:15the language but your general point I
60:18think is valid I think part of the issue
60:22there is that they're taking a good idea
60:28and turning it into an implementation is
60:32a lot of work in a very often there's a
60:36lot of grungy details and very often you
60:44know the people who are going to have to
60:46deal with those grungy details are you
60:49know their salaries are being paid by
60:52somebody who you know once results
60:54yesterday and so it's really hard to
60:58find the time to work through something
61:03sort of interesting at that level and
61:06turn it into a real useable thing in a
61:10product the guy who wants the result
61:12yesterday being aided by a consumer who
61:14thinks
61:15okay if his program unexpectedly quits
61:18right just not cool off the other thing
61:21is when you look at examples of
61:22languages that have really tried to do
61:24it right like you're surely thinking
61:25like ml or Haskell or something like
61:27that is it turns out that I mean they're
61:32just really really hard right it's just
61:35really I think those things end up just
61:37being very very difficult if you improve
61:39me impossible
61:41yeah and and the other thing is if you
61:43look at like ml for instance you know
61:45one of the things they've done is to is
61:48to really in order to have a reasonably
61:52complete type system they've had to sort
61:55of will sell consistent I guess they've
61:57had to really you know lop off stuff
62:00that is just pragmatically useful you
62:03know so on the 1 maybe it's a difference
62:05between science and engineering too
62:06isn't it because ml or Billy you know ml
62:09was sort of done as as a piece of
62:11science and well you know Common Lisp
62:14for example is a piece of engineering
62:16right it's there are very different kind
62:18of trade-offs there
62:21yeah a good tough question yeah yeah
62:28yeah I
62:30I see you next Valley
62:32as the added complexity and potential of
62:34an efficiency of multi methods works
62:36reports to gain a critic might say that
62:39it's pretty heavyweight solution to the
62:40binary operation problem
62:47that arose from my point of view when
62:50less people cycles involved in the guy
62:52writing the multi bathroom and I mean
62:55there are a dozen people in the room who
62:57could probably answer that question but
63:00the fact is is in the face of in the
63:02face of good typing information either
63:05declared or inferred and in the face of
63:08a reasonable library compilation month
63:11model there just isn't any of difference
63:13in efficiency and in fact if you end up
63:15having to do sort of staged single
63:17dispatch you get hosts because when it
63:20comes time to sort of do you know share
63:22registers and information across the
63:24stage thing the multi methods stuff all
63:27gets packaged into a neat little thing
63:28and just does much better anyway you
63:32know go talk go talk to Jonathan about
63:34all of this he can he can probably
63:36repute you point by point for four hours
63:46techniques interpretive program so I'm
63:50wondering what you guys think about sort
63:52of whether it's whether all their hand
63:55generator automated proof techniques
63:57when you're writing program Isis is in
63:59any way feasible but whether you think
64:02an increase whether you think it's worth
64:04like being able writing a program in
64:06which you can express more complicated
64:08properties than just normal type systems
64:10that you know have people in mine and
64:11and whether that's useful
64:18proving program correctness would be a
64:20great idea I've never seen it work but
64:22I've never really tried to look for it I
64:26think I think I'm saying that I'm
64:29ignorant
64:34I'd say that I'm encouraged by the fact
64:40that type systems seem to have gotten
64:42better and that there is real utility
64:46there some of the there are syntactic
64:52issues in some languages that make the
64:56make dealing with types clumsy but those
65:00are you know more syntactic issues then
65:02and than anything else and there is
65:07useful stuff that comes out of it so I'm
65:11encouraged by that you know that the
65:13formalisms for type systems have I think
65:16improved our lives but how much further
65:21we can go I don't know that I probably
65:25claim ignorance like Dave that's not an
65:27area that I've studied very much I'm an
65:31ignorant of current progress in it but I
65:34know twenty thirty years ago in the
65:37security business they were trying to do
65:39program proof automated program proof
65:42there was some success there and I know
65:45that that effort continues
65:49and it's obviously it would be a great
65:52thing if you could know that your
65:53program is really gonna do what you
65:55wanted it to do but I know that it's
65:57still an area of research I think that
66:00it's a largely a trade-off issue in the
66:02sense that you know producing correct
66:05programs it's more working this in
66:07correct programs and so there are
66:12programs you know large programs with
66:14people have proven correct for this
66:15Harley what that means is you can
66:18correct the courage to some
66:19specification than is the specification
66:21like specification so it has a never it
66:25never actually bottoms out and you said
66:27you know I had true theory but it just
66:32read it increases the cost of the
66:34program and so if it's in an environment
66:35where that really matters then it has
66:41been some success for that but there's
66:42also been success with just paying a lot
66:45of people and setting up an
66:46institutional structure to produce
66:49correct programs as well so obviously
66:52you know the more you can automate the
66:54cheaper it's going to be to do it but
66:56ultimately it's always going to be
66:58easier to write it's getting cheaper to
67:01produce
67:01corrects but not proven correct programs
67:07sometimes it's harder to get things done
67:09correctly can I ask a question back is
67:13there sort of sort of a statistical
67:15notion of proving something correct that
67:17is to say if you have something that
67:19obeys a set of you know some set of
67:23protocols and you can actually you know
67:26found the inputs then you just start to
67:29start firing dot darts at it and see if
67:31it actually is best to say is it enough
67:34to actually so I'm thinking of sort of
67:36security of just not downloading viruses
67:39and whatnot here you can see with
67:40something that would actually that would
67:43actually give you a reason this thing
67:46with reasonable probability does what it
67:48says it's going to do as opposed to this
67:50thing absolutely positively provably
67:51does what's going to do yeah I mean it
67:55has to be a really big search space
67:59is highly kind of talked about I guess I
68:02could be sort of considered
68:05system at least you know increasing your
68:08faith in the rivals reliability
68:12you can tell I'm ignorant just seems
68:15really hard and really valuable perhaps
68:18an alternative to correctness is
68:20accountability
68:25there's a there's a bunch of factors
68:27that conspired to make
68:30hard to use like a lot of documentation
68:34rely on some really complicated of
68:36stretches wondering what your peeps are
68:39different these are things that make
68:42language
68:45and what you take things I want to do to
68:48make the music
68:51my pet peeve is any language that makes
68:53me type something twice when I didn't
68:55when I shouldn't have had to yeah like
68:58the same type like declaration over and
69:00over one another is languages where they
69:05have a lot of things in them not almost
69:06but not quite work that definitely
69:13contributes to usability and and the one
69:16you mentioned is very important for
69:18documentation
69:23being based on weird ideas that I don't
69:26understand it makes it hard to use for
69:30me and it's not easy to tell whether
69:32that's a problem with me or with the
69:34language
69:37and having weird syntax not to mention
69:41any particular scripting languages or
69:43anything weird syntax aware of or even
69:51like the same thing 17 different ways
69:53yeah we're we're small changes in the
69:55input do not produce errors but produce
69:58wildly different changes in the output
70:04yeah I think it's you know having 27
70:11different ways to do the same thing
70:13except slightly different you know with
70:16say wildly different efficiency models
70:18and the other thing is you know I guess
70:20this is a maple for everybody who worked
70:22on common lisp is sort of failure to to
70:26draw modularity boundaries between
70:28things I think we really blew it we
70:31didn't know it at the time but I think
70:32we blew it and Common Lisp when we just
70:34made this big ol fat manual instead of a
70:36bunch of little skinny ones that you
70:38could all put on a on a shelf next to
70:40each other
70:41so um Java learned that lesson pretty
70:44well actually they yeah they're really
70:46good
70:51no but the point is is the point is you
70:53can get one book that talks about one
70:55thing yeah I think there's a lot to be
70:57said for that yeah
71:02it's a goldmine for a language what kind
71:08of real-time claims and runtime systems
71:12make with all the scheduling and garbage
71:14place
71:20for us to decide
71:24well garbage collection I think can be
71:29dealt with in a real-time system I have
71:32personal evidence of that I I have a
71:38garbage collector that's been 800 feet
71:40into an oil well yes and it's planning
71:47we're planning on sending it down
71:49several miles in a couple months it's
71:58obviously more rigorous than having it
72:00in the competition maybe so one of the
72:03last things Symbolics did was to to
72:05write a version of general called minima
72:09that actually had a that was well it's
72:14it's real time on sort of the
72:17millisecond scale right which actually
72:19had boundaries on the amount of time you
72:21would spend in garbage collection and
72:23whatnot it was meant to actually run
72:25inside a phone switch and harlequin one
72:27up women made one they actually did it
72:29well yeah and then heart and then
72:31Harlequin actually did the same thing
72:32basically in PCs right and I mean it it
72:36sort of passed all of the you know even
72:39with garbage collection it you know did
72:41everything and you know sort of the
72:44millisecond time frame which was
72:45actually the boundary of the
72:48requirements so and that was with you
72:52know machine sir well that was what five
72:55years ago so that was with machines that
72:57were you know twenty times slower than
72:58once Warren and now and the trade-off
73:01was a fixed but bounded cost yeah maybe
73:04a larger cost but it was fixed yeah I
73:07was bounded yes and predictable too are
73:10you going to experience
73:12so definitely at least three existence
73:15proofs of of it working
73:20now
73:36okay we're gonna open it up babe well
73:40that's okay who was asked some of the
73:46stuff that has been talked about is
73:49seems to me to be in the realm of
73:51sufficiently smart compilers and
73:53sufficiently simple abstractions and the
73:57state of the skill of practitioners of
74:02the crap doesn't seem to be able to
74:06support sufficiently simple and elegant
74:08abstractions so the way industry deals
74:13with this is by working on very small
74:15problems and there's a lot of
74:21of advancement not in big big elegant
74:26systems I guess but rather in very small
74:30things that is unspecialized partner
74:33telephones toaster ovens so I'm not sure
74:39what dynamic language is in particularly
74:41dynamic runtimes have to offer in in
74:45this specialized space but what I do
74:48think they have something to offer is in
74:51making these various specialized things
74:54work together where you don't have
74:57control over the abstractions where
75:00you've got a lot of different software
75:02written by different people with
75:03different abstractions it seems to me a
75:05dynamic language and a particular didn't
75:07have a runtime and adapt to that with
75:11any of you like to comment on the
75:15strength of dynamic languages
75:18one times for those two different
75:20purposes
75:23I'd like to interject one comment first
75:26I don't think the you know the canonical
75:32sufficiently smart compiler is the
75:35answer to much of anything when we were
75:38talking about simplicity I at least and
75:40I think most of the other people here
75:41did not mean you know included the
75:45compiler as part of you know keeping
75:48things as simple as you can make them
75:49and still get the job done I think a
75:54good example of that by the way is if
75:57you've never looked at like the gtk+
75:59source code which is just written in C
76:02that's a really great example of
76:04terrific abstraction in in C right it's
76:09just beautifully designed just my hats
76:11off to whoever I don't remember the name
76:14of the authors but it's just great
76:18just see
76:20I also think by the way that given that
76:42you're wizards I'd like to know what
76:46sort of things are part of your daily
76:47practice that you just can never
76:49understand why no one else does test
77:00their code before checking it in explain
77:13what we do yeah yeah I'm serious about
77:19that one actually
77:22that's why I'm only a journeyman I have
77:24checked while Wizards do that - but we
77:30always have a good excuse vacation I
77:37mean I think the most useful practice is
77:41you you know what this old mint are
77:44called character and discipline then
77:45it's just always being skeptical it's
77:48being skeptical you know it's okay to be
77:52skeptical of other people's stuff but
77:54you should be even more skeptical about
77:56your own stuff right you just you just
78:00can't hope to get better at what you're
78:02doing unless you're just really
78:03skeptical about everything so it just
78:07just makes you really insufferable -
78:09unfortunately well going back to your
78:12bozo lesson I guess think of it before I
78:14start writing the code right here it's
78:17often tempting to just start sketching
78:20up some code and before you know it well
78:22that's easier to do that you think about
78:24it - yeah well you you it's okay to
78:27write some code and then think you just
78:28can't leave out the thing Margot yeah
78:30right it's okay to write some code to
78:33organize your ear ideas and then think
78:35and then throw that away and write some
78:37more code right being a being willing to
78:40throw away codes although I have found
78:42that it's unquestionable that all kinds
78:46of computer monitors you met stupid
78:48raise the vanity students and when you
78:50sit in front of them
78:51getting up walking away from it it's
78:53even a liquid crystal yeah even my lcd
78:58Howie I want to pick up a thread that
79:02somebody was just raising which was
79:03invention doing room apparently I the
79:08numbers I've heard from friends of mine
79:09who work in the auto industry is but a
79:11mid-range car right now I something on
79:12you under 30 processors in it that's
79:16going up every year and denying cars are
79:18already about 60 some of those are
79:20reports things that are you know
79:21basically watches some for thick
79:24computers do it's a very specific thing
79:26but a lot of them are actually quite
79:28competent issues the PowerPC for example
79:31and they're doing complicated tasks like
79:33running engines and transmissions in
79:35fact often it's one computer running in
79:38two engine one running two transmission
79:40and beginning to think about them
79:42talking to one another and then at the
79:45far extreme there's the aircraft
79:46industry which is I don't know the
79:47numbers are what they're much larger but
79:49it strikes me that that's a field that
79:51really needs abstraction real bad I've
79:55talked to people who actually do the
79:56programming and it's it's the style of
79:59programming all of us did in our infancy
80:01it's extremely low level you'd see at
80:04the highest levels and the assumption is
80:06that you can keep building complexity at
80:08that level but my take is that in fact
80:11it's a world where of both to sing music
80:14which is a combination of lots of
80:16extremely simple things as an ensemble
80:17and also the internal complexity of
80:20those are growing very quickly and then
80:22it's a field that needs both real-time
80:24demands and high reliability constraints
80:27as provably so and the power of
80:30abstraction so different
80:32I was wonder if you got one comment on
80:34that I'm really frightened about the
80:36idea that I will have a fly-by-wire carb
80:39on Thursday that replies isn't Gregor
80:42kick saw us trying to address this isn't
80:45that what is this aspect stuff is
80:48attempting to do I mean maybe I'm stupid
80:55but I can't actually much see difference
80:57between that sort of well-crafted sets
81:00of macros but but that probably reflects
81:04my appearance more than anything else
81:12a commitment question my comment is that
81:15I can't help wondering whether the
81:17watchword keep it simple is merely the
81:20mantra of an ageing generations and
81:22realizing it's running out of time
81:27exuberantly wasting my time on trying to
81:29conquer complexities in these very walls
81:3125 years ago and I have experience of
81:33not denying that the final question is
81:45what is the panel think of literate
81:47programming is a spouse spied on for
81:50example as a means of enhancing
81:52maintainability and reliability
81:56well that idea is in Java right you can
81:59intermix documentation with code by
82:01itself that's great but by itself it
82:04doesn't do it that much I just done
82:05rather badly involved yeah but if you
82:09look at the source code protect or
82:10something that's it's qualitatively
82:13different than just reading of source
82:14code listening and what everything you
82:15know experience your opinions about that
82:17well for it to work well it requires
82:21writing well and that is unfortunately
82:26something that isn't taught really well
82:32now comments are only we're worth the
82:38the amount of thought that went into
82:40them and unfortunately maintainability
82:46and future you know transfer of
82:49information to the next person who's
82:52going to read the code is not given a
82:55lot of ways in many in many
82:57organizations there are exceptions to
83:01that but
83:05there's a lot of non exceptions
83:10increases right
83:25and it's not a big obstacle but it's an
83:29obstacle to a point so I think it's so
83:38different to find the question is what
83:41kind of comments for canoes I think
83:44there was definitely a sentence which
83:45you did publish a thing as a book I
83:47think an hour even as a book in that
83:48case is simply no short types at all but
84:01I think I think the point about I mean
84:06you put them together for a reason at
84:07the point of having fun and then asking
84:10about literate program are really maybe
84:12in some sense you know the exuberance of
84:15just having fun programming is really
84:17sort of a solo activity right where you
84:19just read something for the sheer
84:20pleasure of doing it because you can do
84:22something complicated and hairy and then
84:24it just magically works and it's great
84:26and that sort of thing and you know we
84:29all have a boundary on exactly how much
84:31code we can write that does so much and
84:34then there's the requirement if you're
84:36saying industry where you where it's
84:38just more than one person can do and
84:42then all of a sudden well you have to
84:45leave back a little bit of that you have
84:47to leave behind some of that exuberance
84:49because you because there are other
84:51people doing it too and you've got a you
84:54know you've got to write stuff that all
84:56of you can do something with and and
84:59it's interesting because I mean in my
85:02experience people people don't even work
85:05to keep comments up-to-date
85:07never mind writing them carefully to
85:09begin with so even though
85:12even though in theory it strikes me as a
85:15great idea I just I'm not sure how you
85:18actually you know culturally get people
85:23to realize that that's what do you do
85:25you take the Dykstra rule right you find
85:28everybody a dollar for every line of
85:30code they write pay them two dollars for
85:32every comment they write or something
85:33like that yeah can I say something more
85:39about literate programming I'm not sure
85:42the novel is really the best model for
85:44how to capture a design I have believed
85:48for a very long time without any
85:49evidence that source code should be part
85:53of just a small part of a vast hypertext
85:57that links the source code to the reason
86:01why things are the way they are I
86:04haven't really seen that implemented but
86:06you should be able to look at any line
86:07of code and say let me find the
86:10discussion that led to this being the
86:12way it is and the design criteria and
86:15the you know the test cases that refute
86:17other ways of doing it and so on of
86:19course that would be a far larger bulk
86:21of information and you could actually
86:23absorb when you're trying to maintain
86:25the probe
86:26it seems like something along that line
86:28where the links between things that
86:31exist at the instant they're created are
86:33not lost to history could be valuable
86:35especially if there's some way to
86:37automatically summarize that vast email
86:41archive
86:44okay yeah more mundane question this
86:50curious feel that source of debugging is
86:53important in designing a language and if
86:55you do how do you use all the tension
86:58between that and also the desirable
87:00features of having code generators
87:01hygienic macros source of generation so
87:06you've got to be smarter than your
87:08source alone with the ronger so that it
87:10can backtrack from all it has to be able
87:15to backtrack all the way from the
87:16machine code bits to the original source
87:20code and everything interesting in
87:21between that's not always easy we never
87:24solved that on the list machine
87:27but that's that's our Delilah we did we
87:31came Closen Harlequin villain but we but
87:35but in effect sort of the rule based
87:38macro stuff makes it easier than list
87:40style macros but even so I think it's
87:44good research project
87:53the worst jobs we have powerful tools
87:55and other
88:01you'll love to talk about when they're
88:03talking about runtimes implicitly here
88:05all talking about you know single
88:07language single application but I know
88:10that some of you are sympathetic to the
88:11idea of object oriented operating
88:13systems do you think you need odd
88:16auditory operating systems to accomplish
88:18some of the goals and things you want
88:21from computer systems and kind of a
88:23separate question do you think you'll
88:24never be able to work on them if you're
88:26interested in that because it seems like
88:28it's right now it's looking pretty dark
88:34I wonder what you mean by
88:36object-oriented operating system well I
88:38mean where the safety of the safety
88:41integrity of the system can take
88:42advantage of all the things that object
88:44or II as opposed to just the application
88:47or process or module or class extend the
88:52benefits of oh we designed down to
88:54dental 'evil the integrity of the system
88:57you know where's was the time right now
89:00we can run in our nice little sand boxes
89:01inside the UNIX or in tea or whatever
89:03but then we're at the mercy of certain
89:07certain limitations and the operating
89:09system you know
89:12that are due to the way that operating
89:14systems at the structure traditionally
89:15know the world is follow an increasing
89:18number of object oriented pieces of
89:20operating systems whether it's
89:21object-oriented api's for device drivers
89:24or application frameworks stuff like
89:27that something where there's the same
89:29object model throughout the operating
89:31system the I don't know if that idea
89:33will come back I'll take you but you can
89:37get a lot of benefit from the pieces can
89:39that's true a different poke at that
89:43idea to me the operating system is where
89:46you put the pieces that are working
89:48right because everybody needs them I
89:50would like to see object-oriented
89:53runtimes migrated into the operating
89:55system in particular garbage collection
89:58because you could do a much better job
89:59if you work closer to the hardware the
90:02garbage collector
90:05and object-oriented it's like a slippery
90:08turret right because yes some people say
90:10oh that means the center of everything
90:12is sort of this class and you go well
90:15are the instances of the class going to
90:17be self-identifying right are they
90:19manifestly type that would be pretty
90:21useful right but yeah I don't want to
90:24get it to particular flavors of object
90:26but but you get the general
90:27self-identifying do mark the construct
90:31that you know to be identified no that's
90:33quite the most general way yeah I'm sort
90:36of would Tucker on that or maybe
90:39everybody it's it would be nice and who
90:41knows I mean at some point for safety
90:44concerns something like that's going to
90:48be inevitable or a world we're all going
90:51to die in horrible accidents work and
90:53you know that kind of stuff right
90:55because the more the more we're
90:57depending on this bird literally our
90:59safety the more we have to start
91:02adopting that that that kind of that set
91:06of ideas the other thing the other
91:08definition of object-oriented of course
91:10is actually sort of you know protocol
91:13oriented right should things just no
91:15babies discrete protocols and you don't
91:17actually need objects for that and might
91:20I mean it strikes me that anything that
91:23more than a few people are working on is
91:25probably designed with that in mind
91:26anyway so
91:28but other tournaments that your new
91:30single is operating system and isn't so
91:33clear always what the operators
91:39supplying working with runtime systems
91:42and seems now more more of what goes
91:45into and this stuff that when years ago
91:47was the operating system just because
91:50you need functionality that the opposite
91:53doesn't arrive to provide that level
91:55even though it's something as
91:57traditional operating systems provide
92:01we had a question
92:03question is there any decent way to do
92:06macros up top as Jonathan yes
92:18next question it's having yes
92:24you're not profile get efficiency do you
92:27put filers a lot
92:30- that kind of design here
92:32I would say that if he don't crow file
92:36you'll be optimizing the wrong things
92:39your intuition is going to be wrong very
92:44often about what where the the the
92:48actual hotspots are I think you have
92:52good intuition that it's not going fast
92:54enough well but finding out well writes
92:59what's so Pro yeah I mean yeah they
93:02modify a lot it's really bad but there
93:05isn't really anything better often it's
93:10a better idea to just add a little
93:11temporary code to information about
93:16where the time is gone at the places in
93:19your program that you think are
93:20interesting get the time and record it
93:22and that may cause you to change what
93:25parts you think are interesting but it
93:27doesn't take very long these days to add
93:29temporary code and recompile and a lot
93:32of times that sort of ad hoc tool is
93:34better than finding some package tool
93:36that doesn't really do it
93:37and for instance if you're hacking like
93:39in the web domain all these web servers
93:41are just dynamically loading stuff and
93:43blah blah you can't even you can't even
93:46get a profiler around the code that
93:49we're trying to profile so it's pretty
93:52painful of course the problem with
93:55profiling is
93:58problem that you want to profile your
94:00dataset or your employee all right
94:02there's no sense in profiling a
94:04benchmark that doesn't it all resemble
94:06what your product is actually being used
94:08for
94:09that's
94:11exactly
94:15Scott mentioned that we should read the
94:17hell out of code I've read some of your
94:20guys code but what should I be reading
94:22today
94:28no the classics are the latest stuff
94:32yeah yeah tough to tell some of it
94:37you're still not allowed to read
94:39yeah unfortunately yeah
94:44you know I actually think that the you
94:47know download you know download when I
94:49was doing read that code it's there's
94:51some pretty good stuff in there
94:53what does that open source some of it
94:56some of its openers but there's a lot of
94:59it where the source is publish it's not
95:01that is to say it's not under sort of an
95:03open source agreement but you can just
95:05the resource read-only generous style
95:09open source I guess question one of the
95:14things that I found very valuable in
95:16symbolics was the fact that generally in
95:19order to make any modifications you have
95:20to have a second person sanity check
95:22your courage and that's something that
95:24I've seen in very crowded places
95:29what sort of address that it's becoming
95:31more common the whole you know the
95:34extreme programming pair program and
95:36that kind of idea is becoming more
95:41common and code reviews have been around
95:44for a long time
95:47Frederick Brooks also made the point I
95:50think he's right that sort of the
95:53predictable outcome of a project is
95:58based on you know do you have one really
96:00talented chief architect or not the
96:04answer is more than one or less than one
96:06that your project will fail have exactly
96:10one it will succeed and and he says well
96:13what's one of the jobs of that person
96:15and one of the jobs of that person's to
96:17be like a wicked busybody right it's
96:19like you know it's like all code goes
96:21across that guy's desk for example and
96:24this is one of the things that sort of
96:26makes well that makes me insufferable
96:28for instances it's like I in in our
96:31stuff I read everybody's code when it
96:32gets checked in right and we don't have
96:34a formal process but I read it on I have
96:36to tell you that you know I fix like
96:40sort of five bugs every morning when I
96:42come in you know with my morning coffee
96:44because and it's not because I'm being
96:48some brilliant genius or something it's
96:50just because it's another pair of eyes I
96:53think that's you know any sort of
96:56production environment having somebody
96:57else read every line of code is really
97:00important and one thing I'd never been
97:02convinced of until I actually had a good
97:03source code stepper is you know one of
97:06those Microsoft's books about project
97:10management and writing maybe it's in
97:12writing solid code the guy says run a
97:14source stepper on every line of code you
97:16can get to and I said what an amazingly
97:20laborious stupid idea
97:21and then and then I gave it a try and it
97:24just I mean if you think you don't have
97:26very many bugs in your permian that will
97:28that will embarrass
97:30it's like it just extremely tends line
97:33will go off it's just unbelievable yeah
97:38cobra view is is an essential idea the
97:42only negative thing to say about it is
97:44there's a lot of different ways to do it
97:46from you know line by line very intense
97:49review where the reviewer really
97:51understands what's going on to a cursory
97:53examination
97:56and you know the value and the cost both
97:58vary tremendously for things that go by
98:00the name of code review it's amazing
98:02what you can discover though just trying
98:04to explain your change do you want if
98:06you are listening right yeah okay we're
98:11gonna start wrapping up three more
98:13questions
98:16the aircon uses a garbage collection
98:18technique of having reference counting
98:20and then backing that up with a
98:22generational marketing suite garbage
98:25collector does this in part so that
98:28we'll have predictable destructor a
98:31method invocation unlike Java in which
98:35final I've finalized their methods are
98:36rather useless and idea when they're
98:38going to invoke what do you think of
98:40this scheme
98:47I don't know what are the requirements
98:49yeah yeah well it might have performance
98:52implications that are not been wondering
98:55about batteries I liked it because it
98:57give good semantics to the language but
98:58I don't like features and may have
99:00really bad performance implications
99:09yeah look what's the requirement I mean
99:12yeah you're carrying a lot a lot of
99:15extra baggage to do that but if the
99:17requirement the hard requirements is
99:19that destructors should predictably fire
99:22then that strikes me is a pretty good
99:25way to meet that requirement and then
99:28you just have to decide for yourself if
99:29you think that's a good requirement or
99:31not right I mean I guess it just depends
99:36how you feel like arguing that day some
99:40it might be a good thing I know one
99:44piece of code that I've had the
99:46misfortune of doing some maintenance on
99:48has essentially all of its logic and the
99:50destructors not work at all in an
99:54environment that didn't have those
99:56characteristics and you know other
99:57things really care very little about
100:01when cleanup happens so there's no
100:04one-size-fits-all answer problem
100:07reference counts are good as long as you
100:10don't use them everywhere sir
100:22so what this is this is a against
100:26in a dynamic language here going here
100:30like add and delete classes and types of
100:33runtime and you're also going to have to
100:36be doing a lot of type checks and I
100:39wondered if you had any ideas on how to
100:42do that fast but you also have to make
100:44sure the the whole thing is more things
100:46are 30
100:50every
100:53it'll help from the hardware yeah well
100:56there's that one and and Dylan also
101:00solved that by adding some engineering
101:02right wrong Java does too right there's
101:04you know Java has a notion of things
101:07being final and Dylan has the notions of
101:09things being sealed and that just puts
101:12restrictions on where you can add and
101:14remove things I mean there's a real
101:17trade-off between just pure flexibility
101:20ends and high performance you could also
101:24can you could also think of it almost as
101:27sort of a you know a truth maintenance
101:29sort of thing where you know where
101:31you've got a compiler that keeps track
101:34of assumptions that it makes and then
101:36retracts them as you change the rules on
101:38it but like yeah I guess one question is
101:43what are you going to use it for and
101:45water and if you need both flexibility
101:48and the high performance I think that
101:49would be challenging
101:57one more question
102:02this money okay it's blood contacts
102:09ascended harder record programs
102:13what I'm glad he was pursued
102:18you know
102:30consider party one time to start the
102:33library two things right of
102:37we're part of the program
102:41well that's a problem that is in many
102:44ways close to profiling and some of the
102:48same techniques seem to be used I've
102:51seen you know coverage kinds of tools
102:56that basically change you change the
103:00compiler switch kind of thing to insert
103:02additional code and you can do that sort
103:05of arbitrarily
103:11keeping track of the sort of sequence of
103:16the program through its life it is
103:21probably it well is more expensive
103:26I don't think I've seen any tools you
103:28know that Authority Lieberman actually
103:30did that yeah with Christopher I years
103:33ago at the Media Lab 4zz step or
103:36something Henry Lieberman did this years
103:38ago it's actually you can sort of run
103:41programs forward and backwards and law
103:43but of course it just just cons this
103:46gigabytes it's actually really cool but
103:50it's I mean you just pay through the
103:52nose for it
103:58because it's been freelancing about
104:00their sentiment kind of exactly
104:05basically the content is another factor
104:08programs interested
104:17just happened
104:21talk business demonic memory where they
104:24use the garbage collected into and
104:27absolutely appropriate moments take a
104:29snapshot of the system and then they
104:31could go forward and backwards from
104:33those two
104:40okay thanks a lot let's thank and I just
104:52wanted to say that we'll have two more
104:54of these one on focusing on compilation
104:56to advance compilation techniques on for
104:5924 and then language design 510 thanks
105:04for coming
105:28Hey
