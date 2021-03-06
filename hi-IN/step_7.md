## TNT ब्लॉक के साथ खेलना

एक और दिलचस्प ब्लॉक TNT (विस्फोटक) है! एक सामान्य TNT ब्लॉक को रखने के लिए इसका उपयोग करें:

```python
tnt = 46
mc.setBlock(x, y, z, tnt)
```

![](images/mcpi-tnt.png)

हालांकि, यह TNT ब्लॉक काफी उबाऊ है। `data` (डेटा) को `1` के रूप में लागू करने का प्रयास करें:

```python
tnt = 46
mc.setBlock(x, y, z, tnt, 1)
```

अब अपनी तलवार का उपयोग करें और TNT ब्लॉक पर बायाँ क्लिक करें: यह सक्रिय हो जाएगा और कुछ ही सेकंड में इसमें विस्फोट हो जाएगा!

अब TNT ब्लॉक का एक बड़ा घन बनाने का प्रयास करें!

```python
tnt = 46
mc.setBlocks(x+1, y+1, z+1, x+11, y+11, z+11, tnt, 1)
```

![](images/mcpi-tnt-blocks.png)

अब आप TNT ब्लॉक से भरा एक बड़ा घन देखेंगे। जाएँ और किसी एक ब्लॉक को सक्रिय करें और फिर शो देखने के लिए वहाँ से भाग जाएँ! ग्राफिक्स को प्रस्तुत करना वास्तव में धीमा होगा क्योंकि कई चीजें एक साथ बदल रही हैं।

![](images/mcpi-tnt-explode.png)