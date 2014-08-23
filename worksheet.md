# Getting Started with Programming the Minecraft World

With Raspberry Pi you are able to write programs that take effect in the world of Minecraft! You will create a program to post a message to the chat screen, locate your player in a world, and have that player drop flowers when they walk on grass.

## Step 1: Post a message to Minecraft Pi

We are going to have some fun with Minecraft Pi and the chat window.

1. Start by double clicking the LXTerminal icon on the desktop to open a terminal window and entering the following commands to run Minecraft:

    ```bash
    cd mcpi
    ./minecraft-pi
    ```

1. When Minecraft has loaded, click on **Start Game**, followed by **Create new**.

1. Hit the tab key on your keyboard to gain control of your mouse outside of the Minecraft window, then double click the IDLE icon again to open the Python environment window.

1. Click `File > New Window` to open a new text editor window.

1. Click `File > Save` and navigate to `mcpi/api/python` then save the empty file as `chat.py`.

1. Type the following three lines:

    ```python
    import mcpi.minecraft as minecraft
    mc = minecraft.Minecraft.create()
    mc.postToChat("Type your message here")
    ```

    Replace the `Type your message here` with your own message, like `Minecraft rocks!`

    Remember to use capital letters in the right places in the code!

1. Now save your file with `Ctrl+X Ctrl+S` and then run with `F5`.

## Step 2: Finding a Player's Location

Your Minecraft Pi Python program is beginning to take shape! Now you are going to add some code to locate where the player is in the Minecraft world.

1. At the top of the file, underneath `import mcpi.minecraft as minecraft`, add the following line:

	```python
	from time import sleep
	```

	This will import the `sleep` function from the `time` module, allowing you to add pauses to your program.

1. Now go to the bottom of your code, and type the following underneath the last line:

	```python
	sleep(1)
	x, y, z = mc.player.getPos()
	mc.postToChat("You are located @ x: %s / y: %s / z: %s" % (x, y, z))
	```

	The command `getPos` (get position) will locate the co-ordinates of your player in Minecraft. This information will then be displayed in the chat window.

1. Save your program and run again with `F5`.

	What happens?

	`mc.player.getPos()` will return the player's location in the Minecraft world. This information is then stored in the variable `pos` so that you can send that information to the chat window in Minecraft with `mc.postToChat`.

## Step 3: Drop Flower Blocks

So far you have located your player's position and posted information to the chat window. Now you will write some Python code to drop flower blocks.

To do this we can create a loop that checks the player's location, and sets a flower block at that player's position every tenth of a second.

1. Return to your code and go to `File > Save as` and save in the same folder, but with a new name: `flowers.py`. This has made a copy to keep the old code saved and work on a new file without having to type out the essential lines at the top again.

1. Delete the lines from `sleep` onwards, and replace with the following:

	```python
	flower = 38
	```

	Minecraft blocks use values to identify them; Minecraft block ID 38 is a flower. We used a variable here to store the value as well as to remind us what it is! This is useful if you are using lots of different types of block in your program.

1. Next you'll add a few lines to perform a loop that goes on forever:

	```python
	while True:
		x, y, z = mc.player.getTilePos()
		mc.setBlock(x, y, z, flower)
		sleep(0.1)
	```

    The code beneath the `while` line needs to be indented. IDLE will do this for you, but make sure you don't lose the indentation.

1. Save and run the code. Then run around and see what happens...

## Things to try next

- Adapt the code so that flower blocks are only dropped on grass
- Replace the flower block number with a number for another type of block
- Drop TNT blocks!
