```
; Here is a simple sequence which: 
; turns the prop red, 
; then uses a sub-sequence to flash green, 
; turns the prop blue, 
; and then re-uses the sub-sequence to flash it green again.

R, 255                ; Red full brightness
D, 100                ; Pause 1 second
R, 0                  ; Red off

SUB, flashGreen       ; Call ‘flashGreen’ sub-sequence

B, 255                ; Blue full brightness
D, 100                ; Pause 1 second
B, 0                  ; Blue off

SUB, flashGreen       ; Call ‘flashGreen’ sub-sequence again

END                   ; End of main sequence

DEFSUB, flashGreen    ; Start defining sub-sequence ‘flashGreen’

L, 10                 ; Loop 10 times
G, 255                ; Green full brightness
D, 10                 ; Delay one tenth of a second
G, 0                  ; Green off
D, 10                 ; Delay one tenth of a second
E                     ; End loop

ENDSUB                ; End sub-sequence ‘flashGreen’
```
