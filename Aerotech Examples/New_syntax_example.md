# NEW SCRIPT Example

This exaple shows the commands and syntax of the enhanced script.

The old script syntax is still supported and you can combine both in your scripts.

The main changes are:

## Command names are now fully spelled to increase script clarity

The list of the command names follows:

```
delay
color
colour
color.red
colour.red
color.green
colour.green
color.blue
colour.blue
ramp
loop
endloop
endLoop
sub
call
defsub
defSub
endsub
endSub
end
```

## Parameters of the commands can be enclosed in parenthesis. 

If you don't want to use parenthesis make sure you separate the command and the parameters by comma character ','

Example:

```
delay (100)   ; this is valid
delay , 100   ; this is valid
D, 100        ; this is valid - old syntax
delay 100     ; !!!! Error !!! This is invalid - no separator
```

## Added definition of constants. 

The syntax of the definition is:

```
#define  NAME    VALUE
```

All constants in your script are replaced by their defined values.

NAME must be unique and must not equal one of the command names. See above, and the legacy command names: 

```
D, C, R, G , B, L, E, RAMP, SUB, DEFSUB, ENDSUB, END
```

NAME must not start with a number or one of these reserved characters:  

```
- + . , : # ;
```

Example:

```
#define RED 255,0,0 ; this is a valid color definition
```

# NEW SCRIPT Example Code

```
; ===[Constants] ====================================================

#define RED           255, 0, 0       ; red color
#define BLUE          0, 0, 255       ; blue color
#define GREEN         0, 255, 0       ; green color
#define YELLOW        255, 255, 0     ; yellow color
#define BLACK         0, 0, 0         ; black color
#define ONE_SECOND    100             ; 1 second value
#define SMALL_DELAY   20              ; 0.2 seconds


; ---[Constants referencing other constants] ------------------------

; Note: PRIMARY constant references another constant so 
; make sure the referenced constant is already defined!

#define PRIMARY     RED
#define SECONDARY   BLUE

; Alternative colors  - uncomment to enable them
; Note: the new values will overwrite the old ones
; so after uncommenting the Primary color will be Green
; and the Secondary color will be Yellow.

; #define PRIMARY     GREEN
; #define SECONDARY   YELLOW


; ===[Start of the main sequence] ===================================

loop (10)                         ; Loop 10 times
  color (PRIMARY)                 ; Red full brightness
  delay (ONE_SECOND)              ; Pause 1 second
  ramp  (SECONDARY, ONE_SECOND)   ; Blend from Red to Blue in 1 second
  call  (StrobeSecondaryColor)    ; call strobing sub-sequence
  ramp  (PRIMARY, ONE_SECOND)     ; Blend from Black (last color of the strobe) to Red
endLoop                           ; End 1st loop

end                               ; end of the main sequence

; ===[Subsequence definition] =======================================

defSub (StrobeSecondaryColor)
  loop (5)                ; Loop 5 times
    color (SECONDARY)     ; Blue full brightness (red off)
    delay (SMALL_DELAY)   ; Pause 0.1 seconds
    color (BLACK)         ; Blue off
    delay (SMALL_DELAY)   ; Pause 0.1 seconds
  endLoop                 ; End 2nd loop
endSub                    ; end of StrobeSecondaryColor subsequence

```
