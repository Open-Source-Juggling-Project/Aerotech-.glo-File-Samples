# RGB Quarters

## Concept: 

Looking at the various colourings using the RGB values at 0, 64, 128, 192, and 255. 

```
; ===[Constants] ====================================================

#define DELAY_TIME  100       ; This value can be changed each time when testing. 

; ===[Main Sequence] ================================================

colour (0, 0, 0)
delay (DELAY_TIME)
colour (0, 0, 64)
delay (DELAY_TIME)
colour (0, 0, 128)
delay (DELAY_TIME)
colour (0, 0, 192)
delay (DELAY_TIME)
colour (0, 0, 255)
delay (DELAY_TIME)
colour (0, 64, 0)
delay (DELAY_TIME)
colour (0, 64, 64)
delay (DELAY_TIME)
colour (0, 64, 128)
delay (DELAY_TIME)
colour (0, 64, 192)
delay (DELAY_TIME)
colour (0, 64, 255)
delay (DELAY_TIME)
colour (0, 128, 0)
delay (DELAY_TIME)
colour (0, 128, 64)
delay (DELAY_TIME)
colour (0, 128, 128)
delay (DELAY_TIME)
colour (0, 128, 192)
delay (DELAY_TIME)
colour (0, 128, 255)
delay (DELAY_TIME)
colour (0, 192, 0)
delay (DELAY_TIME)
colour (0, 192, 64)
delay (DELAY_TIME)
colour (0, 192, 128)
delay (DELAY_TIME)
colour (0, 192, 192)
delay (DELAY_TIME)
colour (0, 192, 255)
delay (DELAY_TIME)
colour (0, 255, 0)
delay (DELAY_TIME)
colour (0, 255, 64)
delay (DELAY_TIME)
colour (0, 255, 128)
delay (DELAY_TIME)
colour (0, 255, 192)
delay (DELAY_TIME)
colour (0, 255, 255)
delay (DELAY_TIME)
colour (64, 0, 0)
delay (DELAY_TIME)
colour (64, 0, 64)
delay (DELAY_TIME)
colour (64, 0, 128)
delay (DELAY_TIME)
colour (64, 0, 192)
delay (DELAY_TIME)
colour (64, 0, 255)
delay (DELAY_TIME)
colour (64, 64, 0)
delay (DELAY_TIME)
colour (64, 64, 64)
delay (DELAY_TIME)
colour (64, 64, 128)
delay (DELAY_TIME)
colour (64, 64, 192)
delay (DELAY_TIME)
colour (64, 64, 255)
delay (DELAY_TIME)
colour (64, 128, 0)
delay (DELAY_TIME)
colour (64, 128, 64)
delay (DELAY_TIME)
colour (64, 128, 128)
delay (DELAY_TIME)
colour (64, 128, 192)
delay (DELAY_TIME)
colour (64, 128, 255)
delay (DELAY_TIME)
colour (64, 192, 0)
delay (DELAY_TIME)
colour (64, 192, 64)
delay (DELAY_TIME)
colour (64, 192, 128)
delay (DELAY_TIME)
colour (64, 192, 192)
delay (DELAY_TIME)
colour (64, 192, 255)
delay (DELAY_TIME)
colour (64, 255, 0)
delay (DELAY_TIME)
colour (64, 255, 64)
delay (DELAY_TIME)
colour (64, 255, 128)
delay (DELAY_TIME)
colour (64, 255, 192)
delay (DELAY_TIME)
colour (64, 255, 255)
delay (DELAY_TIME)
colour (128, 0, 0)
delay (DELAY_TIME)
colour (128, 0, 64)
delay (DELAY_TIME)
colour (128, 0, 128)
delay (DELAY_TIME)
colour (128, 0, 192)
delay (DELAY_TIME)
colour (128, 0, 255)
delay (DELAY_TIME)
colour (128, 64, 0)
delay (DELAY_TIME)
colour (128, 64, 64)
delay (DELAY_TIME)
colour (128, 64, 128)
delay (DELAY_TIME)
colour (128, 64, 192)
delay (DELAY_TIME)
colour (128, 64, 255)
delay (DELAY_TIME)
colour (128, 128, 0)
delay (DELAY_TIME)
colour (128, 128, 64)
delay (DELAY_TIME)
colour (128, 128, 128)
delay (DELAY_TIME)
colour (128, 128, 192)
delay (DELAY_TIME)
colour (128, 128, 255)
delay (DELAY_TIME)
colour (128, 192, 0)
delay (DELAY_TIME)
colour (128, 192, 64)
delay (DELAY_TIME)
colour (128, 192, 128)
delay (DELAY_TIME)
colour (128, 192, 192)
delay (DELAY_TIME)
colour (128, 192, 255)
delay (DELAY_TIME)
colour (128, 255, 0)
delay (DELAY_TIME)
colour (128, 255, 64)
delay (DELAY_TIME)
colour (128, 255, 128)
delay (DELAY_TIME)
colour (128, 255, 192)
delay (DELAY_TIME)
colour (128, 255, 255)
delay (DELAY_TIME)
colour (192, 0, 0)
delay (DELAY_TIME)
colour (192, 0, 64)
delay (DELAY_TIME)
colour (192, 0, 128)
delay (DELAY_TIME)
colour (192, 0, 192)
delay (DELAY_TIME)
colour (192, 0, 255)
delay (DELAY_TIME)
colour (192, 64, 0)
delay (DELAY_TIME)
colour (192, 64, 64)
delay (DELAY_TIME)
colour (192, 64, 128)
delay (DELAY_TIME)
colour (192, 64, 192)
delay (DELAY_TIME)
colour (192, 64, 255)
delay (DELAY_TIME)
colour (192, 128, 0)
delay (DELAY_TIME)
colour (192, 128, 64)
delay (DELAY_TIME)
colour (192, 128, 128)
delay (DELAY_TIME)
colour (192, 128, 192)
delay (DELAY_TIME)
colour (192, 128, 255)
delay (DELAY_TIME)
colour (192, 192, 0)
delay (DELAY_TIME)
colour (192, 192, 64)
delay (DELAY_TIME)
colour (192, 192, 128)
delay (DELAY_TIME)
colour (192, 192, 192)
delay (DELAY_TIME)
colour (192, 192, 255)
delay (DELAY_TIME)
colour (192, 255, 0)
delay (DELAY_TIME)
colour (192, 255, 64)
delay (DELAY_TIME)
colour (192, 255, 128)
delay (DELAY_TIME)
colour (192, 255, 192)
delay (DELAY_TIME)
colour (192, 255, 255)
delay (DELAY_TIME)
colour (255, 0, 0)
delay (DELAY_TIME)
colour (255, 0, 64)
delay (DELAY_TIME)
colour (255, 0, 128)
delay (DELAY_TIME)
colour (255, 0, 192)
delay (DELAY_TIME)
colour (255, 0, 255)
delay (DELAY_TIME)
colour (255, 64, 0)
delay (DELAY_TIME)
colour (255, 64, 64)
delay (DELAY_TIME)
colour (255, 64, 128)
delay (DELAY_TIME)
colour (255, 64, 192)
delay (DELAY_TIME)
colour (255, 64, 255)
delay (DELAY_TIME)
colour (255, 128, 0)
delay (DELAY_TIME)
colour (255, 128, 64)
delay (DELAY_TIME)
colour (255, 128, 128)
delay (DELAY_TIME)
colour (255, 128, 192)
delay (DELAY_TIME)
colour (255, 128, 255)
delay (DELAY_TIME)
colour (255, 192, 0)
delay (DELAY_TIME)
colour (255, 192, 64)
delay (DELAY_TIME)
colour (255, 192, 128)
delay (DELAY_TIME)
colour (255, 192, 192)
delay (DELAY_TIME)
colour (255, 192, 255)
delay (DELAY_TIME)
colour (255, 255, 0)
delay (DELAY_TIME)
colour (255, 255, 64)
delay (DELAY_TIME)
colour (255, 255, 128)
delay (DELAY_TIME)
colour (255, 255, 192)
delay (DELAY_TIME)
colour (255, 255, 255)
delay (DELAY_TIME)

end

```