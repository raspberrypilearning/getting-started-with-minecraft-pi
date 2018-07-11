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

#### Test Minecraft

Na spustenie aplikácie Minecraft dvakrát kliknite na ikonu pracovnej plochy alebo do terminálu zadajte `minecraft-pi`.

![](images/mcpi-start.png)

Keď Minecraft Pi naloží, kliknite na **Spustiť hru**, potom **Vytvoriť nové**. Všimnete si, že okno s obsahom je mierne posunuté. To znamená pretiahnuť okno okolo vás musí chytiť titulku za oknom Minecraft.

![](images/mcpi-game.png)

Teraz ste v hre Minecraft!

#### Test Python

Spustenie Minecraft a vytvorenie sveta prinesie vašu pozornosť od hry stlačením klávesu `Tab` , ktorý vám uvoľní myš. Otvorte IDLE (nie IDLE3) na pracovnej ploche a presuňte okná tak, aby boli vedľa seba.

Môžete buď zadávať príkazy priamo do okna Pythonu, alebo vytvoriť súbor, aby ste mohli uložiť kód a spustiť ho znova inokedy.

Ak chcete vytvoriť súbor, prejdite na `Súbor > Nové okno` a `Súbor > Uložiť`. Pravdepodobne budete chcieť uložiť to vo vašom domovskom priečinku alebo v novom priečinku projektu.

Začnite tým, že importujete knižnicu Minecraft, vytvoríte pripojenie k hre a testujete ju odoslaním správy "Hello world" na obrazovku:

```python
z mcpi import minecraft mc = minecraft.Minecraft.create () mc.postToChat ("Hello world")
```

Ak zadávate príkazy priamo do okna Pythonu, stlačte `Po každom riadku zadajte`. Ak je to súbor, uložte s `Ctrl + S` a spustite s `F5`. Po spustení kódu by ste mali vidieť svoju správu na obrazovke v hre.

![](images/mcpi-idle.png)

Ak vidíte okno "Dobrý deň svet" v okne Minecraft, je dobré pokračovať v ďalšom kroku.