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

so that led
34:43to a sort of a first pass which we call
34:46flex and since nobody ever does anything
34:50just for beauty this flex language came
34:57out as a reaction to a project that I
35:01got involved with which is the build a
35:04little desktop computer with my friend
35:06Edie Cheadle and that's what it looked
35:09like that's actually a picture from its
35:10own display and it had kind of an
35:13object-oriented version of what peter
35:15deutsch had done and it had windows was
35:19far from the first system with windows
35:21sketchpad had a window I was one of the
35:24first with multiple windows and it had a
35:27semi graphical interface and it was a
35:32desktop computer for very special desks
35:35namely those made out of steel so
35:38weighed about 400 pounds and so the
35:43thing is that the integrated circuits
35:44back then were so small they only had
35:49fact we can look on this chart here see
35:53that back in 1967 there was maybe a
35:58couple of hundred elements on an
36:00integrated circuit and we built that
36:01machine because there was a rumor of a
36:03512 bit ROM the general Instruments was
36:07going to make but we also knew about
36:11Moore's writings he started writing in
36:1365 and we
36:15a lot of faith that what he said was
36:16going to happen if you're interested
36:18this is Moore's original graph plotted
36:21out where you said it's going to be a
36:22factor of two every year and later he
36:28said well it's not going to be worse
36:29than a factor of two every two years
36:31that's that plot and here's what
36:33happened to ram up until now so that's
36:38pretty good it's about as good as having
36:41Jupiter be where it's supposed to be
36:43after seven years voyage and it's
36:48interesting that Deccan and IBM knew all
36:50about this but thought that that would
36:52give them more margins on their
36:53mainframes let's sort of pink thinking
36:59then pretty much thirty years ago to the
37:04day right now I came out here because I
37:08had heard from Marvin Minsky about
37:10Seymour papper and what he was doing
37:11with children I went out to bridge
37:14school and saw that what Seymour was
37:19doing he wasn't just fooling around with
37:20the kids
37:21he wasn't just giving them games to do
37:26he was actually teaching them advanced
37:28mathematics in a way that was really fun
37:30for them and one of the typical programs
37:33and logo back then was to make a circle
37:36repeat over and over again go a little
37:38internal little and I think everybody
37:41here is supposed to take enough math to
37:43realize that that's the differential
37:45equation of a circle in curvature
37:49coordinates or inertial coordinates
37:52facti what he's saying here is the
37:56curvature of this is some constant and
37:58if you have a constant curvature you're
38:00always going to get a circle and jaysus
38:02that's an unbelievable and so here are
38:04the kids picking those numbers and
38:07getting a little turtle to do this this
38:11completely blew my mind and going back
38:16on the plane to Utah I started sketching
38:18this machine because I was thinking this
38:20is the best what Seymour is doing is the
38:22best idea anybody's had this
38:24half-century because he realizes there's
38:28something special
38:29about the computer that's connected with
38:30thinking and a way to get that something
38:34special out to the general world is not
38:36to try and teach adults that because
38:38they will be too recalcitrant they'll
38:43try and turn it back into pink things
38:47like paper documents but what Seymour is
38:52doing is realizing Yap but way to do
38:54this is teach the powerful ideas to the
38:55kids and you might cut out a hundred
38:58years of bumbling towards what this new
39:02set of ideas is and this just just
39:08absolutely blew my mind I've been
39:10working on the Danny Barbara once said
39:12the do's do we have to pay for having
39:13fun with computers is that we have to
39:16work on our first big project for the
39:18rest of our life now because I also
39:29liked history I knew something
39:31interesting about the last time a medium
39:34like this appeared and that is that
39:37there were 371 hand written manuscripts
39:43in the Vatican Library in 1400 that was
39:46one of the largest libraries in Europe
39:47how do I know it was 371 because you can
39:50count 371 things reliably there was so
39:55few of them Gutenberg and they cost
39:58millions of bucks apiece and today's
40:00money Gutenberg came along $60,000 so in
40:04the way I was thinking of it oh yeah
40:05that's kind of a workstation that's like
40:07my Flex machine thing and then Aldous 50
40:11years later around 14.95 to 1500 came up
40:14with a little book why is it this size
40:20same size that books are today it's
40:22unbelievable that the size of books
40:25hasn't changed that's because the size
40:28the books are today is the size that
40:30saddlebags were in Venice in the Year
40:331495 because Elvis actually went out and
40:35measured them because the first 40 books
40:38he published from his press were called
40:40the portable library
40:42and they were not about religion like
40:44the Gutenberg Bible was but they were
40:45about philosophy but then something
40:48unusual happened that the result of this
40:51revolution didn't start to bear fruit
40:54for hundreds of years wasn't really
40:58until the 17th century that we see it
41:02bearing fruit in science and to the 18th
41:05century in politics that is a long lag
41:08and so the thing that several of us
41:12thought about in the 60s was wow we're
41:15going to be able to get through this
41:16stage also in 50 years Moore's law says
41:20we can do a Dynabook before the year
41:222000 in fact we thought we'd be able to
41:25do it before the year 1985 and the
41:29question is is are we going to have to
41:31wait another 100 or 200 years
41:33for the fruits of these new ways of
41:37thinking to actually spread out into the
41:39general population and the thought was
41:42well let's just do let's really pay
41:45attention to what Seymour is saying and
41:48see if we can get it out earlier so
41:51Xerox PARC came along just at the right
41:54time ARPA funding had gotten muzzled
41:57because of the Mansfield amendment and
41:59so Taylor's skimmed off a lot of people
42:02from the ARPA projects around and this
42:07was a proposal to try and work on a
42:10machine it looked kind of like this and
42:14there's a big problem now we're talking
42:17about khat we're not just talking about
42:18a little machine for kids we're talking
42:20about something cosmic something big the
42:23ARPANET was being worked on back then
42:26there's this huge problem which is
42:29nobody knew how to build scalable
42:31software or indeed scalable almost
42:33anything else except it look like the
42:35ARPANET was going to scale it looked
42:38like it was going to scale because it
42:39had a message passing architecture just
42:44as the nascent
42:45object systems that we're working on and
42:48we had this really good set of examples
42:51of the difference between something like
42:52system/360 now nowadays you'd fill in
42:55Windows 98
42:57or almost any piece of Microsoft
42:59software but basically well that's like
43:07getting applauded for saying the devil
43:09is not nice nothing controversial there
43:21but the thing is that all of these
43:24software systems done by hand tools and
43:26weak ideas tend to resemble pyramids
43:29that is their big garbage dumps that
43:32somebody has plastered over with
43:34limestone and we had some wonderful
43:38examples I was a big fan of building
43:41complex structures so I knew that the
43:42Empire State Building had actually been
43:44physically fabricated in less than 11
43:47months by less than 3,000 people I also
43:50knew the Empire State Building from the
43:52time they decided to do it to the time
43:53they occupied the building was less than
43:5520 months okay and when I thought about
43:59that I was thinking gee whiz we could
44:01never we couldn't must we couldn't
44:04organize 30 30 people 300 people or
44:063,000 people to do anything of any
44:10complexity and software somebody held a
44:12gun to our head we just don't have the
44:17way of doing it and so this is when
44:21these kind of situations are when late
44:24binding starts becoming a more and more
44:27important idea and if you think about it
44:31almost every advance in software has
44:33been a kind of late binding and I
44:35believe this statement is just as true
44:37today as it was back then as that is we
44:39just don't know enough we don't have an
44:42engineering discipline and so even when
44:44we're doing something that looks like
44:46the project that we did the last time it
44:48turns out to have a huge learning curve
44:51and the problem is if we're using an
44:54early bound system back in the old days
44:57like algal or Fortran or COBOL or
45:00machine code nowadays like C or C++ just
45:05as you start learning something the
45:07system has gotten too rigid to be
45:09reformulate
45:10so you say no we have to get the
45:13deadline done let's leave those ideas
45:16until later those ideas ever get in
45:19forget it
45:21so coming back to Lisp here so here's
45:26the other great two great programming
45:28language conceptions of the 60s Simula
45:31and Lisp and Lisp was really early
45:33McCarthy wrote some of his first stuff
45:36about how to do this in 59 and actually
45:44I brought one along I won't admit how
45:48many of these I own but what's wonderful
45:53is mit press still still sells these I
46:00don't know why but there are other
46:05people besides me who buy them but see
46:08if you turn to page 13 here Carl knows
46:15this page very well Harvey knows this
46:22page very well so this is like the
46:24entire world this is like Maxwell's
46:26equations here it's one of the greatest
46:28things anybody ever did for us because
46:30it's not just doing a Turing machine
46:32they are ran for long time
46:34I think it's cool about this this is a
46:35Turing machine that has slope and that
46:39you can get from here to where you want
46:41to go very very rapidly and actually
46:45this is a fun thing about being part of
46:48an art because I as I was talking about
46:50this I could feel chills going up and
46:51down my spine right now because this is
46:53real power intellectual power and
46:57realize that if you could take what was
47:01great about Lisp and add this biological
47:05ecological way of doing things to it
47:07you'd have something pretty darn
47:08interesting and so the second crossroads
47:12was kind of taking this flex machine
47:14which is not very Lisp like and adding
47:16some Lisp and logo ideas to it to get a
47:19children's language that adults could
47:22program in as well
47:24as we like to build Hardware at Xerox
47:26PARC we got a new machine and then a
47:31whole bunch of stuff done they're just
47:33all of a sudden all kinds of things and
47:40what's germane to this talk is that we
47:42had lots of different hardware architect
47:44we just like to build computers they all
47:47have different CPUs on them and small
47:50talk ran on all of them bit identical so
47:55it wasn't the way some systems are today
48:01we wrote a book about it but when
48:04commercialization happened
48:06things started degenerating entropy set
48:10in here's an example so this is one of
48:15the most respected Java developers and
48:19in this book he actually says that any
48:21sivan seasoned Java programmer will
48:23quickly note that write once run
48:25everywhere is a myth along the lines of
48:26Paul Bunyan now it happens to be true
48:30but it is unbelievable to me that they
48:34would be so complacent about it to
48:35actually write it down because isn't
48:39Java supposed to be compatible on all
48:42the systems on the Internet so this is
48:47bad so I claim that the architectures
48:52people are dealing with today are
48:54basically 60s mainframe hardware and
48:56software we look at Intel and Motorola
48:59they've never really gotten I mean Intel
49:02started off as a pocket calculator never
49:04got beyond that much
49:05Motorola started out as a kind of a PDP
49:0811 very early architectures and then
49:13very typical 60s software as done before
49:171965 bad operating systems layers
49:21applications and a whole bunch of stuff
49:23and then grafted onto that today are
49:25some things from Arthur and park by PC P
49:28IP PostScript laser printing more
49:31expandable architectures
49:35about three years ago we got really
49:38really upset about all this because
49:40we've decided that we're going to do
49:42some major new stuff with children we
49:45wanted to do it on the Internet and our
49:49first thought is well we'll do this
49:51stuff on top of the Java VM because
49:54everybody's implementing it like mad and
49:56it's going to be on everything and we
49:57looked at it we thought wait a minute
49:58this is no good you can't do this it's
50:01not reflective it doesn't have any of
50:03these things so we finally said let's
50:07just go back and revive what we had at
50:10Xerox PARC but revive a 90s version of
50:12it so that's what squeak is we call it
50:16squeak instead of small talk because
50:17small talk now has the tinges of the
50:21various commercial versions and what we
50:25had at Xerox PARC was not very much like
50:27the commercial versions ever now it's a
50:34way of thinking about squeak is it's
50:36just a sea of objects here and what
50:41we've tried to do is make it a kind of a
50:42world and so there's an authoring level
50:46for five-year-old kids
50:48by Kiwi there's offing level for Donald
50:52there's one for gyro gear losses which
50:54there are a lot here at MIT and because
50:59every line of code in the system is
51:01available including the stuff in the
51:05bottom most level there's some stuff for
51:08Albert Einstein though I'm giving you
51:14this talk and demo on a Macintosh
51:17there's no Macintosh code running on
51:19this machine right now and there hasn't
51:20been from the time I started there's
51:23nothing this thing is its own operating
51:25system just like we were talking about
51:27and it can be started up from all of
51:30these different platforms including a
51:31couple of bear chips okay so just to
51:36show you a couple of things now why am i
51:39why am i showing you all this stuff well
51:40the reason I'm showing you this is
51:42because this system is free I'm going to
51:45explain this a bit you can get it
51:47tonight from the internet it's been
51:49for the last several years and it's not
51:53a Disney product it's something that we
51:57started at Apple for to have a tool of
51:59our own that would be up to our
52:01standards again and we decided to put it
52:04out in the Internet just for people to
52:05use if they would like to get free of
52:08thought of the sort of the software
52:11paralysis that's affecting everyone it
52:15will take a look and see how large it is
52:16let me show you a couple of things how
52:18many people here use Microsoft Word okay
52:24so if you notice that it takes longer
52:28just get a document up in the screen now
52:30than it used to five years ago in fact
52:36takes a lot longer to get a document up
52:38on the screen now that did ten years ago
52:41so Nicholas Negroponte phrase for this
52:45is Andy giveth but bill taketh away so
52:57we thought Moore's law was irresistible
52:59but we've but Microsoft found a way of
53:02damping it so what I'm going to do here
53:07is bring up my Scientific American
53:08article of a few years ago right now
53:11that's how long it takes in this system
53:14and everything is editable here in fact
53:18this is a whole environment for making
53:21this document if I drop the it's more
53:24than just a text editor it's actually
53:26kind of a desktop publishing system fact
53:28descended from the original desktop
53:30publishing system and in fact I can if I
53:34drop a pallet in it makes me a kind of
53:37an onion skin in case I want to trace
53:39something the simplest thing to do in a
53:43little demo like this is to just make a
53:45corporate logo
53:52this is a little more difficult than it
53:55was when we're at Apple and again this
54:00thing that thing that I made is is felt
54:03by the felt by the text and the other
54:09thing to realize about this this is not
54:11an application because applications are
54:13an old old bad idea if you have an
54:16object-oriented system what you
54:17basically want to do is to gather all
54:20the resources you need and make what you
54:22want so for instance I can just drag
54:27this piece of text out of here and if I
54:31start shoving this up it will start
54:35rolling along if I go to the next page
54:39here and start shoving this all right so
54:47everything is kind of alive here and now
54:51if I go back to where we were notice
54:55that this thumbnail has felt the changes
54:59I made in fact this is the original
55:00Xerox PARC interface which is not really
55:03a desktop interface it was it an
55:05interface of many desks the idea is that
55:08any child or adult usually has three or
55:13four projects they want to work on over
55:15time maybe a few hours a day and today's
55:19user interfaces which are kind of bad
55:22caricatures of what we did at Parc our
55:24interfaces that force you to build up a
55:27lot of Windows then take them down and
55:30build up a lot of Windows and take them
55:31down where's this interface just gives
55:34you a new desk for every project and you
55:36can have hundreds of them let me go over
55:39to here and take a look at a project for
55:43a ten-year-old which might be a kind of
55:52a Montessori project of getting the
55:54ten-year-old to make a car and learn how
55:57to drive it and to see if we can get the
56:02ten-year-old to learn something
56:04whoo
56:04about math without realizing it so we
56:08tell the kid to draw the car from the
56:11top and you put in some specular
56:17reflection because this is Disney a
56:22little bit of Hollywood and maybe make
56:27it into a dune buggy with some tires and
56:34then you say okay that's good enough
56:38then what the system does is makes it
56:41into an object right away that I can do
56:44something with so I'll make it the size
56:47I want it and for free it's given me a
56:51symbolic rendering of this basically the
56:54objects interface over here in a form
56:57the kids can understand so when I take
56:59the blue handle and rotate the car you
57:01can see the the property called heading
57:06over here going positive in that
57:09direction and negative in in that
57:10direction and if I come over here and
57:12start pressing on the carrot it'll
57:16rotate the car there now first thing we
57:20encourage the kid to do is to rename the
57:22thing car try some behaviors car for
57:29where you press on the exclamation point
57:31car turn and then the magic happens when
57:37we say just pull out some of those
57:39behaviors and start them ticking okay
57:50and so now we can play with these things
57:58now notice that we have concrete numbers
58:00here that's good because the kids in
58:03that phase of thinking but we give them
58:06the whole set so they can just use the
58:10the carrots their speed the car up
58:15and I can change what the what happens
58:24when it bounces I'm going to slow it
58:27down here of course the kids will play
58:32at this for a long time but the next
58:35thing we want the kids to do is to think
58:37about steering this car and we notice
58:39that if we go to zero the car will go
58:42straight we go positively the car will
58:45go in that direction if we go negatively
58:46it will go in this direction so that's
58:49kind of a clue as to how we might make a
58:52steerable car so what we do is we tell
58:55the kids okay just make yourself a
58:59steering wheel
59:09just make this smaller and just to keep
59:14it straight for the audience here I'll
59:16go up and name it steer so the thing
59:25that get the kid noticing is that yeah
59:27if we rotate this the heading changes go
59:31in the other direction it goes to minus
59:32numbers and that's kind of what turn was
59:34doing down here so what would happen if
59:36we just picked up the name of the angle
59:41that the steering wheel is set and just
59:43put it in there and then would we be
59:46able to steer the car yeah the kids say
59:55wow this is great but this is it's too
59:57jerky yeah we say yeah you made a race
59:59car so it doesn't have any gears and
60:03they said well what do you mean gears
60:05and we all your parents car has gears so
60:08now is an interesting place for the kid
60:10because ten-year-old kids if you think
60:14about it have never had a reason in
60:16their entire life to ever learn what
60:18multiplication and division are good for
60:20they are the equivalents of gears so see
60:25this little carrot over here if I press
60:27on this it will extend out the
60:29expression here I can click on the
60:31operators not - not times how about
60:34dividing by 3 here and now if I steer
60:39the car I have to turn the steering
60:42wheel three times as far in order to
60:45control it and I've inserted a gear
60:47between the steering wheel and the thing
60:50so
60:56I think you get the idea so this is kind
60:58of seymour papert's turtle graphics
61:00combined with object-oriented
61:02programming and a way of dealing with
61:06what the system can do that gives the
61:10kids a payoff here but gets them to
61:12notice interesting symbolic things about
61:16mathematical parts of this so when we
61:19ask the kids what was the part of this
61:21project that they liked the most
61:24they said learning to drive the car we
61:29asked them what was the hardest part of
61:31this project and they said learning to
61:33drive the car the fact that they'd spent
61:3615 minutes programming completely passed
61:39them by because in fact most kids are
61:41not interested in programming that most
61:44kids are only interested in things that
61:48give them direct payoffs in the in the
61:50world that they live in I'll just show
61:52you a couple more here this is a whole
61:54family of things here's one that a
61:57five-year-old did mommy what's hiding in
62:01the grass I don't know look at this this
62:06is fun they love these little camouflage
62:08games and they're learning this very
62:11simple little differential equation
62:13they're at five
62:16here's one for symmetry let's make the
62:21top rectangle appear to get larger okay
62:26and it's a one line programmer here
62:28program here where they learn what -1 is
62:30good for so you get the idea here I
62:34think now let me go to another a little
62:39more serious thing what we see and we
62:41start off with fun dealing with
62:44particles and when the first thing we
62:45say is why does your bicycle tire get
62:49hot when you blow it up well that's why
62:52why does your soda pop gets cold when
62:55you open it that's why
62:59but then what we want them to think
63:02about is let's let's try doing an
63:04infection here let's learn about
63:06something and complicated so let's turn
63:09everybody to blue except one red one
63:11will let them infect each other then we
63:22can get the history of this infection it
63:24looks kind of like this and then let's
63:35try this on a something like that was
63:37like AIDS let's try this on something
63:40like typhoid here infection history is
63:47like that and here comes the serious
63:51part of this is it happens that human
63:53imagination is is roughly like this it's
63:57like a little keyhole if you look at an
63:59AIDS epidemic when it's starting off
64:02when you can do something about it it
64:04actually doesn't look like anything
64:05wrong is happening it has a long time
64:08constant if you've been following the
64:10papers you probably know that twenty
64:11eight million people are HIV positive in
64:14Africa alone now and almost all of them
64:17are going to die many countries in
64:20Africa are twenty five percent
64:22hiv-positive now why they are not here
64:27the answer is here every scientist and
64:30mathematician when it was when age was
64:32heard about knew what was going to
64:34happen because even though our brains
64:38are terrible at exponential curves by
64:42learning math and learning these new
64:43ways of thinking about it we can
64:45guarantee that something that has these
64:47characteristics is going to be a
64:49disaster down the road and there's
64:50enough beating the politicians didn't
64:52want to do anything because it really
64:54didn't look that bad a difference in
64:58Africa and in the Pacific Rim is that
65:01there are nobody there's nobody to beat
65:02on the politicians they've ignored it
65:04and ignored it and ignored it and all of
65:07a sudden is now seriously bad now the
65:11stuff reason we're doing all this stuff
65:12is
65:13this is the kind of stuff that seem
65:14where I was talking about we want to
65:17better inform and better shape the
65:21common sense of kids not just what
65:24they've learned how to do I'll show you
65:28one more thing here it's kind of cute so
65:33here's a here's a movie here's some
65:42music so if I play it
66:13remember that so so here's an image us
66:19tell you what's going on here so again
66:20this is not quick time this is squeak
66:22time and one of the things that we did
66:27it
66:27Park that we really enjoyed was to make
66:30use of the fact that every computer can
66:32be a high quality synthesizer something
66:34that has been forgotten in the
66:35commercialisation so there's actually no
66:37sound card or anything in here this is
66:40just the equivalent of a Proteus level
66:42stereo synthesizer in the software of
66:45the squeak BM now let me show you how
66:48how we use the thing what I was playing
66:52it was not exactly the way Disney did it
66:57so I'm going to play this thing
66:58backwards I'm going to find this place
67:08where it cuts to the top right there and
67:10I'm going to pull out a thumbnail of
67:14that and I'm going to rewind the score
67:17I'm just going to play through then I'm
67:20going to drop the thumbnails in where
67:23the Disney sync points
67:25well-put
67:35okay it happens that right on this
67:38little inverted trill here is where the
67:41Disney animators long ago decided to cut
67:44to the top of the mountain so on this
67:51note in the trombones is where his right
67:55wing goes up to the top here's where his
68:03left wing goes up to the top
68:15so it happens that he actually puts his
68:17hands down right on this lowest note not
68:20before then when they did so now if we
68:22rewind and play now what it's doing is
68:25calculating how to sample out the mute
68:27the movie to get the cut points right
68:51you
69:01okay so you get the idea there's a lot
69:04of things you can now important thing to
69:06realize that all this these are not
69:07features these are just programs there's
69:11a lot of things that can be done here so
69:15here's the very same this is a book see
69:29hyouta organ piece
69:54let me rewind it
69:56I can orchestrate this thing in various
69:59ways what I'm going to do is edit the
70:01synthetic tomber in here while it's
70:04playing
70:32okay so let me wind up lots more
70:40interesting things here but let's go
70:45back to our eco lie for a second and
70:54let's ask squeaks some questions for
70:57instance how many types of things squeak
70:59do you have 1917 classes how many things
71:06do you have in you that are like
71:09subroutines 16,000 something these are
71:14questions of the system the what you
71:17call the operating system all of the
71:19things you would call applications all
71:20the things I've shown you a browser a
71:23chat interface and a whole bunch of
71:25other things how many bytes of code do
71:28you have mr. squeak in you Oh 936 K
71:33bytes so it's actually rather large by
71:40Xerox PARC standards because we wouldn't
71:44have been able to run this on our little
71:47256 K machines back then but in fact so
71:50I'm trying to make a point here which is
71:53let's ask it how many objects there are
71:57about six hundred and forty-two thousand
72:00objects so the point I'm trying to make
72:03here is that the actual information
72:08content and most software today is
72:10abysmally low monstrously low with a
72:17better architecture you can get a ton of
72:19stuff without even worrying and here's
72:21the other interesting thing is this is
72:23the entire group that made squeak in
72:25less than three years here we were back
72:28last January and these four guys here
72:31did virtually all of the work we put it
72:34out on the web in September 96 and here
72:37we are in November second demo to m.i.t
72:39so we're just coming up on the third
72:41year of development
72:43that's worthwhile pondering that you can
72:47do all of that stuff with just four
72:48people I know there's more than four
72:50people in MIT because I can see the so
72:57architecture and scaffolding meta object
73:02protocol well we don't do it quite the
73:04way Gregor and Danny do but let me just
73:08show you how this how we made the system
73:13so we went to the book we wrote and
73:16actually took an old small talk we typed
73:19the code for the VM that we'd written in
73:22this book which nobody has ever read
73:25into this small talk system to make a
73:30simulator of what the virtual machine
73:32should be then we wrote a translator of
73:37the simulator and then we use that to
73:44make ourselves a new VM that did not
73:47have any of this old small talk in it
73:49and then we moved over the image which
73:52has all of the objects in it and now we
73:54were completely free that took about a
73:55month and a half or so to do and all of
73:58a sudden we have a completely machine
74:00independent version of squeak and all of
74:05these different ports have been to take
74:07this guy and first improve it like when
74:11we put in the music we put them you do
74:13the programming of the VM by making the
74:16simulator do what you want and then
74:18getting this translator to make you a
74:20new VM so you never write any C code by
74:22hand and the ports are all done by
74:25simply diverting the simulated sation
74:28translator to different target machines
74:31so all the ports in fact we're done in
74:32less than two weeks by people we'd never
74:35met before
74:36that just found this on the internet and
74:38and did it the last part of it is this
74:42whole worldwide community is held
74:45together by synchronized code so at any
74:49at any point in time I can I'm not
74:55connected but I can say
74:57update code from server and if I say
75:00Disney internal updates or squeak public
75:02updates it will go out automatically to
75:05the nearest mirror server and find the
75:07latest updates and serialize them in
75:10this system has not been built from
75:12source listing since about 1975 it's
75:16never been stopped it's kind of
75:20important to think about and here's the
75:25URL so everything in this demo was built
75:33from this the versions you'll find there
75:36and you'll find all of the ports and we
75:41offer it to all of you not in the spirit
75:46of competition with anybody else because
75:49it's hard enough to do one's own work
75:51but in the spirit of trying to get more
75:53and better ideas out into the world so
75:56we can get better at doing software
75:58thank
76:11time to save on teeth Lester it's a bit
76:14late so people who want to leave can
76:16leave and but Alan is willing to stay
76:18and answer questions we will take a 30
76:21second pause and then who wants to fire
76:24the first question all right
76:31yeah wait wait 15 seconds okay fantastic
76:37okay that's just what I showed you on
76:42the plane
77:22this is my personal work environment and
77:25what have I done to migrate what have we
77:28done to migrate out in the world into
77:33this so the answer the first question is
77:37about 95 percent now one of our fears
77:43when we started this at Apple was that
77:45there might circumstances might someday
77:47force us to buy an on Mac and we knew
77:51for sure we were never going to run
77:53under Windows so part of the goal yeah
77:56was to get fairly self-sufficient
78:00the migration basically since we did it
78:05for ourselves this is not a product and
78:08it's not intending to compete with Java
78:10or anything else you could think of as
78:12in an intellectual toy except it's the
78:14best kind it's like a like a really good
78:17pipe organ yeah which is basically a toy
78:21you play on it but the idea is you
78:23should be able to play the best music
78:24that was ever written on it there's no
78:30there's no interest for instance in
78:33migrating something like Photoshop to it
78:37even if we wanted to so basically one of
78:41the problems when you do a system like
78:42this is I've ever nice slide set which
78:47is the six reasons why you should not do
78:49a system like this and one of them is
78:52getting back to zero and of course the
78:54zero is not the zero that the world was
78:57at when you start it's the zero the
78:59world is at by the time you get done
79:01another one of the reasons is these
79:03systems tend not to get done right but
79:06so what we had to do when we started the
79:09thing in January
79:1196 our aim was by January 99 to have
79:16something that had all of the things
79:20that we thought we needed for day-to-day
79:21stuff plus some special things that
79:24nobody else had that was our that was
79:26our goal and we're pretty much there
79:28there's just one I would say it's you
79:31know in the sense that therefore
79:33during environments we are and each one
79:38of them has a user interface on it we
79:40are 7/8 there in the functionality that
79:44we're hoping for is pretty much
79:45completely there and 3 out of the 4
79:47authoring environments are fully
79:49functional the last one which is the
79:52Donald one which is the hardest
79:53absolutely hardest one because you're
79:55dealing with adults who don't want to be
79:57the same as professional programmers but
79:59have big ideas that's the that's the
80:02hard one and that one will I think will
80:06be at it a some sort of reasonable place
80:11by when we thought but I believe it will
80:13be tinkering on that one for the rest of
80:1799 just because it's a hard one to do so
80:21it's a on the other hand the it's also
80:26made in this gyro level that anytime we
80:31wanted something for instance we had a
80:33nice summer intern from Georgia Tech
80:37Georgia Tech is teaching this in all of
80:38its programming courses because nice
80:41thing about it is you can drill down
80:42into it if you want to see how the
80:44compiler works it's there if you want to
80:46see how the I mean if you want to this
80:52is kind of cute if you go into the
80:54quantum authoring here you want to see
80:58look at the interpreter and see how it
81:00does a primitive ad you can look at that
81:03if you want to see what the interpreter
81:05simular simulator does you can look at
81:13it because it's just all all there so in
81:16a computer science course even an early
81:19one you can start off with fairly simple
81:23stuff but if a question comes up you can
81:26just drill down and say yeah here's how
81:28this piece of quantum mechanics works
81:31down it down at the bottom here and
81:33let's change it and see what happens so
81:35that's basically what it's for in one of
81:38our slogans is the system should be the
81:40curriculum so the idea is that things
81:44and books don't actually help much in
81:46this dome
81:46you really this is goes harks back to
81:48the way Marvin used to teach incoming
81:51graduate students programming used to
81:53give them the previous years PhD thesis
81:55and Lisp and so they had this big huge
81:58piece of more or less working list code
82:01but the nice thing about is they didn't
82:03have to worry about the syntax that much
82:05and a whole bunch of other things that
82:06had already been structured by people
82:08could program and the same thing with
82:10learning any complex system you kind of
82:12I don't think you want to learn
82:13algorithms first because it gets you in
82:15the wrong frame of mind for everything
82:17else you're going to do later so by the
82:21way while the thing was playing all that
82:22music and showing the movies and stuff
82:24like that there was a real time garbage
82:26collector running this is a completely
82:29garbage collected system and I had the
82:31pleasure a few days ago at the
82:33University of Maryland after a
82:35vociferous discussion about what why
82:38Java is no good because it has a garbage
82:40collector of getting up and showing that
82:43it wasn't the existence of a garbage
82:46collector that it was the problem is the
82:48fact that the garbage collector in Java
82:49is not very good and many people are
82:53sort of throwing the baby out with the
82:55bathwater right they somehow assume that
82:58there's something special about the
83:00people programming Java and therefore if
83:02they're if they're garbage collector is
83:04too slow then there must be something
83:07wrong with using a garbage collector
83:09yeah so so the answer is we have this
83:13kid from Georgia Tech and and just in
83:16the summer in a couple of months he did
83:18us an internet browser an email pop3
83:22email client and a chat client because
83:27and they're in there and it was it was
83:29just one kid for about seven weeks to do
83:32it so it's for a lot of things is
83:35relatively easy to do stuff I mean
83:36there's a real-time FFT in there was all
83:40kinds there's a wavelet transform and
83:42there's a whole bunch of things in there
83:44again all in this program will will form
83:47so a person could do I think quite a bit
83:49of what Photoshop does without too much
83:52trouble and then if it runs too slowly
83:55in the upper level you just turn the
83:58translator on it and turn it into
84:00part of a part of the VM let's take one
84:02or two more quick yeah in the back oh
84:06sorry yeah put there's somebody's easy
84:18to move data around with abstraction but
84:20we want to have some kind of version
84:22behavior functions that occurs this gets
84:27a little tricky yeah well I mean
84:30basically one of the it's always hard to
84:35give any reasonable account of the
84:38different streams that fed into the
84:40development of OOP
84:42but I think one of the things that any
84:44programmer would like is that any level
84:48of a system they're working on to be
84:49able to add new stuff as though it were
84:52linear right I mean this is and of
84:57course it almost never works out that
84:59way so for example the so this is the
85:05opposite of what you're talking about
85:09what you would like is the where you're
85:13adding stuff that's whose intention is
85:15to be nonlinear and it's not going to
85:17bite you right so I think that is very
85:20difficult
85:21although sketchpad is the closest thing
85:24to do it because it basically said I'm
85:27only going to do things that I have
85:29criteria for and so in essence it was
85:34solving a series of nonlinear equations
85:36to determine what its behavior was on
85:40the other hand even though when it was
85:42doing it successfully it sometimes
85:43surprised people because it was not
85:46clear to the person putting in the new
85:49knowledge exactly what all the
85:51ramifications of the new knowledge we're
85:53going to be even if everything went well
85:55so I think this is a very difficult and
85:59you find it in lots of different areas
86:00you find it in things like multiple
86:02inheritance which various people have
86:05tried to find a way of getting synergy
86:08between the different inheritance
86:10streams in a way that makes sense
86:13and some success has been had but right
86:17now I think most people would agree that
86:18it's almost more trouble than it's worth
86:22that it becomes kind of a hack rather
86:24than an algebraic kind of say one lost
86:27wish and Ron Rivest tries to be
86:33comprehensive to deal with code that's
86:35easily shared someone eventually has to
86:36deal with security issues can you say a
86:39few words about what your thinking is oh
86:41yeah wisely we've thought about that
86:43quite a bit and the so my theory about
86:52security is it's very similar to locks
86:56in that you can make great locks but
87:04somebody with enough resources can get
87:07through the lock and so basically I
87:12think what locks are for are discouraged
87:14various grades of criminal yeah yeah and
87:21in particular these things that I was
87:24showing as projects these kind of
87:26desktops are actually independent
87:29modules because they're designed to be
87:30things that you might wander into on the
87:33Internet
87:33and so they actually have a have a
87:37certain security to them and then
87:39there's interesting question of how you
87:41can run them safely when you bring them
87:43into your machine and so I think the may
87:49be the only thing I can add to a
87:53mechanism with everybody are familiar
87:55with because if there's any number of
87:57ways of doing things including one of
87:59the things that we ran with at Apple
88:01successfully for many years was simply
88:03confining making it impossible for the
88:09system to write to the disk in
88:11unrestricted ways confining other kinds
88:15of things however this is up since you
88:17asked the question I I have a I have a
88:19prejudice about how it should be done
88:22which is orthogonal but sin
88:26logistic with encryption ideas but it's
88:29basically that on every machine like on
88:32this machine although Apple doesn't use
88:34it there is a memory management unit and
88:39it's not used very well on Windows
88:41either and so if you think about the
88:44general problem of dealing with the
88:46internet where you're you're out there
88:50you see something that looks like it
88:52might be useful let's say it's an object
88:55the probability it's going to be your
88:57favorite kind of object like a squeak
88:59object is low or any other kind of
89:02object and so but if it's really an
89:06object it should communicate with other
89:08objects not of its species right because
89:13otherwise what what use is having an
89:14object you really don't have an object
89:16if they can't send messages - like if a
89:19squeak object can't send messages to a
89:21Java object it's not very object
89:23oriented and neither is Java so if you
89:26get this notion that the objects are
89:28kind of recapitulating the heterogeneity
89:31of hardware on the network and using
89:33tcp/ip for sending messages back and
89:35forth then the question is is if I have
89:41to bring an object in in order to run it
89:44in a reasonable way how should I do it I
89:47believe the answer is you stick that
89:49object in a separate address space and
89:51if it needs to bring in its handle you
89:53let bring in its handler into that
89:54separate address space and you run that
89:56object and any other objects in that
89:58special address space and you monitor
90:00the traffic between that address space
90:03and the other parts of the system that
90:06is the way I would like to do it because
90:08I because all other ways are and you can
90:12encrypt wherever you want but to me what
90:15you really want to do is be able to
90:16enforce what a set of things that you're
90:20not quite sure what they are can do but
90:22still let them run this is what you
90:24might call a constitutional approach the
90:27pond where you don't want to tell the
90:28objects what to do but you want to make
90:29sure they can't do a lot of damage I
90:32think we must stop otherwise Alan is
90:35going to miss his plane to Chicago
90:36there's the most fascinating talk
