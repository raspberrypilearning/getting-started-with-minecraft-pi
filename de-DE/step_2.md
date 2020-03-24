## Was du brauchen wirst

### Software

#### Software installation

Minecraft ist seit September 2014 standardmäßig in Raspbian installiert.

![Minecraft Pi desktop icon](images/minecraft-pi-shortcut.png)

Wenn Sie eine ältere Version von Raspbian verwenden, öffnen Sie ein Terminalfenster und geben Sie die folgenden Befehle ein (Sie müssen online sein):

```bash
sudo apt-get update
sudo apt-get install minecraft-pi
```

Sobald dies abgeschlossen ist, sollten Minecraft Pi und die Python-Bibliothek installiert werden.

#### Test Minecraft

To run Minecraft double click the desktop icon or enter `minecraft-pi` in the terminal.

![](images/mcpi-start.png)

When Minecraft Pi has loaded, click on **Start Game**, followed by **Create new**. You'll notice that the containing window is offset slightly. This means to drag the window around you have to grab the title bar behind the Minecraft window.

![](images/mcpi-game.png)

You are now in a game of Minecraft!

#### Test Python

With Minecraft running, and the world created, bring your focus away from the game by pressing the `Tab` key, which will free your mouse. Open Python 3 (IDLE) on the Desktop and move the windows so they're side-by-side.

You can either type commands directly in to the Python window or create a file so you can save your code and run it again another time.

If you want create a file go to `File > New window` and `File > Save`. You'll probably want to save this in your home folder or a new project folder.

Start by importing the Minecraft library, creating a connection to the game and testing it by posting the message "Hello world" to the screen:

```python
from mcpi import minecraft

mc = minecraft.Minecraft.create()

mc.postToChat("Hello world")
```

If you're entering commands directly in to the Python window, just hit `Enter` after each line. If it's a file, save with `Ctrl + S` and run with `F5`. When your code runs, you should see your message on screen in the game.

![](images/mcpi-idle.png)

If you see "Hello world" in the Minecraft window, you're good to proceed to the next step.