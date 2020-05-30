```
C,255,255,255

D,60000           ; WHITE FOR 10 MINUTES

L,120
	C,255,0,0	      ; RED 10-20 Min
	D,25
	C,255,255,255
	D,475
E


L,60			        ; Keep it on a low light just to show it has passed the 20 minutes
	L,20
		C,20,0,0
		D,100
		C,0,20,0
		D,100
		C,0,0,20
		D,100
	E
E
C,0,0,0

END
```
