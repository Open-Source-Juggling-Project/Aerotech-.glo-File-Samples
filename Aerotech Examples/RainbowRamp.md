```
RAMP, 255, 0, 0, 1000       ; Set initial colour to RED

L, 10                       ; Loop 10 times
RAMP, 255, 255, 0, 10000    ; Ramp up the Green leaving red on full to give YELLOW
RAMP, 0, 255, 0, 10000      ; Ramp down the Red and leave the green to make GREEN
RAMP, 0, 255, 255, 10000    ; Ramp up the Blue and leave the green on full to make CYAN
RAMP, 0, 0, 255, 10000      ; Ramp down the green and leave the blue to make BLUE
RAMP, 255, 0, 255, 10000    ; Ramp up the red and leave the blue to make MAGENTA
RAMP, 255, 0, 0, 10000      ; Ramp down the blue and leave the red to make RED again!
E                           ; End Loop

END                         ; End main sequence
```
