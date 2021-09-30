## المرح مع الحمم المتدفقة

كتلة ممتع جداً اللّعب بها هي الحمم المتدفقة.

```python
من mcpi.minecraft استورد Minecraft

mc = Minecraft.create()

x, y, z = mc.player.getPos()

lava = 10

mc.setBlock(x+3, y+3, z, lava)
```

جد الكتلة التي وضعتها للتو ، و يفترض أن ترى الحمم تتدفق من الكتلة إلى الأرض.

الجميل في الحمم هو أنها عندما تبرد تتحول إلى صخرة. انتقل لمكان آخر في عالمك وجرب هذا:

```python
من mcpi.minecraft استورد Minecraft
من time استورد sleep

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

يمكنك تعديل خيار `sleep` للسماح بتدفق أكثر أو أقل من الحمم.

![الحمم](images/lava.png)