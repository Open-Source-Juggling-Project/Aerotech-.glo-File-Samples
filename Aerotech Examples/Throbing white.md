```
RAMP, 255, 255, 255, 200      ; Set initial colour to White

L, 10                         ; Loop 10 times
  RAMP, 100, 100, 100, 200    ; Ramp up/down white
  RAMP, 255, 255, 255, 200    ; Ramp up higher white
E                             ; End Loop

RAMP, 0, 0, 0, 200            ; Ramp to off

END                           ; End main sequence
```
