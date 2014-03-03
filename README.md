# Programming the Minecraft World

**Introduction:**

With Raspberry Pi you are able to write programs that take effect in the world of Minecraft! You will create a program to post a message to the chat screen, locate your player in a world, and have that player drop flowers when they walk on grass.

A Raspberry Pi is a small computer that we can use to create exciting technology. It was created in the UK by the Raspberry Pi Foundation to help young people like you learn how to code.

This small computer features amazing HD (high-definition) quality video and playback, sports high quality audio and has the ability to play 3D games. 

To get going with your Raspberry Pi, you will need to connect cables and add an SD card before logging in.

## Step 0: Setting Up your Pi
First check that you have all the parts you need to get your Raspberry Pi set up and working:

- Raspberry Pi
- Micro USB power adapter
- An SD Card with Raspbian already set up through NOOBS
- USB Keyboard
- USB Mouse
- HDMI cable
- A Monitor or TV
- Some headphones 

**Activity Checklist:**

1.	Place the SD card into the slot of your Raspberry Pi. It will only fit one way so be careful not to break the card. 

2.	Next connect the HDMI cable from the monitor (or TV) to the HDMI port on the Pi and turn on your monitor. 

3.	Plug in a USB keyboard and Mouse into the USB slots on the Pi.

4.	Plug in your headphones to the 3.5mm sound output jack.

5.	Plug in the micro USB power supply and you should see some text appear on your screen.

6.	When prompted to login type:

	```
	Login: pi
	Password: raspberry
	```

7.	Once you have logged in, type startx to load the desktop.


##Step 1: Post a message to Minecraft Pi

We are going to have some fun with Minecraft Pi and the chat window.

To begin, you will need to be able to write Python code into a text editor. For this you can use the text editor nano in a terminal window.

**Activity Checklist:**

1.	Begin by opening LXTerminal and running Minecraft Pi if it is not already running, by typing the following lines:

  ```
  cd mcpi

  ./mincraft-pi
  ```

2.	When Minecraft Pi has loaded, click on **Start Game**, followed by **Create new**. 

3.	Go back to the LXTerminal window on your desktop using your mouse, and open a new tab by clicking on **File** and **New Tab**.

    You need an open tab so that you can type commands in LXTerminal to run your code whilst Minecraft Pi is also running.

4.	Next, make sure that you are in the correct folder by typing `cd api/python`

5.	To create your first Python Minecraft Program type the following to open the text editor nano and name your file `nano chat.py`

6.	Type the following line and press enter:

    ```python
    import mcpi.minecraft as minecraft
    ```

  This imports the minecraft module into your Python program.

7.	Underneath, type the following being sure to use a capital letter for the second minecraft:

    ```python
    mc = minecraft.Minecraft.create()
    ```

    This line connects the Python program you are coding to Minecraft.

8.	Now type the command that will post a message to the screen in Minecraft:

    ```python
    mc.postToChat("Type your message here")
    ```
    Replace the "Type your message here" with your own message, like "Code Club is awesome!"
    Remember to use capital letters in the right places too!

9.	Press `CTRL+X` at the same time to exit, and press `Y` (for Yes) followed by `Enter` to save your code.

10.	To run your program in the LXTerminal window type `python chat.py`


## Step 2: Finding a Players Location

Your Minecraft Pi Python program is beginning to take shape! Now you are going to add some code to locate where the player is in the Minecraft world.


**Activity Checklist:**

1.	Open flowers.py in a text editor like nano. You can do this from an LXTerminal window by navigating to the correct folder like this:

	```
	cd mcpi/api/python
	```

	You can check to see if the file is there by typing the command `ls`. Then type `nano chat.py`

2.	At the top of the file, underneath `import mcpi.minecraft as minecraft`, type the following code:

	```python
	import time
	```

	This will import the time time module allowing you to add pauses to your program.

3.	Now go to the bottom of your code, and type underneath the last line the following:

	```python
	time.sleep (1)
	pos = mc.player.getPos()
	posTemplate = "You are located @ x: {0} / y: {1} / z: {2}"
	mc.postToChat(posTemplate.format(pos.x, pos.y, pos.z))
	```
 
	The command getPos, short for get position will locate the co-ordinates of your player in Minecraft. This 			information will then be displayed in the chat window in Minecraft. 

4.	Save your program. If you are using nano press `CTRL+X`, then `Y`, and `Enter`.

5.	Run your code in LXTerminal, ensuring that Minecraft Pi is already running, by typing `python chat.py`

	What happens?
	
	`mc.player.getPos()` will return the players location in the minecraft world. This information is then stored in 		the variable pos so that you can send that information to the chat window in Minecraft in the line
	`mc.postToChat(posTemplate.format(pos.x, pos.y, pos.z))`


## Step 3: Drop Flower Blocks

So far you have located your players position and posted information to the chat window. Now you will write some python code to drop flower blocks.

To do this we can create a loop that checks the players location and sets a flower block at that players position every 0.1 of a second.

**Activity Checklist:**

1.	Create a new python file by typing `nano flowers.py` in an LXTerminal window. 

2.	Type the following code to connect your python program to Minecraft Pi:

	```python
	import mcpi.minecraft as minecraft
	import time
	mc = minecraft.Minecraft.create()
	```
	
3.	Underneath type the following variable:

	```python
	flower = 38
	```
	
	Minecraft blocks use values to identify them. Minecraft Block ID 38 is a flower. We used a variable here to store 	the value as well as remind us what it is! This is useful if you were using lots of different types on block in your 	program.

4.	Navigate to the bottom of your program and type while True: to begin the loop. The capital letter T used here is 		important, make sure you use the same capital letters in your code!

	The code entered after this needs to be indented. If you are using nano you will need to press the tab button on 		the keyboard:

	```python
	while True:
		pos = mc.player.getTilePos()
		mc.setBlock(pos.x, pos.y, pos.z, flowers, 1)
		time.sleep(0.1)
	```

5.	Save and exit nano by pressing `CTRL + X`, then `Y` for yes, and `Enter`.

6.	Ensure that you have minecraft Pi running and are in a world, then run your code by typing the following into an 		LXTerminal Window:

	```
	python flowers.py
	```
	
	

