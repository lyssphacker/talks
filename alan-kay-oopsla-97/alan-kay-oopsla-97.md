0:17[Music]
0:31[Music]
0:47thank you
0:51well I presume most of you have been up
0:53all night can't imagine ever seeing this
0:57many programmers at 8 o'clock in the
0:59morning guess this is the largest
1:06bathroom I've ever given a talk in so
1:14that was just a test to see if you could
1:15understand me I can't actually
1:18understand myself up here now actually
1:24haven't been to ups less since the the
1:29first one and when I got invited to give
1:34this talk I was thinking about well
1:37should I should I go or should I not or
1:40what should I do and it occurred to me
1:44that this conference on this day is
1:49pretty much in the epicenter of the 25th
1:52anniversary of small talk the
1:58[Applause]
2:04the one-page interpreter scheme that I
2:10wrote out I was done just a few weeks
2:13ago 25 years ago and the first working
2:17version of it was done a few weeks from
2:19now 25 years ago so this is about in the
2:24center and let me see if I can get our
2:30motto up on could I have that first
2:32slide please
2:33so now I thought one way I didn't want
2:38it I'm not going to give a historical
2:39talk because I finally discharged those
2:42obligations in the history of
2:44programming languages conference a
2:46couple of years ago but I thought it
2:48might be interesting interesting for
2:51some of you who might not have been
2:54computing for the last 25 or 30 years to
2:57take a two minute trip I believe that
3:01this set of images is basically goes
3:07back to 1973 in 1974 at Xerox PARC shows
3:13some of the first children that we
3:14worked with the music that you'll hear
3:17on this clip was composed by one of the
3:20members of our group Chris Jeffers it's
3:23called the happy hacker in case you want
3:26a theme song is played in the real-time
3:30FM synthesis that we developed for the
3:34alto computer so this is the first the
3:38forerunner of the workstations and the
3:41Macintosh without any additional sound
3:45synthesis hardware at all because why
3:47should you have that if your computer is
3:50designed well and you'll just get a I
3:55think you'll get a little picture of it
3:57before I turn on that clip let's just
4:00for the heck of it see how many people
4:02are in this room today who participated
4:06in the Xerox PARC small talk experience
4:08between roughly 1971 and 1983 could you
4:13stand up let's see if we how many people
4:16are
4:17we hear anybody without gray hair thank
4:26you
4:27okay let's roll that that clip
4:32[Music]
5:26well that was things as they existed
5:29about 25 years ago and the other thing I
5:34want to do in the beginning part of this
5:38talk tried to figure out how to work my
5:41way into it and I finally remembered the
5:43paper that Dijkstra I don't know how
5:48many of you have ever met Dijkstra but
5:51you probably know that arrogance in
5:53computer science is measured in Nano
5:55Dijkstra's
6:04and he once wrote a a paper of the kind
6:10that you like to write a lot of which
6:12had the title on the fact that the
6:15Atlantic has two sides and it was
6:19basically all about how different the
6:23approaches to computing science were in
6:26Europe especially in in Holland and and
6:30in the United States and there many
6:33interesting you know in the u.s. here we
6:37were not mathematical enough and Gian in
6:42Holland if you're a full professor
6:44you're actually appointed by the Queen
6:46and there are many other important
6:51distinctions made between the the two
6:53cultures so I wrote a rebuttal paper
6:58just called on the fact that most of the
7:01software in the world is written on one
7:02side of the Atlantic and it was
7:10basically about cuz I had a math degree
7:12to was basically about that computers
7:16form a new kind of math you can't judge
7:20them they don't really fit well into
7:21classical math and people who try to do
7:23that are basically indulging a form of
7:27masturbation maybe even realizing it
7:35and was about that was a kind of a
7:40practical math that was the balance was
7:43between making structures that were
7:47supposed to be consistent of a much
7:50larger kind than classical math had ever
7:52come close to dreaming of attempting and
7:57having to deal with exact same problems
7:59the classical math of any size has to
8:02deal with which is being able to be
8:07convincing about having covered all of
8:09the cases there was a mathematician by
8:13the name of Euler whose speculations
8:17about what might be true formed 20 large
8:22books that most of them were true most
8:24of them were right almost all of his
8:26proofs were wrong and many PhDs in
8:30mathematics in the last and this century
8:33have been formed by mathematicians going
8:37to Euler's books finding one of his
8:40proof showing it was a bad proof and
8:42then guessing that his insight was
8:47probably correct and finding a much more
8:50convincing proof and so debugging
8:52actually goes on in mathematics as well
8:56and I think that the I think the main
9:00thing about doing oop work or any kind
9:05of programming work is that there has to
9:07be some exquisite blend between beauty
9:12and practicality there's no reason to
9:16sacrifice either one of those and people
9:20who are willing to sacrifice either one
9:21of those I don't think really get what
9:23computing is all about it's like saying
9:27I have really great ideas for paintings
9:30but I'm just going to use a brush but no
9:34paint you know so my ideas will be
9:39represented by the gestures I make over
9:41the paper and don't tell any twentieth
9:43century artists that or they might
9:45decide
9:46make a videotape of them doing that and
9:48put it in a museum so I thought at this
9:54problem figuring out what to talk about
9:58it's always difficult because technical
10:00people always seem to know so much but
10:05it's interesting to again to look at
10:09what's actually being done out in the
10:10world under the name of OOP and I've
10:15been shown some very very strange
10:18looking pieces of code over the years by
10:23various people including people in
10:25universities that they have said is code
10:30and written in an OOP language and
10:33actually I made up the term
10:35object-oriented and I can tell you I did
10:38not have C++ in mind
10:41[Applause]
10:49so the important thing here is I have
10:54many of the same feelings about small
10:57talk and I'm going to try and extend
11:02here because I think there's one really
11:05important thing about small talk and
11:08some of the languages like it that we
11:11should pay really really close attention
11:13to but it has almost nothing to do with
11:16either the syntax or the accumulated
11:21superclass library both of which of
11:25these are taken as being the language as
11:29though it was issued from some gods on
11:32Olympus so I want to talk a little bit
11:35more about my personal reaction to when
11:40I started thinking about it in the in
11:42the 60s and instead of making it a
11:46historical talk to try and think about
11:48whether these reactions and and insights
11:52have any place today so let me I'll just
11:57move
12:05so I guess my slide thing doesn't work
12:09maybe it does yeah just go to that
12:14there's a blank slide there just go to
12:16the next one so in the 60s things were
12:23quite mechanical there's a sense of
12:28simple mechanism because computers of
12:30course were as large as as its room some
12:33of them the one that Ivan Sutherland did
12:35sketchpad on was the size of this room
12:37was one of the last computers in the
12:40u.s. large enough to have its own roof
12:42it was the building it was in but the
12:48programs were quite small and they had a
12:52lot in common with their mathematical
12:55antecedents and one way of thinking
12:59about the semantics of of math that is
13:02based on logic is as interlocking gears
13:07everything kind of has to fit together
13:09and if it does and everything is
13:12compatible at the end you get the final
13:15turning of the shaft that that you want
13:18and sort of a real world analogy go the
13:23next slide please
13:26whoops so we missed the slide go back to
13:30slides please
13:32there we go so an analogy to these
13:36programs of the 60s is a dog house you
13:42take any random boards nail and hammer
13:46pound them together and you've got a
13:48structure that will stay up you don't
13:50have to know anything except how to
13:52pound a nail to do that now somebody
13:57could come along and look at this
13:58doghouse and say wow if we could just
14:01expand that by a factor of 100 we could
14:04make ourselves a cathedral it's about
14:06three feet high that would give us
14:07something 30 stories high and that would
14:11be really impressive we could get a lot
14:13of people in there and so the Carpenters
14:17would set to work
14:18blowing this thing up by a factor of 100
14:21now we all know being engineers in
14:25scientists that when you blow something
14:27up by a factor of a hundred its mass
14:29goes up by a factor of a million and
14:32it's strength which is mostly due to
14:34cross-sections of things only goes up by
14:37a factor of 10,000 so when you blow
14:41something up by a factor of 100 it gets
14:44about a factor of 100 weaker in its
14:47ability and in fact what will happen to
14:49this doghouse it will just collapse into
14:51a pile of rubble and then there are two
14:55choices you can have when that happens
14:58the most popular one is to say well that
15:01was what we were trying to do all along
15:07put more garbage on it plaster it over
15:10with limestone and say yes we were
15:13really trying to do pyramids not Gothic
15:15cathedrals that in fact I think accounts
15:21for much of the structure of modern
15:22operating systems today
15:31or you can come up with a new concept
15:37which the people who started getting
15:41interested in complex structures many
15:45years ago did they called it
15:46architecture literally the designing and
15:50building of successful arches a non
15:54obvious nonlinear interaction between
15:58simple materials to give you non-obvious
16:02synergies and a vast multiplication of
16:07materials it's quite remarkable to
16:10people when I tell them that the amount
16:13of material in Chartres Cathedral which
16:17is an enormous physical structure is
16:19less than the amount of material that
16:22was put into the Parthenon and the
16:26reason is it's almost all air in almost
16:31all glass everything is cunningly
16:33organized in a beautiful structure to
16:37make the whole have much more integrity
16:41than any of its parts so that's the
16:44other way you can go and part of the
16:46message of who was that as complexity
16:51starts becoming more and more important
16:53architecture is always going to dominate
16:55material and in fact the sad fact I
17:04think about OBE is people didn't get
17:06interested in architecture because of
17:09the beauty of it
17:10they're only starting to get interested
17:12in architecture now when the Internet is
17:14forcing everybody to do it that's pretty
17:17pathetic
17:23so I'm going to use a metaphor here for
17:27this talk which is drawn from a
17:30wonderful book called the act of
17:32creation by Arthur Kessler Kessler was a
17:36novelist who became a cognitive
17:39scientist in his later years and one of
17:44the great books he wrote was about what
17:47might creativity be learning he realized
17:51that learning of course is an act of
17:53creation itself because something
17:56happens in you that wasn't there before
17:58and used in a the metaphor of thoughts
18:06as ants crawling on a plane this case
18:11it's a pink pink plane and there's a lot
18:14of things you can do on a pink plane you
18:17can have goals you can choose directions
18:21you can move along but you're basically
18:24always in the pink context and if you
18:29think about that that means that
18:31progress in a fixed context is almost
18:36always a form of optimization because if
18:42you're actually coming up with something
18:44new it wouldn't have been part of the
18:47the rules or the context for what the
18:50pink plane is all about so creative acts
18:54generally are ones that don't stay in
18:57the in the same context that they are in
19:01so he says every once in a while even
19:05though you've been taught carefully by
19:08parents and by school for many years you
19:11have a blue idea maybe when you're
19:15taking a shower maybe when you're out
19:19jogging
19:20maybe when you're resting in an
19:23unguarded moment suddenly that thing
19:25that you were puzzling about wondering
19:29about looking at appears to you in a
19:32completely different light as though it
19:34were something else
19:35and Kessler said the emotional reaction
19:39to this comes basically in three forms
19:41which is if you're telling a joke
19:44it's haha if you're doing science
19:48it's a ha and if you're doing art it's
19:51ah he says because in each case
19:56something very similar is happening a
19:58joke takes you down the garden path and
20:02then suddenly reveals it's about
20:03something else and you get a very
20:05aggressive explosion and science has
20:09much of the same feeling to it and often
20:13when you see something in science you
20:16start laughing because it was right
20:18there in front of you and it is a kind
20:20of a joke and of course art is there to
20:24remind us great art is there to remind
20:27us that whatever context we think we're
20:30in there are other contexts art is
20:32always there to take us out of the
20:34context that we're in and make us aware
20:37of other other contexts so this is a
20:39very simple you could even call it a
20:42simple-minded metaphor but it will
20:45certainly serve for for this talk today
20:47and he also pointed out that you have to
20:51have something blue to have blue
20:54thoughts with I think this is generally
21:00missed in people who specialized to the
21:04extent of anything else when you
21:05specialized you're basically putting
21:07yourself into a mental state where
21:12optimization is pretty much all you can
21:14do have to learn lots of different kinds
21:18of things in order to have the start of
21:21these other contexts so here's a couple
21:27of hit knocks on the head I had over the
21:30years that I just want to tell them to
21:32you quickly this one I think you'll find
21:35interesting because it is the earliest
21:37known form of what we call data
21:41abstraction
21:43it goes all the way back
21:45actually pre 1961 I was in in the Air
21:49Force in 1961 and I saw it in 1961 and
21:52it probably goes back one year before
21:56and so back then they didn't really have
21:59operating systems they had Air Training
22:03Command had to send tapes of many kinds
22:06of records around from Air Force Base to
22:09Air Force Base there's a question of how
22:11could you deal with all of these things
22:14that used to be card images and then
22:16because tape had come in we're starting
22:18to be more and more complicated formats
22:22and somebody almost certainly an
22:26enlisted man because officers didn't
22:28program back then came up with a coming
22:32up with the following idea this person
22:35said on the third part of the record on
22:40this tape we'll put all of the records
22:42of this particular type the second part
22:49the middle part we'll put all of the
22:52procedures that know how to deal with
22:55the format's on this third part of the
23:00tape and in the first part we'll put
23:03pointers into the procedures and in fact
23:08let's make the first 10 or so pointers
23:10standard like reading and writing fields
23:15and trying to print and them let's have
23:19a standard vocabulary for the verse 10
23:21of these and then we can have videos and
23:22kradic ones later on and so all you have
23:25to do to read a tape back in 1961 was to
23:29read the front part of a record one of
23:33these big records into core storage and
23:36start jumping in direct through the
23:39pointers and the procedures were there
23:41now really would like you to contrast
23:43that with what you have to do with HTML
23:46on the Internet
23:47think about it HTML on the Internet has
23:51gone back to the dark ages because it
23:54presupposes that there should be a
23:56browser that should under
23:57stand it's formats this has to be one of
24:01the worst ideas since ms-dos this is
24:10really a shame it's it's maybe what
24:13happens when you when physicists decide
24:15to play with computers I'm not sure and
24:19in fact we can see what's happened to
24:21the internet now is it's gradually
24:24getting the two wars going on there's a
24:26set of browser Wars which are 100%
24:29irrelevant they're basically an attempt
24:33either at demonstrating a non
24:36understanding of how to build complex
24:39systems or a even cruder attempt simply
24:45to gather territory which I suspect
24:48Microsoft is in the latter camp here you
24:54don't need a browser if you followed
24:57what this staff sergeant in the Air
25:00Force knew how to do in 1961 you just
25:05read it in it should travel with all the
25:09things that it needs and you don't need
25:12anything more complex than something
25:14like X Windows hopefully better but
25:20basically you want to be able to
25:22distribute all the knowledge of all of
25:24these things that are there and in fact
25:25the Internet is starting to move in that
25:29direction as people discover ever more
25:32complex HTML formats ever more
25:35intractable this is one of these
25:38mistakes that has been recapitulated
25:40every generation and it's just simply
25:44not the way to do it so here's a great
25:46idea by the way this this kind of
25:50programming was done before there were
25:52higher-level languages in the airforce
25:54and this but this approach to things was
25:58forced out of the Air Force by COBOL
26:01when they standardized on COBOL Ivan
26:07Sutherlands sketchpad
26:09I've usually shown a movie of what it
26:12was like I won't I won't today immensely
26:15sophisticated almost staggering in its
26:19conception of what it was able to do
26:22very much in an object-oriented system
26:24it had an actual notion of classes and
26:29subclasses it had a notion of
26:33polymorphism even stronger than the the
26:37eighth Air Training Command version next
26:44slide please
26:50now that I'd seen the idea three or four
26:53times but wasn't till I had to figure
26:55out Simula we thought it was supposed to
27:00be an algal and it turned out the this
27:04pile of tapes was a was the first Simula
27:08an algal that had been doctored by Case
27:12Western Reserve and the inventors of
27:15Simula Nygaard and dal in Norway and
27:20distributed along with some
27:22incomprehensible documentation in 1966
27:26and it was through trying to understand
27:30what Simula was that finally I'm not
27:35sure exactly why it's just I think it's
27:37maybe if you see a good idea that's odd
27:40four times and four different costumes
27:43it finally starts to make an impression
27:46and here's the the choice you have when
27:50you're faced with something new you can
27:55take this technological advance and you
27:58can decide this is a better way of doing
28:02the stuff I'm doing now and I can use
28:05this to continue on the path that I'm
28:09going that's staying in the pink plane
28:12or you can say this is not a better old
28:15thing this is almost a new thing and I
28:18wonder what that new thing is trying to
28:20be and if you do that there's a chance
28:23of actually perhaps gaining some
28:27incredible leverage over simply
28:29optimizing something that can't be
28:31optimized very much so the choice here
28:37was Simula came out of the world of data
28:42structures and procedures and had much
28:45of that flavor if you wanted to look at
28:47it that way but it had a way of making
28:52relationships of the states of your
28:56computation with procedures that was
28:59extremely helpful and much better
29:02and more general than the what we call
29:04own variables in Algol 60 so that was
29:08one way to think of it then there's this
29:11other question of if it was almost a new
29:13thing what kind of a new thing was it
29:17well one of my undergraduate majors was
29:21in molecular biology in my particular
29:25interest was both in cell physiology and
29:28in embryology morphogenesis they call it
29:34today in this book molecular biology of
29:39gene had just come out in 1965 and
29:43wonderful book still in print and of
29:46course it's gone through many many
29:47editions and they're probably the only
29:51words that are common between the this
29:53book and the one of today are the are
29:55the articles like the in and actually
29:59the word gene I think is still in there
30:01but it means something completely
30:02different now but one of the things that
30:05Watson did in this book was to make an
30:08assay first assay of an entire living
30:14creature and that was the e.coli
30:16bacteria next slide please
30:27so if you look inside one of these the
30:31complexity is staggering those popcorn
30:35things are protein molecules that have
30:39about 5000 atoms in them and as you can
30:43see on the slide when you get rid of the
30:47small molecules like water and calcium
30:51ions and potassium ions and so forth
30:53constitute about 70% of the mass of this
30:59thing
31:00the 30% that remains has about 120
31:03million components that interact with
31:06each other in an informational way and
31:09each one of these components have as
31:13carries quite a bit of information and
31:16you can think of it you know the simple
31:20simple minded way of thinking of these
31:21things is it works kind of like ops five
31:25there's a pattern matcher and then there
31:29are things that happen if patterns are
31:31matched successfully so the state that's
31:36involved in that is about a hundred gigs
31:40and you can multiply that out today it's
31:46only only 100 desktops or so but it's
31:51still still pretty impressive as a as
31:54amount of computation and maybe the most
31:56interesting thing about this structure
31:59is that the rapidity of computation
32:07seriously rivals that of computers today
32:10particularly when you're considering
32:12it's done in done in parallel for
32:14example one of those popcorn sized
32:16things moves its own length in just two
32:19nanoseconds so one way of visualizing
32:24that is if an atom was the size of a
32:26tennis ball
32:27then one of these protein molecules will
32:31be about the size of a Volkswagen and
32:34it's moving
32:36its own length in two nanoseconds that's
32:40about eight feet on our scale of things
32:42and can anybody do the arithmetic to
32:46tell me what fraction of the speed of
32:48light moving eight feet in two
32:50nanoseconds is four times yeah four
33:00times the speed of light scale so if you
33:04ever wondered why chemistry works this
33:06is why the thermal agitation down there
33:09is so unbelievably violent that we could
33:13not imagine it even with the aid of
33:15computers there's nothing to be seen
33:18inside one of these things until you
33:20kill it because it is just a complete
33:24blur of activity and in under good
33:27conditions it only takes about 15 to 18
33:30minutes for one of these two completely
33:32duped hiriam of course lots more is
33:38known today then another fact to relate
33:45this to us is that these bacteria about
33:471 5 hundredth the size of the cells in
33:51our bodies which instead of 120 million
33:55informational components have about 60
33:58billion and we have between 10 to the
34:0212th and 10 to the 13th maybe even more
34:07of these cells in our body and yet only
34:1350 cell divisions happen in the nine
34:20month pregnancy only takes 50 cell
34:23divisions to make a baby actually if you
34:27multiply it out you realize you only
34:29need around 40 and the extra 10 powers
34:34of 10 are there because during the
34:37embryo logical process many of the cells
34:41that are not fit in one way or another
34:44for the organism as a whole are killed
34:47so things are done by over proliferating
34:50testing and trimming to this much larger
34:54plant then of course each one of these
34:59structures us is embedded in an enormous
35:01biomass so to a person who's blue
35:07context might have been biology
35:11something like a computer could not
35:13possibly be regarded as being
35:16particularly complex or large or fast
35:24slow small stupid that's what computers
35:28are so the question is how can we get
35:31them to realize their destiny next slide
35:40please
35:48as we're using a form of technology that
35:52that monopoly n' use which remember
35:55those semaphore is across France so the
36:02the shift in point of view here is from
36:06mechanic's oh there's this problem if
36:08you take things like dog houses they
36:10don't scale by a factor of 100 very well
36:12you take things like clocks they don't
36:15scale by a factor of 100 very well take
36:20things like cells they not under scale
36:23by factors of 100 but by factors of a
36:26trillion and the question is how do they
36:29do it and how might we adapt this idea
36:34for building complex systems okay this
36:38is the simple one this is one by the way
36:42that C++ is still not figured out though
36:47there's no idea so simple and powerful
36:50that you can't get zillions of people to
36:52misunderstand it so you must must must
37:00not allow the interior of any one of
37:05these things to be a factor in the
37:08computation of the whole okay and this
37:12is only part of the story it's not just
37:14the cell cell membrane is there to keep
37:17most things out as much as it is there
37:20to keep certain things in and a lot of I
37:26think are confusion with objects is the
37:30problem that in our Western culture we
37:35have a language that has very hard nouns
37:37and verbs in it so we are process words
37:42stink so it's much easier for us when we
37:47think of an object and I'm I have
37:49apologized profusely over the last 20
37:53years for making up the term
37:55object-oriented because as soon as it
37:59started to be Mis applied I realized
38:01they should have used a much more
38:03process-oriented term for now the
38:07Japanese have an interesting word which
38:13is called ma spelled in English just ma
38:16ma and in ma is the stuff in between
38:23what we call objects the stuff we don't
38:26see because we're focused on the nowness
38:29of things rather than the process list
38:32of things whereas the in japanese has a
38:36more processed feel oriented way of
38:40looking at how things relate to each
38:42other you can always tell that by
38:44looking at the size of a word it takes
38:47to express something that is important
38:49so ma is very short we have to use words
38:54like interstitial or worse to
38:58approximate what what the Japanese are
39:01talking about so the realization here
39:07and it's not possible to assign this
39:10realization to any particular person
39:13because it was in the seeds of sketchpad
39:18and in the seeds of the 8th Air Training
39:21Command file system and in the seeds of
39:24Simula and that is that once you have
39:27encapsulated in such a way that there is
39:32an interface between the inside and the
39:35outside it is possible to make an object
39:38act like anything and the reason is
39:40simply this that what you have
39:42encapsulated is a computer so you've
39:47done a powerful thing in computer
39:49science which is to take the powerful
39:52thing you're working on and not lose it
39:54by partitioning up your design space
39:57this is the bug and data procedures data
40:00and procedure languages and I think this
40:04is the most pernicious thing about
40:05languages like C++ and Java is that they
40:09think they're helping the programmer Buy
40:12in
40:13by looking as much like the old thing as
40:15possible but in fact they're hurting the
40:17programmer terribly by making it
40:19difficult for the programmer to
40:21understand what's really powerful about
40:23this new metaphor so that now again
40:27people who are doing time sharing
40:29systems had already figured this out as
40:31well
40:31Butler Lampson thesis in 1965 was about
40:38that what you want to give a person on a
40:40time sharing system is something that is
40:43now called a virtual machine which is
40:46and not that not the same as what the
40:49Java VM is but something something that
40:53is as much like the physical computer as
40:55possible but give one separately to
40:57everybody
40:58UNIX had that sense about it and the
41:03biggest problem with that scheme is that
41:07a UNIX process had an overhead of about
41:12two thousand bytes just to have a
41:15process and so it was going to be very
41:17difficult in UNIX to let a UNIX process
41:19just be the number three so you'd be
41:23going from three bits to a couple of
41:25thousand bytes and you have this problem
41:26with scaling so a lot of the problem
41:29here is both deciding that the
41:34biological metaphor is the one that is
41:36going to win out over the next 25 years
41:38or so and then committing to it enough
41:43to get it so it can be practical at all
41:46of the levels of scale that we actually
41:48need then we have one trick we can do
41:53that biology doesn't know how to do
41:55which is we can take the DNA out of the
41:58cells and that allows us to deal with
42:02cystic fibrosis much more easily than
42:04the way it's done today and systems do
42:08have cystic fibrosis and some of you may
42:10know that if cystic fibrosis today for
42:14some people is treated by infecting them
42:17with a virus a modified cold virus
42:21giving them a lung infection
42:24but the defective gene for cystic
42:27fibrosis is in this cold virus and the
42:31cold virus is too weak to actually
42:33destroy the lungs like pneumonia does
42:35but it is strong enough to insert a copy
42:37of that gene in every cell in the lungs
42:40and that is what does the trick that's
42:44it's a very complicated way of
42:47reprogramming an organism's DNA once it
42:50has gotten started so here's one that it
42:57is amazing to me that we haven't seen
43:00more for instance one of the most
43:02amazing things to me of people who have
43:04been trying to put up on the Internet is
43:06that I do not and I'm hoping somebody
43:09will come up afterwards and tell me of
43:11an exception to this but I do not know
43:13of anybody yet who has realized that at
43:17the very least every object should have
43:20a URL because what the heck are they if
43:26they aren't these things and I believe
43:29that every object on the Internet should
43:31have an IP because that represents much
43:36better what the actual abstractions are
43:39of physical hardware to to to the bits
43:45so this is an early insight that objects
43:49basically are like servers and this
43:54notion of polymorphism which used to be
43:56called generic procedures is a way of
44:01thinking about classes of these servers
44:03everybody knows about that
44:05and here's one that we haven't really
44:07faced up to much yet that now we have to
44:11construct this stuff and soon will be
44:14required to grow it so it's very easy
44:18for instance to grow a baby six inches
44:21they do it about ten times in their life
44:24you never have to take it down for
44:26maintenance but if trying grow a 747 you
44:32are faced with an unbelievable problem
44:34because it's in a
44:35it's in this simple-minded mechanical
44:38world in which the only object has been
44:42to make the artifact in the first place
44:44not to fix it not to change it not to
44:47let it live for a hundred years so let
44:53me ask a question just I won't take
44:55names but how many people here still use
44:58a language that essentially forces you
45:04in the development system forces you to
45:07develop outside of the language compile
45:11and reload and go even if it's fast like
45:15JA virtual cafe how many how many here
45:21still still do that let's just see come
45:24on admit it we can have a Texas tent
45:27meeting later yeah so if you think about
45:30that that cannot possibly be other than
45:34a dead end
45:35for building complex systems where much
45:39of the building of complex systems is in
45:41part going to go to trying to understand
45:43what the possibilities for
45:45interoperability is with things that
45:47already exist now I was a just played a
45:52very minor part in the design of the
45:54ARPANET I was one of thirty graduate
45:56students who went to systems design
45:59meetings to try and formulate design
46:02principles for the the ARPANET also
46:04about 30 30 years ago and the if you
46:09think about what the ARP the ARPANET of
46:14course became the internet and from the
46:16time it started running just around 1969
46:21or so to this day it was expanded by
46:26about a factor of 100 million so that's
46:30pretty good
46:31eight orders of magnitude and there's as
46:36far as anybody can tell I talked to
46:38Larry Roberts about this the other day
46:41there is not one physical atom
46:46in the Internet today that was in the
46:49original ARPANET and there was not one
46:52line of code in the internet today that
46:55was in the original ARPANET of course
47:00we'd had IBM mainframes in the original
47:02ARPANET that wouldn't have been true so
47:09this is a system that is expanded by a
47:10hundred million has changed every atom
47:13in every bit and has never had to stop
47:18that is the metaphor we absolutely must
47:21apply to what we think are smaller
47:25things when we think programming is
47:29small that's why your programs are so
47:34big that's why they become pyramids
47:39instead of Gothic cathedrals next
47:47okay here's the other big source
47:52certainly the greatest single language
47:56along with Simula of the 60s I think one
48:02with as many profound or more profound
48:05insights list on page 13 of this book
48:10that was published in 1962 there's a
48:13half page of code which is the
48:17reflective model of Lisp written in
48:20itself all the important details of Lisp
48:25semantics and the guidelines for how to
48:28make a list interpreter are in that half
48:31page and it is this aspect this meta
48:36reflective aspect that I think is the to
48:40me is the the saddest thing about what's
48:45happening with Java when Java first
48:49happened I thought well it's
48:51legitimizing something that most people
48:54have not believed in for a long time
48:55which is this byte code approach of
48:58being multi-platform like we had at
49:01Xerox PARC it's not a new idea it
49:03actually goes back into the into the 60s
49:06but when I looked at job I thought my
49:09goodness how could they possibly and of
49:12course we know that the history was not
49:13was more about programming toasters
49:16originally then them being on the
49:18Internet but my goodness how do they
49:21hope to survive all of the changes
49:25modifications adaptations in
49:28interoperability requirements without a
49:31meta system without even for instance
49:34being able to load new things in while
49:38you're running so to me this is the fact
49:41that people adopted this as some great
49:44hope is probably the most distressing
49:47thing to be personally as I said since
49:49the ms-dos and it represents a real
49:53failure of people to understand what the
49:56larger picture is
49:58and is going to be next slide so this
50:07notion of metaprogramming lots of
50:10different ways of looking at it one of
50:13them is that any particular
50:16implementation is making pragmatic
50:19choices and these pragmatic choices are
50:23likely not to be able to cover all of
50:27the cases in the at the level of
50:30efficiency and even at the level of
50:33richness required of course this is
50:36standard OOP lore this is why we
50:39encapsulate we need to hide our messes
50:44we need to have different ways of
50:47dealing with this with the same concepts
50:49in a way that does not distract the
50:52programmer but in fact it's also
50:55applicable as the list people found and
50:59we at Xerox PARC found you can also
51:02apply it to the building of the language
51:04itself the more the language can see its
51:06own structures the more liberated you
51:10can be from the tyranny of a single
51:15implementation I think this is one of
51:18the most critical things that very few
51:19people are worrying about in a practical
51:22form one of the reasons why this meta
51:29stuff is going to be important in such a
51:32way that nobody will be able to ignore
51:34it is this whole question of how do we
51:37really interrupt operate on the Internet
51:40five and ten years from now if you think
51:44about it I don't believe Microsoft is
51:47going to be able to capture the Internet
51:48I think it's too big I think there are
51:52too many people supplying ideas into it
51:54and I think that people are going to be
51:57sophisticated enough to realize that an
51:59IBM or a Microsoft type solution is
52:02simply neither called for nor possible
52:06what that means is they're going to be
52:09dozens and does
52:11they're almost already are dozens and
52:15dozens of different object systems all
52:18with very similar semantics but with
52:20very different pragmatic details and if
52:25you think of what a URL actually is and
52:29you think of what an HTTP message
52:32actually is you can think of what an
52:34object actually is and if you think of
52:37what an object-oriented pointer actually
52:39is I think it should be pretty clear
52:42that any object-oriented language can
52:47internalize its own local pointers to
52:50any object in the world regardless of
52:52where it was made that's the whole point
52:54of not being able to see inside and so a
52:59semantic interoperability is possible
53:04almost immediately by simply taking that
53:07stance so this is going to change really
53:11everything and things like Java beans
53:13and CORBA are not going to are not going
53:16to suffice because at some point one is
53:20going to have to start really
53:21discovering what objects think they can
53:24do and this is going to lead to a
53:27universal interface language which is
53:29not a programming language per se it's
53:35more like a prototyping language but
53:38that allows an interchange of deep
53:42information about what objects think
53:44they can do allows objects to make
53:46experiments with other objects in a safe
53:48way to see how they respond to various
53:52messages this is going to be a critical
53:54thing to automate in the next 10 years
53:57next slide so here's a great book how
54:04many people read this book ok so when
54:09they wrote this book I called them up I
54:11said this is the best book anybody's
54:13written in 10 years but why the hell did
54:16you write it in such a Lisp centric
54:21closed
54:23club centric way this is a hard book for
54:27most people to read if you don't know
54:29the list culture it's very hard to read
54:32if you don't know how si los is done
54:37it's a very hard book to read this book
54:39has some of the most profound insights
54:41about and the most practical insights
54:44about OOP than anybody has done in the
54:47last many years so I really commend it
54:50to you and if there any university
54:54professors here who would like to get
54:56the next Limoge balloon I will give it
55:00to anybody who rewrites that book so
55:03that the general object-oriented
55:05community can understand it would be a
55:08great service to mankind so what
55:15happened in most of the world starting
55:18in this in the 70s was abstract data
55:21types which is really staying with an
55:24assignment centered way of thinking
55:27about programming and I believe that in
55:32fact when I made this slide C++ was not
55:35a was not was just sort of a speck on
55:38the horizon was not it's one of those
55:41things like ms-dos that nobody took
55:43seriously because who would ever fall
55:47for a joke like that next slide please
55:56- my favorite C++ story is at Apple
56:03there is this operating system
56:05remarkably coincidentally named pink
56:13it's so great and there are two
56:17interesting features of this new
56:20operating system that they're working on
56:21one was was always going to be done in
56:23two years and you know we have known
56:30some really great operating systems
56:32designers over over the years and I do
56:34not know of any decent operating system
56:36has ever been done in two years even by
56:39people who had ten times the IQ of the
56:42of the pink people and the other thing
56:45about it was that it was going to be
56:46done in C++ for efficiency oh let's not
56:52do it in small talk that's too slow well
56:56let me tell you there's nothing more
56:58inefficient than spending ten years on
57:01an operating system that never works
57:12actually the worst ones are the ones
57:15that appear to work
57:21[Applause]
57:25so let's let's take our pink plane and
57:29we can also use this McLuhan quote my
57:35favorite McLuhan quote I don't know who
57:36discovered water but it wasn't a fish
57:38and he he meant us as the fish and he
57:42meant water as our belief structures as
57:43our context I believe this is the single
57:47if you had to pick one cause of both
57:51particular difficulty in our field and
57:54also general difficulty in the human
57:57race it's taking single points of view
57:59and committing to them like their
58:01religions this this happened with small
58:04talk there's a wonderful quote by
58:06Schopenhauer German philosopher of the
58:10nineteen nineteenth century who said
58:12every idea goes through three stages
58:15first it's denounced as the work of
58:17madmen this is what Swift called
58:22confederacy of dunces and then later
58:28it's remarked as being totally obvious
58:34the whole time and then the last stage
58:39is when the original denouncer was
58:42claimed to have invented it that's when
58:47it gets in its religious stage now one
58:52of the to me the most distressing thing
58:53that happened to small talk when it came
58:54out of Xerox PARC was for many respects
58:58and purposes that quit changing now I
59:01can tell you at Xerox PARC there are
59:03four major versions completely different
59:06versions of the language over about a
59:09ten year period and many dozens and
59:13dozens of significant releases within
59:16those different versions and I think one
59:20of the things that we like the most
59:21about small talk was not what it could
59:23do but the fact that it was such a good
59:26vehicle for bootstrapping the next set
59:29of ideas we had about how to do systems
59:31building and that for all intents
59:33purposes when small talk went commercial
59:35ceased even though there was a book the
59:39famous blue book that Adele and Dave
59:42wrote that had the actual code in it for
59:46making small talk interpreters and
59:48starting this process oneself almost
59:51nobody took advantage of this almost no
59:53University took advantage of it
59:55almost no commercial insulation took
59:58advantage of it and what they missed was
60:01to me the deepest thing I would like to
60:03communicate with you today and that is
60:05we don't know how to design systems yet
60:08so let's not make what we don't know
60:10into a religion for God's sakes what we
60:13need to do is to constantly think and
60:16think and think about what's important
60:19and we have to have our systems let us
60:23get to the next levels of abstraction as
60:25we come to them and the thing that I'm
60:30most proud of about small talk pretty
60:32much the only thing from my standpoint
60:35that I'm proud of is that it has been so
60:38good at getting rid of previous versions
60:41of itself until it came out into this
60:44world now one of the reasons we got
60:48involved in doing small talk again after
60:51for me it was a 16 years of not working
60:54on programming languages a couple of
60:56years ago
60:57we started this project we call squeak
60:59which is simply not an attempt to give
61:03the world a free small talk but an
61:05attempt to give the world a
61:07bootstrapping mechanism for something
61:09much better than small talk and when you
61:12fooled around with squeak please please
61:14think of it from that stand of how you
61:17can obsolete the damn thing by using its
61:20own mechanisms for getting the next
61:22version of itself so look for the blue
61:29thoughts and
61:32I was trying to think of a way how could
61:35I stop this talk because I'll go on and
61:38on and I remembered a story I'm a pipe
61:41organist and most pipe Organists have a
61:47hero whose name was EEP our bigs
61:51he kind of revived the interest in the
61:56pipe organ especially as it was played
61:59in the 17th and 18th centuries and had a
62:02tremendous influence on all of us
62:04organists and a good friend of mine was
62:08epower Biggs his assistant for many
62:10years back in the 40s and 50s he's in
62:14his 80s now and when we get him for
62:18dinner we always get him to tell you
62:19power Biggs stories and the organ that
62:23he power Biggs had in those days for his
62:25broadcast was a dinky little organ
62:30neither fish nor fowl in a small Museum
62:34at Harvard called the bush wising or
62:37museum but in fact all manner of music
62:40was was played on it and one day this
62:43assistant had to fill in for Biggs and
62:45he asked Biggs well what is the piece
62:47played and he said well I had programmed
62:51Caesar Frank's heroic piece and if you
62:57know this piece it is made for the
62:59largest organs that have ever been made
63:01the loudest organs that have ever been
63:02made in the largest cathedrals that have
63:05ever been made because it's a 19th
63:07century symphonic pipe organ work and
63:10Biggs was asking my friend to play this
63:14on this dinky little organ and he said
63:19but how can i he says how can I play it
63:21on this on this and Biggs he said just
63:26play it grand just play it grand and the
63:32way to to stay with the future as it
63:36moves is to always play your systems
63:39more grand than they seem to be right
63:41now
63:42thank you
63:50[Music]
63:58[Music]
64:15[Music]
64:30you
