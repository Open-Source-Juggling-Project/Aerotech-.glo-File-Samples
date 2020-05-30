# Aerotech Ultimate User Guide 

# Section 3 Only

This section of the guide is reproduced here, in order to make ti easy to copy and paste code samples. 

Minor edits have been made to improve readability. 

[Link to Guide](http://www.aerotechprojects.com/PDF/Ultimate%20User%20Guide.pdf)

## 3. Writing a new sequence

There are several example files included in the Aerotech installation. The example .glo files can be opened using notebook or other editors. We recommend Notepad++ and is free to download.

The sequence layout is comprised of 2 colour commands and 5 control commands:

### Colour commands

Colour commands allow you to select the colour of your Ultimate props. You have a choice of setting the individual colour components or setting them all at once.

### Individual colour commands

The R, G and B commands are followed by a brightness value directly, and set the brightness of the red, green and blue colour components directly. The brightness can range from 255 (full brightness) to zero (off).

```
R, 10   ; Set Red brightness (Intensity) to 10
G, 20   ; Set Green brightness (Intensity) to 20
B, 30   ; Set Blue brightness to (Intensity) to 30
```

Please note the semicolon ';' is only used to separate commands from description 

Save your sequence as a .glo file

### All colours command

If you want to set all the colour components, then the Colour command, C, can simplify this job. It takes 3 brightness parameters for Red, Green, and Blue. 

The following example does the same as job as the preceding example, but uses just one line instead of 3: 

```
C, 10, 20, 30   ; Set Red to 10, Green to 20 and Blue to 30
```

### Delay

Once you have chosen a colour, you will probably want to display it for a while before changing it. To do this, use the delay command, D. The command is followed by a value which specifies the time to delay in one-hundredths of a second. The value can range from 1 (one hundredth of a second) to 65535 (655.35 seconds i.e. 10 minutes 55.35 seconds). 

Here are some example delay commands: 

```
D, 1      ; One hundredth of a second 
D, 10     ; One tenth of a second
D, 100    ; 1 second
D, 1000   ; 10 seconds
```

### Loops

The loop command, L, can be used to repeat some commands a number of times. The loop command is followed by the number of times to loop (1 to 255). The end of the loop command is E.

Here's a simple example of a sequence where a loop repeats the sequence Red Green 10 times: 

```
...
L, 10           ; Loop 10 times
C, 255, 0, 0    ; Red full brightness
D, 100          ; Pause 1 second
C, 0, 255, 0    ; Green full brightness (red off) 
D, 100          ; Pause 1 second
E               ; End loop
...
```

Loops can contain other loops. 

Here's an example where the inner blue flashing is done 100 times (10 x 10), and the outer red flash is done only 10 times (once for each 10 blue flashes):

```
...
L, 10           ; Loop 10 times
C, 255, 0, 0    ; Red full brightness
D, 100          ; Pause 1 second
L, 10           ; Loop 10 times
C, 0, 0, 255    ; Blue full brightness (red off) 
D, 10           ; Pause 0.1 seconds
C, 0,0,0        ; Blue off
D, 10           ; Pause 0.1 seconds
E               ; End 2nd loop
E               ; End 1st loop
...
```

### End Command

All sequences must end their main sequence with an END command. The main sequence starts at the beginning of the file and needs to be terminated with an end command to allow the sub- sequences to be defined (see below). 

The following example shows a simple main sequence that turns the prop red, waits for one second and then finishes: 

```
R, 255    ; Red full brightness
D, 100    ; Wait one second
END       ; End main sequence
```
 
### Sub-sequences

Sub-sequences hold parts of sequences that are repeated. Using sub-sequence can make a sequence much shorter and easier to manage, and can allow longer sequences to be used on the Ultimate props. Clever use of sub-sequence can be used to produce effects like a strobe that can be used throughout your sequence.

Sub-sequences are defined with the DEFSUB command, ended with the ENDSUB command, and called using the SUB command. 

Here is a simple sequence which turns the prop red, then uses a sub-sequence to flash green, turns the prop blue, and then re-uses the sub-sequence to flash it green again: 

```
R, 255                ; Red full brightness
D, 100                ; Pause 1 second
R, 0                  ; Red off
SUB, flashGreen       ; Call 'flashGreen' sub-sequence 
B, 255                ; Blue full brightness
D, 100                ; Pause 1 second
B, 0                  ; Blue off
SUB, flashGreen       ; Call 'flashGreen' sub-sequence again 
END                   ; End of main sequence

DEFSUB, flashGreen    ; Start defining sub-sequence 'flashGreen' 
L, 10                 ; Loop 10 times
G, 255                ; Green full brightness
D, 10                 ; Delay one tenth of a second
G, 0                  ; Green off
D, 10                 ; Delay one tenth of a second
E                     ; End loop
ENDSUB                ; End sub-sequence 'flashGreen'
```

Sub-sequence can call other sub-sequences, and sub-sequences can contain loops. 

Here's a sequence that uses a red blue strobe effect to build up 2 other strobe effects of differing lengths: 

```
SUB, strobeRedBlue10Seconds       ; Call 'strobeRedBlue10Seconds'
C, 0, 255, 0                      ; Green full brightness
D, 100                            ; Pause 1 second
SUB, strobeRedBlue30Seconds       ; Call 'strobeRedBlue30Seconds' 
C, 0, 255, 0                      ; Green full brightness
D, 100                            ; Pause 1 second
SUB, strobeRedBlue10Seconds       ; Call 'strobeRedBlue10Seconds'
C, 0, 255, 0                      ; Green full brightness
D, 100                            ; Pause 1 second
END                               ; End main sequence

DEFSUB, strobeRedBlue10Seconds    ; Define 'strobeRedBlue10Seconds' sub-sequence 
L, 50                             ; Loop 50 times (50 x 0.2 sec = 10 sec)
SUB, strobeRedBlue                ; Call 'strobeRedBlue' sub-sequence
E                                 ; End loop
ENDSUB                            ; End sub-sequence 'strobeRedBlue10Seconds'

DEFSUB, strobeRedBlue30Seconds    ; Define 'strobeRedBlue30Seconds' sub-sequence 
L, 150                            ; Loop 150 times (150 x 0.2 sec = 30 sec)
SUB, strobeRedBlue                ; Call 'strobeRedBlue' sub-sequence
E                                 ; End loop
ENDSUB                            ; End sub-sequence 'strobeRedBlue30Seconds'

DEFSUB, strobeRedBlue             ; Define 'strobeRedBlue' sub-sequence which takes 0.2 second
C, 255, 0, 0                      ; Red full brightness
D, 10                             ; Pause one-tenth of a second
C, 0, 0, 255                      ; Blue full brightness (red off)
D, 10                             ; Pause one-tenth of a second
ENDSUB                            ; End sub-sequence 'strobeRedBlue'
```

### Ramp

The ramp command allows the currently displaying colour to be smoothly blended into a new colour. 

The command has the format: 

```
RAMP, R, G, B, delay
```

The delay takes a parameter in one-hundredths of a second, like the delay command, and can be from 1 (1 hundredth of a second) to 65535 (655.35 seconds).




 
