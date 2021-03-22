## S'amuser avec de la lave qui coule.

Un bloc avec lequel il est très amusant de jouer est la lave qui coule.

```python
from mcpi.minecraft import Minecraft

mc = Minecraft.create()

x, y, z = mc.player.getPos()

lava = 10

mc.setBlock(x+3, y+3, z, lava)
```

Trouve le bloc que tu viens de placer et tu devrais voir de la lave couler du bloc vers le sol.

Ce qui est cool à propos de la lave, c'est que lorsqu'elle refroidit, elle devient de la roche. Déplace-toi vers un autre endroit de votre monde et essaye ceci:

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

Tu peux ajuster les `sleep` pour permettre à plus ou moins de lave de couler.

![lave](images/lava.png)