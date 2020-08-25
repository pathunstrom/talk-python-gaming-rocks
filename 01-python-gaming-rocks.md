Let's start with pythongaming dot rocks.

This resource is a high level overview of a number of game libraries with an
eye to where they fit in the ecosystem. From the low level libraries that
give Python developers hardware access and various game engines and
frameworks in both the 3d space and 2d space, plus specialized engines for
specific genres of game development.

It also tries to answer the question of why use python instead of another
language.

The important elements:

Python was historically slow and in head to head performance against
machine code is often slower, at this point has become performant enough to
work for many kinds of game making. The tradeoff for the slower execution
speed is a language with much more powerful semantics (including type
hinting for those who prefer their static typing) and a much faster
development cycle.

All of this makes python a _great_ choice for small independent games or
rapid prototyping. Combine all of the above with Python's presence as a
great language to learn with and you have the building blocks of a great
education curriculum.

So let's do the whirlwind tour of the space:

In hardware layers we have a bunch of tools. The idea behind calling these
hardware layers is that they handle most (or all) of the native code
required to have performant games in Python. Some of them include a lot of
extra features specific to game making, so don't write these off as _just_
hardware libraries.

At the top of the list is `pygame`, primarily for name recognition if
nothing else. `pygame` is a number of C extensions with its own bindings to
SDL onboard. It's been around forever, and it has released its last
1 point x release: the team's entire focus in knocking down pygame 2 bugs
and getting that out the door.

`pygame` includes one of the best axis-aligned bounding box classes I've 
ever used, though I have some complaints about how its properties are named.
It also pitches itself as providing a significant amount of control over the
game loop: Instead of your code being called by the framework, you call the
relevant Pygame methods. I can attest to the amount of control available as
early versions of ppb were built with `pygame` as our primary dependency.

The other big contender at the top of the list is `pyglet` which bills
itself as a cross-platform windowing and multimedia library. In short, its
for games and things that look like games. `pyglet` vendors all of its
dependencies, so it's always been easy to install on most platforms. Its big
winning feature is a Sprite class that does a lot of the work for you when
rendering.

In more pure hardware access libraries, you have PySDL2 which when combined
with pysdl2-dll can be pip installed on Windows and
Mac systems, no additional downloads needs.

If you prefer OpenGL, there's PyOpenGL and moderngl out there for you.

Finally if you're looking to do VR, Harfang supports Python scripting and
Kivy's focus is mobile applications.

From those bunch, we're off to higher level frameworks, with plenty of
options out there.

Panda3D has been around for longer than I've been talking about game
development. It's built in C++ and supports both C++ and Python APIs and
focuses on 3d games. I can't say much more about it except that they claim
you can build your first game in 15 minutes, which is impressive in the
Python game dev world.

From here, most of the other tools are actually improved APIs on top of
existing tools.

Starting with the newest of the bunch, Ursina Engine is a 3d engine built on
top of Panda3d. Its focus has been making more pythonic APIs on top of the
existing one.

Then we have Arcade, built on top of Pyglet. Its design was for teaching
code generally, and so most of its objects use the standard Python protocols
for the built-in type those objects are most like. One of its big wins is a built-in
physics engine for platformers.

Also built on pyglet is cocos2d, which has multiple bindings across
languages. If you have experience with cocos2d in another language, this
might be a good place to try python for game dev.

Another tool available is PyGame Zero, which is the PyGame API but with an
additional event loop which reduces the amount of boilerplate required to
get started. It does some magic with its script runner to put the most
relevant pygame and pygame zero functions into the global name space so you
just need to call the functions without import.

No discussion of Python based game engines is complete without at least a mention
Ren'Py: It's been around for a long time and a number of visual novels have
been built in it. It uses a custom domain specific language, but the engine
itself is Python.

The great thing about this ecosystem is that with the number of projects and
developers working in the space, there are now enough options to satisfy
just about everyone's tastes. From loose frameworks to full fledged engines.
Great options with all the batteries included or leaner libraries and a
cluster of utility libraries. No matter how you like to code, you've got an
option.

Now this tour is missing one contender I care a lot about: my engine, ppb.
So let's talk about that in a bit of detail.

------
run-times:
1. 4:06
------