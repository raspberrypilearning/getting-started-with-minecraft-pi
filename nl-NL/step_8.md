## Plezier met vloeiende lava.

Een blok dat erg leuk is om mee te spelen is stromende lava.

```python
from mcpi.minecraft import Minecraft

mc = Minecraft.create()

x, y, z = mc.player.getPos()

lava = 10

mc.setBlock(x+3, y+3, z, lava)
```

Vind het blok dat je zojuist hebt geplaatst en je zou de lava van het blok naar de grond moeten zien stromen.

Het leuke van lava is dat wanneer het afkoelt, het rots wordt. Ga naar een andere locatie in je wereld en probeer dit:

```python
from mcpi.minecraft import Minecraft
from time import sleep

mc = Minecraft.create()

x, y, z = mc.player.getPos()

lava = 10
water = 8
air = 0

mc.setBlock(x+3, y+3, z, lava)
sleep(20)
mc.setBlock(x+3, y+5, z, water)
sleep(4)
mc.setBlock(x+3, y+5, z, air)

```

Je kunt de `sleep` parameters aanpassen om meer of minder lava te laten stromen.

![lava](images/lava.png)