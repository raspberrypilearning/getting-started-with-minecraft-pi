## Zábava s tečúcou lávou.

Jedným blokom, s ktorým sa hrá veľa zábavy, je tečúca láva.

```python
z mcpi.minecraft import Minecraft mc = Minecraft.create () x, y, z = mc.player.getPos () lava = 10 mc.setBlock (x + 3, y + 3, z, lava)
```

Nájdite blok, ktorý ste práve umiestnili a mali by ste vidieť lávu tečúcu z bloku na zem.

Chladná vec o láve je, že keď sa ochladí, stane sa to rock. Presuňte sa na iné miesto vo vašom svete a skúste to:

```python
z mcpi.minecraft import Minecraft z času importu spánku mc = Minecraft.create () x, y, z = mc.player.getPos () lava = 10 voda = 8 vzduchu = 0 mc.setBlock (x + 3, y + 3 (x + 3, y + 5, z, voda) spánok (20) mc.setBlock (x +

```

Parametre `spánku` môžete nastaviť tak, aby umožnili viac alebo menej toku lávy.

![láva](images/lava.png)