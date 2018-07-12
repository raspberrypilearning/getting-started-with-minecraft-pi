## Zábava s blokmi TNT

Ďalším zaujímavým blokom je TNT! Ak chcete umiestniť normálny blok TNT, použite:

```python
tnt = 46
mc.setBlock(x, y, z, tnt)
```

![](images/mcpi-tnt.png)

Tento blok TNT je však dosť nudný. Skúste použiť `data` s hodnotou `1`:

```python
tnt = 46
mc.setBlock(x, y, z, tnt, 1)
```

Teraz použite svoj meč a kliknite ľavým tlačidlom na blok TNT: ten sa aktivuje a za niekoľko sekúnd exploduje!

Teraz sa pokúste vytvoriť veľkú kocku blokov TNT!

```python
tnt = 46
mc.setBlocks(x+1, y+1, z+1, x+11, y+11, z+11, tnt, 1)
```

![](images/mcpi-tnt-blocks.png)

Teraz uvidíte veľkú kocku plnú blokov TNT. Choďte a aktivujte jeden z blokov a potom utečte, aby ste sa pozreli na show! Bude to naozaj pomalé vykresliť grafiku, pretože toľko vecí sa mení naraz.

![](images/mcpi-tnt-explode.png)