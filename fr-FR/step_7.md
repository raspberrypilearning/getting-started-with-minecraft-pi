## Jouer avec des blocs TNT

Un autre bloc intéressant est TNT! Pour placer un bloc TNT normal, utilise:

```python
tnt = 46
mc.setBlock(x, y, z, tnt)
```

![](images/mcpi-tnt.png)

Cependant, ce bloc TNT est assez ennuyeux. Essaye de passer la valeur `1` à `data` :

```python
tnt = 46
mc.setBlock(x, y, z, tnt, 1)
```

Maintenant, utilise ton épée et fais un clic gauche sur le bloc TNT: il sera activé et explosera en quelques secondes!

Essaie maintenant de créer un gros cube de blocs TNT!

```python
tnt = 46
mc.setBlocks(x+1, y+1, z+1, x+11, y+11, z+11, tnt, 1)
```

![](images/mcpi-tnt-blocks.png)

Maintenant tu verras un gros cube plein de blocs TNT. Va activer l'un des blocs puis pars vite pour regarder le spectacle! Le rendu des graphiques sera très lent car il y a tellement de choses qui sont modifiées à la fois.

![](images/mcpi-tnt-explode.png)