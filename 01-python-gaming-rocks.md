Let's start with pythongaming dot rocks.

This resource is a high level overview of a number of game libraries with an eye to where they fit in the ecosystem.
From the low level libraries that give us hardware access and various game engines and frameworks in both the 3d space and 2d
space, plus specialized engines for specific genres of game development.

It also tries to answer the question of why use python instead of another tool.

Let's do the whirlwind tour:

In hardware layers we have a bunch of tools. There's Pygame and Pyglet, both venerable at this point, and straddling the line
between low level access and a full feature game framework. They do a little of both. Pygame is quickly approaching version 2,
where they'll be switching to SDL2 which should bring incredible perfomance gains.

In more pure hardware access libraries, you have PySDL2 which when combined with pysdl2-dll can be pip installed on Windows and
Mac systems with pip, no additional downloads needs. If you prefer OpenGL, there's PyOpenGL and moderngl out there for you.

And if you're looking to do VR, Harfang supports Python scripting.

From those bunch, we're off to the frameworks, and there are plenty:

Panda3D has been around for longer than I've been talking about game design and does 3D games with Python scripting. Built on top
of that we have Ursina Engine, the other bear themed game engine in Python.

In 2D games we have even more choices:

Arcade, built on top of Pyglet, is a library built for teaching code, with focus on typical programming building blocks: A sprite
list looks and feels like a list. It pitches simplicity as it's primary goal.

Also built on pyglet is cocos2d, which has multiple bindings across languages. If you have experience with cocos2d in another
language, this might be a good place to try python for game dev.

Then there's PyGame zero that is both a PyGame based framework and a game runner. It's primary focus is eliminating the
boilerplate of pygame.

Then there's Kivy which is as much a GUI toolkit as it is a game engine, with a specific focus on mobile development.

And no discussion of Python based game engines is complete without mentioned Ren'Py: It's been around for a long time and a number
of visual novels have been built in it. It uses a custom domain specific language, but the engine itself is Python.

And the only engine I haven't talked about here is mine: PursuedPyBear.
