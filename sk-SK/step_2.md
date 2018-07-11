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

Môžete buď zadávať príkazy priamo do okna Pythonu, alebo vytvoriť súbor, aby ste mohli uložiť kód a spustiť ho znova inokedy.

Ak chcete vytvoriť súbor, prejdite na `Súbor > Nové okno` a `Súbor > Uložiť`. Pravdepodobne budete chcieť uložiť to vo vašom domovskom priečinku alebo v novom priečinku projektu.

Začnite tým, že importujete knižnicu Minecraft, vytvoríte pripojenie k hre a testujete ju odoslaním správy "Hello world" na obrazovku:

```python
z mcpi import minecraft mc = minecraft.Minecraft.create () mc.postToChat ("Hello world")
```

Ak zadávate príkazy priamo do okna Pythonu, stlačte `Po každom riadku zadajte`. Ak je to súbor, uložte s `Ctrl + S` a spustite s `F5`. Po spustení kódu by ste mali vidieť svoju správu na obrazovke v hre.

![](images/mcpi-idle.png)

Ak vidíte okno "Dobrý deň svet" v okne Minecraft, je dobré pokračovať v ďalšom kroku.