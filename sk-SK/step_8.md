## Zábava s tečúcou lávou.

Jedným blokom, s ktorým si užijete veľa zábavy, je tečúca láva.

```python
from mcpi.minecraft import Minecraft

mc = Minecraft.create()

x, y, z = mc.player.getPos()

lava = 10

mc.setBlock(x+3, y+3, z, lava)
```

Nájdite blok, ktorý ste práve umiestnili a mali by ste vidieť lávu tečúcu z tohto bloku na zem.

Na láve je super, že keď sa ochladí, stane sa kameňom. Presuňte sa na iné miesto vo vašom svete a vyskúšajte toto:

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
mc.setBlock(x+3,y+5, z, water)
sleep(4)
mc.setBlock(x+3, y+5, z, air)

```

Pomocou parametra `sleep` môžete nastaviť, či bude lávy vytekať viac alebo menej.

![láva](images/lava.png)