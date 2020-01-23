## Čo budete potrebovať

### Softvér

#### Inštalácia softvéru

Minecraft je predinštalovaný v Raspbian-e od septembra roku 2014.

![Minecraft Pi desktop icon](images/minecraft-pi-shortcut.png)

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

Keď je Minecraft spustený a svet je vytvorený, odísť z hry môžete stlačením klávesu `Tab`, ktorý vám uvoľní myš. Open Python 3 (IDLE) on the Desktop and move the windows so they're side-by-side.

Príkazy môžete zadávať priamo do okna Python-u alebo si môžete vytvoriť súbor, aby ste mohli svoj kód uložiť a znova spustiť neskôr.

Ak chcete vytvoriť súbor, prejdite na `File > New window` a `File > Save`. Pravdepodobne ho budete chcieť uložiť vo vašom domovskom priečinku alebo v novom priečinku pre projekty.

Začnite tým, že importujete knižnicu Minecraft, vytvoríte spojenie s hrou a otestujete ho odoslaním správy "Hello world" na obrazovku:

```python
from mcpi import minecraft

mc = minecraft.Minecraft.create()

mc.postToChat("Hello world")
```

Ak zadávate príkazy priamo do okna Pythonu, stlačte `Enter` po každom riadku. Ak píšete do súboru, uložíte ho stlačením `Ctrl + S` a spustíte s `F5`. Keď spustíte váš kód, mali by ste vidieť vašu správu v hre na obrazovke.

![](images/mcpi-idle.png)

Ak vidíte "Hello world" v okne hry Minecraft, možete pokračovať v ďalšom kroku.