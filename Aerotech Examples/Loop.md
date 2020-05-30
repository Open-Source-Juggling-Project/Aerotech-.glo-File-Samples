```
L, 10               ; Loop 10 times
  C, 255, 0, 0      ; Red full brightness
  D, 100            ; Pause 1 second
  L, 10             ; Loop 10 times
    C, 0, 0, 255    ; Blue full brightness (red off)
    D, 10           ; Pause 0.1 seconds
    C, 0, 0, 0      ; Blue off
    D, 10           ; Pause 0.1 seconds
  E                 ; End 2nd loop
E				            ; End 1st loop

END
```
