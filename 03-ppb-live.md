So I'm going to demonstrate what I mean.

First, once you have a functioning environment, you can make a window with
two lines of code:

import ppb

ppb dot run

```python
import ppb

ppb.run()
```

To add your first sprite, you just need to do this: modify the run function
with a lambda, accepting a scene object, and add a Sprite to that scene.

```python
import ppb

ppb.run(setup=lambda scene: scene.add(ppb.Sprite()))
```

Now we have block on the screen. This is. . . not the most useful thing, so
how about we replace sprite with our default behavior sprite TargetSprite.

Here, I'm setting some values on the TargetSprite. ppb sprites accept
arbitrary keyword arguments and set them as values on the Sprite. This is
great for rapidly iterating on something.

```python
import ppb
from ppb.features import default_sprites

ppb.run(
    setup=lambda scene: scene.add(
        default_sprites.TargetSprite(
            position=ppb.Vector(0, -9),
            target=ppb.Vector(0, 20)
        )
    )
)
```

Movement!

Now, if you watch, I'm going to add a `target_sprite.png` to my project
directory and rerun this. And now we have a spaceship 

And what about player interaction?

We need to make some edits as we've been relying on built ins so far.

First, let's make our scene class Ship. We'll need to rename our image file,
or we can just add a ppb.Image and point to the `target_sprite.png` instead.

Let's give our Ship a default speed of 5. You can use class attributes to
provide fallback values if you don't set them elsewhere.

And then we'll write our first event handler: on_mouse_motion.

Here, we're going to typehint our event with a MouseMotion event type.

Then we set the Ship's target and facing based on the mouse motion.

Down in the lambda, lets delete everything inside the add, and replace it
with a Ship. It doesn't need any additional values.

```python
import ppb
from ppb.features import default_sprites


class Ship(default_sprites.TargetSprite):
    image = ppb.Image('target_sprite.png')
    speed = 5

    def on_mouse_motion(self, event: ppb.events.MouseMotion, signal):
        self.target = event.position
        self.facing = event.position - self.position


ppb.run(setup=lambda scene: scene.add(Ship()))
```

So in <<<time>>> we've built a tiny video game.

(Honestly, this is much more impressive when I do it live, but I hope I've
made my point.)
