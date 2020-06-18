## Spaß mit fließender Lava.

Ein Block, mit dem es viel Spaß macht zu spielen, ist fließende Lava.

```python
from mcpi.minecraft import Minecraft

mc = Minecraft.create()

x, y, z = mc.player.getPos()

lava = 10

mc.setBlock(x+3, y+3, z, lava)
```

Suche den Block, den du gerade platziert hast und du solltest sehen, wie Lava vom Block zum Boden fließt.

Das Coole an Lava ist, dass sie beim Abkühlen zu Fels wird. Bewege dich an einen anderen Ort in deiner Welt und versuche Folgendes:

```python
from mcpi.minecraft import Minecraft
from time import sleep

mc = Minecraft.create()

x, y, z = mc.player.getPos()

lava = 10
wasser = 8
luft = 0

mc.setBlock(x+3, y+3, z, lava)
sleep(20)
mc.setBlock(x+3, y+5, z, wasser)
sleep(4)
mc.setBlock(x+3, y+5, z, luft)

```

Du kannst die `sleep`-Parameter anpassen, damit mehr oder weniger Lava fließen kann.

![Lava](images/lava.png)