## Mit TNT-Blöcken spielen

Ein weiterer interessanter Block ist TNT! Um einen normalen TNT-Block zu platzieren, verwende:

```python
tnt = 46
mc.setBlock(x, y, z, tnt)
```

![](images/mcpi-tnt.png)

Dieser TNT-Block ist jedoch ziemlich langweilig. Versuche, `Daten` als `1` hinzuzufügen:

```python
tnt = 46
mc.setBlock(x, y, z, tnt, 1)
```

Verwende jetzt dein Schwert und klicke mit der linken Maustaste auf den TNT-Block: Er wird aktiviert und explodiert in Sekundenschnelle!

Versuche nun, einen großen Würfel aus TNT-Blöcken zu erstellen!

```python
tnt = 46
mc.setBlocks(x+1, y+1, z+1, x+11, y+11, z+11, tnt, 1)
```

![](images/mcpi-tnt-blocks.png)

Jetzt siehst du einen großen Würfel voller TNT-Blöcke. Geh hin und aktiviere einen der Blöcke und renne dann weg, um die Show zu sehen! Das Rendern der Grafiken wird sehr langsam sein, da sich so viele Dinge gleichzeitig ändern.

![](images/mcpi-tnt-explode.png)