```
; Sub-sequence can call other sub-sequences and sub-sequences can contain loops.  
; Here’s a sequence that uses a red blue strobe effect to build up 2 other strobe effects of differing lengths.

SUB, strobeRedBlue10Seconds       ; Call ‘strobeRedBlue10Seconds’

C, 0, 255, 0                      ; Green full brightness
D, 100                            ; Pause 1 second

SUB, strobeRedBlue30Seconds       ; Call ‘strobeRedBlue30Seconds’

C, 0, 255, 0                      ; Green full brightness
D, 100                            ; Pause 1 second

SUB, strobeRedBlue10Seconds       ; Call ‘strobeRedBlue10Seconds’

C, 0, 255, 0                      ; Green full brightness
D, 100                            ; Pause 1 second

END                               ; End main sequence

DEFSUB, strobeRedBlue10Seconds    ; Define ‘strobeRedBlue10Seconds’ sub-sequence
L, 50                             ; Loop 50 times (50 x 0.2 sec = 10 sec)
SUB, strobeRedBlue                ; Call strobeRedBlue sub-sequence
E                                 ; End loop
ENDSUB                            ; End sub-sequence ‘strobeRedBlue10Seconds’

DEFSUB, strobeRedBlue30Seconds    ; Define ‘strobeRedBlue30Seconds’ sub-sequence
L, 150                            ; Loop 150 times (150 x 0.2 sec = 30 sec)
SUB, strobeRedBlue                ; Call ‘strobeRedBlue’ sub-sequence
E                                 ; End loop
ENDSUB                            ; End sub-sequence ‘strobeRedBlue30Seconds’

DEFSUB, strobeRedBlue             ; Define ‘strobeRedBlue’ sub-sequence which takes 0.2 second
C, 255, 0, 0                      ; Red full brightness
D, 10                             ; Pause one-tenth of a second
C, 0, 0, 255                      ; Blue full brightness (red off)
D, 10                             ; Pause one-tenth of a second
ENDSUB                            ; End sub-sequence ‘strobeRedBlue’
```
