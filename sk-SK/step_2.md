## Čo budete potrebovať

### Softvér

#### Inštalácia softvéru

Minecraft je predinštalovaný v Raspbian-e od septembra roku 2014.

![Ikona Minecraft Pi na pracovnej ploche](images/minecraft-pi-shortcut.png)

Ak používate staršiu verziu systému Raspbian, otvorte okno terminálu a zadajte nasledujúce príkazy (musíte byť pripojený):

```bash
sudo apt-get update
sudo apt-get install minecraft-pi
```

Po skončení by stem mali mať nainštalovaný Minecraft Pi spolu s knižnicou pre jazyk Python.

#### Testujeme Minecraft

Ak chcete spustiť aplikáciu Minecraft, dvakrát kliknite na ikonu na pracovnej ploche alebo zadajte príkaz `minecraft-pi` do terminálu.

![](images/mcpi-start.png)

Keď sa Minecraft Pi spustí, kliknite na **Start Game** a následne na **Create new**. Všimnete si, že príslušné okno je mierne posunuté. To znamená, že ak chcete okno presunúť, musíte ho chytiť za titulok okna za oknom aplikácie Minecraft.

![](images/mcpi-game.png)

Teraz ste v hre Minecraft!

#### Testujeme Python

Keď je Minecraft spustený a svet je vytvorený, odísť z hry môžete stlačením klávesu `Tab`, ktorý vám uvoľní myš. Na pracovnej ploche otvorte prostredie IDLE (nie IDLE3) a usporiadajte okná tak, aby boli vedľa seba.

Príkazy môžete zadávať priamo do okna Python-u alebo si môžete vytvoriť súbor, aby ste mohli svoj kód uložiť a znova spustiť neskôr.

Ak chcete vytvoriť súbor, prejdite na `File > New window` a `File > Save`. Pravdepodobne ho budete chcieť uložiť vo vašom domovskom priečinku alebo v novom priečinku pre projekty.

Začnite tým, že importujete knižnicu Minecraft, vytvoríte spojenie s hrou a otestujete ho odoslaním správy "Hello world" na obrazovku:

```python
from mcpi import minecraft

mc = minecraft.Minecraft.create()

mc.postToChat("Hello world")
```

Ak zadávate príkazy priamo do okna Pythonu, stlačte `Enter` po každom riadku. Ak píšete do súboru, uložíte ho stlačením `Ctrl + S` a spustíte s `F5`. Keď sa váš kód spustí, mali by ste vidieť vašu správu v hre na obrazovke.

![](images/mcpi-idle.png)

Ak vidíte okno "Dobrý deň svet" v okne Minecraft, je dobré pokračovať v ďalšom kroku.