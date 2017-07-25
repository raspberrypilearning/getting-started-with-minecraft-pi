## Use the Python programming interface

With Minecraft running, and the world created, bring your focus away from the game by pressing the `Tab` key, which will free your mouse. Open Python 3 from the application menu and move the windows so they're side-by-side.

You can either type commands directly into the Python window or create a file so you can save your code and run it again another time.

If you want create a file, go to `File > New window` and `File > Save`. You'll probably want to save this in your home folder or a new project folder.

Start by importing the Minecraft library, creating a connection to the game and testing it by posting the message "Hello world" to the screen:

```python
from mcpi.minecraft import Minecraft

mc = Minecraft.create()

mc.postToChat("Hello world")
```

If you're entering commands directly into the Python window, just hit `Enter` after each line. If it's a file, save with `Ctrl + S` and run with `F5`. When your code runs, you should see your message on screen in the game.

![](images/helloworld.gif)

### Find your location

To find your location, type:

```python
pos = mc.player.getPos()
```

`pos` now contains your location; access each part of the set of coordinates with `pos.x`, `pos.y` and `pos.z`.

Alternatively, a nice way to get the coordinates into separate variables is to use Python's unpacking technique:

```python
x, y, z = mc.player.getPos()
```

Now `x`, `y`, and `z` contain each part of your position coordinates. `x` and `z` are the walking directions (forward/back and left/right) and `y` is up/down.

Note that `getPos()` returns the location of the player at the time, and if you move position you have to call the function again or use the stored location.

### Teleport

As well as finding out your current location you can specify a particular location to teleport to.

```python
x, y, z = mc.player.getPos()
mc.player.setPos(x, y+100, z)
```

This will transport your player to 100 spaces in the air. This will mean you'll teleport to the middle of the sky and fall straight back down to where you started.

Try teleporting to somewhere else!

### Set block

You can place a single block at a given set of coordinates with `mc.setBlock()`:

```python
x, y, z = mc.player.getPos()
mc.setBlock(x+1, y, z, 1)
```

Now a stone block should appear beside where you're standing. If it's not immediately in front of you it may be beside or behind you. Return to the Minecraft window and use the mouse to spin around on the spot until you see a grey block directly in front of you.

![](images/mcpi-setblock.png)

The arguments passed to `set block` are `x`, `y`, `z` and `id`. The `(x, y, z)` refers to the position in the world (we specified one block away from where the player is standing with `x + 1`) and the `id` refers to the type of block we'd like to place. `1` is stone.

Other blocks you can try:

```
Air:   0
Grass: 2
Dirt:  3
```

Now with the block in sight, try changing it to something else:

```python
mc.setBlock(x+1, y, z, 2)
```

You should see the grey stone block change in front of your eyes!

![](images/mcpi-setblock2.png)

#### Block constants

You can use a inbuilt block constants to set your blocks, if you know their names. You'll need another `import` line first though.

```python
from mcpi import block
```

Now you can write the following to place a block: 

```python
mc.setBlock(x+3, y, z, block.STONE.id)
```

Block ids are pretty easy to guess, just use ALL CAPS, but here are a few examples to get you used to the way they are named.

```
WOOD_PLANKS
WATER_STATIONARY
GOLD_ORE
GOLD_BLOCK
DIAMOND_BLOCK
NETHER_REACTOR_CORE
```

### Block as variable

If you know the id of a block it can be useful to set it as a variable. You can use the name or the integer id.

```python
dirt = 3
mc.setBlock(x, y, z, dirt)
```

or

```python
dirt = block.DIRT.id
mc.setBlock(x, y, z, dirt)
```

### Special blocks

There are some blocks which have extra properties, such as Wool which has an extra setting you can specify the colour. To set this use the optional fourth parameter in `setBlock`:

```python
wool = 35
mc.setBlock(x, y, z, wool, 1)
```

Here the fourth parameter `1` sets the wool colour to orange. Without the fourth parameter it is set to the default (`0`) which is white. Some more colours are:

```
2: Magenta
3: Light Blue
4: Yellow
```

Try some more numbers and watch the block change!

Other blocks which have extra properties are wood (`17`): oak, spruce, birch, etc; tall grass (`31`): shrub, grass, fern; torch (`50`): pointing east, west, north, south; and more. See the [API reference](http://www.stuffaboutcode.com/p/minecraft-api-reference.html) for full details.

### Set multiple blocks

As well as setting a single block with `setBlock` you can fill in a volume of space in one go with `setBlocks`:

```python
stone = 1
x, y, z = mc.player.getPos()
mc.setBlocks(x+1, y+1, z+1, x+11, y+11, z+11, stone)
```

This will fill in a 10 x 10 x 10 cube of solid stone.

![](images/mcpi-setblocks.png)

You can create bigger volumes with the `setBlocks` function but it may take longer to generate!

