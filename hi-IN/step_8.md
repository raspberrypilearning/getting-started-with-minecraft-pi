## बहते लावा के साथ मज़ा।

बहता लावा एक ऐसा ब्लॉक है जिसे खेलने में बहुत मज़ा आता है।

```python
from mcpi.minecraft import Minecraft

mc = Minecraft.create()

x, y, z = mc.player.getPos()

lava = 10

mc.setBlock(x+3, y+3, z, lava)
```

जिस ब्लॉक को आपने अभी-अभी रखा है उसे ढूँढें, और आपको उस ब्लॉक से जमीन पर बहता हुआ लावा दिखाई देना चाहिए।

लावा के बारे में एक बढ़िया बात यह है कि ठंडा हो जाने पर यह चट्टान बन जाता है। अपनी दुनिया में किसी दूसरी लोकेशन पर जाएँ और इसे आजमाएँ:

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
mc.setBlock(x+3,y+5, z, water)
sleep(4)
mc.setBlock(x+3, y+5, z, air)

```

आप लावा को अधिक या कम प्रवाहित करने के लिए `sleep` (स्लीप) के पैरामीटर समायोजित कर सकते हैं।

![लावा](images/lava.png)