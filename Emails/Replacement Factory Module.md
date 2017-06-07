# Replacement Factory Module
You have been told to create a replacement for a signal booster (Factory Module)

You have a single boards: 
```
|----------------------------------------------|
|                                              |
|  Input                                       |
|  "control-in"                                |
|  |                                           |
|  |    |--- MC4000 ---|                       |
|  |    |--------------|                       |
|  |    |  mov p0 acc  |p1--|                  |
|  |    |  mul 2       |    |                  |
|  |    |  mov acc p1  |    |                  |
|  |--p0|  slp 1       |    ---- Output        |
|       |--------------|         "control-out" |
|                                              |
|----------------------------------------------|
```


MC4000
```asm
  mov p0 acc
  mul 2
  mov acc p1
  slp 1  
```

### Diagram
![Diagram](https://github.com/CallumCarmicheal/Shenzhen-IO-Solutions/blob/master/Emails/Images/Replacement%20Factory%20Module.PNG?raw=true "Diagram")


### Notes