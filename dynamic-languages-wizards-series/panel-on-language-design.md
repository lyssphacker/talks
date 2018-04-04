### Dynamic Languages Wizards Series, Spring 2001

### [Panel on Language Design, May 10, 2001](https://www.youtube.com/watch?v=5abnmTYJHl4)

Paul Graham, John Maeda, Jonathan Rees, Guy Steele  
Unaffiliated, MIT Media Lab, Unaffiliated, and Sun respectively.  

Paul Graham has written about CommonLisp.  
John Maeda is a professor at the MIT Media Lab.  
Jonathan Rees was involved in the T and Scheme languages.  
Guy Steele worked on CommonLisp, C, Scheme, Java, etc.  

hi
0:03welcome everybody my name is Jonathan
0:05backrack this is a panel on it language
0:11design and it's sponsored by the dynamic
0:15language group this is our website here
0:18we have a number of events is the third
0:20panel in of three we had one on runtime
0:25compilation this is the language design
0:27panel and you can see the movies through
0:32this website there they're
0:34electronically stored and we're
0:36broadcasting this live today and it will
0:41be viewable later as well this is part
0:45of the six dot 894 seminar that's taught
0:50by kostas greg sullivan and myself and
0:56we are covering the material of advanced
0:59object orient damik language design and
1:01implementation and to wear this panel
1:07here is um is targeted towards grad
1:11students at large and specifically at
1:14MIT and even more specifically in our
1:16class and it's meant to help them come
1:21up with research ideas and and emulate
1:24the these illustrious panelists here so
1:29we're going to have this some the panels
1:32going to be divided into two parts we're
1:35going to start with round robin
1:36questions that we've prepared ahead of
1:39time and given the panelist time to
1:41consider they'll have two minutes per
1:43question and then finally we'll open up
1:45the questions to the audience and we'll
1:49give priority to grad students first
1:52then we'll open up beyond that I'd like
1:56to say that I'm just completely thrilled
1:58by the panelists agreeing to come we
2:03were very lucky here to have these these
2:07four people I can't you know give a full
2:11account of their their great careers
2:13I'll just highlight them first I'd like
2:16to introduce Paul
2:17gram he most recently worked for Yahoo
2:20Inc previously was president via web
2:24which became yahoo store when bof was
2:27acquired by yahoo in the summer of
2:29nineteen ninety-eight he has also
2:31written a couple books on list and has
2:35been thinking about language design
2:37issues next I'd like to introduce John
2:42mida he is associate director of the MIT
2:45Media laboratory where he's also a Sony
2:48career development professor of media
2:50arts and sciences he's the author of two
2:53books mida at media a 480 page
2:57retrospective his decade of
2:59experimentation in new media
3:02simultaneously published in four
3:04languages and also designed by numbers
3:07an introduction to programming for the
3:09mathematically challenged he is the 1999
3:12recipient of the prestigious dame ler
3:15chrysler design prize numerous other
3:17design awards notably mida was undergrad
3:20and grad in course six i'd like to
3:24introduce jonathan reece now Jonathan's
3:27interest in programming language goes
3:31back to his discovery at age 13 of X PL
3:33a so-called compiler compiler or parser
3:38generator in high school he was writing
3:40his own compilers and snowball for at
3:42Yale drew McDermott taught him APL
3:44prologue stimulus 67 Lisp and scheme he
3:49wrote T the first compiler based scheme
3:51implementation in 1982 and edited third
3:53revision of the scheme report in 1986 he
3:57was a consultant to the deck Common Lisp
3:59product group and to chestnuts common
4:01list to see translator effort at MIT was
4:05ta for the graduate course on
4:06programming languages and wrote a
4:07dissertation on secure programming
4:09language is based on scheme 48 system he
4:12has been developing with with Richard
4:13Kelsey for almost 15 years at Cornell he
4:17turned his attention to how robots might
4:18be programmed and at University of
4:20Sussex he looked at how animals might be
4:22programmed more most recently his
4:25open working on various distributed
4:27systems including a social virtual
4:29reality system at trensicourt he is
4:33currently unaffiliated guys I'd like to
4:36introduce guy Steele really happy you're
4:40here I can't even do a tiny I can only
4:46do a tiny fraction of his of the height
4:51of his great career I'll start by saying
4:54that he got a Navy in applied
4:56mathematics from Harvard ph.d in career
4:59science and AI at MIT he was an
5:02assistant professor of computer science
5:05at Carnegie Mellon University senior
5:07scientist at thinking machines
5:09corporation this is just a sampling
5:11author or co-author of numerous books on
5:14computer science including books on C
5:16common lisp and Java author of two dozen
5:18papers on list language and
5:20implementation served on numerous
5:21language standards committees including
5:23see Fortran Common Lisp and scheme
5:25winner of numerous awards including ACM
5:28in triple-a I fellow currently working
5:32for son responsible for research in
5:35parallel algorithms implementation
5:37strategies architectural and software
5:40support and for the specification of the
5:41java programming language thank you very
5:43much for coming so we'll start off with
5:47questions and Paul will give each the
5:51panelists two minutes for question and
5:53we'll start with your guiding philosophy
5:57yeah you're on Paul all right by the way
6:04guys deal has designed all the languages
6:06and I designed nice so the key and I
6:08seem to disagree about anything he's
6:09probably right you go do you hear me in
6:13the back even now can you give it in the
6:17back now all right loud it is um so
6:21guiding philosophy um I think one
6:24programming languages are for people if
6:27you think what a programming language is
6:29for its for telling a computer what to
6:30do right I think the computer would be
6:32just as happy talking in any way
6:34as long as it was unambiguous um so who
6:37is the programming language really
6:38forwards for the person i think the
6:41entire point of programming languages is
6:43to save our weak human brains from being
6:46overwhelmed by a massive detail um and
6:48this makes designing programming
6:50language is different from designing
6:52other kinds of software in designing in
6:55the world of architecture designing
6:57bridges for example is very different
6:59from designing chairs designing bridges
7:00is a fairly nice impersonal problem of
7:03spanning a large space with not too much
7:05material whereas designing chairs
7:07requires the desire to be sort of
7:09intimately acquainted with and always
7:12thinking about the human butt and so
7:15people who design great bridges don't
7:17necessarily design great chairs although
7:19they tried programming problems are like
7:23that too some problems are a lot more
7:25about people than others designing
7:27algorithms for routing data around a
7:28network is a fairly nice and personal
7:30sort of problem you may deal with
7:32outages you don't have to deal with
7:33personal idiosyncrasies whereas
7:35designing programming language is the
7:37whole purpose of programming languages
7:38to support personal idiosyncrasies like
7:41it or not this doesn't mean you can't
7:43design languages that are mathematically
7:45elegant because mathematical elegance
7:48some kinds of it make programming
7:50languages easier for people to
7:51understand but that is not the raison
7:54d'etre programming languages just to
7:55help from having a good one how much
7:57time to address
7:58uh like a minute a minute I'm going to
8:02blow through the other points I hate
8:03when people talk to you are so number
8:07two I think it's a good rule of thumb
8:09probably to design a programming
8:10language free for your own self to use
8:12rather than for other people um I've
8:15been thinking about this and it seems
8:17like a lot of the best languages were
8:19designed for people to use themselves
8:21and a lot of the worst languages were
8:23designed for other people to use and
8:25that's because when programmers design
8:27languages for other people to use it's
8:29always a specific kind of other people
8:31they have in mind other people who are
8:32not as smart as the language designer
8:34need to be told what to do and prevent
8:36it from getting themselves into too much
8:38to cover you know and hackers especially
8:42do not like to be told what to do they
8:44like to sort of mess around with things
8:45I think it would be an interesting
8:47problem if an interesting approach if
8:49just for once language designers tried
8:51to design a language that was for people
8:53smarter than them right like they just
8:56have this small conception of what
8:57ultimately fabulous things these
8:59programmers might want to do with this
9:00language and they better just get out of
9:02the way and let these guys have control
9:04of everything um so number four aim for
9:08brevity um that was two and three
9:11combined um brevity is underestimated
9:14and even is scorned um but if you look
9:16into the hearts of hackers who find that
9:18they really love it um how many times
9:21have you heard hackers speak fondly
9:23about the amazing of things that could
9:25do with just a couple lines in APL and I
9:29think that anything that really really
9:31smart people really really like that
9:33much deserves paying some attention to
9:35you and I think it's probably worth just
9:37as a little experiment to just see how
9:39brief you can make everything and I
9:41think in particular you should try and
9:43make the description of the language be
9:44brief if you forced yourself never to
9:47left of language description be more
9:48than say 150 pages you know you'd find
9:51as you are having to write the
9:52description that you know you get to
9:54some page where you have to give like a
9:56page of qualifications and warnings and
9:58caveats and special cases you know if
10:00you have to if you didn't have room for
10:02that page in the manual
10:03maybe you have to go back and redesign
10:04the language to make it simpler so you
10:06wouldn't have to give all these
10:07explanations um five admit what hacking
10:10is I think a lot of people wish that
10:12hacking or mathematics or something like
10:14a natural science I think really it is
10:17its own thing and it's something closest
10:19to probably architecture architects have
10:22to know about physics or at least have
10:23to know engineers from know physics if
10:25their buildings don't fall over but
10:26they're not doing physics they're not
10:28like inventing some kind of thing in the
10:29Natural Sciences they're just trying to
10:31build great buildings and hacker dislike
10:33they don't get rewarded very making
10:35great programs and I think you know you
10:38don't get tenure for it anyway you have
10:39to like write some great program and
10:41then make up some paper about some
10:42little thing you discovered in the
10:43process of writing this great program so
10:45you can publish a paper about it and get
10:46out of grad school I think at least
10:48amongst ourselves you have to admit that
10:50it's a great thing to write great
10:51software even if no one will give us 10
10:53years for it all right okay um the
10:57air-conditioning's on so we had to keep
11:00the voices up k people here okay really
11:05boom okay yell everything Mike's getting
11:09Austin mom can't it turns out we can't
11:12use an amp or speakers because feedback
11:16in the system so we just have to use
11:18Christ instead without heads stand up
11:20that's good idea do you mind okay he's
11:24wearing shorts I barely really prepared
11:29be prepared for this shield you guys go
11:34Paul has all the answers not just have
11:36questions I guess I find this business
11:41it's very interesting you know in the
11:4270s and 80s we have the sort of dream
11:44you know if only you could come up with
11:46just the right language than just the
11:49right implementations then it would sort
11:50of take off and it would be used for all
11:53applications as your shell command
11:55language
11:56scripting and the scientific computing
11:58computing and high performance stuff and
11:59so a lot of people put a lot of effort
12:01into into universal languages I think
12:05it's very mysterious that with so many
12:07smart people working on it that hasn't
12:09happened and I don't know that I have an
12:13answer there but oh it still can't hear
12:16I don't know that I have an answer to
12:18this question of the continuing
12:19proliferation of languages but i think
12:24is i think it's a very interesting sort
12:25of meta question about this field of
12:28endeavor you know we still have you know
12:32multiplication of languages with sort of
12:33a major language coming out every year
12:35or two it seems and no sort of consensus
12:39or you know commonality between them so
12:47this it's languages are proliferate
12:50languages are programs after all they
12:52are into in some sense they are there
12:54with their implementations and that's
12:57and it's so their programs and there are
12:59lots of programs so what you might
13:00expect there to be lots of languages so
13:02maybe this is natural but but it still
13:08seems odd and interesting if you're
13:11designing a language you want to think
13:13about about the the audience and you
13:15know if we're 1980 you would think that
13:17your audience was everyone but i guess
13:21this
13:24well one thing I worry about is du du
13:28program is really care about the
13:29language they use all right people
13:31people want to solve problems typically
13:34I'm time talking very generally hear
13:36about to the extent i can about what i
13:40perceive is the kind of the biggest
13:41market for languages and they'll use
13:43whatever language is is going to solve
13:46their particular problem best at the
13:48time they may regret a language choice a
13:50few years down the line because it
13:52prevents growth but you know if this
13:54language is very good for image
13:55processing they're going to use it even
13:57if they you know that doesn't matter
13:58what they think about about to scheme or
14:02Python or or or or or you know prologue
14:06or anything else it's they don't have a
14:08choice of what language to use they need
14:10to use the one that's best for their
14:11application so that's kind of another
14:15sort of mystery that the proliferation
14:17is really a proliferation of libraries
14:19and of applications and the languages
14:22are all they're almost like the tale
14:24being pulled along behind the
14:26applications so you know guiding
14:31philosophy I guess I have a few short
14:34ideas to toss out here at my ideal for
14:37programs and four languages is that they
14:39you know we talked about modularity and
14:41and as some sort of ideal or you know
14:46simplicity or parsimony or something
14:48like that and the way I've been thinking
14:50about it lady lately is that you want
14:51your programs and your languages to be
14:53to be rewritable right you know a
14:56program that's simple enough is one that
14:58you don't need right it's one that that
15:00has produced such an such an amount of
15:02understanding in the general population
15:03that anyone can take the ideas and
15:06reproduce the program from those ideas
15:08so that's what I mean by a rewritable
15:11program in an example of a rewritable re
15:13implementable language which i think is
15:16a good property I see that happening
15:18with scheme which has you know high
15:20school students going and implementing
15:22it you know
15:23a week or something with 20 30 40
15:26implementations that you can find just
15:29on the web and I see it happening to
15:31some extent mate with maybe with some of
15:34the other newer languages I I don't know
15:35much about Python but I CJ Python coming
15:38along and sort of a variety of Python
15:40implementations in silence that that
15:42something that seems somehow good to me
15:45I'm probably out of time so she called
15:47so I should do it yeah good guy okay
15:55well Paul has already mentioned what I
15:57considered my first and foremost point
15:58which is that a good language should be
16:00simple to describe and the main point of
16:03this is that you want to be able to keep
16:04most of it in your head every cache miss
16:07you take in order to pull the reference
16:08manual from the shelf as a loss of
16:10productivity so you want to keep the
16:12language small enough you can keep most
16:13in your head most of the time now I had
16:16the chance to help right the
16:18specification for the java programming
16:19language one of the books I've written
16:21and by the way you can actually count
16:23all the books I've written on the
16:24fingers of one hand now it's kind of you
16:25to describe five as numerous I guess
16:27five is a number and I was brought in
16:34not as a designer job of it as a
16:35biographer of Java and my principal
16:37contribution of language was that as I
16:39was I was writing the specifications
16:41language I would constantly return to
16:43james gosling and say well I could
16:45describe what you did in 20 pages or you
16:47can make the simple changed I could
16:48describe it in two pages which g1 and
16:52once or twice you push back but usually
16:54the simplification went through in that
16:55last year but where the book came out
16:56and I think it really helped the
16:58language of it we have all the rules for
17:00resolving overloaded methods used to be
17:02a lot more complicated until we made the
17:04primitive types behave more like objects
17:05in that respect it's important to this
17:10to establish design principles early on
17:12that is in fact to do meta design
17:14because as you evolve the designers the
17:17language grows later you want to remain
17:19true to initial vision this again has do
17:22keeping the description small and if you
17:24can resort to a meta principle to help
17:26your resolve of particular design
17:27decision and keeps the language more
17:29consistent a good example of this you
17:31might decide early on that plus and
17:34times are going to be associative and
17:35commutative
17:36East as much as possible this got broken
17:38in a bad way in Java if you add the
17:40string food to the number two and then
17:41add that to the number three you get
17:43food to three but if you add food to the
17:45sum of two and three you get foo five
17:47you know that's a very bad breaking of
17:49associativity I one should strive for
17:53completeness and orthogonality again
17:55these are consequences of simplicity if
17:56you've got five different features your
17:58language nature of binary choices that
18:00ought to make 32 combinations if you've
18:02implemented only 23 of them because the
18:04other nine turned out to be hard for
18:06obscure reasons then the design of the
18:08language is going to remain obscure to
18:09the user he's constantly thing OMG is
18:11that particular combination supported or
18:13not you know avoid that kind of thing
18:14it's important to consciously separate
18:17language for metal language is great to
18:19have a language be its own metal
18:20language you also need to be clear on
18:22where the boundaries of separation and
18:23when you cross that line I've seen a lot
18:25of really badly structured list programs
18:27written written with it used eval all
18:29over the place where they really didn't
18:31need to but assuming a convenient thing
18:32to do and the problem there is it was
18:34crossing the line between language and
18:35metal language in unpredictable ways
18:36which made the program harder to
18:38understand it's a good idea to avoid
18:42special cases but on the other hand
18:45common things should be easy to say a
18:47simple example is the for loop in C or
18:50Java in fact that's a very general
18:52mechanism and there's even an even more
18:54general version of that for loop and
18:55countless called the do loop and yet
18:58about ninety five percent of all the for
19:01loops that I see em c or java are
19:03counting i from 0 to n minus 1 and that
19:06gets expressed using a standard idiom
19:08that you have to write over and over and
19:09over again it's easy to mistype the
19:10character and get it wrong there are
19:12advantages in having a few special case
19:14constructs to cover the very common
19:16cases make them easier easier to write
19:18but more important harder to screw up so
19:21Commons for example five things called
19:23do x and do list they capture the very
19:25common idioms i think an important thing
19:29that when you design a piece of a
19:30language that does a familiar thing that
19:33you do the familiar thing exactly or
19:35else stay well away from it but don't
19:37get really close to the real thing
19:38release something slightly different
19:39trip up trip up the programmer a very
19:42prosaic example is the division operator
19:45I think it's criminal nowadays you can
19:48write 1 / 2 in a programming
19:49and get a value that's nowhere near
19:50one-half this is bad design finally I
19:54part my philosophy is to experiment with
19:57language and to play with it rather than
19:58trying to design all on whack I try to
20:01build a small interpreter and try it out
20:03and it's important to try out the
20:04language on real applications in the
20:06intended application area it's really
20:09bad idea to make the compiler for the
20:10language be your big test case unless
20:13the purpose of language is to write
20:14compilers but if it's not then you
20:16should build programs that are larger
20:18than your compiler to try it out on a
20:20real application area
20:24i'm using a overhead projector
20:26technology I'm not sure it works at work
20:33ok well I come from the viewpoint less
20:37of designing a computer languages more
20:40perspective of a what's a cultural role
20:42of the software in design and in regards
20:46to a gutting philosophy of where i
20:48contested about this is supposed to be
20:50situated is a is what does it mean when
20:54something is happening in the computer
20:56how do you make more people aware of
20:57that I think best example I can think of
21:00actually recently was a back when there
21:02was a TI Explorer list machine it was
21:04very noisy and it had a particular salad
21:07mail came in because in a sense that it
21:09was happening he knew exactly what it
21:10was and I had the same experience at the
21:12Museum on an arc where my group was
21:14building something there for the for the
21:17exhibitions and we had a small table
21:19about three quarters of wickedness size
21:21and there were six de stop really as
21:24hackers building something there and the
21:26installation guy comes around and says
21:28they're so are they browsing the web so
21:31then no no sense that there was all this
21:32stuff being built here now it's the
21:34bridge the architect was being built
21:35there but that whole world is invisible
21:38and I find it very lamentable
21:44in general I am very interested in how
21:47do we somehow situate the act of working
21:51in this very invisible invisible domain
21:53into a to the same level of culture as
21:56for example on oftentimes you can say
21:59like you know I'm a I'm a writer I write
22:02books i'm in a novel you know they say
22:04oh wow great you know like I'm a painter
22:06and I mean the painter you know it's how
22:08did you build this thing in this guy all
22:09messed up whatever you know but so I i
22:11wrote mac paint or something and they
22:13said oh oh people actually feel sorry
22:15for you turns out something I'm not sure
22:21what it is but I know that there's a
22:23very famous prize called a print
22:24surprise in architecture anyhow they
22:26make true train stations and airports
22:28not going to count I wonder just like
22:30Paul why isn't there some kind of
22:32cultural sort of us their value for that
22:34person and finally one thing I very
22:38interested in is how do we get sorry
22:40more people that are interested in the
22:42design not think of the semantics of a
22:45language of butter or how it sort of
22:47feels and then also give you their ism
22:50oftentimes me think of like something
22:52like a flatware silverware there's a lot
22:55of silver out there it isn't like five
22:57of them it isn't like a doubt it's like
22:59millions of them a lot of choice but on
23:02the choice there's some very good ones
23:04very bad ones good to hold about to hold
23:06and I don't feel that in the area of a
23:09least computation the varieties are our
23:12great this is nice hand books on the
23:14latest languages but as a state senator
23:16of a certain of macing aspect of how we
23:18sort of feel about those languages
23:23okay we'll move on to question number
23:26two and we'll start with Jonathan race
23:29this time open problems future
23:31directions to sentence perhaps
23:38definitely
23:39what is that a dynamic language
23:42Oh
23:44well anyone want to take that on the
23:47positive way from what is it then I'll
23:53leave that to the panelists to take on
23:594chan is not it's you you know one when
24:05you see one but of what the network
24:12language is one that defers as many
24:14decisions as possible to till runtime
24:16not always it something to control the
24:18programmer the programmer might choose
24:19that some decisions made a compile-time
24:20but the IDS refer as many decisions for
24:23example about array size about number of
24:25data objects to allocate there are all
24:28kinds of decisions like that the app
24:29view concept is deferring into a runtime
24:31that's what I understand by dynamic ok
24:35great Jonathan open problems future
24:39Giants and we're going to continue
24:40standing upright yeah and booming your
24:44voice too yeah
24:48let's see I guess I already I already
24:51mentioned one I mean you're talking
24:52about potential research topics i think
24:54there's there's room for a lot more sort
24:57of empirical work about about how
24:59programmers actually work and how how
25:01could teams or individuals make
25:04decisions about about what language to
25:07use you see some of that but i think
25:10it's just in the literature it's just
25:11sort of the tip of the iceberg i think
25:18most of the rest of what i have to say
25:20is sort of is motherhood i mean that the
25:23clearly you know distributed computing
25:25and cryptography and security issues are
25:29sort of at the front of a lot of
25:31people's awareness and minds and if
25:34those these things have had not a lot of
25:38impact I mean people have been thinking
25:40about programming languages for
25:41distributed systems for a long time but
25:44I think that's that that's potentially a
25:48very hot area related to this is I came
25:52back to Mike Dixon's work on he was
25:56arguing that programs typically and the
25:59languages that you write programs in are
26:00you are talking about entities that are
26:03inside one computer inside the computers
26:05address space and then the the
26:09implementations are very poor at
26:11supporting the notion of objects or
26:13activities that are going on outside the
26:15direct control program his his example
26:17was all the bugs in the Macintosh
26:20operating system having to do with the
26:22use of floppy disk drives because the
26:24language didn't understand that there
26:27was this floppy disk that a user might
26:29actually remove from the drive and so
26:31the program's ended up being full of
26:32assumptions that the same disk was in
26:34there you know for one moment to the
26:36next and you end up reformatting your
26:38system disk because you would put it in
26:39an order to get the reform attic program
26:41things like that so I the relation
26:44between that and distributed programming
26:45is just the idea of objects that are
26:49that you have some control over because
26:51you can talk to them but they're there
26:52and there's some constraints on them
26:54because they have predictable behavior
26:55but they're sort of outside of the
26:57program so if I'm trying I'm trying to
27:00get people to do research
27:02particular topics in something I want
27:04people to look at so right any notion
27:11the this whole thing about security is
27:14this we see this big tension between
27:16objects or object oriented systems and
27:19distributed systems because distributed
27:21system here you have parts of a program
27:25that it's a single distributed program
27:26if you will that are trading information
27:28they don't trade objects you can't send
27:30an object object is here and have stay
27:33if you're lucky you can you can sort of
27:35pretend that an object can move but
27:37that's that's just smoke and mirrors so
27:42the notion of an object is something
27:45with which has state or is a simulation
27:47of a real world object or a
27:49representative of a piece of hardware or
27:52something is it seems to me is a very
27:54different you know metaphysically
27:57different kind of thing from information
27:59and distributed systems are about
28:01information because they're sending
28:02information around information is
28:04interesting because you can do all kinds
28:05of things with it you can't do with
28:08objects you can encrypt it you can copy
28:10it you can compress it you can cash it
28:14and these seem like really basic ideas
28:17and I don't see them I may be missing
28:20some of some some relevant research here
28:22but the closest you come to this as long
28:25as languages that have an explicit
28:26notion of value that's different from an
28:29object like Pascal right and languages
28:34like functional programming language is
28:36where all you have is bow is all you
28:38have is information there are no objects
28:39there's nothing that has state I've I
28:43pulled a fast one here because i made
28:45this implicit assumption that objects or
28:46things that have state I guess that's
28:49subject of another rant about how poorly
28:52defined objects are clearly defined
28:55entrepreneur programs but I think I've
28:57used my
28:59big guy okay the first open problem that
29:04left to mine is not actually a language
29:06design problem but enabling technology
29:08and that's garbage collection of
29:10terabyte heat set up we're trying to
29:13tackle the garbage collection at the
29:15gigabyte and 10 gigabyte level now that
29:17problem is only going to get worse and
29:19it may be the garbage collection is the
29:21wrong idea to begin with I'm not sure
29:22another important open problem is
29:25finding a good model for parallel
29:27programming for multi-threaded systems
29:29and I'm taking a dayum data model for
29:31using a parallel programs we use shared
29:32data messages monitors what should it be
29:36java at least tried to put forward a
29:39particular model and tried to nail it
29:41down in great detail turned out to be a
29:42lousy model in a number of ways but at
29:44least it's well specified enough that we
29:45get a reasonable out of portability and
29:47using it which i think was in advance
29:49william pugh don at university of
29:51maryland has been spearheading an effort
29:52to try to clean up some of the poorer
29:55parts that specification but i think an
29:56open problems try to come up with a
29:57really good specification for a parallel
29:59programming I'm also worried about the
30:03robustness of multi-threaded systems how
30:05do you deal with pushing a computation
30:08forward in the face of the fact that
30:10components may disappear or things may
30:13fail or the floppy disk might get pulled
30:15out of the drive how do you have you
30:16design software and design language is
30:18to support software better robust in
30:20this way finally I'm interested in in
30:23designing a language that scales from 10
30:25line programs to 10 million line
30:27programs you know from scripting all the
30:29way up to you know super large systems
30:33that run corporations and I think you
30:37need to design a language do that
30:38scaling because in the small programmers
30:41won't put up with all the overhead you
30:42need in order to make a large system
30:43robust so how can you make those
30:45robustness features optional in a way
30:47that if they can enter smoothly with
30:50appropriate defaulting in a small level
30:51but be incorporated this programs grow
30:53large I'm not yet quite yet sure how to
30:55design such a language I give a good
30:56thing to do
30:59John
31:02sorry about this in terms of a token
31:08problems I see at least in my
31:10relationship to computers and software
31:12design I think that we rely a lot on
31:16these Lasky's that ascii things he's
31:19putting together I'm trying to figure
31:20out how to make them into something in
31:22many sense is a this thing you might see
31:24her he's a tortured hey he's been
31:26tortured and warped and everything and
31:27he's kind of an a actually but he's not
31:30really an a he's kind of a slippery a
31:33you can look at how to hold on some in
31:34different ways and a lot of me think it
31:37comes out their basic abstraction and I
31:38wondering how did we take that
31:40information i went to the language space
31:42example i had exhibition last year in
31:45New York about I made these objects out
31:48of a white and black paint essentially
31:50and I wonder what is this and so I made
31:54us some pieces of software on Palm
31:56Pilots thinking what is this and so and
31:58instead of think about how to think
32:00about something abstract in a equally
32:02abstract way other thing is I'm sort of
32:06the reverse Podesta to get away from
32:11being a robot I mean every time I sit
32:13down to write code it's like this scene
32:15from matrix where the guy says I need
32:17guns lots of bench and all coming up
32:20because you know you're going to have to
32:21walk all the way to the other side to
32:23get there but you hired yourself there's
32:26something about why can't we just like
32:27throw ourselves at it in a more
32:29full-bodied sense and bothers me the
32:33third things that the third thing is on
32:35how to get more sort of information
32:37beyond the symbols in the system example
32:41is my three daughters play violin and
32:43they're still small and so I got to hear
32:45all this stuff every day but the one
32:47thing I hear is my life staying you know
32:49I learn I would always words it i'll let
32:50girl all these kind of 40 somalis and so
32:52in many senses i realized that a
32:54programming in general is actually kinda
32:58like the electric piano the a is
33:00everybody's a it turns out we messed
33:02around the pitch here and there we get a
33:03little Ridge analogy but there's no no
33:06hey there
33:06sort of a human intention in there such
33:09a strong sort of a aggression as you
33:11leave there and props they leave a kind
33:13of a an overall structure it has a
33:15greater opportunity for our human
33:17brilliance oh all right how many open
33:25problems for for problems that I
33:27currently worry about one is how to
33:29organize big libraries because as
33:31someone was that you pointed out
33:32libraries are getting to be so big and
33:35they're so important and how people
33:36decide what language to use shout
33:38libraries are big big I have just one
33:45word to say Plastics libraries libraries
33:52are big but you know as libraries get
33:54bigger you get to the point where it can
33:56take it long enough it can take longer
33:58to look to find what you want in the
34:00manuals than to just write it yourself
34:02and I first discovered the surprising
34:04thing when I first started using the
34:05symbolic slist machine shed manuals like
34:08the documentation for a nuclear power
34:10plant I know because my father designs
34:13nuclear power plants and it's the only
34:14the second time in my life I had seen
34:16such a long series of documents it is
34:19about the same size how do you organize
34:22these gigantic libraries ideally like
34:25guy said you should be able to guess
34:27what library call will do the right
34:29thing and just heading into work um to
34:32our people really scared of prefix
34:34syntax or not this is an open question
34:38about this all the time i don't know i
34:41mean people people say that they don't
34:43like list because you know it doesn't
34:45talk to the operating system are it's
34:46not they can't hire people who
34:47programming in it maybe it's just that
34:49they're terrified of they look at the
34:50program you think oh my god you know I
34:53don't know I don't know and it really
34:54matters i'm not sure what to do about
34:56this um number three this is a more
34:58serious one what do you need in a
35:00programming language to support server
35:02based software um i think a lot of the
35:05exciting new applications that get rin
35:07in the next couple years like maybe the
35:09next 20 years will be strictly web based
35:10applications programs that sit on the
35:13server and talk to you through a browser
35:15what do you need in a programming
35:17languages sorry shouting shouting what
35:20do you need in a programming language to
35:22support applications like that um but
35:25one thing you need is support for a
35:28different model of releasing because the
35:29way server based applications get
35:31released is as five to ten small changes
35:34a day not one great big bowel movement a
35:37year and so you know how when you have
35:41big programs you can often design
35:42software to be debuggable you also can
35:47design software to be changeable and it
35:50would be a good thing of programming
35:51languages head support for that kind of
35:53thing what the hell do I mean by this
35:54well let me give you an example keyword
35:56parameters who would have guessed it but
35:58it turned out keyword parameters were a
36:00huge win in designing via web because if
36:04I had some piece of software that I
36:06wanted to change I could just add a
36:09keyword parameter and if I only change
36:10the codes that it depended on the
36:12behavior of the new keyword parameter
36:13and everything else stay the same I knew
36:15I wouldn't break anything and being able
36:17to tell what's going to break stuff and
36:18what's not is really important being
36:20able to partition your application
36:22between stuff that you can change easily
36:23no sweat and stuff you really ought to
36:25think about before you change because
36:27you're going to be changing stuff a lot
36:28in server based applications another
36:32thing believe it or not I think
36:34continuations maybe may
36:36have a come back here because I'm not
36:39sure if this is still an open question
36:41but one thing you really want to do in
36:43server based applications is use
36:45something like closures to keep state so
36:47you can get the effect of subroutine
36:49like behavior the way we did it was to
36:51fake I've like made a whole career out
36:53of faking continuations by making them
36:55out of closures and so we just did that
36:57because that's what I do in every
36:58program i right it might be useful to
37:01have actual continuations if it didn't
37:03cost too much and that's an open
37:04question um number for this is just
37:07something that's always running like a
37:08background process what new abstractions
37:11are left to invent this is almost like
37:13asking okay you know what's the next
37:15model of physics it's if you could
37:17answer it you could just you just be
37:19automatically famous it doesn't seem
37:21like new abstractions get invented all
37:22that often but it sure would be fabulous
37:24if there were some left to invent and
37:26one could think of them change right
37:31okay we're going to go on to question 3
37:34little-known secrets and we'll start
37:36with the guys seal ok little-known
37:39secrets um stacks are overrated garbage
37:47collection is good but finalizer zar bad
37:51as if there is a reasonable way there is
37:55a way to give finalizes at reasonable
37:56semantics but involves doing a garbage
37:58collection at every point or alteration
37:59so we don't have a garbage collection
38:01cheap enough I've got a semantics for
38:03you lexical scoping is good but it's
38:08very easy to screw up especially when
38:09you're building an interpreter it also
38:11can interact in surprising ways with
38:13other features for example when inner
38:15classes were introduced in Java suddenly
38:17the rules for named inheritance begin to
38:19interact with the names for lexical
38:21scoping inheritance and some arbitrary
38:23decisions got made that I think our
38:24perhaps best described as confusing type
38:30inference can be good and we're studying
38:33the languages ml and haskell for example
38:36to see how that can be done in practice
38:37but it turns out the error reporting is
38:39hard if the type is inferred and it
38:41doesn't match you end up with 20 pages
38:43of type dump that you would like the
38:44compiler and dot so it's also good to be
38:47able to state types explicitly so that
38:50the the error messages can sort of have
38:52pegs to hang on monads may be very good
38:56that's still a topic research I think if
38:59we're studying go to ww señor gif you
39:02haven't already and study the Haskell
39:04language has a number of very
39:04interesting ideas in it finally
39:07higher-order functionals I think are
39:09underrated and be very good as the years
39:12passed the more I use common lists the
39:13more I find myself using the sequence
39:15functions including a lot of map cars I
39:16had to do a matrix tensor product fruity
39:19me about two weeks ago and I was trying
39:21to puzzling over how to do the nested do
39:23loops and so forth and I finally I
39:24realized it was just map carved map grab
39:26apply of a kind of map car map car done
39:27you know no big deal in other words
39:31thinking an APL can improve your list
39:33good
39:36John
39:43big secrets I think one secret i've
39:48discovered is parameters boring now this
39:50actually comes from of my discussions
39:52with my esteemed colleague at the meal
39:54oppressive brian smith with an expert in
39:56a media movies and critique and he knows
40:01job of a quick time says if i have to do
40:03another import quicktime the component
40:05that movie whatever you says going crazy
40:07i understand that craziness on the flip
40:09side if we think let's what would happen
40:11if it made it easier for us we'd have
40:13like the paperclip god being like
40:14codewarrior or something like I see
40:16you're making a compiler this machine
40:28manual windshield let's machines up I
40:30remember what I learned SIA have their
40:33kar it was about this bin and he was
40:36like wow I guess read this book I
40:37understand see it's hard but you're
40:39actually plug harvesting wood steel to
40:40fix the problem but uh it's like this
40:43said now and when we think let's machine
40:45manual was it was big goes it all the
40:47different ones together well I tell my
40:48student I was a list machine my way tons
40:50of manuals and the guys to take a
40:52dreamcast manuals look at this you know
40:54different scale as well sort of a
40:57concerning and our secret that I've
41:01discoverable teaching here at MIT kind
41:03of a fundamental concern I have is that
41:06there's a kind of opportunity now it's
41:08happening where there are people who are
41:10sort of crossing into this sort of quasi
41:12art and technology people are very good
41:14computer science and also very artistic
41:16sort of attitude the vice versa and I've
41:18discovered that in general in the
41:21general population and perhaps a
41:22thousand artists and designers today you
41:25can you find at least so at least
41:27seventy percent of in the one line of
41:28code on the other hand you can have a
41:30thousand software people or maybe three
41:33years so one under 7 is 9 minus very
41:35lamentable however the good news is that
41:37in terms of it it's okay because even if
41:40you have a lot in both sides and also
41:41the evens out because if only a few
41:42people aren't you last on both sides
41:45thank you
41:49yeah any guy to start this time oh yeah
41:52really to join with number three and the
41:54reason is the secret's out we want
41:56secrets all right little-known secrets
41:57um five little-known secrets um this
42:02first little known secret is a
42:03little-known secret for application
42:05programmers but it involves programming
42:06languages can you hear back there all
42:08right this is sort of a little known
42:11secret to write applications at least on
42:13web on web servers you can actually use
42:16whatever language you want um and this
42:19did not used to be true I mean I feel
42:21like just telling everybody you can use
42:23whatever language you want right even
42:25Lisp because that did not used to be
42:28true it used to be writing applications
42:29meant writing applications to run on the
42:32desktop and it was real convenient if
42:34you use the same language the operating
42:35system was written in for it plus plus
42:38but and so there got to be the tradition
42:42that you better not use a weird language
42:44or you get into trouble in this
42:46tradition even penetrated as far as
42:48managers and venture capitalists where
42:49it's still very much alive however it's
42:52just not true you'll find all kinds of
42:55excuses you know why you shouldn't use
42:57weird programming languages oh no one
42:59will want to buy us if we use a weird
43:00programming language well no one will
43:01want to buy you if your competitors beat
43:03your ass don't worry about second order
43:07of problems like whether somebody will
43:09buy you or not just use the best
43:10language you can get and write the
43:12program it will beat all your
43:13competitors and then worry about whether
43:14somebody will buy you or not um number
43:17two speed comes from profilers I found
43:21this in my own in my own life compiler
43:24designers like to write compilers that
43:26generate fast code but compilers that
43:29generate class code is not what will
43:30make your programs run fast as knuth can
43:33tell you and everybody else since
43:35programs have a few small bottlenecks
43:37and you're probably wrong in your guess
43:40as to where they are and so you need a
43:42profiler to tell you where they are the
43:44way you get fast programs is to have a
43:45really good profiler will tell you what
43:47parts of your code you need to rewrite
43:48it's not a matter of making a given
43:50program run fast it's a matter of
43:52figuring out where you need to change
43:53your
43:54in practice so i would spend a lot of
43:56effort on writing really good profilers
43:58and not so much on generating super fast
44:00code who cares if you declare the type
44:02of everything in your entire program so
44:06let's see number three guys steal
44:08already said this you need an
44:10application to drive the design of your
44:11language and I would add like he said
44:14what he said a great are used to say the
44:18application shouldn't be just the
44:20language of writing um a lot of the best
44:23applications seem to have been a lot of
44:25the best languages had been designed by
44:26people who are really pushing to develop
44:29a particular application including Lisp
44:31McCarthy was so excited about doing
44:34symbolic differentiation that he started
44:36doing it even in the first paper about
44:38list back in nineteen sixty it's like
44:39okay we got a language great here's how
44:41we start writing symbolic
44:42differentiation programs um he hadn't
44:45even defined map car yest he was still
44:46using math list right but that was
44:48enough um number for a language has to
44:52be good for writing throw away programs
44:54because I think that's where programs
44:56come from it's too terrifying to think
44:58of making a great big program and so if
45:01you if I bet if you poke around and look
45:03at where programs that come from they've
45:04come from some throwaway program some
45:07languages even who come from being
45:09fairly programs and so you better make a
45:12language that's good for writing throw
45:14away programs because that's where our
45:15programs grow from that's the larval
45:17stage number five this is a shocking
45:19idea and I'll blame it on someone else
45:21professor Robert Morris at MIT my friend
45:24rtm um who I was talking to recently
45:26about the shocking idea that syntax is
45:29actually connected to semantics very
45:31strange idea I couldn't believe it we've
45:32been so trained to separate them into
45:34separate boxes but the point he made was
45:36the Opera operator overloading I was
45:39trying to think you know I never he
45:41program in anything except Lisp really
45:43and so I have to ask people questions
45:44like water finalize our methods
45:46you need them stuff like that and I was
45:47asking what is why everybody's so
45:49excited about operator overloading well
45:51it's a lot bigger win to have operated
45:54for overloading if you have in fix
45:55syntax and if you have prefixed syntax
45:57right if I need to write some special if
45:59I need to design some special kind of
46:02number and write some special function
46:03to add them together I just right you
46:05know some special class function I just
46:07call it like any other function if
46:08you're if you're using in fixed syntax
46:10suddenly it's like the difference
46:11between having a nice infix operator and
46:13having a function call which looks very
46:15different right um so I think this is a
46:18strange idea but it's worth keeping in
46:19mind but that syntax is actually related
46:22to semantic shocking as it sounds
46:28secrets a short list since people been
46:33talking to each other so much I guess I
46:37mentioned one the programmers again this
46:39is my generalization of what's going on
46:41they don't care what language they
46:43program in which doesn't mean that it
46:46doesn't matter let's see to try to make
46:52this quick one of my one thing up my
46:54list of the computers are fast and cheap
46:57and I many people haven't haven't really
46:59understood this and I think he knew
47:03second-order effects I it's hot I hope
47:10tell me if I'm wrong but it's hard to
47:12think of languages or maybe even
47:15language implementations that have
47:18survived their perished based on how
47:22well they performed right I think maybe
47:26things were different in the 70s but I
47:29think it's so it's so hard now just to
47:32get the program right get that get the
47:35language right get the problem well
47:37specified get the prototype done that
47:40you know worrying about you know the
47:43efficiency can come you can rewrite the
47:44program once you understand it use a
47:46profiler to identify hotspots you can
47:49you know instead of using the the free
47:52implementation you you shell out for
47:53some expensive implementation that has
47:57better performance or whatever but it
48:01just it just seems so that I mean I'm
48:04looking here relate to compilation of
48:06dynamic languages at this point I don't
48:08personally I don't find the compilation
48:11aspects that that compelling or
48:13interesting they're important and they
48:15have to be done but they're not sort of
48:16the first order kind of problem that
48:19we're all facing them and the last thing
48:22is just that the object oriented is
48:25there's there's some sort of conspiracy
48:27that too for people to think that that's
48:30a well defined term
48:32and I find it very confusing and I find
48:37a lot of object oriented programs and
48:40programs written in what is called an
48:41object-oriented style here confusing so
48:43I think it's that I don't know this a
48:46secret or a flame but you know there's
48:49some sort of deconstruction than past
48:51half happened the romance with with that
48:53idea has to end somehow
48:57but it's a it's a solution it's not the
49:00solution
49:04okay we're going to move on to question
49:06for and start with John mighta good
49:09ideas that have been dropped but whose
49:11time has now come
49:14I'd like a less machine with no browser
49:17because i hack a guy read a guy keep you
49:20guys waste so much time but there was
49:23something about an idea that you can
49:24have a place to think sort of a camp the
49:27tank and those who supervisor ops know
49:30that it's hard to bring your student in
49:32it with a pentium 3 or they have a
49:33pension for home and so the whole sort
49:36of magic Isis bike here every night
49:38because a year off and as magical coming
49:40to this or the secret cave the super
49:41very unique machines now magic is
49:43actually quite missing today because
49:45it's so can modify the second thing is
49:48that my role as a trying to help the
49:51ministration the media lab and now this
49:52is so a few things and that is that i
49:54was also sick table one lab ta a long
49:56time ago but I remember when he was sort
49:58of fresh and exciting and everyone loved
50:00it and as a victim do new faculty
50:02realize people don't once you put may
50:03want to make a course and then went to
50:05catalog apparently can't get rid of it
50:06it has to stay there forever and
50:08someone's got a ten the fires and that
50:11actually look quite unhappy it turns out
50:12so I've discovered that perhaps it's a
50:14great is to bring back the feeling of a
50:17new courses new ideas versus conquer
50:20ties them into things that just no one
50:21wants to take care of the third thing is
50:24um the fact that all this goodness of
50:27the thoughts space around creating
50:30software systems all kind of vanishes
50:33when you think about it regular call
50:34these comments you have been funny and
50:36finally it compiles it all kicks out
50:38only you get York executable machine
50:40gets the gets the last end and whereas
50:42the human component is missing it so
50:44many senses I believe that the sketches
50:46idea instead of talking about it should
50:49all be are cut into that software system
50:50as to sort of a increase the value of it
50:52culturally
50:59yep alright good ideas I thought up 31
51:03of them stolen 33 good ideas whose time
51:06has come back one is new programming
51:09languages it used to be really
51:11fashionable to design new programming
51:13languages back in like the 1970s and
51:15then sort of respectable intellectual
51:18stopped doing it and left it to systems
51:21programmers of dec but i think i think
51:26new languages will come back and the
51:29reason is related to what i said in the
51:30last round that with server based
51:33applications you control the server you
51:35don't deliver on someone's desk top you
51:37can use whatever language you want and
51:38if there's a language that's more
51:39powerful for what you're doing it will
51:41give you an advantage over competitors
51:42and if you're in a company and so
51:45there's actually going to be users for
51:48new languages and that will give some
51:49impetus to people to design them um
51:52number two I stole from Richard Kelsey
51:55who said it at the last panel an idea
51:58that whose time has come back time
52:00sharing because that's what server based
52:02applications basically are and so I
52:06think I know that Richard and Jonathan
52:09Reeves have put a lot of support maybe
52:11you're going to talk about this am i
52:12stealing your idea um but put us a lot
52:14of support for a process scheduling and
52:17stuff like that right into the scheme 48
52:19language and I think that kind of thing
52:21is going to be the way to go another
52:24idea whose time has come back this is
52:26unfortunately in contradiction to what
52:28someone has said before I think
52:29efficiency is going to come back like
52:31compilers the generate fast native code
52:33nowadays you hear more and more about
52:35bytecode like this thing between
52:37Microsoft and son seems to be developing
52:39into the sort of battle of the byte
52:41codes and to me that suggests that
52:44people feel like we have cycles to spare
52:47but I don't think that's going to be
52:49true with server based software and you
52:51have server based software you got all
52:52these users all sharing some bunch of
52:54servers right and the servers are going
52:56to be paid for by somebody
52:58and the number of users you get per
53:00server will be the divisor of their
53:01capital cost so they're going to care a
53:03lot about that you're going to have to
53:05be able to support a large number of
53:06users per server and there's just no way
53:08around it unless you want to put
53:10software on the client um by the way
53:13look for my in the tit fall section when
53:16I talk about clients so I think I owe
53:20especially will be fast um I think the
53:22reason the reason son and Microsoft are
53:25facing off over byte codes is because
53:28that's a convenient place for them to
53:30insert themselves into the process they
53:31can't control the instruction set
53:33because Intel does that and they can't
53:35necessarily design the programming
53:37language that everybody is going to use
53:38so if they make the war be about byte
53:40codes that's that's the one where they
53:42can get a ground to have their battle
53:43but it may be they have their battle and
53:45like everything else just happens on the
53:46side because nobody uses byte codes that
53:49would be kind of using all right so much
53:51we value
53:57I think I only have one thing to add
54:00here that does it's not redundant with
54:02what what other people have said and
54:03that's that an idea that keeps getting
54:08forgotten over and over again is the
54:09idea of and I'm stealing this from a
54:14conversation i had just before air maybe
54:16with john code analysis source code
54:19analysis and generation that that at one
54:24point enlist there was this ideal that
54:27list was a good language because you
54:28could write programs that could you know
54:30you can write interpreters very easily
54:31we can write preprocessors very easily
54:33you can write programs that understood
54:36aspects of certain programs easily so
54:38that if you wanted to you know do bulk
54:41transformations of source code in some
54:45particular way you could and this was
54:47this was some sort of ideal and that got
54:48lost in in common lisp and even in
54:51scheme i think that if if the you know
54:54if scheme if the scheme report process
54:57or whatever had had a reference
54:59implementation and if part of the goal
55:01was to simplify that implementation or
55:03make sure that the reference
55:06implementation was simple enough that it
55:08was rewritable as i said before so that
55:10you know someone else could come along
55:12and instead of writing that interpreter
55:13they'd write a variant of that
55:14interpreter and understand what it did
55:16if that if that had happened the report
55:20could have come out better um if and I I
55:22don't know exactly what's going on with
55:24with the various in fixed languages like
55:26Python I assume python has some sort of
55:28meta level processing that the parser is
55:31available to programs that want to
55:34manipulate Python programs but my
55:38expectation would be that like most in
55:40fixed languages it's going to be a
55:44pretty complicated data structure the
55:45parse tree is going to take many many
55:48pages to describe and
55:51it's the the notion of having meta
55:54programs things that generate both the
55:56generate source code and understand
55:58source code is done as an afterthought
56:00like you know maybe in Java again I'm
56:02not on top of what's available in Java
56:04but I'm sure that's all there in Java
56:06it's just not it wasn't a priority in
56:08the design of the in the design of the
56:10whole system so I I think that's a very
56:13old idea and it gets forgotten over and
56:15over again even if a project starts out
56:17saying that it wants to adhere to that
56:22guy okay this is a right good idea
56:27struck I want to start and say that you
56:29actually inspired this question with
56:31your Moore's Law talk he talked about no
56:34waiting for technology be ready so that
56:37you could solve some game problem that
56:39was unsolved will until Moore's law
56:42caught up she sounds good tell me more
56:47come back in eighteen actually have one
56:51item on my list here that actually is of
56:52that flavor I don't want keyword
56:55arguments are good call by keyword balls
56:56already covered that I think pretty
56:59printers are vastly underrated and are
57:02can be incredibly useful not only for
57:03debugging but also just for for a quick
57:06printing out of data i'm not talking
57:07about this pretty printing programs are
57:08pretty frigging data is a good idea
57:10dozens of times the waters pretty
57:13printer that was built in the common
57:14list has made my io problems a lot
57:16easier it'd be nice if they're a pretty
57:17parser as well that was easy to do what
57:20I think parsing is fundamentally harder
57:21than pretty printing by that pretty
57:24printing technology I'll be dragged
57:25along in the future languages and
57:27finally I'd like to talk a little bit
57:28about rule-based systems which i think
57:29is an idea that got dropped probably 20
57:32or 15 years ago and his time has come
57:34again and there I think Moore's Law
57:36really does make a big difference
57:38rule-based systems were tried a lot in
57:40the early 80s my wife worked fairly
57:42seriously on one called r1 Carnegie
57:44Mellon in the early eighties and the
57:46problem with the rule-based systems then
57:47was that the the processing power was
57:51sufficiently small in order to get
57:53anything done at all they found
57:54themselves having to carefully craft the
57:56rules to pass control off to one another
57:58and they found that what they didn't
57:59really have was a rule-based system they
58:01had a procedural system whose written in
58:04this extremely awkward language for
58:05writing procedural systems because
58:07they're trying to do it as rules and I
58:09think that now that now that we've gone
58:10for 15 years so by Moore's law that
58:12ought to give us how many orders of
58:14magnitude I can't do it quickly in my
58:15head but some tons
58:19computer show a 100 times faster they
58:22were 15 years ago if not maybe 200 and
58:24so I think we may have enough oomph it's
58:26worth giving rule-based systems a
58:28serious try again they got a bad press
58:30because they became associated with the
58:32big a I bloom of the early 80s and they
58:34made the cover of Time or Newsweek ever
58:36forget which one now if you make the
58:38cover of time and it says you know this
58:40person did this thing that's great but
58:42if you make the cover time it says these
58:44people are going to do this thing that's
58:45a kiss of death because then because
58:48then you can't possibly live up the
58:49expectations and that's what happened
58:50produced the so called AI winter the mid
58:5280s when suddenly industry was turned
58:55off day I because it was promised that
58:56rule based systems would solve all the
58:57problems of the world and they did and
58:59prepares good reasons but that doesn't
59:01esses enemy that will bae systems are
59:02bad idea I think it's time to get me try
59:03again
59:06okay we're going to move on to questions
59:08five then we're going to start back with
59:10Paul pitfalls and gotchas that's all
59:14right now I warn you guys there is a
59:17pitfall and gotcha in here of
59:19radioactives controversy so don't get
59:23too mad um so this is not it number one
59:27pitfall and gotcha I think clients are
59:30loose um I think clients I think client
59:36software is a lose I think designing
59:39software huh designing a fear you back
59:42okay clients or lose designing software
59:46that works on the assumption that
59:48everyone will have your client is like
59:50designing political systems on the
59:52assumption that everyone will just be
59:53honest and nice to one another it would
59:56be fine if it worked but it doesn't seem
59:58to UM I think what will happen is the
60:02opposite i think there will be this huge
60:03proliferation of all these different
60:05devices that can access the web will it
60:07be your phone with a web browser will it
60:08be your palm pilot that turns into a
60:10phone will it be you know um some kind
60:13of tablet um will your watch get a
60:16bigger screen who knows well I don't
60:20know and I don't have to know as long as
60:22I just design as long as all I assumes
60:23the software is going to run on the
60:25server I think that will be a nice model
60:27for a world in which the other end of
60:28the software the other end of the world
60:30Vasily it's wildly between what the
60:32clients are so I think writing software
60:35that involves clients is just going to
60:37be at the black hole that's not the
60:41controversial one this is the
60:42controversial 10 and Jonathan believes
60:45this too we're like this country he said
60:48so we've talked about it
60:50you have to lynch's code I believe
60:52object-oriented programming is well I
60:55don't understand why it's such a big
60:57deal actually I do understand why it's
60:59such a big deal and I think the reasons
61:00are wrong um I could see that it's the
61:03perfect thing for that for the kind of
61:05application specific applications where
61:08you need that data structure like
61:09Windows systems you know simulations of
61:12like traffic bouncing off one another
61:13and CAD programs and stuff like that I
61:15don't understand why it has to be the
61:17model for all programming I can see why
61:20companies big companies think it should
61:22be the model for all programming and
61:25it's like the software cajon and having
61:27meetings it looks like work and so if
61:31you remember back in the days of Fortran
61:33programs on fanfold where you have like
61:35the kind of person who like would write
61:37these programs that are like you know
61:38each piece of stan fold would have four
61:40lines of code on it and 30 lines of
61:42comment at the beginning like all kinds
61:44of protocols for doing stuff well object
61:46Dorian seems to be a way to do that
61:48except they're actually writing code and
61:49not just comments right so something
61:51that you might naturally represent is
61:53like a list of integers you get to build
61:55all this scaffolding and bustle you know
61:57where you have all these classes in a
61:58whole separate file of stuff right it is
62:00so which version of object-oriented
62:02programming
62:07sounds like the job can't get into a big
62:31section of all this block scripture that
62:34essentially for my wife I'm after that
62:37ugly they were wasting their time my
62:40mother don't let big corporate a great
62:42continent this is for the main event all
62:46right I should move on to my next I
62:51think the other attraction of object
62:54oriental who aren't used to list is
62:56because it gives them some of the effect
62:58of lexical closures there are these
62:59things called methods and they're one of
63:0150 different ways of using electro
63:03calexico closures and these people think
63:05oh this is so great I'll use it for
63:06everything because they don't realize
63:07there's this underlying idea that they
63:09could use in its in its sort of raw form
63:12in 20 different ways depending on what
63:14kind of program we were trying to write
63:15all right number three I think it's a
63:17big pitfall to have design by committee
63:19and a lot of people know that that's a
63:21problem I think there's a specific
63:23reason that it so it's a problem and
63:25that is that in many things in almost
63:27anything risk is proportionate to reward
63:29and I thought I don't think people
63:31realize that's true for programming
63:32languages as much as it's true for
63:34everything else you probably to design a
63:36great programming languages you probably
63:38have to take shocking risks and when you
63:40have a committee of multiple people
63:42working on something you're going to get
63:43something that's with the sort of
63:44averaging effect and you won't be able
63:46to do it because whoever thinks of the
63:48outrageous ideas won't be able to
63:49convince the other committee members
63:50they should do it so you're probably
63:52better off instead of having a committee
63:53of five people let five different people
63:56design their own languages and pick the
63:58one that ends up being the winner and
63:59we'll probably be better than one you
64:01got from averaging five people together
64:02all right thank you ok John biz
64:10hodgepodge here but I guess the the
64:13biggest one on my list of pitfalls is
64:15has to do with I don't know addictions
64:22or armed with arms races or something
64:24like that that we have you know people
64:29working on languages and and this is I
64:32think this has historically been true
64:34there's a feeling that if you know if
64:36you just work a little bit harder if you
64:37just add one more thing if you know if
64:41you just did a better job then you know
64:43the language would be good enough and it
64:45would take off and everyone will be
64:46happy and you'd solve all the world's
64:47problems there are a lot of things that
64:50that the people in computer science or
64:52in languages do that I think are sort of
64:54structurally similar to this they have
64:56the sort of addictive nature to it you
64:58know that you can say if only the
64:59implementation was fast enough then I'd
65:02have broader adoption I have better
65:03market penetration or whatever if only
65:06now I guess in a sense these things are
65:11true but what you want to do is to set
65:12up institutions that allow all of all of
65:15this richness to grow around the
65:17language as opposed to trying to to
65:20build in a lot of it it's always going
65:21to be compromised but again I don't know
65:25python that well but our languages that
65:28seem to have decent module systems or
65:31decent mechanisms by which to grow grow
65:35right I mean you look at Linux with the
65:37you know all the package infrastructures
65:39that's I mean it's it's not a good
65:42design but in rut and the RR p.m. at
65:45least but it has allowed all of these
65:49things to come into existence and the
65:51software base for Linux to grow and I
65:53think again not knowing first and i
65:55think in languages like Python you're
65:58seeing the same kind of thing one of the
66:00key things they did was a module system
66:02and that's that that basically relieves
66:05the core language implementers and
66:08designers from a huge burden of having
66:10to provide everything to everyone
66:12because now everyone else is providing
66:13everything to everyone else
66:17so
66:20um that's the only one I want to mention
66:26talking about diphthong gotchas yes
66:29pitfalls first pitfall I can mention is
66:32poor namespace management a lot of
66:35languages is about language is about
66:37naming things talking about things you
66:39have to manage those names and if you
66:41don't plan for an appropriate name space
66:43management mechanism in your language
66:45things can get out of hand as the
66:46language grows it's very easy to start
66:48up a small stripping language say oh
66:49well variables are global and then you
66:51realize that well two different guys
66:53want to use I for their do loop and
66:55you're going to run into problems and
66:56and it happens at all levels it's
66:59important to allow name reuse because
67:01name reuse is one of the principal
67:03supports of revenue which Paul is
67:04already address if you make if your
67:06impose a requirement that every name be
67:08unique then you're going to have an
67:10unmanageably clumsy language and if
67:12you're gonna be able to use rename so
67:13you need to do in a disciplined way
67:14hence namespace control access control
67:18is also important now in my day and
67:20probably your day too is fashionable to
67:22complain about fascist programming
67:24languages they don't let a hacker get it
67:25this or that it's important to realize
67:27it is restriction on one part of the
67:29program enables a corresponding freedom
67:31on the part of another part of the
67:33program I used to have a summer job back
67:35in the 70s at Lawrence Livermore
67:36Laboratory which had very tight security
67:39you know they're very strict rules about
67:40showing your badge when you went in and
67:42out and so forth but once you were
67:44inside you could leave your bicycle
67:45anywhere and not worry that it would
67:46travel osmotically through the perimeter
67:49so within within this very strict
67:51structure there was a certain amount of
67:52freedom we should respect to bicycles
67:55I've got a couple of complaints about
67:57how Java did this it turns out that Java
67:59has access key words such as private and
68:02public and protected turns out
68:04protective has a very strange edge case
68:06where are you and where you have three
68:08classes a B and C C in Harrison BB
68:10inherits from a B is in a different
68:13package that C is in the same package as
68:15a and some very strange things happen to
68:17the rules there the access control is
68:18not well defined in that case java
68:21subclassing is very strange if you give
68:24another program entity the right to
68:26declare a variable of a class you have
68:28given that entity the ability to define
68:30a subclass of the class and this plays
68:33havoc with compilers you know it'd be
68:34nice for compiler to know well here's
68:35this class it has five sub classes and
68:37there aren't any
68:38more but you simply hand out the names
68:41you can even refer to it the other guy
68:43can make a subclass so there was a
68:44failure to have a separation of concerns
68:46there in the namespace management a
68:48third example is Java locks if you have
68:50so much as a reference to an object
68:52simply so you can call one of those
68:53methods you have the ability to lock it
68:55this is bad Lock should have had private
68:58and public key words as well and they
68:59don't so it's important methodical about
69:02access and security another pitfall is
69:04full is to be sure that your language
69:06will parse it seems stupid of you to sit
69:11down and start district designing
69:12construction don't worry about how they
69:13fit together you can get a languages
69:15difficult if not impossible to parse not
69:17only for a computer but for person I use
69:19yak constantly as a check of all my
69:22language designs but I very seldom use
69:24yak in the implementation I use it as a
69:25tester to be sure that it's lr1 not
69:28going to say computer but because the
69:29language the lr one is more likely to
69:31the person can deal with it finally I
69:34strongly recommend big norm and rational
69:36or athletic or dynamic languages just
69:38sticking the 32-bit bit ince just leads
69:41to too many pitfalls you can't even
69:42negate a number and be sure to result we
69:44positives I mean this is nuts so
69:46sometimes you need the the mod 2 230
69:49towards intake make that be a separate
69:51type or something but for just ordinary
69:52general run-of-the-mill arithmetic the
69:54overheads and inefficiencies really
69:56aren't all that bad and the gain and
69:58programmer productivity is really well
70:00worth it have big gnomes and rational
70:01numbers
70:04John
70:09sure thing what pitfall is a common
70:13conception that we think everything is
70:14getting better i think that there's a
70:17actually made a book called designed by
70:19numbers two years ago this is a new kind
70:21of a very brough language to teach the
70:24designers how to program actually is
70:26going to make it how to teach java to
70:28designers or seated designers but I went
70:30to the coop and God visual c plus most
70:32six and install it and I couldn't get
70:34hello world to run for half a day I knew
70:36there was problems so I said well spent
70:38long explore them but since that I've
70:41been thinking about the fact that it's
70:42kind of like all of us are kind of
70:44looking for that kind of Suzanne Somers
70:45diet you know looking like what's the
70:47latest this let his language will save
70:49my life we never come canada and i think
70:51i had i hit the log last night went solo
70:53us 10 and i realized this is just next
70:55step just totally shocked so I'm
70:57depressed about that another thing is
71:01that one thing at least I I believe in
71:04is that we have to build to the
71:06self-destruct sequence its adult
71:08language we think about because people
71:10start to build a community around and
71:11it's a waiting for version whatever two
71:12three or four whatever I think if you
71:15build it don't come but it applies let
71:16it die somehow because then you can all
71:18stay free and thinking beyond the third
71:22thing is that a democratizing programmer
71:25everyone is your program robbed a habit
71:27recent experiences in the media lab I've
71:29noticed in all the administrative
71:30assistants can program in Java now and I
71:33just think you know are assimilated but
71:35then I actualize this is actually kind
71:36of a kind of an issue and that is that I
71:39see my kids learn typing in kindergarten
71:41now and I wonder they'll get it all
71:42guitar RSI électronique so I'm
71:44wondering what is a different model of
71:46programming that's what that's more
71:48humane and curious how does that happen
71:52okay that ends the first part of this
71:56panel we're going to move on to the
71:57question period and give preference to
72:00graduate students it's time so
72:07languages without election max have a
72:10present
72:15what do you mean cathedral the pattern
72:18that you have a ball algorithmic ability
72:23blinded
72:28Oh
72:30someone needs that it's not in language
72:33they're going to do it there's some
72:35other group the question is how do you
72:37want people's programs that are actually
72:40doing you know macro expansion and
72:42program manipulation or its language
72:44extensions how do you want those
72:46programs to look you want it to be and
72:48the separate program is doing a
72:49pre-processing step or you want it to be
72:52somehow integrated with the underlying
72:53language
72:56I I think it's I think it's a hard
72:59question because I mean yes it seems
73:02good that you want a feature like that
73:03but it's come very complex because you
73:08bring the reason it's complex because
73:09you started with a conflict a language
73:11of the complex index I'll comment
73:14further on that I haven't tried there
73:17are different kinds of so-called algo
73:19style languages there are some in which
73:22statements and expressions are not
73:24particularly differentiated I'm thinking
73:25for example at the Bliss programming
73:27language there are others were a fairly
73:28strict separations we've made between
73:30statements and expressions such as C and
73:32Java and in the latter sort of language
73:34if you want syntactic macros you should
73:36think about having macro calls that all
73:38of still fall into those categories one
73:39of the things that makes C macros often
73:41so awkward is the macro calls look like
73:44expressions and not like statements and
73:45to make see macro calls that behave like
73:47statements both semantically and
73:49syntactically is actually fairly
73:50difficult and so when we want to design
73:53a macro mechanism that makes that
73:54smoother I I know there are several
73:56papers within the last five to ten years
73:59on the subject Daniel wise work done is
74:03Microsoft there others going up macarons
74:09Dylan has Matt janzene yes okay then
74:13then how they did macros and Dylan we
74:17looked at more closely and I should do
74:19it too because I don't have it something
74:21right now it is it's kind of a nicety or
74:27it's really an essential features you
74:28want in provo language
74:31laughs and three personal
74:33I just can't make myself do it I end up
74:38doing outrageous things like going to
74:40work for any company that will hire me
74:42you know if they seem like they're going
74:44to go out of business start a company
74:46myself well let's show him this the
74:51language was my macros I find myself in
74:53effect using them in my pseudo code man
74:55hand expanding them and as a result
74:56getting code that might be somewhat less
74:58maintainable because some of the
74:59abstractions are too caring anymore yeah
75:01I find it below image doesn't have
75:02macros I write a preprocessor for it
75:04because what I want not necessarily
75:07implementing macros but doing what I
75:09want for a particular application
75:13apparently in terms of language design
75:17do you have any commentary on the role
75:20of the developed environment to come
75:22into the language
75:25most of us he writes next still code in
75:28you know GCC and divided with GDP
75:32threaded all emacs on a good day what is
75:36what is the role or shot what people may
75:39be nothing but what should be the role
75:40of the development environment wait wait
75:44when should I be thought about after
75:46that victory sign of the way
75:51rip flowers plastic spend half the time
75:56you would spend right making the
75:57compiler fast writing a good profiler I
76:00was more thinking I'm server interface
76:03and you want things like like who calls
76:06and who defines this method I mean these
76:12are sort of basic grep like thing I mean
76:13II max+ grep plus you know a few things
76:16that you write in he list is very close
76:19to being you know a sort of halfway
76:21decent but is very close to being at
76:24least as good as any sort of doing it
76:26based ide I've ever used well okay so
76:29here's my specific case an argument i
76:33have is i claim the one of the problems
76:36with s expression syntax is that there's
76:39no syntactic differentiation for
76:41samantha lee different constructs if
76:44looks just like a procedure invocation
76:46in terms of the Quran and when I had
76:50this argument one of the responses has
76:52been well you should just be in a
76:53developed environment where it
76:54highlights these distinctions in some
76:56color if equate this makes sense is can
77:00you consider the development environment
77:02is part of the language should you
77:04consider the moment environment spread
77:05the language when thinking about this
77:10I would say yes my experiences the more
77:15the more what I'm looking for feature
77:19whole the IDE that I had work with the
77:21more productive I can be but it doesn't
77:23get my way on the other hand I've been
77:25used to using stone knives for the last
77:2730 years and right I can easily slide
77:29back that low but maybe that doesn't
77:30mean that I should settle for I just
77:32think thinking about list I mean I find
77:34programming and lists very difficult if
77:35I didn't have friend you know a lot of
77:37her in the bouncing Quran and if I
77:40didn't have you know completion of long
77:43names things like that basic stuff that
77:45you max just gives you and maybe if I
77:48was forced to program some place that
77:50didn't have those two features the you
77:53know the language I would want to use
77:54might look very different it might be
77:56right length might be Python I might use
77:58short names instead of long names the
78:00language might have turned things so
78:01long incident so there's some relation
78:04but tools that help you see the
78:07structure of your program can always be
78:09very valuable for me the number one
78:11thing is just being able to get
78:11reasonably indentation so I can see the
78:13basic block structure what's going on
78:15anything beyond that is wonderful being
78:17able to tools to help you
78:18cross-reference to be able to trace and
78:20profile this will be very helpful so
78:22should it does if when I read programs
78:29if the indentation disagrees with the
78:31parentheses I don't notice I read them
78:34by the indentation in fact that's how I
78:35noticed when there's an infinite program
78:37I noticed by the indentation
78:39so I would agree the Indonesian should
78:41be significant for perhaps it should be
78:42redundant indication of significance and
78:45it's worth having it checked by a good
78:47idea but I want us to point out that the
78:49Ides are so complex now that they break
78:52so easily like I had a bad problem with
78:54the latest version of code where I bring
78:56out fine no whole thing and it goes down
78:58and your whole faith this goes away and
79:02they really change the way approach that
79:03that so you i'm going back to stone
79:05knives actually maybe there's something
79:07to this because i noticed a lot of
79:09programmers i talked to them and they
79:10sort of shamefully admit that they debug
79:13using print statements instead of
79:15whatever fancy debugging environment
79:16they have I I was come out of the closet
79:19I edit program to me I I cut and paste
79:23them into a brown into it into the top
79:25level which I will admit was the one
79:29really awkward thing I found about using
79:31high school for some programming which
79:32it was hard to drop print statement
79:34saying because it's purely functional
79:35phrase otherwise has fabulous an ID but
79:38he's almost out I've never had the
79:42batteries guy in my stone vice okay Sam
79:46speaking of functional programming this
79:48is this is really Berg ice or anyone
79:50else wants to about I'm interested in
79:52how practical you think that purely
79:55functional programs
79:56like a school or any of the other how
80:01much motors can be applied to it how
80:02much how much do you think they can be
80:04applied to regular a real world one foot
80:07on that
80:09I think they're perfectly capable I
80:12don't have the references again in my
80:15head right now to give you left off my
80:16head but some scans large applications
80:18been programming Haskell and going
80:20beyond just a compiler very far as some
80:23retraining yes once per visit our
80:25website is betraying their was
80:27preventing up to you it is especially
80:29different model from usual way but with
80:31your introduction of Mona has to support
80:33side effects you know it really is this
80:35wonderful thing where you can sort of
80:36open your left eye and it looks like a
80:37comparative programming and then you
80:39shut it open your right I'd you say oh
80:41well there's a functional explanation
80:43for it even though it feels inter
80:44comparative and it may be that just
80:46makes you feel better psychologically
80:47about using assignments and print
80:49statements all over the place than
80:52anyone elses panels I I think I think I
80:56concur with that I mean the monads were
80:58a good development and they they they
81:01sorted they helped blur the distinction
81:03between functional and carrot program
81:06ok I'm going to stick with the grad
81:08students while with self question
81:30hey I've heard great things about saver
81:33I never used it
81:45time travel
81:47Oh
81:52so I
81:57yeah absolutely agreed I've done for
81:59amount of programming on mcintoshes
82:00waiting have a plenty of people give us
82:02in the reference so summarize summarize
82:10she says that that a good programming
82:14environment such as for example the
82:15Sabre environment which was popular in
82:17the late 80s makes you so much more
82:19productive because it keeps track of
82:20stuff for you don't need to remember
82:21where your object files of God it just
82:24takes care of a lot of bookkeeping and
82:25makes you so much more productive why is
82:27that not now Universal I guess the
82:29question and and I agree I agree I think
82:31the main thing is that it's possible to
82:33do with the stone knives you can get
82:34something out the door the IEDs take
82:36more work to produce to make them good
82:38and so they tend to come along a little
82:39late but there are very good IDEs on a
82:41Macintosh I've used the code warrior
82:43development environment for example as
82:45well as the semantic think see ten years
82:49ago and i found my c programming much
82:52more productive in that environment that
82:53would have been using Emacs and CC any
82:57other guesses
83:06sure should ask me
83:09program representation format we
83:12consider doing something insane you're
83:14not that great sure unicode test should
83:20text be the representation or should we
83:21think about storing programs in some
83:23lightly compiled format and being able
83:27to represent them in text indented
83:29according to your preferences in the
83:31comments on our own pelvis are you
83:33asking what a programmer should have
83:34complete control of the way out I think
83:40I think well you can look at it like
83:42that what forces but the question is
83:44more whether whether if I get your code
83:46nice trivially reformat it the way I
83:49like thank you let's ask where the
83:56program should be thought of as being
83:57represented as a linear sequence of
83:59anything yes as opposed to being some
84:01more complicated structure on the other
84:02hand people seem to deal well with one
84:04to two dimensional layoffs and Lisa
84:07provides a basic structure it's easy to
84:09understand and hard to screw up a piece
84:12we would like to see unicode a part of
84:13me is afraid of what people would do
84:14with it i think i might settle for for
84:18iso latin 1 plus the two thousand coach
84:21age of unicode which has a lot of the
84:22technical symbols i'm not sure that i
84:26feel an urgent need for the
84:30serbo-croatians off abettin doing my
84:32programming but perhaps someone even if
84:33I disagree are you getting so many more
84:37characters something like this you know
84:41the small talk environments from the 70s
84:43where you know the code really is stored
84:46as clearly as almost as compiled stuff
84:48and it's brought up very dynamically and
84:51that's that really only lives inside of
84:52data structures inside it really lives
84:55on the inside data structures inside of
84:57effectively up a persistent process
85:04you know my bias is to think of I would
85:07like to have at least the option of
85:09having programs be you know represented
85:12as documents some house I'd like be able
85:14to publish them in a book or something
85:16so at least you have to be able to
85:17stract a linear representation of the
85:21program and I yes it would be nice to be
85:23able to put pictures in the program's
85:25might even be able to nice it might even
85:27be nice to be able to put diagrams with
85:30boxes and arrows and call that a program
85:32somehow and have that interpret put some
85:35meaning on pictures am I going to
85:38further than you wanted to ask you about
85:39good hi the thing is the thing is that
85:43the the kind of support structure you
85:46would need in order to make that kind of
85:47thing viable I think would just be so
85:50overwhelming that it would kind of top
85:52alone under its own weight now I'd be
85:54glad to be proven wrong but it
85:56contradicts you know my claim that
85:59programming language implementations
86:01should be rewritable so that's why I
86:05have a little difficulty with it might
86:07not be that hard to write a compiler
86:10that takes in say framemaker files or
86:14adobe illustrator files and things like
86:16that and has specific environments that
86:19are defined that it goes and looks for
86:20and when you say let a equal this
86:22picture you know it's not that big a
86:24deal mostly just being able to embed all
86:26these different data types within the
86:27given structure of your program text and
86:29get assign a meaning to them so yeah
86:31give it a try before we go on a nice to
86:3430 now
86:37Palace can stay we're happy to go on for
86:40more time and open up two more questions
86:42but if you have to leave we understand
86:44so Mike very no importance of software
86:50to the whole world system it's kind of
86:52surprising that venture capitalists
86:54don't want to sort of see program
86:56advance to a state I think it's
86:58interesting that the most the companies
87:00that are going to be producing the
87:01languages may not even say that they're
87:03doing a language for example vostri com
87:06they got a hundred and forty million
87:07dollars of venture capital money talking
87:09about dynamic business webs and all this
87:11stuff and what they're really doing was
87:12doing a programming language environment
87:13but they didn't know it but that was the
87:15way to sort of speed it to people where
87:17they didn't see that it was a language
87:19it was something else and so that's kind
87:21of a technique how do we get the good
87:23languages out there maybe is that we
87:25don't say if they're a language you
87:27don't need these yeah see you develop
87:29language is just fine for free yes it's
87:35it's a funny situation how many people
87:36who know what's you know the history of
87:39programming languages over the last 30
87:40or 40 years 30 yeah for 40 years um will
87:45you know they'll say huge amounts of
87:48research money has been poured into the
87:49problem of you know improving
87:51productivity and coming up with good
87:52languages and nothing is come of it so
87:54you know we're not going to put any more
87:56money into that you know let the people
87:58doing Python or whatever solve solve the
88:01problems with the free software folks
88:03you know basically all of us and whoever
88:06you know fix the problem in an organic
88:08way but but there's no money in it and
88:10there's this and there's no good sort of
88:15argument that you know that that it's
88:19even possible to increase productivity
88:22so that that's the way I see what's
88:24going on as far as the funding
88:26situations it goes but and then as far
88:29as thing you know all these companies
88:31that keep getting funded to do
88:32programming language research and
88:33different languages that's just you know
88:36people who are good salesman and
88:38and and and funders who don't know the
88:41history oh sorry I'm a cynic obviously
88:49I question about the embedding of
88:51programming environments within social
88:53environments and it sort of have to do I
88:55think with something everyone in the
88:57panel has talked about at one point or
88:59another the company that was just good
89:01enough to lay me off had a wonderful
89:04sort of visual editor for a rules-based
89:07system that involved in something
89:09terrible and server-side programming but
89:11the thing is that it allowed a manager
89:13using a little picture based editor to
89:15write a set of rules and then at that
89:17point we could change the underlying
89:19structure underneath could write it in a
89:20different language we're using job and
89:22now quoting what we but the manager
89:26would have that environment then a coder
89:28could go in and start changing text
89:30files and so the thing is that each
89:33person at a different level had a
89:35different picture into the system that
89:38was being built so the managers able to
89:41sketch something out the coder was able
89:43to handle special cases boundary cases a
89:45lot easier and I was wondering what
89:47extent is work being done in this so
89:49that people who don't want a program
89:52know and probably are better off for all
89:55of us not programming and get some sort
89:58of initial input and then that can be
90:00carried on through through the whole
90:01cycle are people looking at this
90:06that's a very productive actually had
90:09not aware of that kind of area
90:13because we've got you know we've got to
90:15be the social system as well as the
90:17information system
90:21was I know seems to what a lot of people
90:25want is a magic wand or the genie in the
90:28bottle which is this thing in fairy
90:30tales that causes something to happen
90:33that makes you happy without your having
90:35to think about the details of what it is
90:36that you want well this case it's
90:39someone who's waving a wand and then
90:41bill said says what they want to happen
90:44and provides a sketch for it and then
90:45people and dozens of magic trolls make
90:48it happen under the table or you don't
90:49have to say yeah programming is work I'm
90:51sorry yes so I have a dispro spy reasons
90:59I have punished in music and electronic
91:01music and recently I learned about the
91:04sea sound system that actually come from
91:06media lab and what sea sound system
91:09really is is it's a compiler which takes
91:11a programming language and produces a
91:13sound file from that programming
91:15language and actually it's a if you're a
91:17student studying programming language
91:18it's a very interesting programming
91:20language because it it has this organic
91:22feel to it means but my question to you
91:25in the relating it to the dynamic
91:28languages seminar right here is the fact
91:30that what people want to do apparently
91:32is due performance and so they want to
91:35have a lot of computing processing power
91:39at their hands and so they can do all
91:43the things in real time so my question
91:45is about making these kinds of systems
91:49that are producing music dynamically
91:52change as you're going on so the idea is
91:56you're having musicians make some input
92:00to control these things and that they
92:02want to change things like algorithm in
92:04fact that can so I guess so how much a
92:07work people doing and actually applying
92:10the techniques of dynamic programming
92:12language and working those kinds of
92:15codes to look for aspects of things
92:19has there been a Lincoln High anything
92:22you learn more the expert that's good
92:24could be okay let's sit down well
92:29there's a graphical programming language
92:31called max but how's that aspect all
92:34those doesn't have the power textual
92:37programming language
92:38there's there's work at CMU in that area
92:42there's no quit week small talk of a
92:45source project that allows you to
92:48generate music on the fly and modify it
92:51I'm not aware of anyone that has been
92:55ill to do both the high level scripting
92:58and the low level DSP in the same
93:00language so that's the sort of that's
93:03I'm actually interested in doing that
93:06it's really real time bangin program
93:09which is great that's where max came
93:23already teach one
93:25for life
93:26yeah for they do I guess they're an air
93:30pump but
93:32terms of real time it was mostly
93:34ask Evie
93:36it's hard feelings
93:43almost
93:53orbitz help anyway CMU's working on
93:59something you might want to look at in
94:01the area of computer-supported
94:02performances that cord has a new
94:04synthesizer out called karma there's a
94:05review of the latest keyboard magazine
94:07and reading that review maybe itch to
94:09get a programming interface on the front
94:11of it but this proprietary i think is
94:12sealed off at this point but it's a very
94:15interesting looking system where in
94:17response to your midi gestures it tries
94:19to think of other things that would go
94:20along with it and that makes us sound a
94:22little bit like band in a box or you
94:23don't wanna be sad sound damn things but
94:25apparently has gone a large step beyond
94:27that's worth taking a look at so let me
94:31make this a little provocative the guys
94:33sound like you're living 10 15 years ago
94:37as if way we we wrote we actually wrote
94:41programs in the real world is the way we
94:43teach them in six double or one namely a
94:47well-defined base and to build up from
94:49that but in fact my experience recently
94:53is
94:54people don't write programs they gobble
94:56them together so for example I'm
94:59teaching a medical computing course one
95:01of our students gave a presentation this
95:04morning of a project he had done to the
95:06course in which he took something that
95:09is able to take an hl7 data stream and
95:12turn it into XML and then add some XML
95:16parser that was able to interface with
95:19some design environment which she's been
95:23mapping into a relational database
95:24structure and then it had something else
95:27that's sorted and in for mix and
95:29something else that pulled it out of
95:31there and of course these things are all
95:33implemented with no rationality
95:35whatsoever they have bizarre api's if
95:40any positive written in different
95:42environments in different languages and
95:44the hard part of doing all this is not
95:47the 150 lines of code that he wound up
95:49writing but it's figuring out how to
95:52glue this god-awful mess together and
95:54how to make it even slightly robust
95:57enough that when one of the
96:00he doesn't have control over heels over
96:02debt this whole thing does you over that
96:05and I I don't see very much support for
96:10that style of programming and yet that's
96:12what I see a lot of people drink now
96:16in some programming environments again
96:20i'm thinking the macintosh that familiar
96:21with it some of the high scale
96:24applications actually go to a great deal
96:26of trouble to make themselves scriptable
96:27and provide a programming API so you can
96:30for example you can write programs that
96:32tell illustrator what to do instead of
96:33using mouse clicks that kind of thing
96:35and to some extent those things can be
96:38pulled together with Apple script made
96:39to work in a reasonably smooth manner
96:41but I agree that a lot of other
96:44applications are built with no thought
96:45whatsoever to a programmatic interface
96:47and you just have to cobble together try
96:48to pretend you're person and make the
96:50gestures and it's awful like repeat one
96:54would constitute a solution to this
96:55problem hey you guys know it's just
97:02striking to me then that if you ask me
97:05where am i suffering right now from a
97:08lack of solutions in the programming
97:11arena it's in this type of environment
97:14and not that you know I my Lisp is
97:18perfectly fine for doing the things that
97:20that I've been doing within 25 years I
97:23wanted to say one thing one of the
97:25panelists who was unable to come today
97:27like my band started coming called over
97:29on and they are specifically addressing
97:33gluing together these complicated
97:36libraries and making them work with
97:38graphical programming so you might want
97:40to look at in their work
97:43that was great as is that is historical
97:47dynamic language is designed question I
97:49don't know if anybody on the panel hood
97:50was there I heard that when scheme
97:55design either for our for us I guess the
97:58discussions that led up to that there
98:00was an agreement that decisions would be
98:03made by consensus and if they couldn't
98:05be making couldn't get consensus then
98:08they wouldn't make it in and heard that
98:11that really slowed down the adoption of
98:14anything slightly ambitious so question
98:16is you know was that true is that just
98:18urban legend and and and what might have
98:22been in scheme that had been adopted and
98:24just if anybody was actually there had
98:26any comments on that process
98:29I thought as I remember starting in when
98:33the sort of committee started doing it
98:36stuff the agreement was that that
98:39decisions basically had to be unanimous
98:41right I think that's I think that's how
98:44it went so it wasn't just consensus if
98:45there was one person saying now the you
98:49know this record package is terrible
98:50because I think and then they go into
98:51whatever it's surprising that anything
98:57got done at all but but I I think that's
99:01those are the rules when you know you
99:03know whenever you set up a committee you
99:05basically can't change the rules from
99:07the point that committee is set up
99:08alright so those liberals or minerals
99:11and have it became you know how would
99:13you change the key I think at the time
99:15for the for the gold for the goals that
99:17were there in 1984 they were good rules
99:19I think that that structure may have had
99:24started having problems you know in the
99:26late 80s and and it's basically a
99:29standstill now nothing can happen at
99:31this point
99:32so I astronaut something it's not the
99:35official view of the committee no this
99:37is this is a purely personal view but um
99:41what's new so I mean there were certain
99:48things where there was it seemed like
99:50there was sort of one or two people who
99:52were holding out they had very definite
99:54philosophical objections to to the way
99:56features were formulated and then you
99:58know but nobody else wanted to doubt
100:00their formulation and so the I mean
100:03everyone who knows who's followed this
100:05knows what these things are and that's
100:08the sort of the way it happened it's
100:11also worth pointing out that scheme at
100:12that time developed the context where
100:14they're always an alternative people who
100:16really wanted a version dialect of lists
100:18with explosive feature creep had common
100:20lisp return to remember the committee
100:23was formed with the express purpose of
100:24allowing the three or four groups
100:28geographically separated groups to read
100:30each other's coat and nothing to an
100:32executing code and nothing to do with
100:34standardization or anything like that
100:35that was its only goal and so no the
100:38group wanted to form no wanted want to
100:42set up a little community on that basis
100:44it's worth pointing out actually that's
100:46the original goal of Haskell for example
100:48Chris simply said that everyone could
100:51read each other's papers
100:53if you look in the preface to Friedman
100:58and Springer scheme in the art of
100:59programming I wrote a foreword for that
101:01book and as part of that I did the
101:03exercise of looking at these standards
101:06for a dozen different programming
101:07languages and merely counting the number
101:09of pages in each standard and
101:10interesting enough that time about ten
101:12years ago the two ends of the spectrum
101:15were bracketed by scheme and common list
101:17at 50 pages and a thousand pages and
101:20interesting enough diboll and COBOL were
101:23the next ones in and then you have the
101:24algebraic languages in the middle so
101:27take that for what it's worth sorry rich
101:31pl1 he'll ever stop somewhere in the
101:34middle languages large expense was any
101:37of that a function of poorly or better
101:39done documentation oh absolutely i mean
101:42take these numbers but with a big grain
101:43of salt early within a factor of two or
101:45four but but still is interesting that
101:47that the list people had alternatives at
101:50each end rather than being closed in the
101:52middle and there was value of that you
101:54know my question is on I thought it was
101:58very interesting John's comment about
102:00hardest being interested in coding but
102:03coders maybe not been yesterday
102:06and I'm thinking about it and maybe the
102:09artist seems like another way of
102:11expressing another tool to express their
102:13art but I found out like many people
102:16were like really really crazy hackers
102:17really good hackers are actually a very
102:19artistic and then do a lots of thing so
102:21there's lots of coders and some of them
102:24artistic I think this pool of people is
102:26maybe the more artistic side and that
102:29was sort of a point that I've been
102:30trying to make it MIT actually it's
102:33actually quite hard because at MIT art
102:36is supposed to be a pansy activity or
102:39you take a break and paint or something
102:41like that and so it really is an issue
102:43of how to review artistic practices in
102:47the technical domain and wrap the next
102:4920 years something will happen to where
102:51people who are at this sort of strange
102:53hybrid state can have a kind of
102:56credibility most and what I thing else
102:58but i'm waiting for the actually it
103:01takes time art is something that gets
103:03declared in retrospect Leonardo got paid
103:06the same amount for paintings paintings
103:07as the people who made the frames did
103:09for making the frames back in Leonardo's
103:12time it wasn't considered nearly as
103:13prestigious as his work is now
103:15considered and I wouldn't be surprised
103:17the things that's true they had really
103:21good be still you were going to invest
103:24in one or the other I would have
103:26invested in the art rather than the
103:27frame I wouldn't be surprised if the
103:29stuff people are cooking up right here
103:31in you know a couple hundred years from
103:33now is considered to be the cool thing
103:35that's being done
103:36whether it's called art or not who knows
103:38but I actually study about I study
103:41painting or is nice for a while and i
103:42can tell you people in the programming
103:43languages world are working a lot harder
103:46and there are a lot more imaginative
103:47than people in art world
103:54really interesting design features you
103:57think will be worth looking at the
103:59design of just for enlightening
104:04you know the question was what obscura
104:07programming language is out there that
104:08Prez have particularly interesting
104:10design features that deserve to be
104:11better known satin adequate summary the
104:16list that was originally described in
104:18McCarthy's paper in 1960 i recently went
104:21put them out in that instance really
104:22actually very cool to see what I mean
104:25it's he sort of was it's a language
104:27whose it was produced not by someone
104:29trying to design a language but someone
104:31was just trying to axiom at eyes
104:32programming and that's what you get out
104:34the end when you try and have a few
104:36axioms and try and make this language
104:38you can consider right everything else
104:40in
104:42I know that's not what you expected here
104:46I can think of three things sort of
104:52opera potoo that what is a there's a
104:54language design effort going on now for
104:56a distributed secure scripting language
105:02basically and it's it's at I rights org
105:05language is called eat and they're going
105:07for for popularity if you're interested
105:10in distributed scripting then you should
105:12go there very very nicely integrated
105:15capability distributed capability
105:17security I think category theory is a
105:20great language should be part of any
105:22language designers repertoire and but
105:26it's I really think of it as a
105:29programming language it's not a part of
105:30mathematics it's it's a it's a notation
105:34and for some reason your question made
105:38me think of a document that I ravit I
105:43reread recently that I that I had sort
105:45of forgotten about and I think everyone
105:47should look at which is perlas
105:48programming epigrams and if you haven't
105:52looked at those you should do that
105:53probably if you do a web search for
105:55perlis TRL is an epigram you'll find it
106:00but a wonderful set of principles for
106:03programming for languages
106:06many of the most interesting programming
106:08languages designs to me you've actually
106:10based on some piece of mathematics it's
106:12interesting in its own right it might be
106:14embodied in a programming language in a
106:15different way and might be worth looking
106:17at for example eight pls who mentioned a
106:19couple of times an APL is largely
106:21inspired by linear algebra and
106:23generalizations they're out looking both
106:25structures of data as well as the way
106:26operations interact with and and you can
106:29combine matrices interesting ways
106:31snowball which is really sort of an
106:33embodiment of regular expressions out
106:35the wazoo that's have another one of
106:41mine we got to think of something
106:43nineties I think its value going back
106:47and looking at earlier designs that have
106:48interesting quirky features and trying
106:50to figure out what parts of the more
106:51worth saving and why this program in
106:53languages i died or didn't make it in
106:55one way or another prologue yes based on
106:58essentially a particular way of using
107:02logic clauses horn clauses to express
107:04programming languages and the
107:06implementation one can argue about and
107:08whether whether chronological
107:10backtracking other kinds of backtracking
107:11the right thing to do with the idea of
107:12using logic was a programming language
107:13was pretty interesting let me also
107:16mention a Tico which you know I think
107:22this editor but it's actually a very
107:24peculiar programming language which is
107:26based in al art in several ways on
107:28finite state machines both in its
107:30program interpreter you've chunk on one
107:32character at a time of each character is
107:33a command by golly but it also had added
107:37ways of defining sub finite state
107:39machines that would process the text in
107:41various ways at least the MIT version
107:43here I guess had a looper now we're
107:46going to take their just three more
107:48questions
107:50I think you've been talking about a bit
107:53about past programming languages and we
107:55are not yet sure about what the future
107:58computer science is going to be like to
108:01teach programming languages to
108:03undergraduate I'd like to see that I've
108:07actually thought about it quite a bit
108:08and I've never been able to answer the
108:10question very well and you mainly be
108:12talking about the past rather than the
108:14future what can we do in the future and
108:17can you write something that relates to
108:20what you talked about that will help us
108:22do good things in the future about
108:24teaching programming languages on the
108:26graduates sorry teaching programming
108:29languages and teaching program do no no
108:31no we assume the petite programming
108:33preparing to teach the quality of
108:35programming languages the fact that
108:37programming languages were very widely
108:40appreciated for example palaces turning
108:44award was related to programming
108:46language work many people received
108:48awards but the programming languages
108:50were a very good topic and now they seem
108:53to be somehow in between and can we
108:56return the field so that it will be as
109:00important in the future as it was in the
109:02past well you know the ACM is
109:05recommending against spending time and
109:06undergraduate curriculum curricular on
109:09programming languages they think it's a
109:11very peripheral subject so x sort of
109:14changed as far as the prestigious so
109:16that maybe you can do something to
109:18change what the is here
109:23it's not about programming languages or
109:25the programming teacher I think he was
109:27talking about teaching the art of
109:29programming languages as opposed to the
109:31art program I'm not sure that
109:35programming languages should have the
109:36prominence that they had 30 years ago
109:38you know much as I love them it may be
109:40that programming languages are like jazz
109:42or perhaps they're more like ragtime
109:43that had an important place in history
109:45and it's important that people still
109:47study it for how it will feed forward in
109:49the future but it may be that the thing
109:51of seeing 50 new programming languages
109:54announced per month or per year it may
109:56not be a healthy thing in the future I
109:58think it is important we understand
109:59language design principles and that a
110:01few new languages be designed so we
110:03don't overlook any possibilities but we
110:06may be settling into a period of
110:08relative stability let let us say and
110:10that may be important to form a solid
110:12platform for moving on and other things
110:14in the future if I were having to learn
110:15a new programming language every month I
110:17wouldn't get much done in the way of
110:19applications above that level I think
110:21you're absolutely right but the question
110:22of how to teach what really needs to be
110:24taught in that area even if it's only
110:26five undergraduate course hours and you
110:28know in a bachelor's degree or something
110:32I think we don't know how to do that but
110:34the this we haven't distilled the ideas
110:37properly and I mean I spent a lot of
110:40time trying to do that with the course
110:42and MIT and I I think we didn't do a
110:44very good job and it's it's very hard to
110:47kind of you know crack this intellectual
110:49in a kind of nice parsimonious way it's
110:52important to teach it but it's also
110:54important to realize that not every
110:56graduate we turn out what we call the
110:57language designer I think it's also an
110:59issue of need I did some experiments to
111:01Japan around seven years ago in design
111:04schools to try to get to create a
111:07program or the more computations into
111:09the curriculum and one thing I started
111:12doing with the sort of a first-year
111:14class was I have a one student sits down
111:17and the three students stand up and they
111:19become pens and this a student has to
111:22draw a picture of course I using their
111:23hands so they would devise this hole
111:25through method of drawing onto the
111:28canvas about their own hands and we
111:30expected exercises of designing
111:31languages to support that activity
111:33answer
111:33you did over two years but that was a
111:36need for that they're thinking I was
111:37relevant there but maybe now it's a nate
111:40is different I'd like to make one more
111:42follow-up which was I would like to turn
111:44around and contradict myself and comment
111:46that according to a another talk that
111:49perhaps some of you heard me give I
111:50believe that every programmer is a
111:51language designer in the sense that as
111:53soon as you've written two or three
111:54hundred subroutines you've made a big
111:56enough vocabulary that you're now
111:57working in a new language anyway want to
111:59give some thought instructor that
112:00language I think programming language
112:02education you can think of that partly
112:04defensively all right you want as many
112:06people as possible to have to have
112:09experience and good ideas about
112:11programming language design because so
112:12many of them will be designing languages
112:15that you'll have to suffer with later
112:17all right so I mean it's easy to think
112:21of examples of that where people just
112:22made languages they were just uninformed
112:24right because they didn't learn any of
112:28the history or any of the concepts and
112:30and now you have millions and millions
112:32of people and billions of dollars
112:34invested in terrible languages and if
112:37you the most valuable parts of having
112:40done CS undergrad at MIT when the
112:41classes that were kind of language
112:42agnostic and
112:44nowhere I could do one problem set
112:46problem less than one job time whatever
112:50but it's hard to get a lot of people
112:52would take advantage of that I mean I
112:55was only kind of within auditing
112:57languages
112:58comments
113:00time to get students to that by choice
113:03and people had met from other kind of
113:05top universities never had that option
113:11you know I want to push back that Paul's
113:13comment about clients being a lose don't
113:18you think though over time that it's
113:20inevitable for economic reasons that
113:22more code is going to be pushed on the
113:24client both because the cost of putting
113:27stuff on the server is very high also
113:29because there's going to be a lot more
113:30unused power on client machines and not
113:33on servers and also because of latency
113:36latency is not going to be improving
113:37over the future the fabulous comedians
113:40just let me be fabulous between if
113:42everybody would be honest you wouldn't
113:43have to lock your door you wouldn't have
113:44to buy us lock hardware or stir it
113:46around these keys and credit cards and
113:47stuff you can lose but you know that's
113:50just not the way the world is I think
113:54you know if you had some sort of scent
113:57if you had some sort of if you were the
113:59Soviet Union right and you could just
114:00tell everybody what they were going to
114:01have on their computers then you can
114:03make this happen but it's hard to see
114:05how it would happen today even if
114:06Microsoft riders your mouth yeah you
114:09already relying on this right now all
114:11I'm all I would ever dare assume is that
114:14you can show HTML pages in the forums
114:16work time necessarily work
114:19and he certainly wouldn't assume that
114:21JavaScript works for example it seems
114:23like people who write software that
114:24depends on JavaScript are always
114:25eighty-five percent done but hTML is
114:28ubiquitous at least once a day I
114:30download some page that crashes my
114:32browser and switching to the other
114:35browser doesn't help always something is
114:39thinking of win for everyone who
114:41implements it then you don't need
114:43central planning to tell everyone to do
114:45it if there's something that you know
114:47some sort of protocol negotiation sort
114:49of thing that could be on every client
114:51it would find its way on every client or
114:54these all talking at once eventually and
114:56no one you can write the server so that
114:58it doesn't assume that it's there but if
115:01it is there it can give you a win well a
115:04new client will usually do protocol
115:06right for talking to the survey new
115:07protocols just don't get invented that
115:09often there's like send mail and then 20
115:11years later HTML HTTP and you know the
115:15next one is doing another 20 years maybe
115:17that will be your clients
115:23me evil eye upon all kinds of things on
115:25people being on client machines he's
115:27expect everybody's got IP now I I mean
115:29eventually things end up on the client
115:32and enough so that there's an
115:33economically for you to zoom it's there
115:38this sort of a spectrum right i mean
115:40most of us have browsers that support to
115:43some extent javascript but I I'm
115:46probably not the only one in the room
115:48that hasn't downloaded the flash
115:50extension and just ignore sites that
115:52require it that's true I'm I need points
115:56that when you're running a site you have
115:57to pay for your servers you have to pay
115:59for your bandwidth and that costs money
116:02and you've seen a lot of companies go
116:04down in the last couple years for this
116:05exact reason sorry go down because of
116:08bandwidth costs because of his mail for
116:10such an operational office or to version
116:12costs very good
116:16so you've each mentioned some aspect of
116:19dealing with huge amounts of information
116:22organizing information is a mobile web I
116:26can you comment on the relationship
116:29between library science and languages or
116:33expressing data XML for example or for
116:38metadata compared with languages for
116:43programming particularly dynamic
116:44languages and should they be different
116:48things or should they is there a
116:51continuum and and how do they relate
116:53other features of dynamic languages that
116:56make them particularly suitable for
116:58dealing with with dealing with
117:00information and that information
117:04system
117:08but libraries have to be very
117:10conservative about what what they do
117:15they want it they want stability in data
117:17structures they want stability and
117:19protocols they want so I think there'd
117:24be a big tension between well I I don't
117:28have I not really qualified sings
117:35you're raising point I agree that it
117:37would be an awfully good thing if
117:39librarians and database designers talk
117:41to each other more than they have
117:42historically but since i'm relatively
117:45unfamiliar of library science except for
117:46knowing that it's a good thing we get
117:48librarians and they have to be extremely
117:51conservative that they're trying to make
117:52sure that their information is is going
117:54to be readable in 500 years right and as
117:58far as librarians are concerned there
118:00there still isn't a digital archival
118:03medium right that's an extremely basic
118:06thing that they're missing if someone
118:08who's worried about that is not going to
118:09be talking is not going to want to talk
118:11to you about to you know dynamically
118:13changing your XML schemas since I've got
118:16each of you dudes they mentioned
118:18something about problems that we started
118:21being that arrow them probably different
118:23from librarians problems though the
118:25company's problems are individuals
118:28sorry okay let's thank the panel good
