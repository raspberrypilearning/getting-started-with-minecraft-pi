## Dropping blocks as you walk

Now you know how to drop blocks, let's use our moving location to drop blocks when you walk.

The following code will drop a flower behind you wherever you walk:

```python
from mcpi.minecraft import Minecraft
from time import sleep

mc = Minecraft.create()

flower = 38

while True:
    x, y, z = mc.player.getPos()
    mc.setBlock(x, y, z, flower)
    sleep(0.1)
```

Now walk forward for a while and turn around to see the flowers you have left behind you.

![](images/mcpi-flowers.png)

Since we used a `while True` loop this will go on forever. To stop it, hit `Ctrl + C` in the Python window.

Try flying through the air and see the flowers you leave in the sky:

![](images/mcpi-flowers-sky.png)

What if we only wanted to drop flowers when the player walks on grass? We can use `getBlock` to find out what type a block is:

```python
x, y, z = mc.player.getPos()  # player position (x, y, z)
this_block = mc.getBlock(x, y, z)  # block ID
print(this_block)
```

This tells you the location of the block you're standing *in* (this will be `0` - an air block). We want to know what type of block we're standing *on*. For this we subtract 1 from the `y` value and use `getBlock()` to determine what type of block we're standing on:

```python
x, y, z = mc.player.getPos()  # player position (x, y, z)
block_beneath = mc.getBlock(x, y-1, z)  # block ID
print(block_beneath)
```

This tells us the ID of the block the player is standing on.

Test this out by running a loop to print the block ID of whatever you're currently standing on:

```python
while True:
    x, y, z = mc.player.getPos()
    block_beneath = mc.getBlock(x, y-1, z)
    print(block_beneath)
```

![](images/blockbeneath.gif)

We can use an `if` statement to choose whether or not we plant a flower:

```python
grass = 2
flower = 38

while True:
    x, y, z = mc.player.getPos()  # player position (x, y, z)
    block_beneath = mc.getBlock(x, y-1, z)  # block ID

    if block_beneath == grass:
        mc.setBlock(x, y, z, flower)
    sleep(0.1)
```

Perhaps next we could turn the tile we're standing on into grass if it isn't grass already:

```python
if block_beneath == grass:
    mc.setBlock(x, y, z, flower)
else:
    mc.setBlock(x, y-1, z, grass)
```

Now we can walk forward and if we walk on grass, we'll leave a flower behind. If the next block is not grass, it turns into grass. When we turn around and walk back, we now leave a flower behind us.

![](images/mcpi-flowers-grass.png)

