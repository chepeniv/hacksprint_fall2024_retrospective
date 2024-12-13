# Tourist Simulator

for the given prompt, travel, we came up with the idea to create a
simulator of what being a tourist trapped in a foreign city is like without
actually having to leave the comfort of one's own home, for much less the
cost, and delivering a realistic experience complete with disappointment and
unpleasant interactions

## Background

three times a year, new students in their second trimester at atlas, are tasked
with their first open-ended group project, the hacksprint. a much mythologized
undertaking which seems to have taken on the ritualistic aura of a
right-of-passage. the hacksprint is kicked off with the announcement of the
one-word theme. the challenge is to then come up with a workable product idea
matching the theme and actually deliver a working prototype in the span of one
week. that's it, but boy is it challenging.

the crew we assembled together was Malik Vance, Michael Balou, and I, Chepe.
malik - story elements, theming, asset library, presentation, readme, and slides
michael - maze gen algorithm research, presentation
chepe - front end website logic, back end server, maze gen algorithm, and maze
data handling

## Description

this is a maze game based on the plot that through some unfortunate happenstance
you find yourself nearly wiped out of cash and with your essential belongings
gone, you frantically run around lost trying to somehow gather enough cash to
buy yourself a plane ticket back home.

## Experience

### beginning

drawing inspirations, brainstorming kinds of projects, laying out the structure,
determining the technologies necessary, planning out our schedules, delegating
responsibilities, gauging the mvp

### middle

late night coding, partners out of town / on the road, busy with work,
taking over other's responsibilities, fixing issues, reliance, having to
dramatically restructure the project

enjoyed putting together the website structure, setting up the core css classes,
building the interactive logic, and creating the algorithms to handle the maze

getting swamped

hunting down bugs wasn't that bad

### end

interacting with peers, instructors, the audience

putting together a last minute presentation without any planed monologue

the unexpected interest others had and their positive reception to my work

having to give a post presentation talk about the algorithm itself

the relief of it being over

## Challenges

what the mvp was ultimately going to be
from my perspective
restructuring and refactoring
people don't have enough time seemingly -- my sleep schedule
technical and collaborative
expectations, unforeseen issues
css issues, having to use flask, technical idiosyncrasies

## Technical

%% tools

standard html, css, jquery, json, flask, and pretty much vanilla python

the front end
drawing a maze
generating a maze

### Structure

frontend.py
static/
	assets/
	data/
	scripts/
	styles/
utility/
	maze_gen.py
templates/
	homepage.py

## End Result

given the limited time allotted what we ultimately were able to produce was an
abstract core game which is basic and functional enough to serve as a foundation
for others to build their own maze games over

### Demo / Experience

## Lessons

a browsers role between a user's machine and a server
how a website has to be put together to fit the constraints given
how to generate a random maze, encode it, decode it, and draw it

%% closing statement

   x --  l --  r -- lr (y + x)
  00 -- 01 -- 10 -- 11
0000  0001  0010  0011 -- 00 y
0100  0101  0110  0111 -- 01 t
1000  1001  1010  1011 -- 10 b
1100  1101  1110  1111 -- 11 tb
