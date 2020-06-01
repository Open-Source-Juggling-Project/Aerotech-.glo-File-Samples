# RGB Fulls

## Concept: 

Looking at the various colourings using the RGB values at 0 and 255. 

```
; ===[Constants] ====================================================

#define DELAY_TIME  100       ; This value can be changed each time when testing. 

; ===[Main Sequence] ================================================

colour (0, 0, 0)
delay (DELAY_TIME)
colour (0, 0, 255)
delay (DELAY_TIME)
colour (0, 255, 0)
delay (DELAY_TIME)
colour (0, 255, 255)
delay (DELAY_TIME)
colour (255, 0, 0)
delay (DELAY_TIME)
colour (255, 0, 255)
delay (DELAY_TIME)
colour (255, 255, 0)
delay (DELAY_TIME)
colour (255, 255, 255)
delay (DELAY_TIME)

end

```
