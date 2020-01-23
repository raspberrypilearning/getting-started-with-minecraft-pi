## Spelen met TNT-blokken

Een ander interessant blok is TNT! Om een normaal TNT-blok te plaatsen, gebruik:

```python
tnt = 46
mc.setBlock(x, y, z, tnt)
```

![](images/mcpi-tnt.png)

Dit TNT-blok is echter behoorlijk saai. Probeer `data` als `1` toe te passen:

```python
tnt = 46
mc.setBlock(x, y, z, tnt, 1)
```

Gebruik nu je zwaard en klik met de linkermuisknop op het TNT-blok: het wordt geactiveerd en zal binnen enkele seconden exploderen!

Probeer nu een grote kubus van TNT-blokken te maken!

```python
tnt = 46
mc.setBlocks(x+1, y+1, z+1, x+11, y+11, z+11, tnt, 1)
```

![](images/mcpi-tnt-blocks.png)

Nu zie je een grote kubus vol TNT-blokken. Activeer een van de blokken en ren dan weg om de show te bekijken! Het zal even duren om de afbeeldingen weer te geven, omdat zoveel dingen tegelijkertijd veranderen.

![](images/mcpi-tnt-explode.png)