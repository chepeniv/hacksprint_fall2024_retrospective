# Tourist Simulator

for the given prompt, travel, we came up with the idea to create a
simulator of what being a tourist trapped in a foreign city is like without
actually having to leave the comfort of one's own home, for much less the
cost, and delivering a realistic experience complete with disappointment and
unpleasant interactions

## Background

three times a year, new students in their second trimester at atlas, are tasked
with their first ever open-ended group project, the hacksprint. a much
mythologized undertaking which seems to have taken on the ritualistic aura of a
right-of-passage. the hacksprint is kicked off with the announcement of the
one-word theme. the challenge is to then come up with a workable product idea
matching the theme and actually deliver a working prototype in the span of one
week. that's it, but boy is it challenging.

## the Team

the crew we assembled together was Malik Vance, Michael Ballou, and I, Chepe.
even though we had some preliminary delegation of what our responsibilities were
going to be, we more-or-less naturally fell into our roles. Michael carried out
the research for the various algorithms we could use, as well as helping Malik
finalize the presentation. Malik for his part developed the core story elements:
the plot, lore, interactions, and dialogue. He built the asset library which we
were going to use. primarily, he took charge of putting together the
presentation, writing out the `README`, and coming up with a user-interface
theme for our the final product. I laid out the website structure, defined the
various placeholder `css` themes, built the core game mechanics and logic, built
the server. Most proudly, I developed the maze generating algorithm, as well as
the encoding and decoding functions. naturally, since i was most familiar with
the codebase, most all of the refactoring, restructuring, and debugging of our
code base fell upon me as well.

## Description

we based our maze game on the plot that through some unfortunate happenstance
you find yourself nearly wiped out of cash and with your essential belongings
missing. as a result, you frantically run around lost trying to somehow gather
enough cash to buy yourself a plane ticket back home.

## the Experience

the first thing we did was consider all the creative sources we could draw
inspiration from that also fit the theme. in conjunction to that we also
brainstormed the various kinds of projects we could take on. we made our choice
through a mix-and-match process of these two aspects.

following that, we made the shift to then making a first approximation of what
our minimum-viable-product (mvp) was going to look like, laying out the core
structure, determining the necessary technologies, discussing schedules and
availability, and partitioning responsibilities.

the overall development for me involved a lot of solitary all-night coding. it's
really the way i like to work. unfortunately however, this means that there's a
builtin delay in communication between me and my team. compounding to the
difficulties, were the circumstances that my partners had with various
commitments outside of our project that had to be attended to. those primarily
being their work and personal relationships. for better or worse, their
resultant absence gave me the liberty to take initiative on my own without much
consultation.

in the end, i really enjoyed the entire development process. going from
composing the front-end, the interactive logic, setting up the back-end, writing
the maze algorithm, and determining how to handle the generated data was really
more enlightening than i initially thought. i really gained an appreciation for
the way that the whole website delivery pipeline is put together.

furthermore, i found hunting down bugs was also pretty engaging and quite
revealing as to how the various technologies are implemented.

finally, the day came which we had to present our accomplishment. personally, i
think i was fairly chill about it. nonetheless, i found it wise to do a few
practice runs to gain some comfort, familiarity, and flow with what i would be
presenting. i'd say our presentation itself was nothing noteworthy, but it did
go well.

although we had the least impressive ui, the part that i found most unexpected
was the positive reception and interest the algorithm and encoding, i had come
up with, received from my peers and instructor. it was quite validating to see
my hard work appreciated by people i respect. i ended up basically giving a
short impromptu lecture on the way my algorithm works after the formal
presentation ceremony itself. that was cool.

## Challenges

besides any of the issues we had with coordinating with each other and our
availability, the technical challenges we ran into were quite typical -- typos,
various idiosyncrasies of the technologies we used, as well as working around
how they handled the various data by default. mostly however, `css` was a
pain-point here and there, and finding out that we really did _need_ to use a
server was initially disappointing. this led to quite the drastic restructuring
and refactoring in order to implement properly.

perhaps the most challenging thing to get right, however, was actually
determining what the mvp was going to be. as issues arose that would expand our
expected workload, we had to consider where to scale back on what we could
realistically deliver with the given timeframe.

## Technical

on the technical side, the tools and workflow was fairly standard. firstly,
we laid down the `html` structure, then defined the `css` classes to decorate
our webpage. we then wrote the interactive logic with `jquery`. to then store
and read data we used `json`. we implemented the backend with `flask`. and the
whole maze generating algorithm was basically implemented with vanilla `python`.
the only crucial import therein was `choice` from the `random` module. the
rendering of it was then done with `javascript` and `css`. that was pretty much
it.

the overall structure ended up being composed of three core directories:
`static/`, `utility/`, and `templates/`. within `static/` the subdirectories
created were `assets/`, `data/`, `scripts/`, and `styles`. lastly the two `python`
scripts which made everything possible are `frontend.py` for the `flask` server
and `maze_gen.py` for the maze generating and encoding algorithms.

## End Result

given the limited time allotted what we ultimately were able to produce was an
abstract core game which is basic and functional enough to serve as a foundation
for others to build their own maze games over.

the basic experience is the player has control of a single block which they use
to navigate the maze. they are able to collect items along the way and add them
to their inventory. there is also an encounter game mechanic for players to
interact with characters in the game. these encounters along with the inventory
items can then affect one of the two pre-built stats. once the player
reaches the end of the maze, the webpage reloads a new randomly generated
maze, populated randomly with items and encounters as well, for the players to
navigate and the game continues. right now the game goes on indefinitely, but
an end-point can certainly be coded in at some point.

## Lessons

so what are the lessons learned here ? life lessons, i don't know, but
technical ones i do. i gained an appreciation of the way a website service is
setup between an end-user's machine, their browser, and the server, how a web
service then has to be put together to then fit the constraints given be this
framework, and lastly i learned how to generate random mazes, how to encode and
decode the data generated, how to optimize the various algorithms involved
for both space and time, and how to render a maze in a browser.

## Closing Statement

i have nothing significant to say, but for now, i'm just relieved that it's
over. i feel liberated to finally have time to my self, so that i can take
care of my own life as my laundry has actually pilled up...

----

### Addendum

given the encoding i had settled on for the wall configuration of the blocks, a
more efficient alternative would have been to use bytes instead of `int`'s where
each bit represents one of the wall's presence in order of `btlr`

```python
	#   x --  l --  r -- lr   (y + x)
[	#  00 -- 01 -- 10 -- 11
	[0000, 0001, 0010, 0011], # 00 y
	[0100, 0101, 0110, 0111], # 01 t
	[1000, 1001, 1010, 1011], # 10 b
	[1100, 1101, 1110, 1111]  # 11 tb
]
```

however since the directional ordering isn't very natural we could modify our
scheme further. if we reverse the elements of the code table, this allows us to
achieve the more intuitive ordering of `tblr`

```python
	#   x --  l --  r -- lr   (y + x)
[	#  00 -- 01 -- 10 -- 11
	[1111, 1110, 1101, 1100]  # 11 tb
	[1011, 1010, 1001, 1000], # 10 t
	[0111, 0110, 0101, 0100], # 01 b
	[0011, 0010, 0001, 0000], # 00 y
]
```

finally, in order to then implement this encoding we would need to make few
modifications to our algorithm. primarily, we would need to initiate each block
with index (0, 0) rather than (3, 3) and to then perform the inverse indexing
operation when generating the paths -- that is, to sum instead of subtract.
