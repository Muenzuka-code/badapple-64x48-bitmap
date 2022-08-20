# badapple-64x48-bitmap
Bad apple bitmap head file in resolution 64x48 for embedded system to draw.
Resolution is 64x48.
FPS is 30.
## size
The bit maps take about 2.6MB flash space.

## usage
``` C
#include "badapple.h"
#include "U8g2lib.h"
//@Init your u8g2
int t1 = 0,t2 = 0;
for (size_t i = 0; i < BADAPPLE_FRAMES; i++)
        {
            t1 = millis();
            u8g2.clearBuffer();
            u8g2.drawBitmap(96,1,BADAPPLE_WIDTH/8,BADAPPLE_HEIGHT,badapple[i]);
            u8g2.sendBuffer();
            t2 = millis()-t1;
            delay(1000/30-(t2));

        }
```
