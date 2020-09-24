## ಹರಿಯುವ ಲಾವಾದೊಂದಿಗೆ ಮೋಜು.

ಹರಿಯುವ ಲಾವಾ ಒಂದು ಬ್ಲಾಕ್ ಆಗಿದ್ದು ಅದು ಆಡಲು ತುಂಬಾ ಖುಷಿಯಾಗುತ್ತದೆ.

```python
from mcpi.minecraft import Minecraft

mc = Minecraft.create()

x, y, z = mc.player.getPos()

lava = 10

mc.setBlock(x+3, y+3, z, lava)
```

ನೀವು ಈಗ ಇರಿಸಿರುವ ಬ್ಲಾಕ್ ಅನ್ನು ಹುಡುಕಿ, ಮತ್ತು ಆ ಬ್ಲಾಕ್ನಿಂದ ಲಾವಾ ನೆಲಕ್ಕೆ ಹರಿಯುವುದನ್ನು ನೀವು ನೋಡಬೇಕು.

ಲಾವಾದ ಬಗ್ಗೆ ಒಂದು ವಿಶೇಷವಾದ ವಿಷಯವೆಂದರೆ, ತಣ್ಣಗಾದಾಗ ಅದು ಬಂಡೆಯಾಗುತ್ತದೆ. ಇದನ್ನು ಪ್ರಯತ್ನಿಸಲು ನಿಮ್ಮ ಜಗತ್ತಿನ ಮತ್ತೊಂದು ಸ್ಥಳಕ್ಕೆ ತೆರಳಿ:

```python
from mcpi.minecraft import Minecraft
from time import sleep

mc = Minecraft.create()

x, y, z = mc.player.getPos()

lava = 10
water = 8
air = 0

mc.setBlock(x+3, y+3, z, lava)
sleep(20)
mc.setBlock(x+3, y+5, z, water)
sleep(4)
mc.setBlock(x+3, y+5, z, air)

```

ಲಾವಾ ಹೆಚ್ಚು ಅಥವಾ ಕಡಿಮೆ ಹರಿಯುವಂತೆ ಮಾಡಲು ನೀವು `sleep` (ನಿದ್ರೆ) ನಿಯತಾಂಕಗಳನ್ನು ಹೊಂದಿಸಬಹುದು.

![ಲಾವಾ](images/lava.png)