## Kladenie blokov počas chôdze

Keď už viete, ako klásť bloky, poďme využiť zmenu našej polohy tak, aby sme mohli bloky klásť počas chôdze.

Nasledujúci kód bude za vás klásť kvietky kamkoľvek pôjdete:

```python
from mcpi.minecraft import Minecraft
from time import sleep

mc = Minecraft.create()

flower = 38

while True:
    x, y, z = mc.player.getPos()
    mc.setBlock(x, y, z, flower)
    sleep(0.1)
```

Teraz sa chvíľku poprechádzajte a otočte sa za seba, aby ste videli kvietky, ktoré ste za sebou nechali.

![](images/mcpi-flowers.png)

Vzhľadom na to, že sme použili cyklus `while True`, bude sa kód vykonávať donekonečna. Ak ho chcete zastaviť, stlačte v okne jazyka Python `Ctrl + C`.

Skúste sa preletieť vzduchom a sledujte kvietky, ktoré za sebou na oblohe zanechávate:

![](images/mcpi-flowers-sky.png)

Čo ak by sme chceli kvietky klásť len vtedy, ak sa hráč bude pohybovať po tráve? Na zistenie typu bloku môžeme použiť funkciu `getBlock`:

```python
x, y, z = mc.player.getPos()  # pozicia hraca (x, y, z)
this_block = mc.getBlock(x, y, z)  # ID bloku
print(this_block)
```

Tým získate polohu bloku, *v* ktorom stojíte (čo bude `0` - blok vzduchu). My však chceme vedieť, akého typu je blok, *na* ktorom stojíme. Za týmto účelom odčítame 1z hodnoty súradnice `y` a pomocou volania funkcie `getBlock()` zistíme typ bloku, na ktorom stojíme:

```python
x, y, z = mc.player.getPos()  # pozicia hraca (x, y, z)
block_beneath = mc.getBlock(x, y-1, z)  # ID bloku
print(block_beneath)
```

Tým zistíme ID bloku, na ktorom hráč stojí.

Otestujte to vytvorením cyklu, ktorý bude vypisovať ID akéhokoľvek bloku, na ktorom hráč práve stojí:

```python
while True:
    x, y, z = mc.player.getPos()
    block_beneath = mc.getBlock(x, y-1, z)
    print(block_beneath)
```

![](images/blockbeneath.gif)

Aby sme rozhodli, či kvietok zasadíme alebo nie, použijeme príkaz `if`:

```python
grass = 2
flower = 38

while True:
    x, y, z = mc.player.getPos()  # pozicia hraca (x, y, z)
    block_beneath = mc.getBlock(x, y-1, z)  # ID bloku

    if block_beneath == grass:
        mc.setBlock(x, y, z, flower)
    sleep(0.1)
```

Možno by sme mohli zmeniť dlaždice, na ktorých stojíme, na trávu, ak už náhodou trávou nie sú:

```python
if block_beneath == grass:
    mc.setBlock(x, y, z, flower)
else:
    mc.setBlock(x, y-1, z, grass)
```

Teraz môžeme kráčať dopredu a ak kráčame po tráve, položíme za seba kvietok. Ak však ďalší blok nie je tráva, zmení sa na trávu. Keď sa otočíme a budeme kráčať naspäť, budeme za sebou nechávať kvietky.

![](images/mcpi-flowers-grass.png)