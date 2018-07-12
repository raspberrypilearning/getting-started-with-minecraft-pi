## Použite rozhranie programovacieho jazyka Python

Keď je Minecraft spustený a svet je vytvorený, odísť z hry môžete stlačením klávesu `Tab`, ktorý vám uvoľní myš. Z ponuky aplikácií otvorte Python 3 a usporiadajte okná tak, aby boli vedľa seba.

Príkazy môžete zadávať priamo do okna Python-u alebo si môžete vytvoriť súbor, aby ste mohli svoj kód uložiť a znova spustiť neskôr.

Ak chcete vytvoriť súbor, prejdite na `File > New window` a `File > Save`. Pravdepodobne ho budete chcieť uložiť vo vašom domovskom priečinku alebo v novom priečinku pre projekty.

Začnite tým, že importujete knižnicu Minecraft, vytvoríte spojenie s hrou a otestujete ho odoslaním správy "Hello world" na obrazovku:

```python
from mcpi.minecraft import Minecraft

mc = Minecraft.create()

mc.postToChat("Hello world")
```

Ak zadávate príkazy priamo do okna Pythonu, stlačte `Enter` po každom riadku. Ak píšete do súboru, uložíte ho stlačením `Ctrl + S` a spustíte s `F5`. Keď spustíte váš kód, mali by ste vidieť vašu správu v hre na obrazovke.

![](images/helloworld.gif)

### Zistite svoju polohu

Ak chcete zistiť svoju polohu, napíšte:

```python
pos = mc.player.getPos()
```

`pos` teraz obsahuje vašu pozíciu; získať pristup ku každej časti z množiny súradníc môžete cez `pos.x`, `pos.y` a `pos.z`.

Ďalší pekný spôsob, ako sa k súradniciam dostať cez samostatné premenné, je použiť techniku rozbaľovania jazyka Python:

```python
x, y, z = mc.player.getPos()
```

Premenné `x`, `y`a `z` teraz obsahujú každú súradnicu vašej polohy. `x` a `z` sú súradnice určujúce smer chôdze (dopredu/dozadu a doľava/doprava) a `y` je pre smer hore/dole.

Všimnite si, že `getPos()` vracia miesto hráča v danom čase a ak ho presuniete, musíte funkciu zavolať znovu alebo použiť uloženú lokáciu.

### Teleport

Podobne, ako zistenie vašaj aktuálnej polohy, môžete určiť konkrétne miesto, na ktoré sa chcete teleportovať.

```python
x, y, z = mc.player.getPos()
mc.player.setPos(x, y+100, z)
```

Týmto sa váš hráč presunie o 100 pozícií do vzduchu. To znamená, že sa teleportujete do stredu oblohy a okamžite začnete padať späť na miesto, kde ste začali.

Skúste sa teleportovať niekde inde!

### Vytvorenie bloku

Jeden blok môžete umiestniť na zvolené súradníce zavolaním `mc.setBlock()`:

```python
x, y, z = mc.player.getPos()
mc.setBlock(x+1, y, z, 1)
```

Vedľa miesta, kde stojíte, by sa mal objaviť blok kameňa. Ak nie je hneď pred vami, môže byť vedľa vás alebo za vami. Vráťte sa do okna Minecraft a pomocou myši otočte sa na mieste, kým neuvidíte šedý blok priamo pred vami.

![](images/mcpi-setblock.png)

Argumenty odovzdané `set bloku` sú `x`, `r`, `z` a `číslo`. `(x, y, z)` vzťahuje na pozíciu na svete (určili sme jeden blok od miesta, kde hráč stojí `x + 1`) a `id` týka typu bloku, ktorý by sme rád umiestniť. `1` je kameň.

Ďalšie bloky si môžete vyskúšať:

    Air:   0
    Grass: 2
    Dirt:  3
    

Teraz s blokom v očiach skúste zmeniť ho na niečo iné:

```python
mc.setBlock(x+1, y, z, 2)
```

Mali by ste vidieť zmenu sivého kamenného bloku pred tvojimi očami!

![](images/mcpi-setblock2.png)

#### Blokové konštanty

Môžete použiť vstavané blokové konštanty na nastavenie blokov, ak poznáte ich názvy. Budete potrebovať ďalšie `import` riadok prvej hoci.

```python
from mcpi import block
```

Teraz môžete napísať nasledovné a umiestniť blok:

```python
mc.setBlock(x+3, y, z, block.STONE.id)
```

Bloky ids sú docela ľahké uhádnuť, stačí použiť ALL CAPS, ale tu je niekoľko príkladov, ako si zvyknúť na spôsob, akým sú pomenované.

    WOOD_PLANKS
    WATER_STATIONARY
    GOLD_ORE
    GOLD_BLOCK
    DIAMOND_BLOCK
    NETHER_REACTOR_CORE
    

### Blok ako premenná

Ak poznáte id bloku, môže byť užitočné nastaviť ho ako premennú. Môžete použiť meno alebo celé číslo id.

```python
dirt = 3
mc.setBlock(x, y, z, dirt)
```

alebo

```python
dirt = block.DIRT.id
mc.setBlock(x, y, z, dirt)
```

### Špeciálne bloky

Existujú niektoré bloky, ktoré majú ďalšie vlastnosti, napríklad Vlna, ktorá má nastavenie navyše, môžete určiť farbu. Ak chcete nastaviť toto použitie, voliteľný štvrtý parameter v `setBlock`:

```python
wool = 35
mc.setBlock(x, y, z, wool, 1)
```

Tu štvrtý parameter `1` nastaví farbu vlny na oranžovú. Bez štvrtého parametra je nastavená na predvolenú hodnotu (`0`), ktorá je biela. Niektoré ďalšie farby sú:

    2: Magenta
    3: Light Blue
    4: Yellow
    

Skúste ešte viac čísel a sledujte zmenu bloku!

Ďalšie bloky, ktoré majú ďalšie vlastnosti, sú drevo (`17`): dub, smrek, breza atď .; vysoká tráva (`31`): ker, tráva, papraď; baterka (`50`): smerujúca na východ, západ, sever, juh; a viac. Viac informácií nájdete v referenčnom dokumente [API](http://www.stuffaboutcode.com/p/minecraft-api-reference.html).

### Nastaviť viac blokov

Rovnako ako nastavenie jedného bloku s `setBlock` môžete vyplniť objem priestoru v jednom kroku s `setBlocks`:

```python
stone = 1
x, y, z = mc.player.getPos()
mc.setBlocks(x+1, y+1, z+1, x+11, y+11, z+11, stone)
```

Tým sa vyplní 10 x 10 x 10 kocka pevného kameňa.

![](images/mcpi-setblocks.png)

Môžete vytvoriť väčšie zväzky s funkciou `setBlocks` ale generovanie môže trvať dlhšie!