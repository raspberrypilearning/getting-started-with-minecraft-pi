## Wat heb je nodig

### Software

#### Software installatie

Minecraft is standaard in Raspbian geïnstalleerd sinds september 2014.

![Minecraft Pi-bureaubladpictogram](images/minecraft-pi-shortcut.png)

Als je een oudere versie van Raspbian gebruikt, open je een terminalvenster en typ je de volgende opdrachten (je moet online zijn):

```bash
sudo apt-get update
sudo apt-get install minecraft-pi
```

Zodra dat is voltooid, moeten Minecraft Pi en de Python-bibliotheek worden geïnstalleerd.

#### Test Minecraft

Dubbelklik op het bureaubladpictogram om Minecraft uit te voeren of voer `minecraft-pi` in de terminal in.

![](images/mcpi-start.png)

Wanneer Minecraft Pi is geladen, klik je op **Start Game**, vervolgens op **Create new**. Je zult merken dat het venster enigszins is verschoven. Dit betekent dat als je het venster wilt slepen, je de titelbalk achter het Minecraft-venster moet pakken.

![](images/mcpi-game.png)

Je speelt nu een spelletje Minecraft!

#### Test Python

Terwijl Minecraft actief is en de wereld gecreëerd is, breng je je aandacht weg van het spel door op de `Tab` toets te drukken, waardoor je muis vrijkomt. Open Python 3 (IDLE) op het bureaublad en verplaats de vensters zodat ze naast elkaar staan.

Je kunt opdrachten rechtstreeks in het Python-venster typen of een bestand maken zodat je jouw code kunt opslaan en deze een andere keer opnieuw kunt uitvoeren.

Als je een bestand wilt maken, ga je naar `File > New window` en `File > Save`. Je wilt dit waarschijnlijk in je thuismap of een nieuwe projectmap opslaan.

Begin met het importeren van de Minecraft-bibliotheek, maak een verbinding met de game en test het door het bericht "Hallo wereld" op het scherm te plaatsen:

```python
from mcpi import minecraft

mc = minecraft.Minecraft.create ()

mc.postToChat ("Hallo wereld")
```

Als je opdrachten rechtstreeks in het Python-venster invoert, druk je na elke regel op `Enter`. Als het een bestand is, sla het op met `Ctrl + S` en voer het uit met `F5`. Wanneer jouw code wordt uitgevoerd, zou je jouw bericht op het scherm in het spel moeten zien.

![](images/mcpi-idle.png)

Als je "Hallo wereld" ziet in het Minecraft-venster, kun je doorgaan naar de volgende stap.