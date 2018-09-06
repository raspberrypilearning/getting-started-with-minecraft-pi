## Du plaisir avec la lave en fusion!

### Liste de contrôle d'activité

+ Un bloc qui est très amusant à utiliser est la lave en fusion.
```Python
    from mcpi.minecraft import Minecraft

    mc = Minecraft.create()

    x, y, z = mc.player.getPos()

    lave = 10

    mc.setBlock(x+3, y+3, z = lave)
```

Trouvez le bloc que vous venez de placer et vous devriez voir de la lave en fusion couler du bloc vers le sol.

+ Ce qui intéressant avec la lave c'est qu'en refroidissant elle devient de la pierre. Déplacez vous à une autre position dans le monde et essayez ceci:
```Python
    from mcpi.minecraft import Minecraft
    from time import sleep

    mc = Minecraft.create()

    x, y, z = mc.player.getPos()

    lave = 10
    eau = 8
    air = 0

    mc.setBlock(x+3, y+3, z, lave)
    sleep(20)
    mc.estBlock(x+3, y+5, z, eau)
    sleep(4)
    mc.setBlock(x+3, y+5, z, air)
```

Vous pouvez ajuster les paramètres de la fonction `sleep` pour laisser plus ou moins de lave couler.

![Capture d'écran](images/mcpi-lava.png)