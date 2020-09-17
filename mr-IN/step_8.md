## वाहत्या लावा सह गम्मत

खेळायला खूप मजा असलेला एक ब्लॉक म्हणजे वाहता लावा.

```python
from mcpi.minecraft import Minecraft

mc = Minecraft.create()

x, y, z = mc.player.getPos()

lava = 10

mc.setBlock(x+3, y+3, z, lava)
```

आपण आत्ताच ठेवलेला ब्लॉक शोधा आणि आपल्याला त्या ब्लॉकवरून जमिनीवर वाहणारा लावा दिसला पाहिजे.

लावा बद्दल छान गोष्ट अशी आहे की जेव्हा ते थंड होते तेव्हा ते खडक होते. आपल्या जगातील दुसर्‍या ठिकाणी जा आणि हे करून पहा:

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

आपण लावाला कमी-अधिक प्रमाणात प्रवाहीत करण्यासाठी `sleep` (स्लीप) हे पॅरामीटर समायोजित करू शकता.

![लावा](images/lava.png)