# Security Camera (Fake)
You have been told to create a simple Led blinking feature on a fake camera to imitate network read/write access.

You have 2 boards: 
```
    |--------------------------
    |  Output                 |
	/  "active"               |
___/   |                      |
|      |---  MC4000 "Red Led" |
|                             |
|------------------------------

|------------------------------
|     Ouput                   |
\__   "network"               |
   \  |                       |
    \ |-- MC4000 "Blue Led"   |
	|                         |
	|--------------------------
```


MC4000 "Red Led"
```asm
  mov 0 p0
  slp 6
  mov 100 p0
  slp 6
```

MC4000 "Blue Led"
```
start: mov 0 p0
  slp 4
  mov 100 p0 
  slp 2
  mov 0 p0 
  slp 1
  mov 100 p0 
  slp 1
```

### Diagram


### Notes