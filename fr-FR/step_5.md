## Étape 4: Jouer avec des blocs de TNT!

### Liste de contrôle d'activité

+ Un autre bloc intéressant est le bloc de TNT! Pour placer un bloc de TNT, utilisez:
```Python
    tnt = 46
    mc.setBlock(x, y, z, tnt)
```

![Capture d'écran](images/mcpi-tnt.png)

+ Toutefois, ce bloc de TNT est plutôt ennuyant. Essayez de régler `data` à `1`:
```Python
    tnt = 46
    mc.setBlock(x, y, z, tnt, 1)
```

+ Maintenant, utilisez votre épée et cliquez à gauche sur le bloc de TNT: Il sera activé et explosera d'ici quelques secondes!

+ Essayez maintenant de créer un énorme cube de blocs de TNT!
```Python
    tnt = 46
    mc.setBlocks(x+1, y+1, z+1, x+11, y+11, z+11, tnt, 1)
```

![Capture d'écran](images/mcpi-tnt-blocks.png)

Vous verrez maintenant un gros cube plein de blocs de TNT. Allez activer un bloc puis courrez pour aller regarder le spectacle d'une bonne distance! Le rendu graphique sera lent étant donné que beaucoup de choses changent en même temps.

![Capture d'écran](images/mcpi-tnt-explode.png)