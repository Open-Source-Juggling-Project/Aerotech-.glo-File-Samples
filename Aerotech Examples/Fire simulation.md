```
L, 10                     ; Loop 10 times
  RAMP, 100, 0, 0, 20     ; Ramp up/down red
  RAMP, 255, 255, 0, 10   ; Ramp to red and green ie yellow
  RAMP, 50, 25, 0, 20     ; Ramp down yellow
  RAMP, 255, 100, 0, 20   ; Ramp up red and green ie yellow
E                         ; End Loop

RAMP, 0, 0, 0, 200        ; Ramp to off

END                       ; End main sequence
```
